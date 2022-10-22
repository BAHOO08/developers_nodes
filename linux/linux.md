# linux
-  [tcpdump](tcpdump.md) чтобы анализировать сеть
-  [openssl](openssl.md) чтобы анализировать сеть
## grep

```bash
grep "hello"  file.txt
grep -c "123" file.txt // количество
grep -r "hello"  /path // поиск в папке
grep -r -c "hello"  /path // сколько в каждом файле повторяется
```

Конект по ssh
Ключи хранятся
~/.ssh/id_rsa
~/.ssh/id_rsa.pub
На сервере авоторизированые ключи 
~/.ssh/authorized_keys

## curl

```bash
curl https://example.com -I
```

Подробная инфа в которой можно увидеть инфу о сертификате и когда он истекает
```bash
curl https://example.com -Iv
```
Определить срок годности сертификата
Обычный греп тут не отработает, чтобы он отработал надо перенаправить вывод
```bash
curl https://example.com -Iv --stderr - | grep "expire date"
```
или
```bash
curl https://example.com -Iv 2>&1 | grep "expire date"
```
Обрезать то что после двоеточия
```bash
curl https://example.com -Iv --stderr - | grep "expire date" | cut -d":" -f 2-
```