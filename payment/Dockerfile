FROM python:3.9
EXPOSE 8080
USER root
WORKDIR /opt/server
ENV AMQP_USER=roboshop
ENV AMQP_PASS=roboshop123
COPY *.py /opt/server
COPY requirements.txt /opt/server
COPY payment.ini /opt/server
RUN pip3.9 install -r requirements.txt
CMD ["uwsgi","-ini","payment.ini"]