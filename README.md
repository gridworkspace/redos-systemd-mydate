# redos-systemd-mydate

Учебный проект: systemd-сервис и timer, которые пишут дату в лог каждую минуту.

## Что делает
- `mydate.sh` — скрипт, пишущий дату в `/var/log/mydate.log`
- `mydate.service` — systemd-юнит (Type=oneshot)
- `mydate.timer` — запускает сервис каждую минуту

## Установка
```bash
sudo cp mydate.sh /usr/local/bin/
sudo chmod +x /usr/local/bin/mydate.sh
sudo cp mydate.service /etc/systemd/system/
sudo cp mydate.timer /etc/systemd/system/
sudo systemctl daemon-reload
sudo systemctl enable --now mydate.timer
