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

