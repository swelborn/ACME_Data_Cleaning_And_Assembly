FROM python:3.11-slim

WORKDIR /usr/src/app

COPY ./docker/publisher/requirements.txt ./requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

COPY ./src/acme_data_cleaning /usr/src/app

ENV PYTHONPATH=/usr/src/app

# Run script when the container launches
CMD ["python", "./acme_data_cleaning/simulate_zmq_from_stxm_file.py"]
