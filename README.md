# opctoodbc
<h2>ODBC to OPC Server v0.1.44</h2>

<h3>Описание:</h3>
---------<br/>
OPC сервер получающий информацию из базы данных через ODBC. 
Сервер для облегчения процесса визуализации произовльных велични, законов распределения или любых других целей. <br/>
Смысл заключается в формализации доступа к данным в различных базах и представлении их в формате OPC. <br/>
Настройка тегов заключается в указании их имен и параметров чтения из базы в виде указания полей и условий, все остальное происходит автоматически.<br/>
Сервер написан на базе свободно распространяемой библиотеки <br/>
lightopc v0.88 (http://www.ipi.ac.ru/lab43/lopc-ru.html).<br/>
<br/>
<h3>Описание файла настроек:</h3>
-----------------
Файл настроек odbc.ini нужно переписать в директорию %SYSTEMROOT%\system32<br/>
<pre>
[database(N)] 	- база данных номер N, например [database1], [database1] итд
host=buf	- имя хоста, источника данных
login=root	- имя пользователя
pass=		- пароль

[database1 tag1]	- раздел описания тега, который нужно прочитать, база номер 1, тег номер 1
table=prdata		- таблица из которой берем данные в источнике
type=1			- тип значения, 1-число с плавающей точкой
name=Температура в подающем трубопроводе,C (T1)	- имя назначенного тега
field2=84606977		- указание полей, поле номер 2 должно иметь значение 84606977
field3=4		- поле номер(порядковый) 3, должно быть равно 4
field4=0		- поле номер(порядковый) 4, должно быть равно 0
field8=0		- поле номер(порядковый) 8, должно быть равно 0
status=7		- статус тега берем из поля номер 7
value=6                 - значение тега берем из поля номер 6
date=5			- дату для формирования поля архива берем из поля номер 5
rights=1		- права 1-чтение, 2-запись, 3-чтение/запись
key=type=0		- ключ, используется для оптимизации запроса и ускорения выборки
</pre>

<h2>Установка и настройка:</h2>
-------------------<br/>
Инсталлятора к этому простейшему серверу не прилагается. Подразумевается, что пользователь имеет
представление о работе компонентов системы и сможет осуществить нижеперечисленные операции (если, конечно, он обладает правами администратора).<br/>
После настройки, конфигурационный файл необходимо скопировать в директорию %SYSTEMROOT%/System32<br/>
Остальное содержимое архиво можно разархивировать в произвольную директорию.<br/>
После распаковки сервер необходимо зарегистрировать, запустив его с ключом /r.<br/>
Если сервер вам больше не нужен, то вы можете его разрегистрировать с ключом /u.<br/>
Например <br/>
opc11.exe /r  - регистрировать сервер<br/>
opc11.exe /u  - удалить регистрацию сервера <br/>
opc11.exe /?  - вывод справки <br/>

<h2>история:</h2>
--------<br/>
v0.1 build 1<br/>
релиз<br/>
