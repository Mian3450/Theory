# Типы данных
## **Численные типы данных в C++**

В C++ существует множество типов данных для работы с числами. Они делятся на две основные категории: **целочисленные** и **числа с плавающей точкой**. Кроме того, типы данных могут быть **знаковыми** (signed) или **беззнаковыми** (unsigned), а также неизменяемыми (`const`).

---

### **1. Целочисленные типы данных**

**Описание:**  
Целочисленные типы данных используются для хранения целых чисел без дробной части.  
Размер и диапазон зависят от архитектуры системы (чаще всего 32-битная или 64-битная).

| Тип данных    | Размер (байты) | Диапазон значений            |
|---------------|----------------|------------------------------|
| `short`       | 2              | от -32,768 до 32,767        |
| `int`         | 4              | от -2,147,483,648 до 2,147,483,647 |
| `long`        | 4 или 8        | от -2,147,483,648 до 2,147,483,647 (4 байта) или больше (8 байт) |
| `long long`   | 8              | от -9,223,372,036,854,775,808 до 9,223,372,036,854,775,807 |

**Пример использования:**  
```cpp
#include <iostream>

int main() {
    short a = 32767; // Максимальное значение для short
    int b = 2147483647; // Максимальное значение для int
    long c = 2147483647; // long (4 байта на большинстве систем)
    long long d = 9223372036854775807; // Максимальное значение для long long

    std::cout << "short: " << a << std::endl;
    std::cout << "int: " << b << std::endl;
    std::cout << "long: " << c << std::endl;
    std::cout << "long long: " << d << std::endl;

    return 0;
}
```

---

### **2. Типы данных с плавающей точкой**

**Описание:**  
Используются для хранения дробных чисел. Их диапазон и точность зависят от типа.

| Тип данных    | Размер (байты) | Диапазон значений                      | Точность (знаков) |
|---------------|----------------|----------------------------------------|-------------------|
| `float`       | 4              | ±3.4E-38 до ±3.4E+38                  | ~7                |
| `double`      | 8              | ±1.7E-308 до ±1.7E+308                | ~15               |
| `long double` | 12 или 16      | ±1.2E-4932 до ±1.2E+4932 (зависит от компилятора) | ~18               |

**Пример использования:**  
```cpp
#include <iostream>

int main() {
    float pi = 3.14159f; // Суффикс 'f' указывает на тип float
    double e = 2.718281828459; // Без суффиксов — тип double
    long double precision = 2.7182818284590452353602874713527L; // Суффикс 'L' для long double

    std::cout << "float: " << pi << std::endl;
    std::cout << "double: " << e << std::endl;
    std::cout << "long double: " << precision << std::endl;

    return 0;
}
```

---

### **3. Беззнаковые типы данных (`unsigned`)**

**Описание:**  
Для хранения только **положительных** чисел, что удваивает максимальный диапазон значений.  

| Тип данных          | Размер (байты) | Диапазон значений            |
|----------------------|----------------|------------------------------|
| `unsigned short`     | 2              | от 0 до 65,535              |
| `unsigned int`       | 4              | от 0 до 4,294,967,295       |
| `unsigned long`      | 4 или 8        | от 0 до 4,294,967,295 (4 байта) или больше (8 байт) |
| `unsigned long long` | 8              | от 0 до 18,446,744,073,709,551,615 |

**Пример использования:**  
```cpp
#include <iostream>

int main() {
    unsigned int positiveNumber = 4294967295; // Максимальное значение unsigned int
    std::cout << "Unsigned int: " << positiveNumber << std::endl;

    return 0;
}
```

---

## **Константы (`const`)**

**Описание:**  
Константы — это переменные, значения которых нельзя изменить после инициализации. Используются для фиксированных значений, которые не должны изменяться в программе.  

**Пример использования:**  
```cpp
#include <iostream>

int main() {
    const double pi = 3.14159; // Константа
    // pi = 3.14; // Ошибка! Нельзя изменить значение константы

    std::cout << "Число Pi: " << pi << std::endl;

    return 0;
}
```

---

# **Тип данных `char` в C++**  

В языке C++ тип данных `char` используется для хранения одиночного символа. Он представляет собой 8-битное целое число со знаком (`signed char`) или без знака (`unsigned char`). В ASCII-кодировке `char` может хранить символы из стандартного набора, включая буквы, цифры, знаки препинания и управляющие символы.  

---

## **1. Основные свойства `char`**  
- Размер: **1 байт (8 бит)**  
- Диапазон значений:
  - `signed char`: от **-128** до **127**
  - `unsigned char`: от **0** до **255**
- По умолчанию `char` может быть **signed** или **unsigned**, в зависимости от компилятора.  

### **Пример объявления переменной `char`**
```cpp
#include <iostream>

int main() {
    char symbol = 'A';  // Символ 'A'
    std::cout << "Символ: " << symbol << std::endl;
    
    return 0;
}
```
**Вывод:**  
```
Символ: A
```

> **Важно!** Символьные литералы записываются **в одинарных кавычках** (`'A'`), а не в двойных (`"A"`), так как двойные кавычки обозначают строки.

---

## **2. Кодировка символов (ASCII и Unicode)**  
Тип `char` в основном используется для представления символов в **ASCII**-кодировке, где каждому символу соответствует числовое значение.  

### **Пример вывода ASCII-кода символа**
```cpp
#include <iostream>

int main() {
    char letter = 'A';
    
    std::cout << "Символ: " << letter << std::endl;
    std::cout << "ASCII-код: " << static_cast<int>(letter) << std::endl;

    return 0;
}
```
**Вывод:**  
```
Символ: A
ASCII-код: 65
```
> **Примечание:** `static_cast<int>(letter)` приводит `char` к `int`, чтобы показать его числовое значение.

### **Таблица ASCII-кодов**
| Символ | Код (десятичный) |
|--------|------------------|
| `A`    | 65               |
| `B`    | 66               |
| `a`    | 97               |
| `b`    | 98               |
| `0`    | 48               |
| `1`    | 49               |
| ` ` (пробел) | 32        |
| `\n` (новая строка) | 10 |

---

## **3. `char` как целочисленный тип**
Так как `char` хранит числовые значения, можно выполнять с ним арифметические операции.

### **Пример инкрементации `char`**
```cpp
#include <iostream>

int main() {
    char letter = 'A';
    
    letter++;  // Увеличиваем ASCII-код на 1
    std::cout << "Следующий символ: " << letter << std::endl;

    return 0;
}
```
**Вывод:**  
```
Следующий символ: B
```

---

## **4. `signed char` и `unsigned char`**
Если `char` явно указан как `signed` или `unsigned`, его диапазон значений меняется.

| Тип            | Минимальное значение | Максимальное значение |
|---------------|--------------------|--------------------|
| `char` (зависит от компилятора) | -128 или 0 | 127 или 255 |
| `signed char` | -128 | 127 |
| `unsigned char` | 0 | 255 |

### **Пример разницы `signed char` и `unsigned char`**
```cpp
#include <iostream>

int main() {
    signed char sc = -100;
    unsigned char uc = 200;

    std::cout << "signed char: " << static_cast<int>(sc) << std::endl;
    std::cout << "unsigned char: " << static_cast<int>(uc) << std::endl;

    return 0;
}
```
**Вывод:**  
```
signed char: -100
unsigned char: 200
```

> **Важно!** `unsigned char` не может хранить отрицательные значения.

---

## **5. Управляющие символы (`\n`, `\t`, `\b`)**  
Некоторые `char` представляют не печатные символы, а управляющие команды.

| Управляющий символ | Описание |
|-------------------|----------|
| `\n` | Перевод строки |
| `\t` | Табуляция (отступ) |
| `\b` | Backspace (удаляет предыдущий символ) |
| `\r` | Возврат каретки (перевод в начало строки) |
| `\'` | Одинарная кавычка |
| `\"` | Двойная кавычка |
| `\\` | Обратный слеш |

### **Пример использования `\n` и `\t`**
```cpp
#include <iostream>

int main() {
    std::cout << "Первая строка\nВторая строка" << std::endl;
    std::cout << "Слово1\tСлово2\tСлово3" << std::endl;
    
    return 0;
}
```
**Вывод:**  
```
Первая строка
Вторая строка
Слово1    Слово2    Слово3
```

---

## **6. Символьные массивы (`char[]`) и строки**
В C++ можно создавать массивы символов (`char`), которые формируют строки.

### **Пример строки в виде массива `char[]`**
```cpp
#include <iostream>

int main() {
    char greeting[] = "Hello";  // Строка из символов

    std::cout << "Приветствие: " << greeting << std::endl;
    
    return 0;
}
```
**Вывод:**  
```
Приветствие: Hello
```
> **Примечание:** Строки в стиле C оканчиваются нулевым символом (`'\0'`), который обозначает конец строки.

---

## **7. Современные строки (`std::string`)**
Вместо `char[]` в C++ часто используют `std::string` из библиотеки `<string>`.

### **Пример использования `std::string`**
```cpp
#include <iostream>
#include <string>

int main() {
    std::string name = "Alex";

    std::cout << "Имя: " << name << std::endl;
    
    return 0;
}
```
**Вывод:**  
```
Имя: Alex
```

---

## **Заключение**
| Свойство | Описание |
|----------|----------|
| `char` | Хранит один символ (1 байт) |
| ASCII-код | Числовое представление символа |
| `signed char` | От -128 до 127 |
| `unsigned char` | От 0 до 255 |
| `\n`, `\t`, `\b` | Управляющие символы |
| `char[]` | Строка в стиле C |
| `std::string` | Современная строка в C++ |

> **Совет:** Если вам нужно работать с текстом, **используйте `std::string`**, так как `char[]` менее удобен.

---

# **Тип данных `bool` в C++**  

Тип данных `bool` в C++ предназначен для хранения **логических значений**:  
- `true` (**истина**)  
- `false` (**ложь**)  

Этот тип используется в **условных операторах (`if`, `while`, `for`)**, а также в **логических выражениях**.

---

## **1. Основные свойства `bool`**
- Размер: **1 байт** (может отличаться в зависимости от компилятора)
- Возможные значения:  
  - `true` (1)  
  - `false` (0)  
- Любое **ненулевое значение** интерпретируется как `true`
- Число `0` интерпретируется как `false`

---

## **2. Объявление и инициализация `bool`**
### **Пример:**
```cpp
#include <iostream>

int main() {
    bool isSunny = true;    // Переменная с значением "истина"
    bool isRainy = false;   // Переменная с значением "ложь"

    std::cout << "Солнечно? " << isSunny << std::endl;
    std::cout << "Идет дождь? " << isRainy << std::endl;

    return 0;
}
```
**Вывод:**
```
Солнечно? 1
Идет дождь? 0
```
> **Важно!** `true` выводится как `1`, а `false` — как `0`.

---

## **3. `bool` в условиях (`if`)**
Тип `bool` используется в **условных операторах**.

### **Пример:**
```cpp
#include <iostream>

int main() {
    bool isNight = false;

    if (isNight) {
        std::cout << "Сейчас ночь." << std::endl;
    } else {
        std::cout << "Сейчас день." << std::endl;
    }

    return 0;
}
```
**Вывод:**  
```
Сейчас день.
```
> **Примечание:** `if (isNight)` работает, потому что `isNight` — это `false`, а значит, код внутри `if` не выполнится.

---

## **4. `bool` и числа**
Переменная `bool` **может принимать числовые значения**, но они автоматически преобразуются в `true` или `false`.

### **Пример:**
```cpp
#include <iostream>

int main() {
    bool a = 10;  // Любое ненулевое значение → true
    bool b = 0;   // Ноль → false

    std::cout << "a = " << a << std::endl;
    std::cout << "b = " << b << std::endl;

    return 0;
}
```
**Вывод:**
```
a = 1
b = 0
```
> **Примечание:** `bool a = 10;` интерпретируется как `true`, а `bool b = 0;` как `false`.

---

## **5. Логические операторы с `bool`**
| Оператор | Описание | Пример |
|----------|----------|--------|
| `&&` | Логическое "И" (оба должны быть `true`) | `a && b` |
| `\|\|` | Логическое "ИЛИ" (достаточно одного `true`) | `a \|\| b` |
| `!` | Логическое "НЕ" (инверсия) | `!a` |

### **Пример с логическими операторами**
```cpp
#include <iostream>

int main() {
    bool a = true;
    bool b = false;

    std::cout << "a && b: " << (a && b) << std::endl;
    std::cout << "a || b: " << (a || b) << std::endl;
    std::cout << "!a: " << !a << std::endl;

    return 0;
}
```
**Вывод:**
```
a && b: 0
a || b: 1
!a: 0
```
> **Разбор:**  
> - `a && b` → `true && false` → `false`  
> - `a || b` → `true || false` → `true`  
> - `!a` → `!true` → `false`  

---

## **6. `bool` в циклах**
`bool` часто используется для **управления циклами**.

### **Пример с `while`:**
```cpp
#include <iostream>

int main() {
    bool running = true;
    int count = 0;

    while (running) {
        std::cout << "Итерация " << count << std::endl;
        count++;

        if (count == 3) {
            running = false;  // Останавливаем цикл
        }
    }

    return 0;
}
```
**Вывод:**  
```
Итерация 0
Итерация 1
Итерация 2
```
> **Примечание:** Цикл **работает, пока `running == true`**.

---

## **7. `bool` в `return` функции**
Функции могут **возвращать `bool`**, если нужно проверить какое-то условие.

### **Пример функции с `bool`**
```cpp
#include <iostream>

bool isEven(int number) {
    return number % 2 == 0;
}

int main() {
    int num = 10;
    
    if (isEven(num)) {
        std::cout << num << " - четное число" << std::endl;
    } else {
        std::cout << num << " - нечетное число" << std::endl;
    }

    return 0;
}
```
**Вывод:**  
```
10 - четное число
```
> **Разбор:**  
> - `isEven(10)` вернет `true`, так как `10 % 2 == 0`.  
> - Значит, `if (true)` — и программа выводит "10 - четное число".

---

## **8. `boolalpha` для вывода `true/false`**
По умолчанию `bool` выводится как `1` и `0`. Чтобы вывести `"true"` и `"false"`, используйте **`std::boolalpha`**.

### **Пример:**
```cpp
#include <iostream>

int main() {
    bool isCold = true;
    
    std::cout << std::boolalpha; // Включаем вывод в виде true/false
    std::cout << "На улице холодно? " << isCold << std::endl;

    return 0;
}
```
**Вывод:**  
```
На улице холодно? true
```
> **Примечание:** `std::noboolalpha;` вернет стандартный вывод (`1` и `0`).

---

## **Заключение**
| Свойство | Описание |
|----------|----------|
| `bool` | Хранит `true` или `false` |
| `true == 1`, `false == 0` | Автоматически преобразуется в числа |
| `&&, \|\|, !` | Используется в логических выражениях |
| `if (boolVar)` | Проверяет истину/ложь |
| `std::boolalpha` | Выводит `true`/`false` вместо `1`/`0` |

> **Совет:** `bool` улучшает читаемость кода, особенно в условиях (`if`) и флагах (`running` в цикле).

---
