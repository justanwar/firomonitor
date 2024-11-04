FROM alpine:3.14
RUN apk add uwsgi-python3 py3-pip python3=~3.9
RUN addgroup -S firomon && adduser -S firomon -G firomon
USER firomon
COPY firomon-web/ /firomon
COPY shared/ /shared
WORKDIR /firomon
RUN pip install --user -r Requirements.txt
WORKDIR /firomon/display

CMD ["uwsgi", "--ini", "display.ini"]
