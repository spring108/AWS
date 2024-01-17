## DevOps \ Домашнее задание №13 - AWS

Написать Ansible playbook, который разворачивает 2 ноды в AWS EC2: сборочную и продовую. На сборочной ноде происходит
сборка Java проекта, полученный артефакт передается на продовую ноду и на ней запускается.
Не в докере.


## облако AWS
  - #### Подготовка инфраструктуры:
    - создаём пользователя в IAM Dashboard: Access managemrnt \ Users \ Create user \ 
      - User name = <b>user15</b>, [next]
      - Permission options: "Attach policies directly" + "AdminisatratorAccess", [next]
      - [Create user]
      - кликаем на пользователе, выдаём ему "Security credentials"
      - Access keys \ Create access key: "Command Line Interface (CLI)", [next]
      - Set description tag - Пусто, [Create access key]
      - Видим "Retreive accass keys" - запоминаем:
        - <b>Access key</b> - аналог имя пользователя
        - <b>Secret access key</b> - аналог пароль
        - [Done]


## Сервер "manager" в облаке Yandex управляет серверами assembly и prod с помощью ansible
  - #### Подготовка инфраструктуры:
    - sudo apt update
    - sudo apt-get update
    - sudo apt-get install mc -y
    - sudo mc
    - apt install git -y
    - apt install ansible -y
    - apt install python3-pip -y
    - apt install boto3 -y
    - apt install awscli -y
    - cd /etc
    - sudo git clone https://github.com/spring108/AWS.git
    - cd /etc/AWS
    - cp /etc/AWS/hosts /etc/ansible/
    - создание сервера "assembly" в облаке AWS с помощью aws ec2
    - создание сервера "prod" в облаке AWS с помощью aws ec2

  - #### Запуск сборки и запуска сервиса:
    - ansible-playbook playbook_aws.yml



## Сервер "assembly" в облаке AWS
  - #### Подготовка инфраструктуры:
    - нет


## Сервер "prod" в облаке AWS
  - #### Подготовка инфраструктуры:
    - нет



## Смотрим http://prod_ip:8080/hello-1.0/
