# Домашняя работа "Развертывание веб приложения"

<details>
<summary>Введение</summary>

За последние десятилетия, средняя скорость разработки увеличивается с большой прогрессией от года к году, потому что IT продукты приносят огромные деньги бизнесу практически в любой сфере. Высокая интенсивность породила большое количество методологий, ускоряющих разработку. Также выросли требования к инфраструктуре. Появилась необходимость динамически обновлять, откатывать, масштабировать и резервировать нашу инфраструктуру. В нынешних реалиях, одной из ключевых методологий в построении информационных систем, является - Infrastructure as Code ( Инфраструктура как код, IaC ). Она подразумевает подход для управления и описания инфраструктуры ЦОД через конфигурационные файлы, а не через ручное редактирование конфигураций на серверах или интерактивное взаимодействие. Этот подход может включать в себя как
декларативный способ описания инфраструктуры, так и через скрипты.  
IaC несёт в себе следующие плюсы:  
Скорость и уменьшение затрат  
Масштабируемость и стандартизация  
Безопасность и документация  
Восстановление в аварийных ситуациях  
P.S. Подробнее про IaC, вы можете почитать в статье - https://habr.com/ru/company/otus/blog/574278/  
В данной работе, мы применим знания полученные в прошлых уроках и опишем базовую инфраструктуру с помощью конфигураций и манифестов  
</details>

<details>
<summary>Цель</summary>

Получить практические навыки в настройке инфраструктуры с помощью манифестов и конфигураций. Отточить навыки использования ansible/vagrant/docker.   
</details>

<details>
<summary>Описание</summary>

Варианты стенда:  
nginx + php-fpm (laravel/wordpress) + python (flask/django) + js(react/angular);  
nginx + java (tomcat/jetty/netty) + go + ruby;  
можно свои комбинации.  
Реализации на выбор:  
на хостовой системе через конфиги в /etc;  
деплой через docker-compose.  
Для усложнения можно попросить проекты у коллег с курсов по разработке  
К сдаче принимается:  
vagrant стэнд с проброшенными на локалхост портами  
каждый порт на свой сайт  
через нжинкс Формат сдачи ДЗ - vagrant + ansible  

</details>

#### Практика

[test.sh](test.sh) разворачивает виртуальную машину и запускает плейбук ансибл

Столкнулся с проблемой при разворачивании задач ансибл

![tun](https://i.ibb.co/X2FMgC4/111.png)


Проблема с версией питона
+ Решение: В inventory добавил использование ansible_python_interpreter=/usr/bin/python3
Проскочил

![tun](https://i.ibb.co/zF3XK7N/1.png)


Все равно дурил phyton

Решил обновить версию ansible
```
sudo python3 -m pip install -U pip
sudo python3 -m pip install -U setuptools
sudo -H pip install --upgrade ansible
```

[Успех](ansible.log)

![tun](https://i.ibb.co/ByWzSLD/222.png)


Вывод: следить за версиями ansible и других модулей:)







