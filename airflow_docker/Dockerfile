FROM apache/airflow:2.3.2

COPY requirements.txt ./
RUN pip install -r ./requirements.txt

ENV PIP_USER=false

# install dbt into a virtual environment
RUN python -m venv dbt_venv && source ./dbt_venv/bin/activate && \
    pip install --no-cache-dir dbt-postgres==1.8.2 dbt-core==1.8.3 && deactivate