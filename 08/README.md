## Добавление фоновых изображений
Свойство background-image добавляет графический файл в качестве фона элемента.
Чтобы поместить его на заднем плане всей веб-страницы, можно создать
стиль для элемента body:
    ```
    body {
        background-image: url(images/bg.png);
    }
    ```
Свойство принимает единственное значение: ключевое слово url, за которым
следует путь к графическому файлу, заключенный в круглые скобки. 
Вы можете использовать абсолютный URL-адрес, например, так: 
```
url:(http://www.cosmofarmer.com/image/bg.gif)
```
или относительный путь от документа или корневого каталога сайта:
```
url(../images/bg.gif) /* относительный путь от документа */
```
**Относительный путь** представляет собой путь по отношению к текущему рабочему каталогу.
В данном случае он указывает адрес изображения от документа CSS, а не форматируемой
страницы index.html.
Ниже представлена примерная структура проекта:
```
project
│   index.html    
│
├── styles
│   │   style.css
│   │   reset.css
│ 
├── images
│   │   bg.png
│   │   img2.jpg
```
Предположим, у вас есть папка styles (содержащая таблицы стилей сайта)
и папка images (с изображениями сайта). Обе расположены в главном (корневом)
каталоге вместе с начальной (домашней) страницей сайта (index.html). 

Таким образом вы подключаете файл style.css и reset.css в файле index.html:
```
<link href="styles/style.css" rel="stylesheet">
<link href="styles/reset.css" rel="stylesheet">
```
Когда посетитель просматривает index.html, загружается внешняя таблица стилей.
Теперь допустим, что таблица включает стиль body с атрибутом фонового изображения,
в котором в качестве рисунка выбран файл bg.png из папки
images. Относительный путь по отношению к документу приведет от таблицы
стилей к рисунку. Это будет выглядеть следующим образом:
   ```
    body {
        background-image: url(../images/bg.png);
    }
   ```
Относительный путь от документа вычисляется применительно к файлу таблицы стилей,
но не к форматируемой веб-странице.
Этот путь интерпретируется так: символы ../ означают «подняться вверх на
один уровень», то есть к корневому каталогу, к папке, содержащей папку styles;
images/ означает «перейти к папке images», а bg.png определяет имя файла изображения.

**Запомнить**:
- file.php (файл лежит в той же папке)
- images/picture.jpg (файл лежит в капке images, которая находится в текущей)
- ../file.php (файл лежит в папке, которая расположена на один уровень выше от текущей)
- ../../file.php (файл лежит в папке, которая расположена на два уровня выше от текущей)


# Практикум: совершенствуем изображения
Фотогалерея — отличный пример привлекательной веб-страницы. Этот практикум
воедино собирает и наглядно демонстрирует различные способы форматирования
изображений. Файлы текущего практикума находятся в папке 08.
# Заключение изображения в рамку
Мы будем работать над веб-страницей вымышленного сайта CosmoFarmer.com.
У нас уже есть присоединенная внешняя таблица стилей, применяющая
форматирование к веб-странице и обеспечивающая ей простейший дизайн.
1. Откройте файл image.html из папки 08\01_image_ex в браузере.
Изображение занимает на странице слишком много места.
С помощью CSS-кода вы легко можете заключить рисунок в симпатичную рамку
и визуально выделить его из основного текстового контента.
2. Откройте файл styles.css из папки 01_image_ex в редакторе HTML-кода.
Он представляет собой внешнюю таблицу стилей, используемую файлом image.
html. Вы начнете с добавления класса в эту таблицу, а затем примените класс
к элементу img в HTML-файле.
3. Перейдите к концу файла и наберите следующее:
    ```
        img.figure {
        }
    ```
    Селектор img.figure воздействует на любой элемент img, к которому применен
    класс figure. Вы будете использовать его для выборочного форматирования
    некоторых изображений (вы могли бы назвать стиль .figure, но в таком случае
    он применялся бы к любому элементу с этим классом, а не только к изображениям).
4. Добавим в только что созданный стиль свойства float и margin:
    ```
    float: right;
    margin: 10px;
    ```
    Свойство float смещает изображение к правой стороне веб-страницы,
    приподнимая текст вверх и создавая обтекание фотографии с левой стороны. Поля
    обеспечивают небольшие свободные промежутки, отделяющие фото от текста.
    Теперь добавим границу и небольшие отступы, чтобы изображение больше
    походило на настоящий фотоснимок.
5. Добавим границу, цвет фона и отступы. Законченный вариант стиля должен
иметь следующий вид:
    ```
    img.figure {
        float: right;
        margin: 10px;
        border: 1px solid #666;
        background-color: #CCC;
        padding: 10px;
    }
    ```
    Если вы сохраните и просмотрите веб-страницу в браузере прямо сейчас, то не
    будет видно никаких изменений, поскольку класс не возымеет эффекта, пока
    его не применить к элементу.
6. Сохраните и закройте файл styles.css и откройте файл image.html. Найдите
элемент img и примените к нему класс class="figure" так, чтобы код имел следующий вид:
    ```
    <img src="../images/grass.jpg" alt="Трава" width="200" height="200"
    class="figure">
    ```
    Теперь изображение приобретет все свойства форматирования, определенные
    для класса .figure.
7. Просмотрите веб-страницу в браузере.
Изображение может заменить тысячу слов, но нередко требуется добавить к
изображению текстовую подпись с подробной информацией об объекте, месте
съемки и т. д. При этом вы наверняка захотите, чтобы комментарий был единым
целым с изображением, чтобы соседний текст обтекал надпись так же, как и само
изображение. Лучший способ — заключить изображение и текст в контейнер,
для которого будет определено единое форматирование. В таком случае фотография
и связанный с ней текст обрабатываются как цельный блочный элемент.
Если вы позже решите изменить их размещение на веб-странице и, возможно,
установить обтекание с выравниванием по левому краю страницы — никаких
проблем: вам потребуется изменить форматирование для всего элемента-контейнера.
В языке HTML5 именно для решения нашей задачи включены два новых элемента: 
figure предназначен для заключения в него изображения, из которого
хотят сделать иллюстрацию. В дополнение к нему может использоваться элемент
figcaption, который позволяет добавить подрисуночную подпись под изображением. 
Сначала нужно немного подправить HTML-код.
8. Вернитесь в редактор HTML-кода, к файлу image.html. Найдите в коде элемент
img и удалите значение class="figure", которое было добавлено при выполнении
шага 6. Добавьте перед элементом img тег `<figure>`.
Этим тегом будет помечено начало контейнера. Теперь будет добавлена подпись
и элемент figure будет закрыт, чтобы обозначить конец контейнера.
9. После элемента `<img>` добавьте строки, чтобы HTML-код приобрел такой вид:
    ```
    <figure>
        <img src="../images/grass.jpg" alt="Трава" width="200" height="200">
        <figcaption>Рисунок 1: Полевица побегообразующая лучше всего растет в открытом грунте.
        </figcaption>
    </figure>
    ```
10. Вернитесь к файлу styles.css. Прокрутите файл до стиля img.figure,
созданного ранее, и удалите этот стиль.
Для элемента figure будет добавлен новый стиль.
11. Добавите следующий стиль в файл styles.css:
    ```
    figure {
        float: right;
        width: 222px;
        margin: 15px 10px 5px 10px;
    }
    ```
    В предыдущем уроке свойство float: right уже использовалось. Свойство
    margin добавит вокруг всех четырех сторон элемента figure небольшое пустое
    пространство. Возникает вопрос: а для чего нужно свойство width? Хотя у 
    фотографии и есть установленная ширина (200 пикселов), ее нет у абзаца
    подписи. Если не указать ширину, абзац заставит элемент figure стать шире
    фотографии. В данном случае нужно, чтобы подпись была такой же по ширине,
    как фотография и ее рамка.
    Значение 222 пиксела получилось в результате небольших математических
    вычислений общей области, занимаемой фотографией на странице: хотя сама
    фотография занимает в ширину 200 пикселов, у нее появится (вы добавите на
    следующем шаге) по 10 пикселов отступов слева и справа. Кроме того, у
    изображения имеется рамка, занимающая слева и справа по 1 пикселу, что в целом
    и составляет ширину фотографии от одной границы к другой, то есть 222 
    пиксела.
12. Добавьте в файл styles.css следующий стиль:
    ```
    figure img {
        border: 1px solid #666;
        background-color: #CCC;
        padding: 10px;
    }
    ```
    Этот селектор потомков воздействует на любой элемент img, который находится внутри элемента figure. Поскольку здесь используется селектор потомков,
    класс к элементу img добавлять не нужно. Затем добавим стиль к подписи.
13. Добавьте в файл styles.css следующий стиль:
    ```
    figcaption {
        font: bold 1em/normal Verdana, Arial, Helvetica, sans-serif;
        color: #333;
        text-align: center;
    }
    ```
    Этот стиль использует некоторые свойства, позволяющие создать подрисуночную подпись,
    отформатированную полужирным шрифтом Verdana серого цвета с выключкой по центру.
    Сокращенный способ записи свойства font позволяет записать четыре различных свойства в одном
    объявлении (на одной строке).
    Чтобы подрисуночную подпись выделить еще больше, добавим цветной фон
    и границу.
14. Добавьте в стиль figcaption следующие три свойства:
    ```
    figcaption {
        font: bold 1em/normal Verdana, Arial, Helvetica, sans-serif;
        color: #333;
        text-align: center;
        background-image: linear-gradient(to bottom, #e6f3ff, white);
        border: 1px dashed #666;
        padding: 5px;
    }
    ```
    Чтобы создать цветную рамку вокруг заголовка, значения свойств background-image,
    border и padding должны быть сброшены. Мы используем линейный 
    градиент с помощью свойства background-image, 
    чтобы создать позади подписи градиент с переходом из светло-голубого в белый цвет.
15. Сохраните файлы image.html и styles.css, а затем просмотрите файл image.html
в браузере.
Теперь можно понять одну из причин, по которой разработку дизайна вести
проще с использованием внешней таблицы стилей — приходится работать только
с одним файлом, а не с двумя, и сохранять только его. 
# Практикум: создание фотогалереи
Раньше веб-дизайнеры создавали фотогалереи на основе HTML-элемента table,
помещая изображения в ячейки таблицы, образуемые строками и столбцами.
Но сейчас вы можете достигнуть того же эффекта с помощью лаконичного CSS-кода
в сочетании с применением гораздо менее объемного HTML-кода.
1. Откройте файл gallery.html из папки 08\02_gallery_ex.
Во-первых, взгляните на HTML-код, который использован для создания фотогалереи.
Веб-страница содержит шесть фотографий и подписей к ним. Каждая
фотография и подпись к ней хранятся в контейнере figure. Сама фотография
находится в элементе img, а подпись к ней — в элементе figcaption.
    ```
    <figure>
        <img src="../images/dandelion.jpg" alt="Dandelion" width="200" height="200">
        <figcaption>Рисунок 6: Фотопокрытия изображают природные склоны. </figcaption>
    </figure>
    ```
    Если вы просмотрите страницу сейчас, то увидите серию фотографий,
    размещенных друг над другом, что выглядит не очень привлекательно. Галерея
    будет выглядеть лучше, если фотографии будут находиться друг рядом с 
    другом, объединяясь в ряды. Вы можете сделать это с помощью всего нескольких
    стилей.
2. Откройте файл styles.css.
Таблица стилей уже содержит код сброса CSS и несколько стилей для заголовка и 
остального текста. Для начала вы добавите несколько стилей для фотографий и их заголовков.
3. Добавьте два новых стиля в верхней части файла styles.css:
    ```
    figure img {
        border: 1px solid #666;
        background-color: #FFF;
        padding: 4px;
    }
    figcaption {
        font: 1.1em Arial, Helvetica, sans-serif;
        text-align: center;
        margin: 10px 0 0 0;
    }
    ```
    Эти стили добавляют границы-рамки ко всем изображениям галереи и устанавливают шрифт, выравнивание и поля для подрисуночных подписей. В первом
    стиле для выбора только тех изображений, которые находятся внутри элементов
    figure, используется селектор потомков.
    Теперь поместим фотографии друг рядом с другом.
4. Добавьте в таблицу стилей такой код:
    ```
    figure {
        float: left;
        width: 210px;
        margin: 0 10px 10px 10px;
    }
    ```
    Он создает такое обтекание, при котором все пары «фотография/подпись» выравниваются по левому краю окна браузера. На самом же деле браузер размещает фотографии на одном уровне, рядом друг с другом, пока не закончится
    свободное место в строке. Затем браузер переносит следующие изображения на
    строку ниже, пока не отобразит все, и т. д. Общая ширина складывается из ширины самой фотографии плюс отступы и границы-рамки. В данном примере
    имеем: 200 пикселов на фотографию, 8 пикселов на левый и правый отступы
    и 2 пиксела на левую и правую границы.
5. Сохраните файл и просмотрите веб-страницу gallery.html в браузере.
Измените ширину окна браузера так, чтобы оно стало уже или шире, и
понаблюдайте, как перераспределяются изображения. Вы увидите, что не совсем все
правильно. Во второй строке изображений имеется два пустых места, где
должны располагаться фотографии. Эта проблема возникает по той причине, что
подпись ко второму изображению на первой строке больше по высоте, чем 
другие на этой же строке. Изображения, которые переносятся на эту подпись, не
могут разместиться рядом. Существует простое решение такой проблемы.
6. Вернитесь к файлу styles.css в редакторе HTML-кода. Найдите стиль figure.
Удалите свойство float:left и добавьте свойства display: inline-block; и vertical-align:
top. Код должен приобрести такой вид:
    ```
    figure {
        display: inline-block;
        vertical-align: top;
        width: 210px;
        margin: 0 10px 10px 10px;
    }
    ```
    Свойство display: inline-block рассматривает каждую пару «изображение/подпись» в качестве блока (у которого есть высота и ширина), но также
    и в качестве строчного элемента (то есть блоки могут выстраиваться в ряд).
    Кроме того, свойство vertical-align со значением top гарантирует выравнивание
    каждого элемента figure по верхнему краю других элементов figure, имеющихся в данном ряду.
7. Сохраните файл и воспользуйтесь предварительным просмотром веб-страницы
в браузере.
Если вы измените размеры окна браузера, то вид фотогалереи тоже изменится.
В более широкое окно может вместиться четыре или даже пять изображений, но,
если размер уменьшить, вы увидите, что на одной строке отображается всего один
или два рисунка.
# Добавление теней
Наша фотогалерея выглядит хорошо, но ее можно сделать еще выразительнее. 
Добавление эффектов тени к каждой фотографии придаст веб-странице иллюзию
глубины и обеспечит реалистичность трехмерного пространства. Однако прежде,
чем запускать графический редактор типа Photoshop, стоит узнать, что добавить
эффекты тени к любому изображению веб-страницы можно средствами CSS.
1. Откройте в редакторе HTML-кода файл styles.css, над которым вы работали
в предыдущей части практикума.
Изменение коснется созданного ранее стиля img.
2. Добавьте в конец стиля figure img свойство box-shadow: 2px 2px 4px rgba(0,0,0,.5);,
чтобы придать ему следующий вид:
    ```
    figure img {
        border: 1px solid #666;
        background-color: #FFF;
        padding: 4px;
        box-shadow: 2px 2px 4px rgba(0,0,0,.5);
    }
    ```
    Здесь добавляется тень, распространяющаяся на 2 пиксела вправо от изображения
    и на 2 пиксела ниже его, которая расширяется наружу на 4 пиксела. Использование
    цветовой модели RGBA, можно установить для тени черный цвет
    с 50%-ной прозрачностью.
3. Сохраните файл и просмотрите веб-страницу в браузере.
# Практикум: использование фоновых изображений
Свойство background-image — секретное оружие современного веб-дизайна. Оно превращает скучный текст в великолепный графический образ. Вы можете
использовать его для добавления фоновых изображений к любому HTML-элементу, и дизайн, который сумеете создать, ограничен только воображением. Пример
эффекта тени, приведенный в предыдущем практикуме, — всего лишь один из способов креативного использования фоновых изображений. 
Основное их применение — в качестве общего фона веб-страницы, а также для создания собственных
маркеров в списках. Эти наиболее распространенные способы применения свойства
background-image мы и рассмотрим в текущем практикуме.
# Добавление на веб-страницу фонового изображения
Что бы это ни было: сложный, замысловатый узор, логотип компании или
полноэкранная фотография, — изображения очень часто используются в качестве фоновых рисунков веб-страниц. Фактически это и есть основное применение свойства
background-image.
1. Откройте файл bg_images.html из папки 08\03_bg_ex в редакторе HTML-кода.
Веб-страница имеет двухколоночный дизайн: она очень проста, содержит лишь
немного отформатированного текста на белом фоне.
Для начала добавим линейный градиент. К странице привязана внешняя
таблица стилей с базовым форматированием. Вы используете ее, чтобы добавить
новый стиль.
2. Откройте файл styles.css. Введите следующий код в нижней части страницы:
    ```
    html {
        background-image: linear-gradient(to bottom, rgb(176,194,213), white 700px);
    }
    ```
    Этот код добавляет линейный градиент шириной 700 пикселов, начинающийся голубым цветом
    вверху и плавно переходящий в белый внизу.
3. Сохраните файл таблицы стилей и просмотрите страницу bg_images.html в браузере.
Произошло кое-что странное. Градиент переходит от голубого цвета к белому,
а затем повторяет переход снова. Это неожиданно. Чтобы избежать такого эффекта, необходимо сообщить браузеру, что HTML-элемент должен заполнить
окно браузера, присвоив параметру height значение 100%.
4. В файл styles.css добавьте еще одно свойство :
    ```
    html {
        height: 100%;
        background-image: linear-gradient(to bottom, rgb(176,194,213), white 700px);
    }
    ```
    Теперь, если вы сохраните файл таблицы каскадных стилей и просмотрите
    файл bg_images.html, градиент, расположенный в фоне, не повторится. Смотрится
    неплохо, но синий цвет есть и в фоне текста. Вы можете выделить текст,
    задав для него другой фоновый цвет.
5. Вернитесь к редактору HTML-кода и файлу style.css. Добавьте еще один стиль
для элемента div, в котором находится контент страницы:
    ```
    .wrapper {
        background-color: #FFF;
    }
    ```
    У этого элемента div есть фиксированная ширина, он центрирован на странице
    и содержит весь ее текст. Стиль задает тексту белый фоновый цвет, но с помощью
    изображения вы можете сделать его лучше.
6. Отредактируйте стиль, который вы создали в шаге 5, добавив фоновое изображение:
    ```
    .wrapper {
        background-color: #FFF;
        background-image: url(images/bg_main.jpg);
        background-position: left top;
        background-repeat: no-repeat;
    }
    ```
    Данные строки кода добавляют фоновое изображение в левом верхнем
    углу контейнера div; значение no-repeat свойства background-repeat означает, что
    изображение появляется только один раз. Если вы сохраните файл и просмотрите
    его в браузере, то увидите изображение руки, которая словно держит эту
    страницу. Очень здорово. Но единственная проблема заключается в том, что
    текст находится слишком высоко вверху и прикрывает рисунок. Далее вы
    разместите на странице большой заголовок и левую боковую панель.
7. Добавьте еще два стиля следующим образом:
    ```
    .banner {
        margin-top: 48px;
    }
    .announcement {
        margin-top: 115px;
    }
    ```
    Первая строка добавляет небольшие отступы, смещающие вниз баннер, содержащий заголовок, чтобы он соприкасался с белой страницей, а второй
    стиль смещает вниз левую боковую панель, чтобы освободить достаточно
    места для изображения с рукой. 
# Замена границ изображениями
Свойство border — полезный инструмент,
но ограниченность предлагаемых языком CSS стилей границ быстро надоедает.
Линия, нарисованная карандашом от руки, привлечет внимание посетителей сайта
гораздо больше, нежели прямая черная. Можете смело проигнорировать свойство
border и добавить на свой вкус любую линию в виде фонового рисунка, — это очень
просто. В этом практикуме мы заменим линии подчеркивания под элементами
заголовков h2 собственным рисунком, похожим на рукописную линию.

1. Вернитесь к файлу styles.css в редакторе HTML-кода. Добавьте стиль для 
элемента h2 внутри контейнера div с классом main:
    ```
    .main h2 {
        background-image: url(images/underline.png);
        background-repeat: no-repeat;
    }
    ```
    Свойство background-image назначает фоновое изображение заголовкам h2,
    находящимся внутри элемента с классом main; а значение no-repeat гарантирует, что
    изображение появится только один раз.
    Если сейчас вы просмотрите файл в браузере, то увидите, что рисунок подчеркивания
    расположен не там, где ему положено быть. Он находится над заголовками!
2. Добавьте в стиль .main h2 после свойства background-repeat строку со следующим
кодом:
    ```
    background-position: left bottom;
    ```
    Мы изменили начальную позицию фонового изображения. Теперь оно выводится, начиная от левого нижнего угла элемента h2. Однако при просмотре
    веб-страницы вы не заметите серьезных улучшений: подчеркивание сливается с текстом заголовка.
    Есть простое решение. Поскольку нижняя координата фонового рисунка расположена у основания блока, образуемого элементом h2, 
    необходимо всего лишь увеличить его общую высоту, чтобы сместить линию фонового рисунка немного вниз. 
    Для этого воспользуемся небольшим отступом снизу.
3. Отредактируйте стиль .main h2 последний раз, чтобы он выглядел таким образом:
    ```
    .main h2 {
        background-image: url(images/underline.png);
        background-repeat: no-repeat;
        background-position: left bottom;
        padding-bottom: 7px;
    }
    ```
    Как вы помните, отступ представляет собой промежуток между границей (или
    краем фона) и содержимым. Код также увеличивает суммарную высоту блока — в данном случае добавляется 7 пикселов нижнего отступа. Теперь граница
    изображения находится в нижней части блока h2, но в пустой области, созданной нижним отступом.
4. Сохраните файл и просмотрите страницу bg_images.html в браузере.
Теперь все элементы h2 подчеркнуты рукописной линией. Займемся блоком
боковой панели, сделаем его менее угловатым и плоским, а также улучшим вид
маркированных списков.
# Использование графики для маркированных списков
Стандартный маркер, используемый для списков, представляет собой черное пятнышко, что совсем не
впечатляет. Но вы можете создать интересные маркеры с помощью свойства background-image, заменив однообразные и скучные значки собственным
изображением. Первое, что необходимо сделать, — скрыть стандартные
маркеры, которые предваряют элементы-пункты списка.
1. Вернитесь к файлу styles.css в редакторе HTML-кода. Добавьте стиль для форматирования списка пунктов левой боковой панели.
    ```
    .announcement li {
        list-style: none;
    }
    ```
    Маркированный список находится внутри элемента div с классом announcement,
    так что этот селектор потомков воздействует только на пункты списка (элементы li) 
    внутри этого контейнера div. Стиль удаляет маркеры. Теперь добавим
    наш рисунок.
    >ПРИМЕЧАНИЕ
    Вы можете точно так же применить свойство list-style: none; к элементам ul или ol, чтобы удалить
    маркеры (или цифры) всех элементов-пунктов списка.
2. Добавьте в стиль .announcement li следующие два свойства:
    ```
    background-image: url(images/bullet.png);
    background-repeat: no-repeat;
    ```
    Мы встречались с ними раньше. Одно из них добавляет фоновое изображение,
    а другое отменяет его повтор, чтобы рисунок отображался однократно.
    При просмотре веб-страницы вы увидите, что маркеры накладываются на текст
    элементов списка и пункты списка отображаются очень тесно друг к другу. Небольшие отступы и поля исправят эту проблему.
3. Добавьте в стиль .announcement li еще два свойства:
    ```
    padding-left: 25px;
    margin-bottom: 10px;
    ```
    Левый отступ добавляет пустой промежуток, смещая текст в сторону, чтобы
    отобразить новый значок маркера. Нижнее поле обеспечивает рассредоточение
    элементов списка, образуя небольшие интервалы.
    Однако остался еще один недостаток. Изображение маркера чуть выступает над
    текстом строки, и значок выделяется над текстом пунктов списка. Это легко
    исправить с помощью свойства background-position.
4. Завершим этот стиль, добавив свойство background-position: 0px 4px;.
    Законченный код стиля должен выглядеть следующим образом:
    ```
    .announcement li {
        list-style: none;
        background-image: url(images/bullet.png);
        background-repeat: no-repeat;
        background-position: 0 4px;
        padding-left: 25px;
        margin-bottom: 10px;
    }
    ```
    Последнее изменение стиля позиционирует значок маркера в крайнюю левую
    позицию (это 0), отстоящую на 4 пиксела (4px) от верхнего края элемента-пункта 
    списка, что обеспечивает совсем незначительное смещение значка, тем не
    менее достаточное для того, чтобы маркер выглядел безупречно.
5. Сохраните файл и просмотрите веб-страницу в браузере.
Теперь пункты списка имеют трехмерные маркеры вместо скучных черных
кружков.
# Персонализация боковой панели
На данный момент боковая панель выглядит неплохо. Текст приятно отформатирован, 
маркеры отлично смотрятся, но сама боковая панель теряется на белом фоне.
Добавление фонового изображения позволит ее заметно выделить. Вы можете использовать 
отдельное изображение в виде свитка, в качестве фона элемента div. 
А чтобы убедиться, что весь текст попадает в изображение,
вам следует ограничить количество содержимого, которое вы размещаете на боковой панели. 
Если будет слишком много текста, он не поместится в пределах изображения, и, наоборот, 
если будет слишком мало текста, у вас окажется много пустого пространства.
Более гибкий подход позволяет изображению увеличиваться по мере того, как
на боковой панели увеличивается количество текста.
Хорошо, что эту маленькую хитрость не так сложно реализовать — 
вам понадобится три разных изображения и три разных стиля.
1. Вернитесь к редактору HTML-кода и файлу styles.css. Перейдите к стилю
.announcement (который вы создали в шаге 6 первого раздела этого практикума)
и добавьте одно свойство:
    ```
    .announcement {
        background: url(images/scroll_top.jpg) no-repeat center top,
        url(images/scroll_bottom.jpg) no-repeat center bottom,
        url(images/scroll_middle.jpg) repeat-y center top;
        margin-top: 115px;
    }
    ```
    Да, только одно свойство (background), но оно содержит три изображения. Очередность
    отображения картинок на странице зависит от того, как они перечислены в списке. 
    В данном случае первое изображение выводится в верхней части
    свитка по центру и не повторяется (благодаря параметру no-repeat). Второе
    изображение находится в нижней части свитка. Оно также повторяется один
    раз, но в конце элемента div. Наконец, средняя часть свитка (изображение
    scroll_middle.jpg) появится под двумя другими изображениями (поскольку
    является последним в списке) и будет повторяться по оси Y (по вертикали),
    поэтому, если элемент div поднимется выше, третье изображение заполнит
    освободившуюся область.
    Если вы просмотрите страницу, то заметите несколько проблем. Во-первых,
    текст отображается в верхней и нижней областях свитка, которые свернуты.
    Небольшой отступ исправит это.
2. Обновите стиль .announcement, добавив верхний и нижний отступы. Внесите
изменение:
    ```
    .announcement {
        background: url(images/scroll_top.jpg) no-repeat center top,
        url(images/scroll_bottom.jpg) no-repeat center bottom,
        url(images/scroll_middle.jpg) repeat-y center top;
        padding: 70px 0 60px 0;
        margin-top: 115px;
    }
    ```
    Еще одна проблема проявляется в том, что маркированный список выдается как
    с левой, так и с правой стороны изображения боковой панели. Сделаем так,
    чтобы он соответствовал этому изображению, добавив правое и левое поля.
3. Перейдите к стилю .announcement li, созданному ранее, и добавьте два свойства
в конце:
    ```
    .announcement li {
        list-style: none;
        background-image: url(images/bullet.png);
        background-repeat: no-repeat;
        background-position: 0 4px;
        padding-left: 25px;
        margin-bottom: 10px;
        margin-left: 30px;
        margin-right: 40px;
    }
    ```
    Эти свойства перемещают левый и правый края каждого пункта маркированного списка на достаточное расстояние, 
    чтобы очистить края фонового изображения.
4. Сохраните файл и просмотрите его в браузере.
С помощью нескольких изображений и языка CSS очень легко придать жизнь скучным
страницам.