Постановка на проблема:
Съществуващите инструменти за компресиране с общо предназначение като gzip, bzip2 и zstd са оптимизирани за големи файлове и пакетна обработка. Въпреки това, те са неефективни при използване върху малки текстови файлове (обикновено под 100 KB), където режийните разходи за
компресиране – включително метаданни, заглавни полета и инициализация на речници – могат да надхвърлят спестеното пространство. Това води до слаби коефициенти на компресия, незначително намаление на размера или дори до по-големи изходни файлове.
В много системи – като микросервизи, CLI помощни програми, вградени устройства или системи за контрол на версиите с много текстови файлове – съществува необходимост от ефективно съхранение и предаване на множество малки текстови файлове. Въпреки малкия им размер, тези
файлове често са многобройни и съдържат повтарящи се шаблони, типични за структуриран или написан от човек текст.
Настоящата дипломна работа има за цел да проектира и реализира лек, ориентиран към текст алгоритъм за компресиране, съобразен с малки текстови файлове, който постига по-добър баланс между коефициент на компресия, скорост и режийни разходи в сравнение с компресорите с общо
предназначение.

Защо проблемът е от значение:
Gzip добавя заглавна и крайна част (~40–60 байта).
При конфигурационен файл от 2 KB, gzip може да го намали само със 300 байта – което не е съществено.
Ако имате хиляди такива файлове (например логове, манифести, конфигурации), този допълнителен разход се натрупва.
Вградени системи или контейнери може да срещнат затруднения със съхранението или мрежовата пропускливост.

Моето реение:
Компресор с минимален допълнителен разход, настроен за откриване на повторения в кратък текст.
Оптимизиране на размера на речника, обработката на блокове и метаданните.
Възможност за компресиране на множество малки файлове наведнъж.
Проектиран с малки буфери и линейни времеви ограничения.

istoriq na kompresirane

pri kompresiq - moq format

pri dekompresiq - mainstream formati

parola pri arhiv / razarhiv

drag and drop

thread pri compilirane





