# SSH-Аuthentication
### Содержание:
  - [Генерация ключа](#keygen)
  - [Создание конфига](#config)
  - [Настройки конфига](#settings)
---

#### <a name='keygen'></a> Генерация ключа
Лучший алгоритм для генерации ключа (сложнее всего забрутфорсить):
```
ssh-keygen -t ed25519
```
Даем файлу нужное имя. Имя должно содержать путь.
Относительный путь строится от директории вызова функции.

Ключи должны оказаться здесь: `~/.ssh/key` and `~/.ssh/key.pub`

---

#### <a name='config'></a> Конфиг:

Создаем `~/.ssh/config`
```
#first account
Host github.com-first
    HostName github.com
    User git
    IdentityFile ~/.ssh/first

#second account
Host github.com-second
    HostName github.com
    User git
    IdentityFile ~/.ssh/second
``` 
<a name='settings'></a>
Важно дать корректное название хосту ведь когда мы добавляем
удаленный доступ к гит-репозиторию, мы выполняем:

```git clone git@github.com-first:user/repository.git```


