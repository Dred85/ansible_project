ТЗ_МТС:  
Задание 1.  
Разработать ansible playbook выполняющий следующий функционал:
1) Проверяет статус сервиса на хосте ( сервис на выбор, например Nginx)
2) Если сервис доступен, записать сообщение "{Время проверки}: OK" в логфайл ( Расположение файла на выбор)
3) Если сервис недоступен, записать сообщение "{Время проверки}: Сервис недоступен"
4) Запустить сервис
   4.1 Если сервис стал доступен, записать сообщение "{Время проверки}: Сервис успешно запущен" в логфайл
   4.2 Если сервис по-прежнему недоступен, отправить Email оповещение с текстом: "{Время проверки}: {Сервис} {Статус сервиса}" + записать сообщение в логфайл

Необходимо разработать ansible playbook выполняющий следующий функционал:
Выполняет архивацию логов на группе серверов, логи хранятся в директориях:
/opt/log/service_log/accounting, /opt/log/service_log/authoriz, /opt/log/service_log/authentic.
Имена файлов складываются из названия директории и даты, например: accounting_20220101.log
Логи за второе полугодие 2022 года архивировать не нужно, т.е. только по 30.06.2022.
Исходные файлы сразу после архивации необходимо удалить.
Необходимо учесть, что дата последнего изменения лог-файла может не соответствовать дате указанной в названии файла.



Для запуска playbook, можно использовать команды:   
- ansible-playbook -i inventory/hosts.ini playbooks/check_service.yml  
- ansible-playbook -i inventory/hosts.ini playbooks/archive_logs.yml  