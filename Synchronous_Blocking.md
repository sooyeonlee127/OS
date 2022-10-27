# synchronous와 Asynchronous, Blocking와 Non-Blocking

비슷한 개념이라 혼동할 수 있다. 그러나 정확하게는 다른 개념이다.

**function A () {**

      **function B () {}**

(A의 다른 작업(B가 호출되는 동안 A는 처리될 수 있는가?)

**}**

### **1) synchronous, Asynchronous**

‘**순서대로** 일이 마치는가’에 대한 여부

(순서대로 끝남: 동기, 순서대로 끝나지 않음: 비동기)

A → B → C 함수가 순서대로 호출되었을 때, 순서대로 끝나는가

즉 실행순서와 끝나는 순서가 동일한가에 대한 구분

→ 동시에 작업을 하는가? 이건 다른 문제

### **2) Blocking, Non-Blocking**

‘**동시에** 작업을 할 수 있는가’ == 호출한 함수가 제어권을 계속 가지고 있는가?

A함수에서 B함수가 끝날 때까지 A함수가 아무것도 못하면 Blocking,

A함수가 자기일을 동시에 한다면 Non-Blocking

\[예시\]

사장이 비서한테 일을 시키고, 밥을 먹으러 가고 싶다.

1.  일을 시키고, 밥을 먹으러 감(Non-Blocking)  
    일과 동시에 밥을 먹는 것 - 두 가지 일을 동시에 한다
    1.  밥을 먹는 중에 비서가 일이 끝났다고 말함 (끝나는 순서 동일-Synchronous)  
        ⇒ **“NonBlocking-synchronous하다”**  
        컴퓨터로 치면, 사장이 계속 전화로 확인함: ‘일 끝났니?’
    2.  밥을 먹고 와서 일에 대한 결과를 들음(끝나는 순서 바뀜-Asynchronous)  
        ⇒ **“NonBlocking-Asynchronous하다”  
          
        **
2.  일의 결과를 듣고 밥을 먹으러 가기로 함(Blocking)  
    밥을 동시에 먹지 못함   
      
    이 예시의 경우 무조건 Blocking-Synchronous⇒ 실제 사례를 봐도, 설계를 일부러 하는 경우는 거의 없다.  
    → 개발자의 실수  
    NonBlocking-Asynchronous방식을 쓰는데, 그 과정 중에 하나라도 blocking 요소가 존재한다면, 의도하지 않게 blocking-Asynchronous가 발생가능