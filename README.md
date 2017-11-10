## Лабораторная работа 7

### Инструкция
Каждое задание должно быть выполненно в отдельном `.cpp` файле.
Прототипы функции должны быть вынесены в соответствующие `.hpp` файлы.
Все реализованные функции необходимо вызвать в фунции `main` в файле [lab07](lab07.cpp)
Все `.cpp` файлы добавить в `CMakeLists.txt`

### Как проверить, что cpplint не обнаружил ошибок в ваших файлах
* установите Python2.7
* запустите командную строку
* выполните команду `cd %Путь до папки с файле лабораторной%`. Пример: `cd /user/lab07`
* выполните команду `python cpplint.py %имя проверяемого файла%`. Пример: `python cpplint.py lab07.cpp`
* в консоли появятся сообщения об ошибках (или не появятся)

### Задание 1
* Реализуйте функцию сохранения массива слов в файл
```cpp
void saveToFile(const std::string& filename, const std::vector<std::string>& data);
```

* Реализуйте функцию загрузки массива слов из файла
```cpp
void loadFromFile(const std::string& filename, std::vector<std::string>& outData);
```

### Задание 2
Есть структура `Book`
```cpp
struct Book
{
    std::string Author;
    std::string Title;
    int Year;
};
```

* Реализуйте функцию сохранения массива книг в файл
```cpp
void saveToFile(const std::string& filename, const std::vector<Book>& data);
```

* Реализуйте функцию загрузки массива книг из файла
```cpp
void loadFromFile(const std::string& filename, std::vector<Book>& outData);
```

### Задание 3
Есть структура `Student`
```cpp
enum Score
{
    Unsatisfactory = 2,
    Satisfactorily,
    Good,
    Excellent
};

struct Student
{
    std::string Name;
    int Year;
    std::map<std::string, Score> RecordBook;
};

// в качестве ключа - название группы
// в качестве значения - список студентов
using Groups = std::map<std::string, std::vector<Student>>;
```

* Реализуйте функцию сохранения группы в файл
```cpp
void saveToFile(const std::string& filename, const Groups& groups);
```

* Реализуйте функцию загрузки группы из файла
```cpp
void loadFromFile(const std::string& filename, const Groups& outGroups);
```
