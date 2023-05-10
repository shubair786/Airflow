# Airflow
Airflow Creation Commands-----


docker run -it --rm -p 8888:8080 python:3.8-slim /bin/bash

export AIRFLOW_HOME=/opt/airflow

env | grep airflow


apt-get update -y && apt-get install -y wget libczmq-dev curl libssl-dev git inetutils-telnet bind9utils freetds-dev libkrb5-dev libsasl2-dev libffi-dev libpq-dev freetds-bin build-essential default-libmysqlclient-dev apt-utils rsync zip unzip gcc && apt-get clean
* Install all tools and dependencies that can be required by Airflow


useradd -ms /bin/bash -d ${AIRFLOW_HOME} airflow

pip install --upgrade pip

su - airflow

cd /opt/airflow

python -m venv .airflowvirtualenv



source .airflowvirtualenv/bin/activate




wget https://raw.githubusercontent.com/apache/airflow/constraints-2.0.2/constraints-3.8.txt



pip install "apache-airflow[crypto,celery,postgres,cncf.kubernetes,docker]"==2.0.2 --constraint ./constraints-3.8.txt


airflow db init


airflow scheduler &> /dev/null &


airflow users create -u admin -p admin -r Admin -e mail@gmail.com -f admin -l admin

airflow dags list

docker cp testdag.py 68a7aa0aaa19:/opt/airflow/.sandbox/lib/python3.8/site-packages/airflow/example_dags/testdag.py
