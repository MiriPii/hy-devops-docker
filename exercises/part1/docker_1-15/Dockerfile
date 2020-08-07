FROM python:3.8.5-slim
#RUN apt-get update -y && apt-get install -y --no-install-recommends git && \
#    apt-get clean && rm -rf /var/lib/apt/lists/*
#RUN git clone https://github.com/MiriPii/ihatemoney.git
RUN pip install --no-cache-dir gunicorn pymysql ihatemoney

#WORKDIR /ihatemoney

ENV NIGHTLY="" \
    DEBUG="False" \
    SQLALCHEMY_DATABASE_URI="sqlite:////database/ihatemoney.db" \
    SQLALCHEMY_TRACK_MODIFICATIONS="False" \
    SECRET_KEY="mynewsecret" \
    MAIL_DEFAULT_SENDER="('Budget manager', 'budget@wheremymoney.org')" \
    MAIL_SERVER="localhost" \
    MAIL_PORT=25 \
    MAIL_USE_TLS=False \
    MAIL_USE_SSL=False \
    MAIL_USERNAME= \
    MAIL_PASSWORD= \
    ACTIVATE_DEMO_PROJECT="False" \
    ADMIN_PASSWORD="" \
    ALLOW_PUBLIC_PROJECT_CREATION="True" \
    ACTIVATE_ADMIN_DASHBOARD="False"

VOLUME [ "/database" ]
EXPOSE 5000

RUN mkdir /etc/ihatemoney /var/lib/ihatemoney
RUN ihatemoney generate-config ihatemoney.cfg > /etc/ihatemoney/ihatemoney.cfg && \
    chmod 740 /etc/ihatemoney/ihatemoney.cfg

RUN useradd -ms /bin/bash ihatemoney && \
    chown ihatemoney /var/lib/ihatemoney && \
    chgrp ihatemoney /etc/ihatemoney/ihatemoney.cfg

RUN ihatemoney generate-config gunicorn.conf.py > /etc/ihatemoney/gunicorn.conf.py


#RUN python setup.py build && python setup.py install

CMD [ "/bin/bash" ]