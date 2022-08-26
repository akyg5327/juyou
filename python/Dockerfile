FROM python:3.6

#エディタとDBのインストール（よくない気がする）
#RUN apt-get update -y && apt-get install -y sqlite3 vim 


RUN mkdir /code
WORKDIR /code
COPY requirements.txt /code/

# opencv-devのインストール
RUN apt-get update -y && apt-get install -y libopencv-dev \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# TensorflowとOpencvのインストール
RUN pip install --upgrade pip
RUN pip install -r requirements.txt

ENV APP_NAME tensor-docker
WORKDIR /home/$APP_NAME

CMD [ '/bin/bash'  ]
