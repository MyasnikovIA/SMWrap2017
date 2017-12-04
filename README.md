# SMWrap2017
<h4>Среда разработки приложений на Cache` Intersystems</h4>
<br>Для запуска необходимо установить классы из пакета SMWrap.xml 
<br> 1) Перед инсталяцией переключите базу данных "CACHELIB" в режим записи.
<br> http://localhost:57773/csp/sys/mgr/%25CSP.UI.Portal.Databases.zen  зайти в "CACHELIB" и убрать галочку "Переключитьтолько чтения"


SMWrap.xml

<pre>
   d RUN^%ZMRPMD("C:\BackUp\")  - запустить сервер  в режиме отладки
   d RUN^%ZMRPMD()              - запустить сервер
   d HALT^%ZMRPMD               - Остановить сервер
   d CONFIG^%ZMRPMD             - настроить сервер в Cache' терминале
</pre>
