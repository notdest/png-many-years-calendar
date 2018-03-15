# calendar for a lifetime #

*Read this in other languages: English, [Русский](README.ru.md)*

<img src="https://raw.githubusercontent.com/notdest/png-many-years-calendar/master/img/foto.JPG" alt="example of calendar">

Print version and generating script. All images are in the format *\*.png*, size *A0 (1189x841mm)* and resolution *300dpi* (*14043x9933px*). You can print out it in printing company.

The calendar was created as an instrument for introspection. You may note dates of different events and periods in your life,and **estimate their parting in scale of your life**. By the way, the sum of this events and periods shape your personality. This is the way to understand who you are.

 Также можно объективней оценить отношение цена/выгода у планируемых действий, например готов ли ты подписать какой-нибудь длительный контракт. Ну и высший пилотаж - перевести в время стоимость крупных материальных планов, чтобы понимать: "ради этой машины я пожертвую вот этим вот годом" или "ради этой квартиры я потрачу вот эти 5 лет" и т.п.

Для примера на картинке снизу показан график вероятности доживания. По горизонтальной оси - возраст, по вертикальной - процент людей доживших до него.<br>
 <img src="img/chart.png" alt="график вероятности доживания">

Календари разделены по годам рождения, соответственно каждый начинается с указанного года и исходя из этого формируются заголовки вроде `1994г   15лет`. Есть следующие варианты:

* Календарь на 60 лет на **горизонтально** ориентированном листе. Наиболее применим, т. к. каждый год занимает наибольшую площадь, а ненаступившие годы нужны только для понимания масштаба.<a href="https://github.com/notdest/png-many-years-calendar-output/tree/master/result/rus/60" target="_blank">Папка с изображениями :open_file_folder:</a>

* Календарь на 80 лет на **вертикально** ориентированном листе. Каждый год занимает меньшую площадь, из-за поворота листа. <a href="https://github.com/notdest/png-many-years-calendar-output/tree/master/result/rus/80" target="_blank">Папка с изображениями :open_file_folder:</a>

* Календарь на 100 лет на **вертикально** ориентированном листе. Площадь каждого года такая же, как у предыдущего, но они расположены немного плотнее. <a href="https://github.com/notdest/png-many-years-calendar-output/tree/master/result/rus/100" target="_blank">Папка с изображениями :open_file_folder:</a>

Также есть *pdf-версия* на большом количестве листов А4([Скачать <img src="img/pdf-icon.png" alt="pdf"  height="25" />](https://github.com/notdest/png-many-years-calendar-output/raw/master/result/A4.pdf)).

По коду. Проект содержит единственный файл [generator.py](generator.py), который тянет за собой библиотеку PIL. В нем наиболее интересны для повторного использования функции `printMonth()` и `printYear()` в самом верху. Каждая из них требует наличия глобальной переменной `rus`, значение которой определяет язык заголовков(`True` - Русский, `False` - Английский), и переменной `draw`, которая получается следующим образом
```python
image       = Image.new("L", (imageWidth,imageHeight), 255)
draw        = ImageDraw.Draw(image)
```
Остальные переменные интуитивно понятны из названия. В случае если `yearOfBirth > year`, функция `printYear()` не печатает возраст в заголовке.