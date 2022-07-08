# Самоконтроль выполненения задания

1. Где расположен файл с `some_fact` из второго пункта задания?

```answer1
    Файл в котором определяется значение указанной переменной "для всех":
        group_vars/all/examp.yml
```

2. Какая команда нужна для запуска вашего `playbook` на окружении `test.yml`?

```bash
ansible-playbook -i ./inventory/test.yml site.yml
```

3. Какой командой можно зашифровать файл?

```answer3
    ansible-vault encrypt path/to/file.name
```

4. Какой командой можно расшифровать файл?

```answer4
    ansible-vault decrypt path/to/file.name
```

5. Можно ли посмотреть содержимое зашифрованного файла без команды расшифровки файла? Если можно, то как?

```answer5
    ansible-vault view path/to/file.name
```

6. Как выглядит команда запуска `playbook`, если переменные зашифрованы?

```answer6
        ansible-playbook -i ./inventory/prod.yml site.yml --ask-vault-password

    Также есть альтернативная возможность указать пукть к файлу с паролем 
    для работы в неинтерактивном режиме при помощи параметра:
    --vault-password-file VAULT_PASSWORD_FILES
```

7. Как называется модуль подключения к host на windows?

```answer7
    Исторически для этого предназначался connection:
    winrm                          Run tasks over Microsoft's WinRM                               

    Но теперь также доступен connection к Power Shell:
    psrp                           Run tasks over Microsoft PowerShell Remoting Protocol
```

8. Приведите полный текст команды для поиска информации в документации ansible для модуля подключений ssh

```answer8
    ansible-doc -t connection ssh

```

9. Какой параметр из модуля подключения `ssh` необходим для того, чтобы определить пользователя, под которым необходимо совершать подключение?

```answer9
    - remote_user
            User name with which to login to the remote server, normally set by the remote_user keyword.
            If no user is supplied, Ansible will let the SSH client binary choose the user as it normally.
            [Default: (null)]
            set_via:
              cli:
              - name: user
                option: --user
              env:
              - name: ANSIBLE_REMOTE_USER
              ini:
              - key: remote_user
                section: defaults
              keyword:
              - name: remote_user
              vars:
              - name: ansible_user
              - name: ansible_ssh_user
```


---
