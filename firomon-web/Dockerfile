FROM alpine:latest
RUN apk add uwsgi-python3 py3-pip python3

COPY firomon-web/ /firomon
COPY shared/ /shared

RUN python3 -m venv /venv
RUN /venv/bin/pip install -r /firomon/Requirements.txt

RUN addgroup -S firomon && adduser -S firomon -G firomon
USER firomon
WORKDIR /firomon
WORKDIR /firomon/display

CMD ["uwsgi", "--ini", "display.ini"]
