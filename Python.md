<파이썬 >
# 문자열 포매팅 
1) +연산자를 사용 
	> name = "홍길동"   
	age = 30  
	print("이름:" + name)

2) % 를 사용 
   > pi = 3.141574  
   print("pi=%f" %pi)  
   >소수점 3자리, 10자리 확보 좌측 정렬  : print ("pi=%-10.3f" %pi)
3) format 함수를 사용
   > print("a:{} b{} c:{}, format(10, 20, 30))
4) f 문자열을 사용
    > name = "홍길동"   
    > age = 30  
    > height = 178.5  
    > print(f"이름 : {name}, 나이 : {age}")  
    > print(f"이름 : {name:^10s}, 나이 : {age : <10d}, 키: {height :->10.1f}")  

# 리스트 슬라이싱, 인덱싱
`a = [1, 2, 3, 4, 5, 6, 7, 8, 9]`  
`print(a[0])`  
`print(a[-1])`  
`print(a[2])`    
`print(a[:3])`  
`print(a[1:])`  
`print(a[2:6])`  
`print(a[::])`  
`print(a[-2:])`  

# 튜플 생성하는 방법 
`a = ()`  
`b = tuple()`    
`c = (1,)`     
`d = ('a','b','c')`

# 딕셔너리 생성 
1) 빈 딕셔너리 생성  
`dict_blank = dict()`
2) 딕셔너리 생성  
`dict_a = {"name":"LEE", "age":30, "addr":"서울 강남구"}`  
`print(dict_a)`
3) dict함수를 사용  
`dict_b = dict(name="LEE", age=30, addr="서울 강남구")`
`print(dict_b)`
4) zip 함수를 사용    
`keys = ["name", "age", "addr"]`  
`print(keys)`  
`values = ["LEE", 30, "서울 강남구"]`    
`print(values)`    
`dict_c = dict(zip(keys, values))`  
`print(dict_c)`  

# 리스트와 튜플의 차이
> 튜플은 초기화 후 요소의 추가, 변경, 삭제 등이 불가함
# 딕셔너리 검색하는 방법 
### 검색
`print(dict_a["name"], dict_a["age"], dict_a["addr"])`  
LEE 30 서울 강남구  
### 추가 / 수정
`dict_a = {"name":"LEE", "age":30, "addr":"서울 강남구"}`  
`dict_a["email"] = "LEE@test.kdt.com"`  
`print(dict_a)`  
{'name': 'LEE', 'age': 30, 'addr': '서울 강남구', 'email': 'LEE@test.kdt.com'}  
{'name': 'KANG', 'age': 30, 'addr': '서울 강남구', 'email': 'LEE@test.kdt.com'}  
### 삭제
`dict_a = {"name":"LEE", "age":30, "addr":"서울 강남구"}`  
`del dict_a["name"]`  
`print(dict_a)`  
`del(dict_a["age"])`   
`print(dict_a)`  
{'age': 30, 'addr': '서울 강남구'}  
{'addr': '서울 강남구'}

# 논리 연산자 and , or 등 
객체, 클래스, 
# 객체지향 프로그램의 특징
- 추상성(Abstraction)  
    : 사용자에게 꼭 필요한 부분만 코드로 구현
- 은폐성(Encapsulation)  
    : 객체 내부에 로직과 데이터를 숨기고 메서드를 통해서 접근
- 상속성(Inheritance)  
    : 공통 분모에 해당되는 부분을 상속받아 사용 가능
- 다형성(Polymorphism)  
    ∙ 부모 클래스로부터 상속받은 메서드와 동일한 이름의 다른 액션 수행 메서드 생성  
    ∙ 이름은 같지만 다른 액션을 수행하도록 덮어쓰기(override) 함

# 함수 - 인자값 보내는 여러가지 방법   
1. 인수의 기본값
   - 함수 호출 시 인수값을 전달하지 않을 경우 인수의 기본값 지정 가능
   - 기본값 정의하는 인수는 인수목록의 뒤쪽에 위치해야 함  
   - 기본값을 가지는 인수의 개수는 제약 없음  
` def calsum(a, b=1, c=2):`  
`return a + b + c ` 

print(calsum(10))  
print(calsum(10, 20))  
print(calsum(10, 20, 30))  


2. 키워드 인수 
- 함수 호출 시 인수의 수가 많을 경우 순서에 맞춰 전달이 어려울 경우 사용
- 인수의 이름을 지정하여 대입함으로써 순서와 상관없이 전달 가능함
- 위치 인수와 키워드 인수 혼합시에는 위치 인수 뒤에 키워드 인수 작성해야 함
`def divide(a, b):`  
`	return a / b`  
``  
`print(divide(10, 20))`   
`print(divide(10, b=20))`  
`print(divide(b=20, a=10))`  
`print(divide(a=20, 10))`  

3. 가변 인수 
  - 정의된 인수 개수가 아닌 임의 개수의 인수를 받기 위한 인수  
  - 매개변수 앞에 * 기호 붙임  
  - 가변인수는 위치인수 뒤에 작성하며, 1개만 존재 가능함  
  - 가변인수로 받은 값들은 튜플의 요소로 처리되어 for … in 문으로 처리 가능함  
`def calsum(num, *values):`  
    `sumvalue = 0`  
    `for value in values:`   
        `sumvalue += value`   
    `return sumvalue + num`  
`print(calsum(100))`  
`print(calsum(100, 200))`  
`print(calsum(100, 200, 300, 400, 500))`  

4. 키워드 가변 인수 
  - 여러 개의 키워드 인수 전달 시 인수의 이름과 값을 쌍으로 사전형으로 전달함
  - 인수 하나로 여러 개의 키워드 이름과 값을 한번에 받는 것이 가능함
  - 매개변수 앞에 ** 기호 붙임
  - 키워드 가변인수는 인수의 마지막에 작성함 (위치 인수, 키워드 인수, 키워드 가변인수)  
`def func_a(**dica):`  
`    print(dica)`   
`    for value in dica.values():`  
`       print(value)`  
`func_a(a=1, b=2, c=3)`     

# while 문 , continue 만났을 때 break 만났을 때 

# 파일
### 파일 오픈 : 파일 입출력을 위해 위치를 확인하고 버퍼를 준비하는 과정
`open(파일명, 모드)`    
`close()`  
>  - 파일명 : 파일경로 포함  
>  - 파일 열기 모드  
> r - 읽기 모드(파일을 읽기만)  
> w -쓰기 모드(파일에 내용 작성)  
> a - 추가 모드 (파일의 마지막에 새로운 내용 추가)  
### 입출력 - 읽는 메소드 3개 
  - read() : 파일 내용 전체를 한번에 읽는 함수
  - readline() : 파일 내용을 한 줄씩 읽고 파일 마지막에 빈 문자열 리턴
  - readlines() : 파일 내용 전체를 한번에 읽어 한 줄식 문자열로 만들어 리스트로 리턴


