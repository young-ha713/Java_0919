# Java_0919  
  
  
  
  
  
(공부 방법)
객체(전역변수와 메소드로 구성)  
>>>>코딩능력 젤 중요- 배열 if문,조건문,이중포문 자유자재로 사용 가능해야함  
>>>지금 시점에서 객체와 메서드를 제대로 숙지  
>>>>컴퓨터 시스템에 대한 작동 원리(운영체제 네트워크 등등)  
운영체제 : 윈도우,리눅스  
운영체제에서는 자원관리 : 시피유 관리 ,램관리  
네트워크는 통신의 동작원리 osi 7 layers    왜 공부하나? 한정된 자원을 잘 활용하기 위해  
  
  
코딩 능력을 처음 공부할때는 동작의 성공을 중점으로 , 컴터 시스템을 이해한 후는 성공과 성능 둘 다 알아야함  
  
   
-------------------------------------  
  
**  
1. 코드(그냥 명령문)와 스레드(요리사)는 명령문을 실행하는것  
2. heap영역-객체를 관리하는곳 ,code영역-코드의 명령문이 있는곳(레시피 종이), method영역-호출되는 메소드와 실행중인 메소드로 구분  
-이것들로 프로그램을 동작시키는 곳이 jvm  .
이것을 기준으로 내가 스레드가 되어 힙 영역과 메서드 영역을 잘 생각해본다.  
  
  
스레드가 두개가 있다면?
  
  
메인메소드 부터 시작  
![스레드 흐름](https://user-images.githubusercontent.com/80766275/190935062-36c22363-4aa5-435c-bdba-6aa4729309e8.PNG)  
  
  
  
생성자의 특징 - 메서드의 일종.하나만 있다.리턴타입이 없다.  
pubulic goods(){}까지는 쓸 수 있으나 void 추가시 일반 메서드가 되어버림  
  
  
**
메서드 공부하는법 - 정의와 호출부로 구분  
정의는 접근제어자 리턴타입 메서드명(매개변수)  
호출은 메서드명(매개변수)  
  
  
글 제목 리턴하는 메서드  
public String getTitle(){  
  return title;  
}  
  
조회수 증가시키는 메서드  
public void getCnt(){  
  cnt++;  
}  
개발자가 정의한 메서드  
  
  
업그레이드 6번은 contains를 사용하였기 때문에 자바에서 제공하는 객체의 메서드  
  
  ![6번](https://user-images.githubusercontent.com/80766275/190937948-47b59a2c-2e36-4453-89e6-0252a8a1aa5f.PNG)


  
내가 문자열이라는 자료형을 가지고 검색기능을 만들고 싶은데 어떤 메서드로 만들것인가?  
```  
String a ="abc";

a.(뒤에 스트링의 메서드들 뜸) 

//리턴값 있을떼 변수에 담아줘야함  
String s = a.charAt(0);  

```  
![스트링메서드들](https://user-images.githubusercontent.com/80766275/190936734-4b0071ed-5661-4615-a834-8ff09f8aa074.PNG)
  
  
객체가 가진 자원(변수등은) 바러 접근하지 않는게 좋음..  
  
  
7번  

![7번](https://user-images.githubusercontent.com/80766275/190939869-6458cf5f-6922-42ac-8da3-0279725e7041.PNG)
  
  
  
  
  
7번 응용  

![7번 응용](https://user-images.githubusercontent.com/80766275/190939982-6aa25e0a-8c77-47e0-9f92-320849ad1cd8.PNG)

  
IndexOf는 문자열에서 특정 단어가 있는지를 찾고 있을 경우 위치값을 리턴하는 내장 함수이다. 위치값은 0부터 시작하기 때문에 0 이상값이 나오면 결과가 리턴이 되고, -1인 경우 해당 값이 없을 경우이다.  
  
  
  
8번  
![8번](https://user-images.githubusercontent.com/80766275/190938609-52cdec95-af28-4604-9677-63c9d4ef5ce1.PNG)
  
  
-----------------------------------  
  
  
  
  
  ![객체](https://user-images.githubusercontent.com/80766275/190944608-4b2ca141-0615-4d44-9d6d-b909c11c2a19.PNG)
  
  
  ![선언문 구현문](https://user-images.githubusercontent.com/80766275/190945101-9026d31b-023c-4d5d-8d72-9eada6303c7c.PNG)
  
  
1.참조변수는 객체의 주소값을 가진다.  
2. new 연산자는 객체를 만든다.  
3. 참조변수의 주소값을 참조하여 객체의 전역변수나 메서드를 실행한다.  
  
  
  
  
문제  
  
  
![문제](https://user-images.githubusercontent.com/80766275/190951983-df6e290c-1ef8-4c61-bb3b-11ee80a14779.PNG)
  
  
--------------------------------------------  
 Market 만들기  
   
   
 
 ```
 package Market;

public class MainMarket {

	public static void main(String[] args) {
		// TODO Auto-generated method stub

		new GoodsManager();
		
	}

}
```  
  
굿즈 하나 클래스
  
```
package Market;

public class Goods {

	String name=null;
	String id =null;
	int cnt= 0;
	int price=0;
	
	//물건의 이름을 저장하는 메서드
	public void setting (String name,String id,int cnt,int price) {
		//this는 자기 자신의 전역변수를 구분할때 사용하는 키워드
		this.name=name;
		this.id=id;
		this.cnt=cnt;
		this.price=price;

	}
	
	public void prt() {
		System.out.println("이름:"+this.name);
		System.out.println("아이디:"+this.id);
		System.out.println("수량:"+this.cnt);
		System.out.println("단가:"+this.price);

	}
}
```  
  
  
마켓메니저 클래스  
  
```
package Market;

import java.util.Scanner;

public class GoodsManager {

	Goods[] gList = new Goods[10];
	Scanner in = new Scanner(System.in);
	GoodsManager(){
		//물건을 관리하는 객체 물건 1개가 아니라 전체
		for(;;) {
			menu();
			int selMenu = in.nextInt();
			in.nextLine();
			if(selMenu==1) {
				addGoods();
			}else if(selMenu==3) {
				listGoods();
			}
		}
	}
	
	private void listGoods() {
		for(int i=0; i<gList.length;i++) {
			if(gList[i]!=null) {
				System.out.println(i+"번 정보----");
				gList[i].prt();
				System.out.println("----------");
			}
		}
	}

	private void addGoods() {
		Goods newGoods= new Goods();
		System.out.println("이름입력");
		String name = in.nextLine();
		System.out.println("아이디입력");
		String id = in.nextLine();
		System.out.println("수량입력");
		int cnt = in.nextInt();
		in.nextLine();
		System.out.println("가격입력");
		int price = in.nextInt ();
		in.nextLine();
		newGoods.setting(name, id, cnt, price);
		
		for(int i=0; i<gList.length; i++) {
			if(gList[i]==null) {
				gList[i] =newGoods;
				break;
			}
		}
	}

	private void menu() {
		System.out.println("1. 물건등록");
		System.out.println("2. 물건수정");
		System.out.println("3. 전체보기");
		System.out.println("4. 물건삭제");

	}
}
``` 
  
   
------------------------------------------------------------------  
   
   
   
   
실습 이론  
  
1. 선언문시 참조타입,원시타입
2. 객체를 만드는 연산자는 new,객체의 주소를 가지는것은 참조변수의 값
3. 클래스는 전역변수와 메서드로 구성한다
4. 참조타입 변수 여러개가 같은 주소값을 가지고 있다면 객체를 공유한다는 의미  
  
  
  
오후실습  
  
1. 클래스는 세분화 물건과 물건 관리는 깊게 생각하면 다름
2. 필수기능 -등록,전체보기,삭제 ,수정
3. 세부기능- 사용할 수 있는 아이디의 기준->중복불가 ,욕설 불가  
  
  
  
   
  
  
  




  

  


