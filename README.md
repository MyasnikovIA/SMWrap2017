# SMWrap2017 Makova  (SMWrap V4.0)
<br><h3>www.smwrap.ru</h3>
<h4>Среда разработки приложений на Cache` Intersystems</h4>
<br>Для запуска необходимо установить классы из пакета SMWrap.xml 
<br> 1) Перед инсталяцией переключите базу данных "CACHELIB" в режим записи:
<br> http://localhost:57773/csp/sys/mgr/%25CSP.UI.Portal.Databases.zen  зайти в "CACHELIB" и убрать галочку "Переключитьтолько чтения"
 <img src="https://github.com/MyasnikovIA/SMWrap2017/blob/master/CacheLib(ReadOnly).png?raw=true"/>
 
<br> 
 <br> 2) В терминале написать команду   do $system.OBJ.Load("c:\XML\SMWrap.xml","c")
 <h3> Скрипт для инсталляции:</h3>
 <pre>
      s OldNs=$zu(5)
      d $zu(5,"%SYS")
      set db=##class(SYS.Database).%OpenId("CACHELIB")
      set db.ReadOnly=0 
      w db.%Save()
      do $system.OBJ.Load("c:\XML\SMWrap.xml","c")    ; "c:\XML\SMWrap.xml" - путь к файлу на сервере   
      set db.ReadOnly=1
      w db.%Save()
      do $zu(5,OldNs)
      do RUN^%ZMRPMD()
 </pre>
 

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


<br> <h2>Создать класс для клиента Desktop</h2>
<br>
<br> 1) Запуск MStudio.exe
<br> 2) Файл->Новый-> Класс..
<br> 3) Указываем имя нового класса и выбираем шаблон "SMWrap форма(дизайнер)" 
<br> 4) В правой панели класса , с верху появится закладка "Designer"  вней присутствуют компоненты формы (работать как в Delphi)
<br> 5) F9 запуск формы на просмотр
<br>
<br> для запуска этого класса без MStudio из командной строки:
<h3>MPlayer.exe -h127.0.0.1 -nUSER -t100 -fUser.HelloWorldFRM -p7200</h3>
<pre>
     -h127.0.0.1  - хост сервера "127.0.0.1"
     -p7200       - Порт сервера 7200
     -nUSER       - Область имен "USER"
     -fUser.HelloWorldFRM - класс который мы запускаем  "User.HelloWorldFRM" 
</pre>





