## 챕터 2. 기본 설정

===

이제 본격적으로 설정들에 알아보고 기본적인 설정을 같이 해보도록 하겠습니다.
먼저 같이 project.json 파일을 살펴보겠습니다.

- project.json


        {
        "debugMode"     : 1,
        "frameRate"     : 60,
        "id"            : "gameCanvas",
        "renderMode"    : 1,
        "jsList"        : []
        }

각각의 항목들을 자세히 살펴보면

- debugMode

        0: close all
        1: info level
        2: warn level
        3: error level
        4: info level with web page
        5: warn level with web page
        6: error level with web page

- showFPS

        화면 상에 FPS를 표시할지 여부로서 true/false로 설정하시면 됩니다(기본은 true).

- frameRate

        초당 몇 프레임을 화면에 그려줄지 결정하는 부분으로서 일반적으로 30 ~ 60 사이의 숫자를 적어줍니다.

- renderMode

        0: 기본
        1: Canvas만 사용
        2: WebGL만 사용

- id

        cocos2d가 실행될 DOM 엘리먼트의 아이디를 지정할 수 있습니다.

- jsList

        게임 소스 코드의 리스트입니다.

project.json 파일은 기본 상태에서 특별히 손을 보실 필요는 없이 그대로 사용하시면 되고 이번에는 HelloWorld.html 파일을 살펴보겠습니다.


        <!DOCTYPE html>
        <html>
        <head>
            <title>Hello Cocos2d-JS</title>
        </head>
        <body>
            <canvas id="gameCanvas" width="800" height="450"></canvas>
            <script type="text/javascript" src="cocos2d-js-v3.13-lite.js" charset="UTF-8"></script>
            <script type="text/javascript">
                  window.onload = function(){
                      cc.game.onStart = function(){
                          //load resources
                          cc.LoaderScene.preload(["HelloWorld.png"], function () {
                              var MyScene = cc.Scene.extend({
                                  onEnter:function () {
                                      this._super();
                                      var size = cc.director.getWinSize();
                                      var sprite = cc.Sprite.create("HelloWorld.png");
                                      sprite.setPosition(size.width / 2, size.height / 2);
                                      sprite.setScale(0.8);
                                      this.addChild(sprite, 0);

                                      var label = cc.LabelTTF.create("Hello World", "Arial", 40);
                                      label.setPosition(size.width / 2, size.height / 2);
                                      this.addChild(label, 1);
                                  }
                              });
                              cc.director.runScene(new MyScene());
                          }, this);
                      };
                      cc.game.run("gameCanvas");
                  };
            </script>
        </body>
        </html>

보시면 기본적인 HTML 문서 내에 스크립트 태그 안에 관련 스크립트를 넣어놓은 구조로 되어있습니다.

        cc.LoaderScene.preload(["HelloWorld.png"], function () {

부분을 보시면 cc.LoaderScene.preload에서 게임에서 사용할 리소스들을 미리 불러오게 됩니다.

        var MyScene = cc.Scene.extend({

cc.Scene을 확장하여 MyScene이라는 새로운 Scene을 작성하게 됩니다.

        onEnter:function () {

Scene이 최초로 생성되고 화면에 나타나면서 실행되는 부분입니다.

        this._super();

cc.Scene의 생성자를 오버라이드합니다.

        var size = cc.director.getWinSize();

cc.director를 통하여 윈도우의 사이즈를 구합니다. size.width는 가로 크기, size.height는 세로 크기가 됩니다.

        var sprite = cc.Sprite.create("HelloWorld.png");

sprite라는 변수명으로 HelloWorld.png 파일로 스프라이트를 생성합니다. 이 때 사용하는 파일이 preload되지 않은 경우에 제대로 작동하지 않을 수 있습니다.

        sprite.setPosition(size.width / 2, size.height / 2);

sprite의 위치를 가로 크기의 중간, 세로 크기의 중간, 즉 화면의 중앙 지점에 위치시킵니다. cocos2d의 스프라이트 앵커포인트는 기본적으로 중앙이기 때문에 sprite가 정확하게 화면의 중앙에 위치하게 됩니다.

        sprite.setScale(0.8);

sprite의 크기를 0.8배로 지정합니다.

        this.addChild(sprite, 0);

this는 즉 MyScene이 되고 MyScene의 자식으로서 sprite를 추가합니다. 뒤의 숫자 0은 생략 가능하며 z-index로서 작동합니다.

        var label = cc.LabelTTF.create("Hello World", "Arial", 40);
        
Hello World라고 출력되는 폰트 크기 40의 Arial 글꼴의 label이라는 이름을 가진 라벨을 생성합니다.
        
        label.setPosition(size.width / 2, size.height / 2);
        
label의 위치도 마찬가지로 화면 정중앙에 위치시킵니다.        

        this.addChild(label, 1);
        
사용자의 눈에 보여질 수 있도록 마찬가지로 label도 MyScene의 자식으로 등록합니다.
        
==

이로써 앞서 결과를 확인했던 화면이 왜 그런 형태로 보여졌는지 확인하셨죠?

다음으로는 본격적으로 게임 개발을 위한 씬을 디자인해보도록 하겠습니다.

==

- [챕터 3. 씬 디자인하기](chapter3.md)
