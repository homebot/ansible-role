# Ansible playbooks для Homebot

Набор [Ansible](https://github.com/homebot) playbook для [Homebot](https://github.com/homebot)

## Подготовка к использованию

* Установите [Ansible](https://docs.ansible.com/#project) ([инструкция](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)]
* Загрузите зависимые роли Ansible
```sh
ansible-galaxy install geerlingguy.nodejs
```
* Подготовьте файты `.inventory` и `.playbook`
* Запустите выполнение
```sh
ansible-playbook -i .inventory .playbook -K
```

## Примеры использования

### Установка ПО и настройка ОС (setup)

```sh
ansible-playbook -i test-hosts.yml test-playbook.yml -t setup -K
```

### Развертывание (deploy) 

```sh
ansible-playbook -i test-hosts.yml test-playbook.yml -t deploy
```

## Баг

Наблюдается некорректное выполнение задачи `Start PM2 apps` (файл `roles/homebot/tasks/deploy.yml`)

После выполнения задания следует проверить работу приложения `homebot-homebot`, которое должнобыло запуститься припомощи `PM2`. Для этого необходимо на целевой машине выполнить команду `pm2 status`.
В случае отрицательного результата проверки работы приложения необходимо запустить его командой `pm2 /var/www/homebot/pm2-apps.yml` и выполнить сохранение состояния `pm2` для последующего автозапуска командой `pm2 dump`.
