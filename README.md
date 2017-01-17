# sayme
#### sayme - программа предназначеная для озвучивания текущего времени и даты.
Работает на **Linux/OpenWRT/Paspberry Pi**

### Установка
#### Linux
Скопируйте  
1. Программу **sayme** в директорию "/usr/bin" или "/usr/local/bin"  
2. Директорию **sounds** по указонному пути - "/home/lib"  
Для проверки в терминале выполните команду: **"sayme --help"**  
Готово!

#### Зависимости
Приложение - **madplay**  

### Мультимедия
Все звуковые файлы находятся в директории "sounds", которая в свою очередь может располагаться где угодно,
главное не забыть указать полный путь к ней в переменной "path" в теле программы "sayme". 
Для удобства в директории "sounds" создана поддиректория "mp3_128" с файлами mp3 формата и битрейдом 128 kbit/s, 
если потребуется, то можно создать другие версии файлов с пониженым битрейдом для экономии дискового пространства 
в директории "mp3_96" или "mp3_64".

### Планировщик
#### Сообщать каждый час  
Рабочий пример для планировщика Cron предствален в одноименной директории.  
**ВАЖНО!** Замените **user** на имя текущего пользователя.

      0 * * * * user /usr/local/bin/sayme -s --hour > /dev/null

### Примечание
Все звуки повзаимствованы из **Asterisk**, что позволяет заменить их на другой язык (с небольшой доработкой программы)  

### Помощь
**sayme --help**  

    Использование: sayme [КОМАНДА]...

    Команды:

      Голосовые:
      --time            Время  - текущий час и минута (формат 24 ч.)
      --hour            Время  - только текущий час. (формат 24 ч.)
      --min             Время  - только текущие минута.
      --sec             Время  - только текущие секунда.
      --day             Дата   - число и месяц.
      --dow             Дата   - день недели.
      --date            Дата   - день недели, число и месяц.

      --all             Полные данные.
                        Время  - часы и минуты.
                        Дата   - день недели, число и месяц.

      Дополнительные:
      -b, --beep        Играет короткий сигнал.
      -s, --signal      Играет длинный сигнал оповещения.
      -g, --greet       В начале играет фраза "Текущее время".
      -q, --quiet       Только текст, без голосового оповещения.
                        Используется исключительно перед голосовыми.

      Информационные:
      -i, --info        Вывести расшифрованные данные по текущей дате.
      -d, --deps        Проверить зависимости, те приложения без которых данное не будет работать.

      -h, --help        Показать эту справку и выйти.
      -v, --version     Показать информацию о версии и выйти.


      Примеры:
      sayme --hour --min     Комбинированые команды.
      sayme -q --hour        Команда выводит данные о текущем часе только в консоль терминала.
      sayme -b --hour        Перед сообщением часа играет звуковой сигнал.
         
### Контакты
Email work.makhonin@gmail.com
