# Ansible playbooks для Homebot

Набор [Ansible](https://github.com/homebot) playbook для [Homebot](https://github.com/homebot)

## Примеры использования

### Установка ПО и настройка ОС (setup)

```sh
ansible-playbook -i test-hosts.yml test-playbook.yml -t setup -K
```

### Развертывание (deploy) 

```sh
ansible-playbook -i test-hosts.yml test-playbook.yml -t deploy
```
