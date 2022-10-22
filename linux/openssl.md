# openssl
Утилита для коннектов по ssl
Простой вариант использования

```bash
openssl s_client -connect -host:port -key key.key -cert sert.crt
```
Можно не указывать cert но для этого надо, чтобы ключ был в соответствующей системной папке