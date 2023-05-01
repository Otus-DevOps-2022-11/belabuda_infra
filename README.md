# belabuda_infra
belabuda Infra repository


1. Способ подключения в одну команду с локального компьютера на удаленную машину без внешнего адреса через промежуточную машину с внешним адресом следующий:

ssh -i ~/.ssh/appuser -A -J appuser@62.84.125.92 appuser@10.128.0.19

2. Для подключения по алиасу с ssh клиента, необходимо внести изменения в конфиг ~/.ssh/config:

Host someinternalhost
    User appuser
    Hostname 10.128.0.19
    ProxyJump appuser@62.84.125.92
    IdentityFile ~/.ssh/appuser
    ForwardAgent yes

3. Данные для подключения:
bastion_IP = 62.84.125.92
someinternalhost_IP = 10.128.0.19
