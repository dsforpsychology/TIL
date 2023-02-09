# Ajax
    - 비동기식 자바스크립트 XML(Asynchronous Javascript And XML)의 약자. JavaScript와 XML을 이용한 비동기적 정보 교환 기법. 
    - 하이퍼텍스트 표기언어(HTML)만으로 어려운 다양한 작업을 웹페이지에서 구현해 이용자가 웹페이지와 자유롭게 상호 작용할 수 있도록 하는 기술. 별도 프로그램을 설치하거나 웹페이지를 다시 로딩하지 않고도 메뉴 등 화면상의 객체를 자유롭게 움직이고 다룰 수 있음. 
# 원리
    1. 브라우저가 사이트에 접속하면 서버는 사이트의 기본 얼개를 담은 '템플릿'을 전달한다.
    2. 브라우저는 수신받은 템플릿 HTML과 CSS를 해석해 화면의 기본 모양을 그린다.
    3. 계속해서 서버는 데이터의 요청 방식과 수신받은 데이터를 어떻게 가공해야 하는지를 기술한 자바스크립트 파일을 전달한다. 
    4. 브라우저는 자바스크립트 파일을 해석해서 파일에 기술된 방식대로 서버에 추가 데이터를 요청한다.
    5. 서버는 순수 데이터를 응답으로 되돌려준다.
    6. 브라우저는 수신한 데이터를 해석하여 템플릿의 적절한 위치에 삽입한다. 데이터의 가공 방식에 따라 삽입 외의 작업(변경, 삭제)을 할 수도 있다.

# AJAX 함수의 사용 형식

'$.ajax({
  "url": "접속할 페이지 주소",
  "type": "get/post",
  "data": "파라미터 문자열 key=value&key=value",
  "dataType": "text, jsp, xml, json, jsonp(원격 스크립트 허용)",
  "timeout": 밀리세컨드단위 제한시간,
  "cache" : 이전 요청에 대한 캐시 저장 여부 (true=사용함, false=사용안함),
  "success": function (data) {
  … 통신이 성공했을 때 실행되는 함수 …
  },
  "error": function(xhr, textStatus, errorThrown) {
  … 통신에 실패했을 때 실행되는 함수 …
  }
  '

# AJAX 함수의 주요 매개변수 옵션
    (1) type(String)
        - 사용할 HTTP 메서드로 일반적으로 POST나 GET을 사용하며 기본값으로 GET을 사용한다.
    (2) data(Object)
        - $.ajax 유틸리티 함수가 값의 인코딩을 처리하고 요청에 전달되는 프로퍼티를 가진 객체로 GET 요청이면 데이터는 쿼리 문자열로 제공하고 POST 요청이면 데이터는 요청의 본문으로 제공한다.
    (3) timeout(Number)
        Ajax 요청의 제한 시간을 밀리 초 단위로 설정하며 제한 시간 안에 요청이 완료되지 않으면 요청을 취소하거나 error 콜백이 정의되어 있다면 호출된다.
    (4) contentType(String)
        요청에 명시되는 콘텐츠 타입으로 생략하면 application/x-www-form-urlencoded가 기본으로 설정되며 이는 폼 전송이 기본으로 사용하는 타입과 동일하다.
    (5) success(Function)
       - 응답이 성공 상태 코드를 반환하면 호출되는 함수이다.
       - 함수의 응답 본문은 이 함수의 첫 번째 매개변수로 전달되며 dataType 프로퍼티에 명시한 형태로 구성되고
       - 두 번째 매개변수는 상태값을 나타내는 문자열이며 항상 success로 나타낸다.
    (6) error(Funcction)
       - 응답이 에러 상태 코드를 반환하면 호출되는 함수이다.
       - 함수의 매개변수가 세 개 전달되는데 각각 XHR 인스턴스와 상태값이 향상 error 인 메시지 문자열 그리고 선택사항으로 XHR 인스턴스가 반환한 예외 객체다.
    (7) comptete(Function)
       - 요청이 완료되면 호출되는 함수이다.
       - 함수의 매개변수 두 개가 전달되는데 각각 XHR 인스턴스와 success 혹은 error 를 나타내는 상태 메시지 문자열이다.
       - succes나 error 롤백을 명시했다면 이 함수는 해당 콜백이 호출된 후에 실행된다.
    (8) beforeSend(Function)
       - 요청이 전송되기에 앞서 먼저 호출되는 함수이며 이 함수는 XHR 인스턴스를 전달받으며 사용자 정의 헤더를 설정하거나 요청 전에 필요한 연산을 수행하는 데 사용할 수 있다.
    (9) processData(Boolean)
       - false로 설정되면 URL 인코딩된 형태로 처리되어 전달되는 데이터를 금지한다.
       - 기본값은 데이터가 application/x-www-form-urlencoded 타입의 요청에 사용하는 형태의 URL로 인코딩된다.
    (10) ifModified(Boolen)
       - true 일 때 Last-Modified 헤더를 확인하여 마지막 요청 이후에 응답 콘텐츠가 변경되지 않았다면 요청이 성공되며 만일 생략하면 헤더를 확인하지 않는다.
    (11) dataType(String)
       - 서버에서 응답의 결과로 반환되는 데이터의 형식으로 서버 자원은 올바른 content-type 응답 헤더를 설정해야 하며 이 프로퍼티를 생략하면 응답 텍스트는 어떠한 처리나 평가 없이 콜백에 전달된다.

<pre><code>
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>텍스트 파일 불러오기</title>
<script src="../js/jquery-1.11.2.min.js" type="text/javascript"></script>
<script type="text/javascript">
<!-- 요청으로 읽어올 파일의 경로를 ./test.txt 파일로 지정-->
    $(function( ) {
$("#mybtn").click(function( ) {
$.ajax({
            url : "./test.txt",
            type : "GET",
            dataType : "text",
            timeout : 30000,
            cache : false,
            success : function(data) {
                $("#result").html(data);},
            error : function(xhr, textStatus, errorThrown) {
            $("div").html(
                "<div>" + textStatus + " (HTTP-"
                + xhr.status + " / " + errorThrown
                + ")</div>");
                + }});});
    });
</script>
</head>
<body>
    <h3 class="title">$.ajax( ) 함수를 사용한 텍스트 읽기</h3>
    <input type="button" value="txt파일 가져오기" id="mybtn" />
    <br />
    <div class="console" id="result"></div>
</body>
</html></code></pre>

1. url : "./test.txt",
    ajax 요청으로 읽어올 파일의 경로를 ./test.txt 파일로 지정한다.
2. type : "GET",
    HTTP 메서드 전송 방식을 GET으로 지정한다.
3. dataType : "text",
    데이터타입을 text로 지정한다.
4. timeout : 30000,
    제한시간을 30000 밀리세컨드로 지정하며 30초가 제한시간이 설정된다.
5. cache : false,
    false로 지정하므로 이전 요청에 대한 캐시를 저장하지 않는다.
6. success : function(data) { ~ },
    파일 읽기에 성공한 경우에 실행한다. 파일에 작성되어 있는 내용이success함수의 파라미터인 data로 전달되며 이 값을 result 요소에 출력한다.
7. $("#result").html(data);
    dataType값이 text일 경우에는 단순히 내용에 대한 문자열이므로 직접 HTML 요소에 출력할 수 있다.