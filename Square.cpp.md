```C++
//Работу выполнил Арефьев Роман ВМК-20
#include "square.h"
#include <iostream>
#include <math.h>
#include <cmath>
#include <exception>
#include <string>

square::square()
{
	_a = 1;
}

square::square(float a1)
{
	set_a(a1);
}

void square::set_a(float a1)											//Ввод а
{
	if (a1 < 0)
	{
		throw std::invalid_argument("Не может быть отрицательным");		//Эта ошибка если а отрицательное 
	}
	else
	{
		this->_a = a1;													// a сохраняется в _a
	}
}



float square::get_a(float a1)                                      //Выввод стороны квадрата
{
	return a1;
}


float square::Area() const                                    //Нахождение площади квадрата
{
	float  S;

	S = pow(_a, 2);

	return S;
}

float square::Perimetr() const                                   //Нахождение периметра квадрата
{
	float P;

	P = 2 * _a + 2 * _a;

	return P;
}

float square::Diagonal() const                                  //Нахождение диагонали
{
	float D;

	D = sqrt(pow(_a, 2) + pow(_a, 2));

	return D;
}

float square::VOCircle() const                                //Нахождение вписанной окружности
{
	float VO;

	VO = _a / 2;

	return VO;
}

float square::OOCircle() const                               //Нахождение описанной окружности
{
	float OO;

	OO = _a / sqrt(2);

	return OO;


}

string square::show() const                                 //Вывод 
{
	string str;
	str = to_string(_a);
	return str;
}
```
