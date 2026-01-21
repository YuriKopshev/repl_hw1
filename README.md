# Домашнее задание к занятию "`«Уязвимости и атаки на информационные системы»`" - `Копшев Юрий`


---

### Задание 1.

Ответьте на следующие вопросы:

Какие сетевые службы в ней разрешены?
Какие уязвимости были вами обнаружены? (список со ссылками: достаточно трёх уязвимостей)


Ответ:

Из скана nmap на 192.168.56.102 открыты 20+ портов:
	•	21/tcp: FTP vsftpd 2.3.4

	•	22/tcp: SSH OpenSSH 4.7p1

	•	23/tcp: Telnet Linux telnetd

	•	25/tcp: SMTP Postfix

	•	53/tcp: DNS ISC BIND 9.4.2

	•	80/tcp: HTTP Apache 2.2.8

	•	111/tcp: RPC rpcbind 2

	•	139/445/tcp: Samba smbd 3.X-4.X

	•	512/tcp: exec netkit-rsh

	•	1099/tcp: Java RMI GNU Classpath

	•	1524/tcp: bindshell (root shell!)

	•	2049/tcp: NFS

	•	2121/tcp: FTP ProFTPD 1.3.1

	•	3306/tcp: MySQL 5.0.51a

	•	3632/tcp: distccd v1

	•	5900/tcp: VNC

	•	6667/tcp: IRC UnrealIRCd

	•	8009/tcp: AJP Apache Jserv

	•	8180/tcp: HTTP Apache Tomcat

Обнаруженные уязвимости:

	1.	vsftpd 2.3.4 Backdoor (порт 21): https://www.exploit-db.com/exploits/17491
	2.	Samba Username Map Script (порты 139/445): https://www.exploit-db.com/exploits/16320
	3.	UnrealIRCd 3.2.8.1 Backdoor (порт 6667): https://www.exploit-db.com/exploits/13853


---

### Задание 2.

Проведите сканирование Metasploitable в режимах SYN, FIN, Xmas, UDP.

Запишите сеансы сканирования в Wireshark.

Ответьте на следующие вопросы:

Чем отличаются эти режимы сканирования с точки зрения сетевого трафика?
Как отвечает сервер?

Ответ:
Различия сканирования (SYN/FIN/Xmas/UDP)
SYN (-sS): TCP SYN флаги. Открыт: SYN+ACK, Закрыт: RST

FIN (-sF): TCP FIN. Открыт: нет ответа, Закрыт: RST

Xmas (-sX): FIN+PSH+URG (······U·P··F). Открыт: нет, Закрыт: RST

UDP (-sU): UDP пакеты. Открыт: UDP/nothing, Закрыт: ICMP unreachable

 Скриншоты из Kali linux по SYN и FIN(для примера):

![Скриншот1](https://github.com/YuriKopshev/repl_hw1/blob/main/img/photo_2026-01-21%2018.55.19.jpeg)

![Скриншот2](https://github.com/YuriKopshev/repl_hw1/blob/main/img/photo_2026-01-21%2018.55.23.jpeg)

![Скриншот3](https://github.com/YuriKopshev/repl_hw1/blob/main/img/photo_2026-01-21%2018.55.27.jpeg)

![Скриншот4](https://github.com/YuriKopshev/repl_hw1/blob/main/img/photo_2026-01-21%2018.55.30.jpeg)


---


