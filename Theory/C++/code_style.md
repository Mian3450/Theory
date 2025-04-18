
---

# 📘 Теория по стилизации кода в C++

## 1. 🔤 Именование переменных, функций, классов

### Переменные:
- **Нижний регистр** + **snake_case**  
  Пример: `user_name`, `total_sum`

### Константы:
- **Верхний регистр** + **snake_case**  
  Пример: `MAX_SIZE`, `PI_VALUE`

### Функции:
- **Нижний регистр** + **snake_case**  
  Пример: `calculate_area()`, `print_result()`

### Классы / Структуры:
- **PascalCase** (с заглавной буквы)  
  Пример: `UserProfile`, `DataManager`

### Пространства имён (namespace):
- **snake_case**  
  Пример: `math_utils`, `graphics_engine`

### Переменные-члены класса:
- Либо `m_`-префикс (`m_value`)  
  Либо нижнее подчёркивание (`value_`)  
  Выберите одно и придерживайтесь его во всем проекте.

---

## 2. 🎨 Стилизация отступов и форматирования

### Отступы:
- Используйте **4 пробела** (или 2, если договорились в команде).  
  ❌ Не используйте табуляцию (`\t`), если не настроен единый стиль в редакторе.

### Фигурные скобки:
- Располагаются на **новой строке**:

```cpp
if (condition)
{
    // тело условия
}
```

- Либо **на той же строке** (если проект придерживается этого стиля):

```cpp
if (condition) {
    // тело условия
}
```

Важно выбрать **один стиль** и соблюдать его повсеместно.

---

## 3. 🧱 Разделение логических блоков

- Между функциями — **1 пустая строка**
- Внутри функции — отделяйте логические блоки **пустыми строками** для читаемости

---

## 4. 📚 Комментарии

### Однострочные:
```cpp
// Это комментарий к следующей строке
```

### Многострочные:
```cpp
/*
 * Это многострочный
 * комментарий
 */
```

### Документационные:
Используйте Doxygen или аналогичный стиль:
```cpp
/**
 * Вычисляет площадь круга
 * @param radius Радиус
 * @return Площадь круга
 */
double calculate_area(double radius);
```

---

## 5. 🧵 Использование кавычек

- Для строк используйте **двойные кавычки** (`"Hello"`).
- Одинарные кавычки (`'A'`) — только для **символов (char)**.

---

## 6. 📏 Длина строки

- Старайтесь не превышать **80–120 символов** в одной строке.
- Если строка слишком длинная — разбейте её.

---

## 7. 🧹 Чистота и порядок

- Не оставляйте **неиспользуемые переменные** или `#include`.
- Используйте `#pragma once` или include guards в заголовочных файлах.

---

## 8. 🛠 Рекомендуемые инструменты

- **clang-format** — автоформатирование кода.
- **cpplint** — линтер для C++.
- **CLion / VS Code / Visual Studio** — имеют встроенные автостилизации.

---

## 9. 💡 Общие советы

- Пишите **самодокументируемый код** — переменные и функции должны быть понятны без комментариев.
- Придерживайтесь **одного стиля на весь проект**.
- Используйте **инициализацию через фигурные скобки** в C++11+:

```cpp
int x{5};   // предпочтительно
```

---


---

# 🧭 Мини-гайд по стилю кода в C++

## ✅ Именование переменных

❌ Плохо:
```cpp
int A;
float totalSumFloat;
string userName;
```

✅ Хорошо:
```cpp
int age;
float total_sum;
std::string user_name;
```

---

## ✅ Именование функций

❌ Плохо:
```cpp
int CalculateArea();
void ShowResult();
```

✅ Хорошо:
```cpp
int calculate_area();
void show_result();
```

---

## ✅ Именование классов и методов

❌ Плохо:
```cpp
class userprofile {
public:
    void getname();
};
```

✅ Хорошо:
```cpp
class UserProfile {
public:
    void get_name();
};
```

---

## ✅ Отступы и скобки

❌ Плохо:
```cpp
if(is_valid){
do_something();
}else{
do_something_else();
}
```

✅ Хорошо:
```cpp
if (is_valid)
{
    do_something();
}
else
{
    do_something_else();
}
```

---

## ✅ Комментарии

❌ Плохо:
```cpp
// function
int sum(int a, int b) {
    return a + b; // sums
}
```

✅ Хорошо:
```cpp
/**
 * Вычисляет сумму двух чисел.
 * @param a Первое число
 * @param b Второе число
 * @return Сумма a и b
 */
int sum(int a, int b)
{
    return a + b;
}
```

---

## ✅ Заголовки и include

❌ Плохо:
```cpp
#include "MyHeader.h"
#include "MyHeader.h" // дважды
#include <iostream> // iostream
```

✅ Хорошо:
```cpp
#pragma once

#include <iostream>
#include "my_header.h"
```

---

## ✅ Инициализация переменных

❌ Плохо:
```cpp
int x = 5;
float y = (float)2.5;
```

✅ Хорошо (C++11+):
```cpp
int x{5};
float y{2.5f};
```

---

## ✅ Пробелы

❌ Плохо:
```cpp
int x=10;
if(a==b){
x++;
}
```

✅ Хорошо:
```cpp
int x = 10;
if (a == b)
{
    x++;
}
```

---

## ✅ Пример хорошего кода:

```cpp
#include <iostream>

class Rectangle
{
public:
    Rectangle(int width, int height)
        : width_{width}, height_{height} {}

    int area() const
    {
        return width_ * height_;
    }

private:
    int width_;
    int height_;
};

int main()
{
    Rectangle rect{10, 5};
    std::cout << "Area: " << rect.area() << std::endl;
    return 0;
}
```
