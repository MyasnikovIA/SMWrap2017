# SMWrap2017 Makova
<h4>Среда разработки приложений на Cache` Intersystems</h4>
<br>Для запуска необходимо установить классы из пакета SMWrap.xml 
<br> 1) Перед инсталяцией переключите базу данных "CACHELIB" в режим записи:
<br> http://localhost:57773/csp/sys/mgr/%25CSP.UI.Portal.Databases.zen  зайти в "CACHELIB" и убрать галочку "Переключитьтолько чтения"
<br> 
<br> 2) В терминале написать команду   do $system.OBJ.Load("c:\XML\SMWrap.xml","c")
<br>  "c:\XML\SMWrap.xml" -  путь к файлу на сервере
<br> 
<br> 3) Запустить сервер из Cache' терминала
<pre>
   d RUN^%ZMRPMD("C:\BackUp\")  - запустить сервер  в режиме отладки
   d RUN^%ZMRPMD()              - запустить сервер
   d HALT^%ZMRPMD               - Остановить сервер
   d CONFIG^%ZMRPMD             - настроить сервер в Cache' терминале
</pre>

<br> 
<br> 3) Запустить MStudio.exe настроить соедиение 
<br>   по умолчанию порт соединения 7200
<br>   для изменения настроек в терминале запустите команду d CONFIG^%ZMRPMD 


<br> <h2>Создать класс для дэсктомного клиента</h2>

 
