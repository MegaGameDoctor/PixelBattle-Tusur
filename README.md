# PixelBattle (Tusur)
## Общие сведения
PixelBattle - это мобильное приложение, содержащее простую многопользовательскую игру. Суть игры заключается в закрашивании пикселей на полотне. Пользователь выбирает цвет, закрашивает пиксель и это изменение в тот же момент отображается у всех игроков. Цель игры заключается в отстаивании своего творения на полотне. Проект состоит из мобильного приложения на языке Java под платформу Android, серверной части на языке Java и WEB части, в которой будут задействованы языки PHP, HTML и CSS. В качестве базы данных будет использоваться MySQL сервер.
## Мобильное приложение
Мобильное приложение будет разработано под платформу Android на языке Java. Пользовательский интерфейс приложения будет состоять из одной игровой сцены. На ней изначально пользователю будет предложено авторизоваться, чтобы начать сохранять свою статистику. Для этого нужно будет просто ввести предпочитаемый игровой ник. На игровой сцене игрока встретит полотно определённого размера. Ниже полотна будет находиться список доступных цветов, а сверху - таймер до следующего закрашивания. Пользователь выбирает цвет, нажимает на пиксель и перекрашивает его - это изменение отображается на всех активных устройствах, которые подключены через приложение к этому серверу. Для организации соединения с сервером будет задействована библиотека Netty.
## Сервер
Сервер будет разработан на языке Java с использованием библиотеки Netty для организации соединения с устройствами пользователей. Сервер будет передавать приложению актуальные данные о полотне, рассылать пакеты при изменении пикселей для активных устройств и проводить регистрацию пользователей. Также сервер будет связан с базой данных, сохраняя в соответственных таблицах данные о полотне и историю закрашиваний, а также статистику всех игроков.
Репозиторий: https://github.com/MegaGameDoctor/TUSUR-PBServer
## Сайт
WEB часть проекта будет представлять собою небольшой сайт, на котором будет отображаться актуальное состояние полотна, таблица лидеров с возможностью просмотреть индивидуальный профиль, а также ссылки на скачивание мобильного приложения. Для получения всех перечисленных значений сайт будет обращаться к базе данных MySQL.
Репозиторий: https://github.com/MegaGameDoctor/TUSUR-PBWeb
## Telegram Бот
Для закрашивания пикселей и просмотра полотна с устройств, на которых не установлен Android, будет разработан Телеграмм бот на языке Python. Бот будет обращаться к WEB API и получать данные о текущем состоянии полотна и отправлять пользователю. Чтобы закрасить пиксель - пользователю нужно будет ввести /paint x y и выбрать цвет на появившихся кнопках - бот отправит запрос к WEB API и пиксель появится в базе данных.
