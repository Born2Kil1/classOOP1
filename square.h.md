```C++

#pragma once
#include <iostream>
#include <string>
using namespace std;

class square
{
private:
	float _a;

public:
	void set_a(float a1);         //Ввод а
	float get_a(float a1);        //Вывод стороны квадрата
	float Area()const;            //Поиск площади
	float Perimetr()const;        //Поиск периметра
	float Diagonal()const;        //Поиск диагонали
	float VOCircle()const;        //Поиск вписанной окружности
	float OOCircle()const;        //Поиск описанной окружности
	string show() const;          //Вывод
	square();                     
	square(float a1);             //Конструктор с параметрами 
};
```
