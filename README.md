# SMWrap V3.4.20 (MAKOVA)  
<!--<h3>www.smwrap.ru</h3>-->
<h4>Среда разработки приложений на Cache` Intersystems(IRIS)</h4>

Edit Class in SMWrap studio: https://youtu.be/QykB_8L7DyQ
[![](http://img.youtube.com/vi/QrpkW_bTKHI/0.jpg)](https://youtu.be/QykB_8L7DyQ "")

<br> 1) Перед ручной инсталяцией классов (smwrap.xml) переключите базу данных "CACHELIB" в режим записи:
<br> http://localhost:57773/csp/sys/mgr/%25CSP.UI.Portal.Databases.zen  зайти в "CACHELIB" и убрать галочку "Переключитьтолько чтения"
 <img src="https://github.com/MyasnikovIA/SMWrap2017/blob/master/CacheLib(ReadOnly).png?raw=true"/>
 
<br> 
 <br> 2) В терминале написать команду   do $system.OBJ.Load("C:\Program Files (x86)\SMWrap\smwrap.xml","c")
 <h3> Скрипт для инсталляции:</h3>
 <pre>
      s OldNs=$zu(5)
      d $zu(5,"%SYS")
      set db=##class(SYS.Database).%OpenId("CACHELIB")
      set db.ReadOnly=0 
      w db.%Save()
      ; "C:\Program Files (x86)\SMWrap\smwrap.xml" - путь к файлу на сервере   
      do $system.OBJ.Load("C:\Program Files (x86)\SMWrap\smwrap.xml","c")  
      set db.ReadOnly=1
      w db.%Save()
      do $zu(5,OldNs)
      do RUN^%ZMRPMD()
 </pre>
<br> 
<br> 3) Запустить сервер из Cache' терминала
<pre>
   d RUN^%ZMRPMD()              - запустить сервер
   d HALT^%ZMRPMD               - Остановить сервер
   d CONFIG^%ZMRPMD             - настроить сервер в Cache' терминале
</pre>

<br> <h2>Создать класс для клиента Desktop</h2>
<br>
<br> 1) Запуск smwdev.exe
<br> 2) Файл->Новый-> Класс..
<br> 3) Указываем имя нового класса и выбираем шаблон "SMWrap форма(дизайнер)" 
<br> 4) В правой панели класса , с верху появится закладка "Designer"  вней присутствуют компоненты формы (работать как в Delphi)
<br> 5) F9 запуск формы на просмотр
<br>
<br> для запуска этого класса без MStudio из командной строки:
<h3>smwrt.exe -h127.0.0.1 -nUSER -t100 -fUser.HelloWorldFRM -p7200</h3>
<pre>
     -h127.0.0.1  - хост сервера "127.0.0.1"
     -p7200       - Порт сервера 7200
     -nUSER       - Область имен "USER"
     -fUser.HelloWorldFRM - класс который мы запускаем  "User.HelloWorldFRM" 
</pre>









