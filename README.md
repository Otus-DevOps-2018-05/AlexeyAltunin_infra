# AlexeyAltunin_infra
AlexeyAltunin Infra repository

# ДЗ_3

## Данные для подключения
```
bastion_IP = 35.187.82.86
someinternalhost_IP = 10.132.0.3
```
## Что было сделано
### 1.Cпособ подключения к someinternalhost в одну команду из вашего рабочего у стройства
```
ssh -i ~/.ssh/gcloud_devops -J alexey@35.187.82.86 alexey@someinternalhost
```
### 2.Доп. задание
```
touch /.ssh/config
nano /.ssh/config

Host bastion 

    User alexey
    HostName 35.187.82.86

Host someinternalhost
    User alexey
    Hostname 10.132.0.3
    ProxyCommand ssh bastion nc %h %p


ssh someinternalhost
```

# ДЗ_4
```
testapp_IP = 104.199.20.15
testapp_port = 9292


gcloud compute firewall-rules create "default-puma-server" --allow tcp:9292 --source-ranges=0.0.0.0/0 --target-tags=puma-server
```

# ДЗ_5
## Что было сделано
```
Обязательное ДЗ
Параметризовал ubuntu16.json и добавил доп опции
```

# ДЗ_6
## Что было сделано
```
Обязательное ДЗ
Настроил terraform конфиг для создания VM с запуском provisioners.
Настроил параметризацию
```

# ДЗ_7
## Что было сделано
```
Обязательное ДЗ
Разбиение на модули
Настроил параметризацию
Переиспользование модулей для Prod and Stage
Работа с реестром модулей
```

# ДЗ_8
## Что было сделано
```
Создана директория для работы с ansible
ansible.cfg для управления инстансами
создан playbook для для клонирования репозитория clone.yml

ansible app -m command -a 'rm -rf ~/reddit' удаляет директоию

ansible-playbook clone.yml снова клонирует репозиторий, тк он был удален
```

# ДЗ_9
## Что было сделано
```
Рассмотрены различные подходы от прямого к более гибкому
Один плейбук = один сценарий
Разбиение на сценарии в рамках одного плейбук
Разбиение на несколько плейбуков (избавляемся от тегов)
Замена sh криптов в packer provision на ansible playbook   
```

# ДЗ_10
## Что было сделано
```
роли для app and db
environments для prod and stage
рефакторинг плейбуков
открытие 80 порта в терраформ
роль jdauphant.nginx
созданы зашифрованные credentials с помощью ansible-vault
```

# ДЗ_11
## Что было сделано
```
изучение Vagrant
доработка ролей для Vagrant
тестирование ролей черел Molecule
```

