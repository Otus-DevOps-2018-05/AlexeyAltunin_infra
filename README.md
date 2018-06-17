# AlexeyAltunin_infra
AlexeyAltunin Infra repository

ДЗ-3:
bastion_IP = 35.187.82.86
someinternalhost_IP = 10.132.0.3

1.ssh -i ~/.ssh/gcloud_devops -J alexey@35.187.82.86 alexey@someinternalhost

2.

touch /.ssh/config
nano /.ssh/config
```
Host bastion 

    User alexey
    HostName 35.187.82.86

Host someinternalhost
    User alexey
    Hostname 10.132.0.3
    ProxyCommand ssh bastion nc %h %p
```

ssh someinternalhost