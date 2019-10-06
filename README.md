# DevC++ | BGI | cp1251

## О проекте

Это модифицированная сборка среды Orwell Dev-C++

## Установка и запуск

[Ссылка для скачивания тут.](https://github.com/dshatov/DevCPP-BGI-binaries/releases/download/v1.0.2/Dev-Cpp-BGI.zip)
Распакуйте архив куда угодно.

Для запуска следует использовать файл `devcppPortable.exe` вместо `devcpp.exe`!

## Особенности
* Готова к использованию библиотека [OpenBGI](http://openbgi.sourceforge.net/) - порт графической библиотеки из Turbo Pascal и Borland C++
* Работающий "из коробки" ввод/вывод кириллицы
* Отсутствует компилятор C++ (используйте расширение `.с` вместо `.cpp` для исходников!)
* Режим сборки `GCC-32-BGI-Debug`: консоль отсутствует, отладчик работает, подходит для игр
* Режим сборки `GCC-32-BGI-Console-Debug`: консоль присутствует, отладчик работает, подходит для олимпиад

## Лучше один раз увидеть

#### Графика

```c++
#include <graphics.h>
#include <stdlib.h>

int main() {
    int gd = DETECT, gm = 0;
    initgraph(&gd, &gm, "");
    while(!anykeypressed()) {
        setfillstyle(0, rand() % (MAXCOLORS + 1));
        bar(rand() % getmaxx(),rand() % getmaxy(),rand() % getmaxx(),
            rand() % getmaxy());
        delay(10);
    }
    closegraph();
    return 0;
}
```

#### Ввод/вывод кириллицы

```c++
// Предполагается, что это сохранено в кодировке CP1251.
// DevCPP по умолчанию использует именно эту кодировку в русскоязычной Windows.

// Выберите режим компиляции `GCC-32-BGI-Console-Debug`

#include <stdio.h>

int main() {
    printf("Привет!\n");
    char s[64];
    scanf("%s", s);
    printf("%s", s);
    return 0;
}

```
