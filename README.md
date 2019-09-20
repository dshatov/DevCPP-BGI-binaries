# DevC++ | BGI | cp1251

## О проекте

Это модифицированная сборка портативной (не требующей установки) среды [Orwell Dev-C++](https://sourceforge.net/projects/orwelldevcpp/files/Portable%20Releases/).

## Особенности
* Готова к использованию библиотека [OpenBGI](http://openbgi.sourceforge.net/) - порт графической библиотеки из Turbo Pascal и Borland C++
* Работающий "из коробки" ввод/вывод кириллицы
* Отсутствует компилятор C++ (используйте расширение `.с` вместо `.cpp` для исходников!)
* Режим сборки `GCC-32-BGI-Debug`: консоль отсутствует, отладчик работает
* Режим сборки `GCC-32-BGI-Console-Debug`: консоль присутствует, отладчик работает

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
// Сохраните это в кодировке CP1251.
// DevCPP по умолчанию использует эту кодировку в русскоязычной Windows.

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
