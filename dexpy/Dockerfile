FROM python:2-slim

RUN apt update -y && apt upgrade -y
RUN apt install -y udev ntp

WORKDIR /usr/src/app

COPY . . 
RUN mkdir -p /etc/udev/rules.d
RUN cp /usr/src/app/80-dexcom.rules /etc/udev/rules.d/
#RUN udevadm control -R
#RUN udevadm trigger

RUN pip install --no-cache-dir -r requirements.txt

CMD [ "bash", "./entrypoint.sh" ]
