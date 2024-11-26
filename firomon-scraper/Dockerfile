FROM python:3.11

WORKDIR /scraper

COPY firomon-scraper/Requirements.txt ./
#RUN pip install --no-cache-dir -r Requirements.txt
RUN python3 -m venv /venv
RUN /venv/bin/pip install --no-cache-dir -r Requirements.txt

COPY firomon-scraper/ /scraper
COPY shared/ /shared

CMD [ "/venv/bin/python", "main.py" ]
