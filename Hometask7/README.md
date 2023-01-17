1. 

ssh-keygen -t rsa - створюємо унікальний ключ
/home/di/.ssh/id_rsa.pub - записуємо його

ssh-add /home/olka/.ssh/id_rsa - підключаємо ключ в id_rsa (папка де записаний ключ)

2.

ssh-copy-id -i /home/olka/.ssh/id_rsa.pub -p 4022 root@yoko.ukrtux.com - підключаємо пароль до своєї машинки. Кидаю машинці в японії свій ключ

ssh -D8080 -p4022 root@yoko.ukrtux.com - перенаправлення всіх команд з порта 8080 на порт 4022 (порт Японії)

Перевіряємо ip.

3.

Створили папку на локал хості
python3 -m http server 8888


4. 


ssh -R 14022:localhost:8888 -p 4022 root@yoko.ukrtux.com - підключаємо машину з Японії до моєї ( за допомогою 1 робимо реверснутий порт)

http://yoko.ukrtux.com:14022 - доступаємось до локалхоста через машинку в Японії