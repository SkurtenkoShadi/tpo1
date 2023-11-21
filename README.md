[![CI/CD GitHub Actions](https://github.com/seekerk/ctest/actions/workflows/test-action.yml/badge.svg)](https://github.com/seekerk/ctest/actions/workflows/test-action.yml)
[![Coverage Status](https://coveralls.io/repos/seekerk/ctest/badge.svg?branch=main)](https://coveralls.io/github/seekerk/ctest?branch=main)
[![Quality Gate](https://sonarcloud.io/api/project_badges/measure?project=seekerk_ctest&metric=alert_status)](https://sonarcloud.io/dashboard?id=seekerk_ctest)
[![Bugs](https://sonarcloud.io/api/project_badges/measure?project=seekerk_ctest&metric=bugs)](https://sonarcloud.io/summary/new_code?id=seekerk_ctest)
[![Code smells](https://sonarcloud.io/api/project_badges/measure?project=seekerk_ctest&metric=code_smells)](https://sonarcloud.io/dashboard?id=seekerk_ctest)

# Пример работы связки cmake + Google Test (gtest)

Для подгрузки gtest необходимо выполнить команды:
```
git submodule init
git submodule update
```

# План тестирования:

# Аттестационное тестирование
- Тест А1 (положительный)
- Начальное состояние: Открытый терминал
- Действие: Пользователь запускает программу с аргументами 1, -7, 6
- Ожидаемый результат:
```
Первый корень уравнения = 6.00
Второй корень уравнения = 1.00
Число фибоначчи, соответствующее номеру 1 = 1
Число фибоначчи, соответствующее номеру -7 = 0
Число фибоначчи, соответствующее номеру 6 = 8
```
- Тест А2 (негативный)
- Начальное состояние: Открытый терминал
- Действие: Пользователь запускает программу без аргумента одного или нескольких аргументов
- Ожидаемый результат:
```
Недостаточно аргументов
```
- Тест А3 (положительный)
- Начальное состояние: Открытый терминал
- Действие: Пользователь запускает программу с аргументами 3, 1, 2
- Ожидаемый результат:
```
Первый корень уравнения = Nan
Второй корень уравнения = Nan
Число фибоначчи, соответствующее номеру 3 = 2
Число фибоначчи, соответствующее номеру 1 = 1
Число фибоначчи, соответствующее номеру 2 = 2
```
- Тест А4 (положительный)
- Начальное состояние: Открытый терминал
- Действие: Пользователь запускает программу с аргументами 1, -6, 9
- Ожидаемый результат:
```
Первый корень уравнения = 3.00
Второй корень уравнения = Nan
Число фибоначчи, соответствующее номеру 1 = 1
Число фибоначчи, соответствующее номеру -6 = 0
Число фибоначчи, соответствующее номеру 9 = 34
```
- Тест А5 (негативный)
- Начальное состояние: Открытый терминал
- Действие: Пользователь запускает программу с аргументом 1, -6, a
- Ожидаемый результат:
```
Аргумент 3 не является числом!
```

# Блочное тестирование (класс my_func)
<ol>
<li>
<h3>Метод int fibonachi(int num)</h3>
<ol>
<li>
<h4>Тест Б1.1 (положительный)</h4>
<ul>
<li>Входные данные: 4</li>
<li>Ожидаемый результат: 3</li>
</ul>
</li>
<li>
<h4>Тест Б1.2 (положительный)</h4>
<ul>
<li>Входные данные: 0</li>
<li>Ожидаемый результат: 0</li>
</ul>
</li>
<li>
<h4>Тест Б1.3 (положительный)</h4>
<ul>
<li>Входные данные: -1</li>
<li>Ожидаемый результат: 0</li>
</ul>
</li>
</ol>
</li>
<li>
<h2>Метод double my_sqrt(double* res, double a, double b, double c)</h2>
<ol>
<li>
<h4>Тест Б2.1 (положительный)</h4>
<ul>
<li>Входные данные: 1, -7, 6</li>
<li>Ожидаемый результат:6.00 1.00</li>
</ul>
</li>
<li>
<h4>Тест Б2.2 (положительный)</h4>
<ul>
<li>Входные данные: 3 1 2</li>
<li>Ожидаемый результат: Nan  Nan</li>
</ul>
</li>
<li>
<h4>Тест Б2.3 (положительный)</h4>
<ul>
<li>Входные данные: 1 -6 9</li>
<li>
Ожидаемый результат: 3.00  Nan
</li>
</ul>
</li>
</ol>
</li>
</ol>

# Интеграционное тестирование
<ol>
<li>
<h3>Тест И1</h3>
<ul>
<li>Методы: int fibonachi(int num), double my_sqrt(double a, double b, double c)</li>
<li>Описание: Проверяем, можно ли использовать результат работы функции my_sqrt в функции fibonachi</li>
<li>Входные данные: 4</li>
<li>Ожидаемый результат: 1.73205</li>
</ul>
</li>

</ol>
