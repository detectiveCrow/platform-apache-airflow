## Installation
```
# Airflow needs a home. `~/airflow` is the default, but you can put it
# somewhere else if you prefer (optional)
export AIRFLOW_HOME=~/airflow

# Install Airflow using the constraints file
AIRFLOW_VERSION=2.2.3
PYTHON_VERSION="$(python3 --version | cut -d " " -f 2 | cut -d "." -f 1-2)"

# For example: 3.6
CONSTRAINT_URL="https://raw.githubusercontent.com/apache/airflow/constraints-${AIRFLOW_VERSION}/constraints-${PYTHON_VERSION}.txt"

# For example: https://raw.githubusercontent.com/apache/airflow/constraints-2.2.3/constraints-3.6.txt
pip3 install "apache-airflow==${AIRFLOW_VERSION}" --constraint "${CONSTRAINT_URL}"
```

---

## Run Server
```
# The Standalone command will initialise the database, make a user,
# and start all components for you.
airflow standalone
```

## Access

### check created credential
```
...
standalone | Airflow is ready
standalone | Login with username: admin  password: MfxTv4wvkfATsvWC
standalone | Airflow Standalone is for development purposes only. Do not use this in production!
...
```

### create a user (optional)
```
airflow users create --role Admin --username airflow --email airflow@example.com --firstname FIRST_NAME --lastname LAST_NAME --password password
```

### access with credential

Visit localhost:8080 in the browser and use the admin account details

## Create new DAGs

```
# change working directory to airflow home
cd ${AIRFLOW_HOME}

# create dags directory
mkdir dags

# define dags by using py file
```

## Automate all of above

```
# pwd > .../platform-apache-airflow/sample-local
bash bash.sh

# in other shell 
export AIRFLOW_HOME=~/airflow
cp -R ./dags ${AIRFLOW_HOME}
``` 