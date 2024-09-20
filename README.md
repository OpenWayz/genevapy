
geneva.py
yum install -y python3 python3-devel gcc gcc-c++ git libnetfilter* libffi-devel

pip3 install --upgrade pip

pip3 install scapy netfilterqueue

sudo apt-get install build-essential python3-dev libnetfilter-queue-dev libffi-dev libssl-dev iptables python3-pip -y

pip3 install scapy netfilterqueue
# 运行程序
nohup ./python3 geneva.py -q 100 -w 4 &

iptables -I OUTPUT -p tcp -m multiport --sports 80,443 --tcp-flags SYN,RST,ACK,FIN,PSH SYN,ACK -j NFQUEUE --queue-num 100
# 免责声明
此软件是根据"[geneva 开源软件"](https://github.com/Kkevsterrr/geneva)提供的，无任何明示或暗示的担保，包括但不限于对适销性、特定目的的适用性和非侵权的担保。在任何情况下，开发者或版权所有者都不对任何索赔、损害或其他责任承担责任，无论在合同、侵权或其他行动中，出于使用该软件或其他交易与软件有关的行为而产生的。

