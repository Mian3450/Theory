**# Руководство по началу работы с Java**

## 1. Установка Java Development Kit (JDK)
### Почему это нужно?
JDK содержит все необходимые инструменты для компиляции и запуска программ на Java, включая компилятор (`javac`) и виртуальную машину Java (JVM).

### Как установить?
1. Перейдите на официальный сайт Oracle или OpenJDK (Так же можно использовать дистрибутив от Adoptium):
   - [Oracle JDK](https://www.oracle.com/java/technologies/javase-downloads.html)
   - [OpenJDK](https://openjdk.org/)
   - [Adoptium](https://adoptium.net)
2. Выберите версию (рекомендуется LTS, например, Java 17 или Java 21).
3. Скачайте и установите JDK, следуя инструкциям установщика.
4. Проверьте установку командой:
   ```sh
   java -version
   javac -version
   ```

## 2. Настройка переменных окружения
### Почему это важно?
Для корректной работы Java необходимо добавить путь к JDK в переменную окружения `PATH`.

> **Примечание:** этот шаг может быть автоматически выполнен при установке одного из JDK, из-за чего следующие шаги стоит выполнить лишь для проверки.

### Как настроить (Windows)?
1. Откройте "Win + I" → "Поиск: Изменение переменных среды текущего пользователя".
2. В разделе "Системные переменные" найдите `Path` и добавьте путь к `bin` директории JDK (например, `C:\Program Files\Java\jdk-17\bin`).
3. Добавьте новую переменную `JAVA_HOME` и укажите путь к корневой папке JDK.
4. Перезапустите терминал и проверьте командой `java -version`.

### Как настроить (Linux/macOS)?
1. Откройте терминал и выполните команду:
   ```sh
   echo 'export JAVA_HOME=/path/to/jdk' >> ~/.bashrc
   echo 'export PATH=$JAVA_HOME/bin:$PATH' >> ~/.bashrc
   source ~/.bashrc
   ```
2. Проверьте установку командой `java -version`.

## 3. Установка IDE (интегрированной среды разработки)
### Почему это важно?
IDE помогает писать код быстрее, предоставляет автодополнение, отладчик и инструменты для сборки проектов.

### Популярные IDE для Java:
- [IntelliJ IDEA](https://www.jetbrains.com/idea/) (рекомендуется для начинающих)
- [Eclipse](https://www.eclipse.org/)
- [NetBeans](https://netbeans.apache.org/)
- [Visual Studio Code](https://code.visualstudio.com/) с расширением Java

После установки создайте новый проект и попробуйте запустить простую программу:
```java
public class Main {
    public static void main(String[] args) {
        System.out.println("Привет, мир!");
    }
}
```

## 4. Знакомство с системой сборки
### Почему это важно?
Система сборки управляет зависимостями и автоматизирует компиляцию.

### Популярные инструменты:
- **Maven** ([Apache Maven](https://maven.apache.org/))
- **Gradle** ([Gradle](https://gradle.org/))

Для установки Maven и Gradle можно использовать пакетные менеджеры:
```sh
# Windows (через Chocolatey)
choco install maven gradle

# macOS (через Homebrew)
brew install maven gradle
```

## 5. Написание и запуск первой программы
1. Создайте файл `Main.java` и вставьте код:
   ```java
   public class Main {
       public static void main(String[] args) {
           System.out.println("Hello, Java!");
       }
   }
   ```
2. Скомпилируйте программу:
   ```sh
   javac Main.java
   ```
3. Запустите:
   ```sh
   java Main
   ```
