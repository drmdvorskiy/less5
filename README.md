# less5




Scheme:
![alt text](https://github.com/drmdvorskiy/less5/raw/main/scheme.png "Logo Title Text 1")

Схема стенда:

на фронтах поднят плавающий ип(192.168.4.4), запросы на него по 80 проксируются на бэки
(upstream), после бэки цепляются к базе


для проверки использовал:
curl -I -XGET 'http://192.168.4.4/index.php' (в консоли)
http://192.168.4.4/index.php (в браузере)

должно вернуть список баз на машине db


получается что схема работает с одним из двух фронтов + одним хотя бы беком из 3!!!
