# AlexeyAltunin_infra
AlexeyAltunin Infra repository

#### Данные для подключения
bastion_IP = 35.187.82.86
someinternalhost_IP = 10.132.0.3


#### 1.Cпособ подключения к someinternalhost в одну команду из вашего рабочего устройства
```
ssh -i ~/.ssh/gcloud_devops -J alexey@35.187.82.86 alexey@someinternalhost
```
#### 2.Доп. задание
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