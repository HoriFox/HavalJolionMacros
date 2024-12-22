# HavalJolionMacros
Макросы MacroDrouid на ГУ Haval Jolion для автоматизации работы

## Описание  
`change_drive_mode.macro` - по нажатию на модальную кнопку (поверх всех) сменяет режимы между "СТАНД" и "СНЕГ", работает по контенту кнопки  
`seat_settings.macro` - открывает меню настройки обогрева/охлаждения сидений, работает по координатам, будет полезно тем, у кого есть охлаждение водительского сидения т.к. кнопки в быстром меню нет

## Планируемые доработки  
* Сделать смену режима коробки от кнопки на руле, для этого нужен Android Debug Bridge и выдача прав на него, потом считывать нажатия из LogCat  
* Нужна кнопка, чтобы после открытия настроек сидений можно было вернуться туда, откуда я нажал эту кнопку  

## Первичная установка  
* Левый нижний угол - зажать, правый нижний угол - медленно нажимать 4-5 раз (задержка меньше секунды)  
* Переходим `Launch Debug App`, если нет раздела `Settings`, то открываем `GWMV2Terminal` и вписываем  
`am start --user 0 com.android.settings`
* Открываются настройки android. Вставляем флешку форматированную под FAT32 с приложением `filemanager`, открываем раздел `Хранилище`, выбираем Flash накопитель, устанавливаем `filemanager`. В дальнейшем для удобства установок. Сразу ставим `Back_button`, иногда пригождается для выхода из некоторых приложений и `macrodroid`. Версия 5.27.8 проверена и работает, последняя версия 5.49.x не устанавливается

## Разрешение на установку сторонних приложений  
* В настройках android в поиске ищем и открываем `Специальный доступ`
* В самом низу открываем `Установка неизвестных приложений`
* Внутри даём разрешение на установленном `filemanager`  

## Включить режим разработчика и вывести отладку по координатам нажатия  
* В настройках android в поиске ищём и открываем раздел сведений о телефоне
* В самом низу находим строку `Номер сборки` и многократно нажимаем на неё, появится уведомление, которое предупредит, что вот-вот включится режим разработчика, выполните необходимое кол-во кликов для достижения надписи `Режим разработчика включен`
* Выходим назад и переходим в раздел `Для разработчиков`
* Находим и включаем пункт `Визуальный отклик` - отображение координат, а также визуализация перемещение курсора по экрану
* Находим и включаем пункт `Отображать касания` - поможет в отладке макросов macrodroid, когда макрос будет отрабатывать - вы сможете наблюдать места касания  

## Наблюдения  
* Случайно в `GWMV2Terminal` ввёл блокирующую утилиту, которая выполняется до тех пор пока не сделаешь комбинацию `Ctrl+C`. Но нашёл, что можно закрыть текущий терминал (визуально на крестик), при этом вместо него открывается новый. Тот процесс, что был запущен под тем терминалом, полагаю, должен был завершиться.  
