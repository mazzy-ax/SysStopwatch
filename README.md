# SysStopwatch

[project]:https://github.com/mazzy-ax/SysStopwatch
[license]:https://github.com/mazzy-ax/SysStopwatch/blob/master/LICENSE
[ax2009]:ax2009
[ax2012]:ax2012
[ax4]:ax4

[SysStopwatch][project] &ndash; это класс-обёртка над таймером [System.Diagnostics.Stopwatch](https://docs.microsoft.com/en-us/dotnet/api/system.diagnostics.stopwatch). Класс написан на X++ в [Microsoft Dynamics AX 2009][ax2009], [Microsoft Dynamics AX 2012][ax2012] и [Axapta 4.0][ax4].

Класс `SysStopwatch` позволяет создавать, запускать и останавливать таймеры из Аксапты, получать строку со временем работы, а также обращаться к методам .net-объекта Stopwatch.

Быстрый и эффективный класс `SysStopwatch`:

* не задействует метод `new()`, поэтому можно спокойно использовать `classFactory.createClass()` и другие фабрики
* служебные объекты создаются в памяти только по необходимости
* содержит минимум вычислений на `X++`, форматирование и преобразование в строку выполняется в `.net`
* скрывает взаимодействие с CLR - программист может просто использовать `X++` класс в своем коде
* метод `stopwatch()` возвращает CLR-объект  - программист может получить доступ ко всей функциональности .net-объекта
* метод `toString()` позволяет видеть время выполнения в отладчике

## Пример использования

````java
static void SysStopwatchDemo(Args _args)
{
    SysStopwatch timer = SysStopwatch::startNew();

    setprefix(funcname());

    sleep(1500);

    info(strfmt("Elapsed: %1", timer.elapsed()));
    info(strfmt("Elapsed: %1", timer.elapsedWide()));
}
````

![SysStopwatch demo job](https://github.com/mazzy-ax/SysStopwatch/wiki/img/SysStopwatch.png)

## ChangeLog

* [CHANGELOG.md](CHANGELOG.md)
* <https://github.com/mazzy-ax/SysStopwatch/releases>

## Помощь проекту

Буду признателен за ваши замечания, предложения и советы по проекту как в разделе [Issues](https://github.com/mazzy-ax/SysStopwatch/issues), так и в виде письма на адрес <mazzy@mazzy.ru>

Мазуркин Сергей (mazzy)
