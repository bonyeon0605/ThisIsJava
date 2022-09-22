# 기본 API 클래스  

## java.lang과 java.util 패키지   
### java.lang 패키지   
- 기본적인 클래스를 담고 있기 떄문에 import없이 사용 가능   
- ex) Object, System, Class, String, StringBuffer, StringBuilder, Math  
### java.util 패키지   
- 컬렉션 클래스들이 대부분 포함   
- ex) Arrays, Calendar, Date, Objects, StringTokenizer, Random  
## Object 클래스   
- Object는 최상위 부모 클래스   
- 모든 클래스는 암시적으로 java.lang.Object 클래스를 상속하게 된다.   
### 객체 비교(equals())
> public boolean equals(Object object) {}   
- 매개타입이 Object라는 의미는 모든 객체가 대입가능하다는 의미   
- 논리적으로 동등하다는 것은 같은 객체이건 다른 객체이건 상관없이 객체가 저장하고 있는 데이터가 동일함을 뜻한다.   
- equals()메소드를 재정의할 때는 동일한 객체인지 먼저 확인(instanceof 활용)