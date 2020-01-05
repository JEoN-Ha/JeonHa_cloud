# 문서를 읽기 전(README)

- 이 문서의 저작권은 '팽대원(FoRA)'에게 있음.
- 중요하다고 생각되는 단어 및 문장은 ***강조 효과***를 달았음.
- 추가적인 설명은 다음과 같이 회색으로 각주 효과를 달았음.

> 각주효과, 각주효과, 각주효과

# HTML_Study

### HTML5란

HTML5는 2012년도에 나온 HTML 언어의 최신이자 현재 표준으로 사용되는 html 버전이다.

### HTML 구성

![image-20191122023859249](C:\Users\fora2\AppData\Roaming\Typora\typora-user-images\image-20191122023859249.png)

**<!Doctype html>**  : 마크업 언어 문서 타입이 html임을 선언

`<html></html>` html 문서는 <html>로 시작하고 </html>로 끝난다.

`<head></head>` <head>와 </head>사이는 이 웹 문서의 정보를 나타낸다.

`<title></title>` <title></title>사이는 해당 웹 문서의 최상위 제목에 대해 나타낸다.

`<body></body>` 사이에는 본문에 대한 내용을 태그한다.

`<h></h>` 본문에서 단락 제목에 관해 나타내는 태그이다. <h1> 부터 <h6>까지 6가지가 있으며 각각 크기가 다르다.

`<p></p>` 파라그래프, 즉 단락의 내용을 나타내는 태그이다.

태그와 태그 사이에 들어가는 내용을 요소, 엘리먼트 컨텐츠(element contents)라 한다.

### Web address의 의미

WWW는 "World Wide Web"의 약자이다.

http://troyboy.tistory.com:80/home.html

http:// <- 이 부분을 프로토콜이라 한다. 프로토콜은 통신 규약이라고 생각하면 된다. 우리가 인터넷을 사용할 때 사용자의 컴퓨터와 웹 사이트가 구축된 서버 컴퓨터 사이의 통신이 있을 것이다. 이 때 이 약속을 프로토콜이라 한다. http는 '정보만' 받는다. FTP는 '파일도' 받는다. 따라서 보통 주소창에 직접 쳐서 다운 받는 경우 ftp://로 시작한다.

IP는 인터넷상의 컴퓨터 주소로서, DHCP라는 규약을 같이 사용한다. 이 DHCP가 각 가정 집에 IP를 분할해서 할당해준다. 이 IP주소를 인간이 알아보기 쉽게 문자로 바꾼 것이 DNS라고 한다. 주소의 `troyboy.tistory.com`이 이에 해당된다.

Port는 같은 서버내의 프로그램 주소이다. 보통 기준이 80으로 되어 있다. 80이면 생략이 가능하다. 실제로 주소후 : 80을 붙이면 제대로 사이트에 들어가지지만 포트번호를 : 470 이런식으로 다르게 지정하다면 사이트에 들어가지 못하는 현상을 확인 가능하다.

___

### Elements

Elements는 시작 태그에서부터 끝 태그까지를 전부 Element라 한다..

예를 들어 `<p> Hi </p>`라 써있다면 <p>부터 </p> 까지 전부 P(단락) Element라 할 수 있다.

HTML Element는 Content로 중첩이 가능 하다. 다음을 살펴보자

```html	
<!DOCTYPE html>
<html>
    <body>
        <h1>My First Heading</h1>
        <p>My first paragraph.</p>
    </body>
</html>
```



