```C++
//Работу выполнил Арефьев Роман ВМК-20
#include <iostream>
#include "square.h"

using namespace std;

int main()
{
	setlocale(LC_ALL, "Russian");
	float a;

	cin >> a;


	square t1;

	try														//Защищенный блок кода 
	{
		t1.set_a(a);										//Ввод а
	}

	catch (exception e)                                     //Проверка введены ли положительные данные
	{
		cout << "Произошла ошибка" << e.what();
	}

	    cout << "Стороны квадрата равны: " << t1.get_a(a) << endl;  //Стороны
		cout << "Площать равна: " << t1.Area() << endl;  //Поиск площади
		cout << "Периметр равен: " << t1.Perimetr() << endl; //Поиск периметра
		cout << "Диагональ равна: " << t1.Diagonal() << endl;   //Поиск диагонали
		cout << "Радиус вписанной окружности равен: " << t1.VOCircle() << endl;   //Поиск радиуса во
		cout << "Радиус описанной окружности равен: " << t1.OOCircle() << endl;   //Поиск радиуса оо
		cout << endl;

		cin >> a;


		square *t2;
		
		t2 = new square;                                        //динамическое выделение памяти

		try														//Защищенный блок кода 
		{
			t2->set_a(a);										//Ввод а
		}

		catch (exception e)                                     //Проверка введены ли положительные данные
		{
			cout << "Произошла ошибка" << e.what();
		}

		cout << "Стороны квадрата равны: " << t2->get_a(a) << endl;  //Стороны
		cout << "Площать равна: " << t2->Area() << endl;  //Поиск площади
		cout << "Периметр равен: " << t2->Perimetr() << endl; //Поиск периметра
		cout << "Диагональ равна: " << t2->Diagonal() << endl;   //Поиск диагонали
		cout << "Радиус вписанной окружности равен: " << t2->VOCircle() << endl;   //Поиск радиуса во
		cout << "Радиус описанной окружности равен: " << t2->OOCircle() << endl;   //Поиск радиуса оо

		delete t2; //очистка памяти
		cout << endl;

		square t_arr[10];											//массив из объектов класса
		t_arr[0].set_a(5);											//меняем 0 эллемент массива 
		cout << "массив: " << t_arr[0].show() << endl;


		square* t_arr1 = new square[10];									//дин массив из объектов класса
		t_arr1[0].set_a(4);											       //меняем 0 элемент
		cout << "дин. массив: " << t_arr1[0].show();					   //выводим 0 элемент
		delete[] t_arr1;											       //очищаем память
		cout << endl;

		cout << "Массив указателей на объекты класса " << endl;
		square* t_arr2[10];											//дин массив указателейн на объекты класса
		for (int i = 0; i < 10; i++)
		{
			a = 1 + rand() % 100;
			t_arr2[i] = new square;									// выделяем память
			t_arr2[i]->set_a(a);									// указываем стороны треугольника для каждого объекта
		}

		for (int i = 0; i < 10; i++)
		{
			cout << "дин массив" << "[" << i << "] = " << (*t_arr2[i]).show();				//вывод информации для каждого объекта
			delete t_arr2[i];
			cout << endl;
		}

	return 0;
}
