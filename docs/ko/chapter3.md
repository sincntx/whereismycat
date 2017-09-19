## 챕터 3. 씬 디자인하기

===

이번에는 배경화면과 캐릭터, 메뉴 등을 배치하여 씬을 디자인해보겠습니다.

그리고 whereismycat_starterkit.zip을 다운 받으시고 압축을 푸시고 index.html 파일을 열어주세요.

        var MyScene = cc.Scene.extend({
        onEnter:function () {
            this._super();
            var size = cc.director.getWinSize();
        }

라는 부분이 보이실텐데요. 그 밑으로 다음의 코드를 추가해주세요.

            var bg = cc.Sprite.create("res/background.png");
            bg.setPosition(size.width / 2, size.height / 2);
            this.addChild(bg, 0);

bg라는 이름으로 배경화면 스프라이트를 만들어서 레이어 중앙에 추가해줍니다.

이때 주의하실 점은 새롭게 사용할 리소스 파일을 사전에 로드해주셔야 유저가 원활한 플레이가 가능하다는 부분인데요.

            cc.LoaderScene.preload(["HelloWorld.png"], function () {

부분을 아래와 같은 형태로 수정해주세요.

            var res = ["res/background.png"];
            cc.LoaderScene.preload(res, function () {

일단 배경화면에서 사용할 리소스를 등록해두시고 새로운 리소스가 생기실 때마다 res 배열에 추가해주시는 식으로 관리해주시면 편리하게 사용하실 수 있습니다.

이번에는 주인공 캐릭터를 추가해볼까요?
아까 배경화면 코드를 추가한 자리 밑에다가

            var cat = cc.Sprite.create("res/cat/n1.png");
            cat.setPosition(size.width / 2, size.height / 2.35);
            cat.anchorY = 1;
            this.addChild(cat, 1);

여기서 cat.anchorY는 주인공 캐릭터의 중심축을 어디에 둘 것이냐를 지정하는 것인데 0, 0.5, 1 중에 하나로 지정할 수 있습니다.
바닥과 주인공 캐릭터의 하단부를 일치시키기 위해서 주인공 캐릭터의 중심축을 밑으로 지정했습니다.

this.addChild(cat, 1);에서 1은 스프라이트가 출력되는 순서인데 배경화면인 bg를 0으로 지정했으므로 배경보다 주인공이 위에 나와야하기 때문에 1로 지정하게 됩니다.

            var title = cc.Sprite.create("res/title.png");
            title.setPosition(size.width / 2, size.height * 0.82);
            addChild(title, 1);

이번에는 타이틀 이미지도 화면에 추가해보겠습니다.

==

- [챕터 4. 애니메이션 적용하기](chapter4.md)
