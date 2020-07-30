//#include<iostream>
//#include<stdlib.h>
//
//using namespace std;
//
//void Function1(int value)
//{//지역변수
//	value += 20;
//
//}
//
//void Function2(int& value)//int형 래퍼런스(참조)참조자가 넘어와서 같은 녀석처럼 쓸 수 있다.
//{
//	value += 20;
//
//}
//
//int main()
//{
//	int value = 10;
//	cout <<"original value = "<< value << endl;
//
//	Function1(value);
//	cout << "second value = " << value << endl;
//
//	Function2(value);
//	cout << "third value = " << value << endl;
//
//	int & ref = value;//ref는 value를 참조한다.//주소를 가리키는 값//참조자//포인터와는 다르다.
//
//	Function2(ref);
//	cout << "forth value = " << ref << endl;
//
//	// value += Function1(); return하는 형식으로 쓴다.
//
//	int&& ref2 = 20;//R value reference라고 한다.(우측참조)
//
//
//	return 0;
//}
  
  //#include<stdio.h>
//#include<iostream>
//#include<stdlib.h>
//
//using namespace std;
//
////함수의 다형성
////함수 원형
//void Function(int temp)
//{
//	cout << "함수 원형" << endl;
//
//}
////오버로딩된 함수
//void Function(float temp, float temp2)
//{
//	cout << "함수 오버로딩" << endl;
//
//}
//
////클래스는 멤버 변수를 받을 수 있고 함수(메소드라고함)를 받을 수 있다.
////자동차라는 클래스에 바퀴의 멤버면수, 이동해라는 메소드.
////클래스는 struct랑 비슷
//
//class A
//{
//public:
//	A()//생성자(클래스와 같은 이름)//클래스가 만들어질 떄 불리는 메소드(생성자라고 부름)
//	{
//		cout << "생성자 불림" << endl;
//
//	}
//	~A()//소멸자(클래스 + ~ ) 소멸자 - > 클래스가 없어질때 불리는 메소드
//	{
//		cout << "소멸자 불림" << endl;
//
//	}
//	void PublicFunction1()
//	{
//		cout << "public Function 불림" << endl;
//
//	}
//	void PublicFunction2()
//	{
//		protectedPublicFunction();
//	}
//
//	void PublicFunction3()
//	{
//		PrivateFunciton();
//	}
//
//protected:
//	void protectedPublicFunction()
//	{
//		cout << "protected public Function 불림" << endl;
//
//	}
//
//	//private는 클래스 자신만 이용가능
//	//데이터를 은닉하기 위해서private를 쓴다.
//private:
//	int level = 0;
//	void PrivateFunciton()
//	{
//		cout << "private public Function 불림" << endl;
//
//	}
//};
//int main()
//{
//	/*
//	Function(1);
//
//	Function(0.1f, 1.0f);
//*/
//	A a;//인스턴스가 만들어짐
//
//
//	a.PublicFunction1();
//	a.PublicFunction2();
//	a.PublicFunction3();
//
//
//	//ctrl,shift+ space(정보찾기)0
//	
//	return 0;
//}
  
  
  //#include<iostream>
//#include<stdlib.h>
//
//using namespace std;
//
//class Character
//{
//public:
//	//접근 제한자, 필드
//	//생성자
//	Character() //아무것도 안적혀 있으면 기본 생성자라고 한다.
//		: m_attack(10), m_defense(m_luck)//초기화를 해줘야 한다. 안하면 에러뜸
//	{
//		cout << "기본 생성자 호출" << endl;
//	}
//	//생성자 오버로딩
//	Character(int level, float attack, float defense, float luck)
//		: m_attack(attack), m_level(level), m_defense(luck)//초기화를 해줘야 한다. 안하면 에러뜸//검은색 값은 인자로 받은 값이다.
//	{
//		cout << "오버로딩된 생성자 호출" << endl;
//		this->m_level = level;
//		this->m_luck = luck;
//
//		m_temp = (int*)malloc(sizeof(int) * 3);
//
//	}
//
//	~Character()
//	{//소멸자
//		if (m_temp != nullptr)//이런 습관을 들여라
//		{
//			free(m_temp);
//			m_temp = nullptr;
//		}
//
//		cout << "소멸자 호출" << endl;
//		
//
//	}
//	void SetLuck(float luck)
//	{
//		this->m_luck = luck;//m_luck = luck;
//	}
//	float GetLuck()
//	{
//		return m_luck;
//	}
//private:
//	int m_level = 0;
//	float m_luck = 0;
//	const float m_attack;
//	float & m_defense;
//	int * m_temp = nullptr;
//	
//
//	void Function()
//	{
//		m_luck = 10;
//
//	}
//
//};
//
////헝거리안 룰?(int는 i,float은 f등등 변수첫번째이름에 쓴다)
////코딩규칙
////코딩컨벤션?
//
//int main()
//{
//	Character c(99, 100.0f, 20.0f, 0.1f);
//
//	/*c.SetLuck(0.5f);
//	float luck = c.GetLuck;
//
//	Character * c2 = new Character[3];
//	c2->SetLuck(0.5f);
//	
//	delete[] c2;*/
//	/*Character * temp;
//
//	for (int i = 0; i < 3; i++)
//	{
//		delete c2;
//		c2++;
//	}
//	*/
//
//	// c2++;//[1]index를 가져온다
//
//	//Character * c1
//
//	Character * c1 = (Character *)malloc(sizeof(Character));
//	Character * c2 = new Character();//malloc을 쓰면 생성자가 안불리고 new는 생성자가 불린다.
//	//malloc은 단순히 메모리만 만듬(생성자의 여부를 모른다.)
//	//생성자는 new와 delete를 사용한다.
//
//	free(c1);
//	delete(c2);
//
//	return 0;
//}
                          
#include<iostream>
#include<stdlib.h>

using namespace std;

enum ECARMAKER//구체적으로 알아볼 수 있게 쓴다.
{
	ECARMAKER_None = 0,
	ECARMAKER_Hyundai,//1
	ECARMAKER_kia,//2
	ECARMAKER_SM,//3
	ECARMAKER_SSangyoung,//4
	//
	ECARMAKER_Audi = 10,//하나씩 늘어남
	ECARMAKER_Benz,//11
	ECARMAKER_BMW,//12

};

class Car
{
public:
//기본생성자는 public이여야 한다.
	Car()
	{
		maker = ECARMAKER_None;
	}
	Car(ECARMAKER maker)
		:maker(maker)
	{

	}
	~Car()
	{

	}
protected:
	ECARMAKER maker;

};

int main()
{

	return 0;
}



#include <iostream>
#include<stdlib.h>

using namespace std;

//부모 클래스
class A
{
public:
	A()
	{

	}
	~A()
	{

	}
	void Function()
	{
		cout << "Function is called ~" << endl;
	}
	
protected:
	void Function1()
	{
		cout << "Function1 is called ~" << endl;
	}
private:
	void Function2()
	{
		cout << "Function2 is called ~" << endl;
	}

};

class B : public A //A를 상속받았다.B는 상속클래스(단 private만 못쓴다)(protected는 가능)
{
public :
	B()
	{

	}
	~B()
	{

	}
	void FunctionB()
	{
		cout << "FunctionB is called ~" << endl;
		Function1();//클래스 내부에서는 상속된 부모 클래스의 Protected에 접근 가능
		//int main에서 호출은 불가능하다.

		//호출 불가능
		//Function2();//private라서 클래스 내부에ㅔ서도 접근 불가능

	}
};

//상속클래스 2
class C : public A
{
public:
	C() {}
	~C() {}

};
int main()
{
	B b;
	b.Function();
	
	C c;
	c.Function();
	
	//호출 불가능. 
	//b.Funtion1();
	


	return 0;


}





//게임회사뉴스보기


// 숙제

// 블랙잭만들기

// 1. 플레이어 초기자본금 100gold(조정 가능)
// 2. 딜러 자본금 9999gold(조정 가능)
// 3. 'A' = 1점으로 계산한다.
// 4. 플레이어나 딜러 한쪽이 파산하면 게임 강제 종료
// 5. 1게임 종료 후 플레이어는 게임 종료를 선택 가능하게.





                          
