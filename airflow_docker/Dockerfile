FROM apache/airflow:2.9.2

COPY requirements.txt ./
RUN pip install -r ./requirements.txt

ENV PIP_USER=false

# install dbt into a virtual environment
RUN python -m venv dbt_venv && source ./dbt_venv/bin/activate && \
    pip install --no-cache-dir dbt-postgres==1.8.2 dbt-core==1.8.3 && deactivate

ENV DBT_ROOT_PATH=/usr/local/airflow/dags/dbt
ENV DBT_DOCS_PATH=/usr/local/airflow/dbt-docs