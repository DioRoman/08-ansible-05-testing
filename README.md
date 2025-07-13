# 08-ansible-05-testing

Установка molecule

python3 -m venv venv

source venv/bin/activate

pip3 install ansible-dev-tools

pip3 install molecule-docker

pip3 install jinja2

Настройка molecule

cd /mnt/c/Users/rlyst/Netology/08-ansible-05-testing/clickhouse

cd /mnt/c/Users/rlyst/Netology/08-ansible-05-testing/lighthouse

cd /mnt/c/Users/rlyst/Netology/08-ansible-05-testing/vector

ansible-galaxy role init clickhouse

molecule init scenario -d docker

molecule test

molecule test --destroy=never - запуск полного сценария тестирования без разрушения инфраструктуры после прогона

molecule login

molecule verify

docker run --privileged=True -v /mnt/c/Users/rlyst/Netology/08-ansible-05-testing/vector:/opt/vector-role -w /opt/vector-role -it aragast/netology:latest /bin/bash

Tox

pip3 install tox

pip3 install molecule-podman

molecule drivers

molecule init scenario tox --driver-name podman

molecule matrix -s tox test