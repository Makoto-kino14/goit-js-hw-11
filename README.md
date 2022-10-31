# Parcel template

Этот проект был создан при помощи Parcel. Для знакомства и настройки
дополнительных возможностей [обратись к документации](https://parceljs.org/).
жается иконкой возле его идентификатора.

Создан репозиторий goit-js-hw-11. При сдаче домашней работы есть две ссылки: на
исходные файлы и рабочую страницу на GitHub Pages. При посещении живой страницы
задания, в консоли нету ошибок и предупреждений. Проект собран с помощью
parcel-project-template. Для HTTP запросов использована библиотека axios.
Используется синтаксис async/await. Для уведомлений использована библиотека
notiflix. Код отформатирован Prettier.

Задание - поиск изображений Создай фронтенд часть приложения поиска и просмотра
изображений по ключевому слову. Добавь оформление элементов интерфейса. Посмотри
демо видео работы приложения.

Форма поиска Форма изначально есть в HTML документе. Пользователь будет вводить
строку для поиска в текстовое поле, а при сабмите формы необходимо выполнять
HTTP-запрос.

HTTP-запросы В качестве бэкенда используй публичный API сервиса Pixabay.
Зарегистрируйся, получи свой уникальный ключ доступа и ознакомься с
документацией.

Список параметров строки запроса которые тебе обязательно необходимо указать:

key - твой уникальный ключ доступа к API. q - термин для поиска. То, что будет
вводить пользователь. image_type - тип изображения. Мы хотим только фотографии,
поэтому задай значение photo. orientation - ориентация фотографии. Задай
значение horizontal. safesearch - фильтр по возрасту. Задай значение true.

В ответе будет массив изображений удовлетворивших критериям параметров запроса.
Каждое изображение описывается объектом, из которого тебе интересны только
следующие свойства:

webformatURL - ссылка на маленькое изображение для списка карточек.
largeImageURL - ссылка на большое изображение. tags - строка с описанием
изображения. Подойдет для атрибута alt. likes - количество лайков. views -
количество просмотров. comments - количество комментариев. downloads -
количество загрузок. Если бэкенд возвращает пустой массив, значит ничего
подходящего найдено небыло. В таком случае показывай уведомление с текстом
"Sorry, there are no images matching your search query. Please try again.". Для
уведомлений используй библиотеку notiflix.

Галерея и карточка изображения Элемент div.gallery изначально есть в HTML
документе, и в него необходимо рендерить разметку карточек изображений. При
поиске по новому ключевому слову необходимо полностью очищать содержимое
галереи, чтобы не смешивать результаты.

Пагинация Pixabay API поддерживает пагинацию и предоставляет параметры page и
per_page. Сделай так, чтобы в каждом ответе приходило 40 объектов (по умолчанию
20).

Изначально значение параметра page должно быть 1. При каждом последующем
запросе, его необходимо увеличить на 1. При поиске по новому ключевому слову
значение page надо вернуть в исходное, так как будет пагинация по новой
коллекции изображений. В HTML документе уже есть разметка кнопки при клике по
которой необходимо выполнять запрос за следующей группой изображений и добавлять
разметку к уже существующим элементам галереи.

Изначально кнопка должна быть скрыта. После первого запроса кнопка появляется в
интерфейсе под галереей. При повторном сабмите формы кнопка сначала прячется, а
после запроса опять отображается. В ответе бэкенд возвращает свойство
totalHits - общее количество изображений которые подошли под критерий поиска
(для бесплатного аккаунта). Если пользователь дошел до конца коллекции, пряч
кнопку и выводи уведомление с текстом "We're sorry, but you've reached the end
of search results.".

Уведомление После первого запроса при каждом новом поиске выводить уведомление в
котором будет написано сколько всего нашли изображений (свойство totalHits).
Текст уведомления "Hooray! We found totalHits images."

Библиотека SimpleLightbox Добавить отображение большой версии изображения с
библиотекой SimpleLightbox для полноценной галереи.

В разметке необходимо будет обернуть каждую карточку изображения в ссылку, как
указано в документации. У библиотеки есть метод refresh() который обязательно
нужно вызывать каждый раз после добавления новой группы карточек изображений.
Для того чтобы подключить CSS код библиотеки в проект, необходимо добавить еще
один импорт, кроме того который описан в документации.