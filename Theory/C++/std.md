### **Разбор основных элементов пространства имён `std`**

`std` (стандартное пространство имён) содержит множество классов, функций и объектов, используемых для решения повседневных задач в C++. Разберём ключевые элементы и их использование.

---

### **1. Стандартный ввод/вывод**
Эти объекты используются для взаимодействия с пользователем через консоль.

#### **`std::cout`**  
Используется для вывода данных в консоль.  

**Пример:**  
```cpp
#include <iostream>

int main() {
    std::cout << "Привет, мир!" << std::endl; // Вывод строки с переходом на новую строку
    return 0;
}
```

#### **`std::cin`**  
Используется для ввода данных из консоли.  

**Пример:**  
```cpp
#include <iostream>

int main() {
    int age;
    std::cout << "Введите ваш возраст: ";
    std::cin >> age;
    std::cout << "Ваш возраст: " << age << std::endl;
    return 0;
}
```

#### **`std::endl`**  
Обеспечивает переход на новую строку (аналог `\n`) и сбрасывает буфер вывода.

---

### **2. Работа со строками**

#### **`std::string`**  
Класс для работы со строками.  

**Основные методы:**
- `size()` или `length()` — возвращает длину строки.
- `append()` — добавляет строку в конец.
- `substr()` — извлекает подстроку.
- `find()` — ищет подстроку.
- `replace()` — заменяет часть строки.  

**Пример:**  
```cpp
#include <iostream>
#include <string>

int main() {
    std::string name = "Иван";
    name.append(" Иванович"); // Добавление текста
    std::cout << "Имя: " << name << std::endl;

    std::cout << "Длина строки: " << name.size() << std::endl;
    std::cout << "Подстрока: " << name.substr(0, 4) << std::endl; // Извлечение "Иван"

    return 0;
}
```

---

### **3. Контейнеры**

Контейнеры — это структуры данных, которые позволяют хранить и управлять наборами данных.

#### **`std::vector`**  
Динамический массив с возможностью изменения размера.

**Основные методы:**
- `push_back()` — добавляет элемент в конец.
- `pop_back()` — удаляет последний элемент.
- `size()` — возвращает количество элементов.
- `at()` — доступ к элементу с проверкой границ.

**Пример:**  
```cpp
#include <iostream>
#include <vector>

int main() {
    std::vector<int> numbers = {1, 2, 3};
    numbers.push_back(4); // Добавление элемента
    numbers.pop_back(); // Удаление последнего элемента

    for (int num : numbers) {
        std::cout << num << " ";
    }

    return 0;
}
```

#### **`std::map`**  
Ассоциативный массив (отображение), где каждому ключу соответствует значение.

**Основные методы:**
- `insert()` — добавляет пару ключ-значение.
- `find()` — ищет элемент по ключу.
- `erase()` — удаляет элемент по ключу.
- `[]` — доступ к элементу по ключу.

**Пример:**  
```cpp
#include <iostream>
#include <map>

int main() {
    std::map<std::string, int> ages;
    ages["Иван"] = 30;
    ages["Мария"] = 25;

    std::cout << "Возраст Ивана: " << ages["Иван"] << std::endl;

    return 0;
}
```

#### **`std::set`**  
Набор уникальных элементов.

**Основные методы:**
- `insert()` — добавляет элемент.
- `find()` — проверяет наличие элемента.
- `erase()` — удаляет элемент.

**Пример:**  
```cpp
#include <iostream>
#include <set>

int main() {
    std::set<int> uniqueNumbers = {1, 2, 3, 3}; // Дубликаты не добавляются
    uniqueNumbers.insert(4);

    for (int num : uniqueNumbers) {
        std::cout << num << " ";
    }

    return 0;
}
```

---

### **4. Алгоритмы**

Алгоритмы из `std` работают с контейнерами.

#### **`std::sort`**  
Сортирует элементы контейнера.  

**Пример:**  
```cpp
#include <iostream>
#include <vector>
#include <algorithm>

int main() {
    std::vector<int> numbers = {5, 3, 8, 1};
    std::sort(numbers.begin(), numbers.end()); // Сортировка по возрастанию

    for (int num : numbers) {
        std::cout << num << " ";
    }

    return 0;
}
```

#### **`std::find`**  
Находит элемент в диапазоне.

**Пример:**  
```cpp
#include <iostream>
#include <vector>
#include <algorithm>

int main() {
    std::vector<int> numbers = {5, 3, 8, 1};
    auto it = std::find(numbers.begin(), numbers.end(), 3);

    if (it != numbers.end()) {
        std::cout << "Элемент найден: " << *it << std::endl;
    } else {
        std::cout << "Элемент не найден" << std::endl;
    }

    return 0;
}
```

---

### **5. Математические функции**

Для выполнения математических операций используется заголовок `<cmath>`.

#### **Основные функции:**
- `std::pow(x, y)` — возведение в степень.
- `std::sqrt(x)` — квадратный корень.
- `std::abs(x)` — модуль числа.
- `std::sin(x)`, `std::cos(x)` — синус и косинус.

**Пример:**  
```cpp
#include <iostream>
#include <cmath>

int main() {
    double base = 2.0, exponent = 3.0;

    std::cout << "2^3 = " << std::pow(base, exponent) << std::endl;
    std::cout << "Квадратный корень из 9: " << std::sqrt(9) << std::endl;

    return 0;
}
```

---

### **6. Умные указатели**

Умные указатели облегчают управление памятью и автоматически освобождают ресурсы.

#### **`std::unique_ptr`**  
Указатель с уникальным владением.

**Пример:**  
```cpp
#include <iostream>
#include <memory>

int main() {
    std::unique_ptr<int> ptr = std::make_unique<int>(10);
    std::cout << "Значение: " << *ptr << std::endl;

    return 0;
}
```

#### **`std::shared_ptr`**  
Указатель с разделённым владением.

**Пример:**  
```cpp
#include <iostream>
#include <memory>

int main() {
    std::shared_ptr<int> ptr1 = std::make_shared<int>(10);
    std::shared_ptr<int> ptr2 = ptr1; // ptr2 разделяет владение с ptr1

    std::cout << "Значение: " << *ptr1 << std::endl;

    return 0;
}
```

---
