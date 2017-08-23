## 챕터 1. Cocos2d-x HTML5 라이트 버전 설치하기

===

자, 지금부터 저와 함께 Cocos2d-x HTML5 라이트 버전을 이용하여 웹기반의 게임을 만들어보겠습니다.

Cocos2d-x HTML5 라이트 버전은 Cocos2d-x에서 HTML5 게임 개발에 필요한 부분만을 추출하여 모아놓은 버전으로서

iOS나 안드로이드 등 네이티브 빌드를 사용하시려면 Cocos2d-x 풀 패키지를 이용하셔야 합니다.

그럼 이제 다운 받으러 가볼까요?

[Cocos2d-x HTML5 라이트 버전 다운로드](http://www.cocos2d-x.org/download)

원하는대로 구성해서 다운받으실 수 있는 다운로드 빌더가 나오실겁니다.

웹기반의 게임은 프레임워크의 용량이 중요하기 때문에 사용하시는 기능만을 커스터마이징하여 다운 받으실 수 있도 친절하게 구성되었습니다.

저희의 경우 일단 배포를 신경 쓰지 않고 마음 편히 개발하기 위하여 Mode는 Full Version을 고르고

리소스 로딩 화면 등 일정 부분 커스터마이징이 필요할 수도 있기 때문에 Compressor는 Uncompressed를 고르고

DOWNLOAD 버튼을 눌러줍니다.

zip 파일의 다운로드가 완료되면 압축을 풀어보겠습니다

가볍게 살펴보면

- build.xml

추후에 Google Closure Compiler를 이용하실 때 사용하시기 위한 파일입니다.

- cocos2d-js-v3.13-lite.js

Cocos2d-x HTML5 라이트 버전의 핵심이 되는 프레임워크 파일로서 저는 3.13 버전을 다운 받았습니다.

- HelloWorld.html

기본 프로젝트의 HTML 파일입니다.

- HelloWorld.png

기본 프로젝트에서 사용하는 이미지 파일입니다.

- project.json

Cocos2d-x 프로젝트의 설정을 할 수 있는 파일로서 디버깅 여부나 FPS 표시 여부, WebGL 사용 여부 등을 설정할 수 있습니다.

- README.md

Cocos2d-x HTML5 라이트 버전에 관한 설명을 담고 있는 문서입니다

그러면 일단 기본 프로젝트를 띄워서 눈으로 확인해볼까요?

HelloWorld.html를 더블 클릭하시거나 웹브라우저로 드래그앤드랍해보세요.

아마 시커먼 화면이 당신을 반길겁니다.

README.md를 읽어보신 분은 아시겠지만 꼭 웹서버를 통해서만 결과를 볼 수 있다고 하네요.

로컬 웹서버를 구축하실 수 있으신 분은 건너뛰고

잘 모르시는 분은 아래 링크를 참조해서 로컬 웹서버를 설정해주세요.

https://brendaniel.github.io/2017/01/03/Web-Server-for-Chrome-%EA%B0%80%EC%9E%A5-%EB%B9%A8%EB%A6%AC-%EC%9B%B9%EC%84%9C%EB%B2%84-%EA%B5%AC%EB%8F%99%ED%95%98%EA%B8%B0/

그러면 저희가 원하던 결과를 확인하실 수 있습니다.

- [챕터 2. 기본 설정](chapter2.md)
