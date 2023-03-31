    FROM continuumio/miniconda3:master
    
    # copy is workdir:
    WORKDIR /app
    COPY . .

    # make the script and copy in workdir:
    RUN  echo 'echo Hellow Netology' > ./1.sh
    RUN chmod u+x ./1.sh

    # install addiction
    # UN conda install -y mlflow boto3 pymysql  - не хотел выполнять установку с ошибкой: executor failed running [/bin/sh -c conda install -y mlflow boto3 pymysql]: exit code: 1
    RUN apt-get update -y \
        && apt-get install -y python pip \
        && pip install --upgrade pip \
        && pip install mlflow boto3 pymysql
    
    # at runing:
    CMD ["bash",  "1.sh"]




