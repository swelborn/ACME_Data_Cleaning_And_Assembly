FROM python:3.11-slim

WORKDIR /usr/src/app

RUN apt-get update && apt-get install -y git

COPY ./docker/subscriber/requirements.txt ./requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

RUN git clone https://github.com/silvioachilles/cosmicstreams.git /cosmicstreams && \
    pip install -e /cosmicstreams

COPY ./src/acme_data_cleaning /usr/src/app/acme_data_cleaning

ENV PYTHONPATH=/usr/src/app

RUN mkdir /outputs

CMD ["python", "acme_data_cleaning/process_live_data.py"]
