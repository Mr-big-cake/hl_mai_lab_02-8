## МАИ(2 курс магистратуры) Архитектура Программных Систем
Разработать приложение на языке C++ осуществляющее хранение сущностей согласно вашего варианта задания. Для выявленных в предыдущем задании вызовов между сервисами создайте REST интерфейс.

Должны выполняться следующие условия:

*  Данные должны храниться в СУБД MariaDb;
*  Должны быть созданы таблицы для каждой сущности из вашего задания;
*  Интерфейс к сущностям должен предоставляться в соответствии со стилем REST;
*  API должен быть специфицирован в OpenAPI 3.0 (должен хранится в index.yaml);
*  Должен быть создан скрипт по созданию базы данных и таблиц, а также наполнению СУБД тестовыми значениями;
*  Для сущности, отвечающей за хранение данных о человеке (клиенте) должен быть реализован интерфейс поиска по маске фамилии и имени.

Приложение вместе с СУБД должно запускаться с помощью docker-compose.  Dockerfile должен собирать приложение, скачивая его из репозитория в github
Сервисы должны проверять login/password пользователя запросом аутентификаци к отдельному сервису отвечающему за работу с пользователем
 

Рекомендуемая последовательность выполнения работы:

1) Создайте схему БД
2) Создайте таблицы
3) Создайте скрипт для первичного наполнение БД  и выполните
4) Реализуйте REST-сервис на C++ с помощью POCO
5) Сделайте спецификацию с OpenAPI с помощью Postman и сохраните ее в index.yml
6) Протестируйте сервис
7) Опубликуйте на github проект
8) Создайте Dockerfile для каждого вашего сервиса
9) Протестируйте его работу в Docker

Необходимо модифицировать приложение, которое было создано в предыдущем задании. Для сущности, отвечающей за хранение клиента (пользователя) необходимо настроить sharding на основе первичного ключа. Все остальные сущности должны храниться в одном экземпляре базы данных.

Должны выполняться следующие условия:

-       Данные должны храниться в СУБД MariaDB;

-       Необходимо распределить данные между двумя серверами равномерно по ключевому;

-       Sharding должен быть настроен с помощью программного обеспечения ProxySQL;

-       Запрос на поиск клиента (пользователя) по маске имени и фамилии должен продолжать работать;

-       Программа при старте должна создавать нужные схемы и таблицы во всех инстансах СУБД;
