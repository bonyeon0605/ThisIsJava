# 예외 처리
- 에러와 예외의 다른점은?   
    - 에러 : 컴퓨터 하드웨어 오작동 또는 고장으로 개발자가 대처할 수 있는게 없다.
    - 예외 : 사용자의 잘못된 조작 또는 개발자의 잘못된 코딩으로 발생하는 오류   
    
    
##예외의 두 가지 종류
- 일반 예외(Exception)   
  - 컴파일러 체크 예외 - 자바 소스를 컴파일하는 과정에서 예외 처리 코드가 필요한지 검사
  - 예외 처리 코드가 없으면 컴파일 오류 발생
  - ex) ClassNotFoundException, InterruptedException
- 실행 예외(Runtime Exception) 
  - 컴파일 과정에서 예외 처리 코드를 검사하지 않는 예
  - ex) NullPointException, ArrayIndexOutOfBoundsException, NumberFormatException  

> 컴파일 시 예외 처리를 확인하는 차이일 뿐, 두 가지 예외는 모두 예외 처리가 필요    
> **트렌잭션 처리 시 일반 예외를 rollback을 하지 않고, 실행 예외는 rollback을 함.**

## 예외 종류에 따른 코드 처리   
- 다중 캐치가 가능하나 순서는 하위 예외 클래스가 상위 에외 클래스보다 먼저 처리 될 수 있도록 해야한다.   
<pre><code>try {

}
catch(NullPointException | ClassNotFoundException e) {

}catch(Exception e) {

}</code></pre>   

## 예외 떠넘기기
- 메서드 내부에 try-catch문을 작성하는 것이 기본이지만, 경우에 따라 메소드를 호출한 곳으로 예외를 넘길 수 있다. 
- 이 때 사용하는 키워드가 **throws**   
- throws는 메서디 선언부 끝에 작성되어 메서드에서 처리하지 않은 예외를 호출한 곳으로 떠넘기는 역할    
<pre><code>public void method1() {
  try {
    method2(); // 실행 시 catch 문 실행   
  } catch(ClassNotFoundException e) {
    System.out.println("클래스가 존재하지 않습니다.");
  }
}
public void method2 thorws ClassNotFoundException {
  Class clazz = Class.forName("java.lang.String2");
}</code></pre>
   
## 사용자 정의 예외와 예외 발생   
- 다양한 예외 종류를 표한하고 싶을 때 사용  
### 사용자 정의 예외 클래스 선언
- 일반 예외로 선언할 경우, Exception 실행 예외로 선언할 경우, RuntimeException 상속   
- 이름은 xxxxException으로 끝나는 것이 좋다.
- 대부분 생성자 선언만 포함 
- 생성자 두 개를 생성하는게 일반적
  - 기본 생성자
  - 예외 발생 원인 메시지를 전달하기 위해 string타입의 매개 변수를 같는 생성자
    - 해당 생성자는 상위 클래스의 생성자를 호출하여 예외 메시지를 넘겨준다.   
  
## 예외 발생 시키기   
- 자신을 호출한 곳에서 예외를 처리하도록 throws 키워드로 예외를 넘긴다.
<pre><code>public void method() throws xxxException {
  throw new xxxException("메시지");
}</code></pre>



  


