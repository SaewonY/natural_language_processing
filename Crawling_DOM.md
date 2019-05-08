
# DOM 개념 정리

DOM이란 무엇인가? HTML 태그? 노드? 용어만 들었을뿐 정확히 설명을 못하기에 간략하게 정리를 해보자. 

<br>

## DOM Definition

* 문서 객체 모델(Document Object Model)은 JavaScript Node 개체의 계층화된 트리다.
* DOM은 HTML, XML 문서의 프로그래밍 API이다.
* 문서의 구조화된 표현을 제공하며 프로그래밍 언어가 DOM 구조에 접근할 수 있는 방법을 제공한다.
* 문서 구조, 스타일, 내용 등을 변경할 수 있도록 돕는다.


<br>

## HTML과 DOM의 차이점

* HTML 파일이 쓴 것들이 DOM은 아니다.
* HTML 작성할 때 생기는 실수를 브라우저가 고쳐준다. (필요한 Tag를 생략한 경우 등)
* <tbody>는 바로 DOM에 있다.
* 그렇기에 CSS, JavaScript로 찾을 수 있고 스타일 변경이나 조작이 가능하다.

<br>

## JavaScript vs DOM

* javascript는 브라우저가 읽고 사용하는 언어이다.
* 하지만 DOM은 그 일이 일어나는 곳이라 할 수 있다.
* javaScript라고 생각되는 것들이 정확히는 DOM API이다.

<br>

## Conclusion

* DOM은 브라우저 내에서 작동하고 존재한다.
* DOM은 parsing 된 HTML이라고 할 수 있다.
* 웹페이지가 로드될 시 브라우저는 DOM 페이지를 만든다.

<br>

#### 참조
* https://shldhee.github.io/2018/04/08/DOM/

<br>
<br>

# 5.3 수업
`

* 우리는 dom tree를 구성함으로써 텍스트를 있는 그대로 해석하지 않게 된다.

* reponse의 body에 해당하는 html을 살펴보고, dom tree를 어떻게 parsing 하는지 살펴보고자 한다.

![dom](https://user-images.githubusercontent.com/40786348/57188743-c37e4a80-6f3e-11e9-868b-53fd9974377c.PNG)


<br>

![html](https://user-images.githubusercontent.com/40786348/57188752-d729b100-6f3e-11e9-9c17-c8a68305c409.PNG)

<br>

## **HTML 구조** 

<br>

1. Head : HTML 문서의 메타데이터(metadata)를 정의 (metadata란 HTML 문서에 대한 정보(data)로 웹 브라우저에는 직접적으로 표현되지 않는 정보를 의미).
이러한 메타데이터는 title, style, meta, link, script, base태그 등을 이용하여 표현할 수 있다.

<br> 

2. title : HTML 문서의 제목(title)을 정의하며, 다음과 같은 용도로 사용된다.

- 웹 브라우저의 툴바(toolbar)에 표시됩니다.

- 웹 브라우저의 즐겨찾기(favorites)에 추가할 때 즐겨찾기의 제목이 됩니다.

- 검색 엔진의 결과 페이지에 제목으로 표시됩니다.

<br> 

3. Body : 웹 브라우저를 통해 보이는 내용(content) 부분입니다.

* h1 ~ h6 : 제목(heading)을 나타냅니다.

* p : 단락(paragraph)을 나타냅니다.

<br>
<br>
<br>

![beautiful soup](https://user-images.githubusercontent.com/40786348/57188756-df81ec00-6f3e-11e9-8c9d-90e5d40329ac.PNG)

* 파싱이란 가공되지 않은 데이터에서 원하는 특정한 문자열을 빼내는 작업이다. 우리는 Beautiful soup 모듈을 활용하여 간편하게 작업할 수 있다. 코드는 주피터 노트북 참조

<br>
<br>
<br>

![parser](https://user-images.githubusercontent.com/40786348/57188759-e6a8fa00-6f3e-11e9-861f-38fc0c1781d7.PNG)

<br>

* C dependent하지만 속도를 위해서 lxml 을 권장한다고 나와있다. 각각의 장단점이 있다.

<br>
<br>
<br>

# HTML 작성 방법

![not-well-formed](https://user-images.githubusercontent.com/40786348/57188762-f0326200-6f3e-11e9-8350-fa84ab5ec982.PNG)

<br>

![html구조](https://user-images.githubusercontent.com/40786348/57188764-f88a9d00-6f3e-11e9-9898-ade07aad2e57.PNG)

<br>

1. **Element** - 페이지 안에서 구조와 컨텐츠를 포함하는 객체를 정의하기 위한 지명자 
2. **Tags** - 시작 태그 <>와 끝 태그 </> element는 하나 또는 여러 개의 태그로 만들어진다. 
3. **Attributes** - element에 주어지는 속성 

* 모든 HTML 문서는 doctype, html, head, body의 선언과 태그를 포함하는 구조로 만들어진다.
* doctype 선언은 사용된 HTML 버전을 웹 브라우저에게 알려주며, HTML 문서의 최상위에 위치한다. doctype 선언에 이어, 문서의 처음과 끝을 뜻하는 html 태그가 위치한다.
* head는 메타 데이타, 문서 title, 외부 화일 링크로 구성된다. 실제 웹 페이지에서는 보여지지 않는다. 웹 페이지에 보여줄 모든 콘텐츠는 body 태그 안에 넣는다.

##### 참조 - https://nolboo.kim/blog/2013/07/22/beginners-guide-to-html-and-css-1-slash-10/

<br>
<br>
<br>

# BeautifulSoup useful functions

![functions](https://user-images.githubusercontent.com/40786348/57188765-ffb1ab00-6f3e-11e9-942f-561c02b10753.PNG)

![functions1](https://user-images.githubusercontent.com/40786348/57188768-050ef580-6f3f-11e9-8f7b-51ccc0fefff4.PNG)


* **BeautifulSoup 매개변수**: (markup='', features=None, builder=None, parse_only=None, from_encoding=None, exclude_encodings=None, **kwargs)

<br>

1. **태그와 속성을 사용해서 가져오기**

* find_all("태그명", {"속성명":'값' ...})
* find("태그명", {"속성명":'값' ...})

<br>

2. **HTML 구조를 이용해 부분부분 가져오기** 
   
~~~
with open("example.html") as fp:
    soup = BeautifulSoup(fp, 'html.parser')
    
    # id=ex_id인 div 태그를 가져와서
    ex_id_divs = soup.find("div", {"id":"ex_id"})
    
    # 그 태그들 안에서 p 태그를 가져온다.
    all_ps_in_ex_id_divs = ex_id_divs.find_all("p")

    print(all_ps_in_ex_id_divs)
~~~

<br>

#### beautifulsoup 구체적인 사용 예제는 jupyter notebook 참조


