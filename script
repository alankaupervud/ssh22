#!/bin/bash

# Разрешаем соединения на порт 22 для SSH
iptables -A INPUT -p tcp --dport 22 -j ACCEPT

# Разрешаем установленные и связанные соединения
iptables -A INPUT -m conntrack --ctstate ESTABLISHED,RELATED -j ACCEPT

# Убеждаемся, что политика по умолчанию не блокирует трафик
iptables -P INPUT ACCEPT
iptables -P FORWARD ACCEPT
iptables -P OUTPUT ACCEPT

# Проверяем, что правила добавлены
echo "Правила iptables обновлены:"
iptables -L -n

echo "SSH на порту 22 разрешен."
