FROM python:3.9

# -- Install Pipenv stable
RUN pip install pipenv==v2018.10.9 --upgrade pip  
RUN pip install psycopg2

# Check system

# -- Install dependencies:
ADD ./Pipfile ./tmp/Pipfile
ADD ./Pipfile.lock ./tmp/Pipfile.lock
RUN cd /tmp &&  pipenv install --system --deploy 

# -- Update system
RUN apt-get update
RUN apt-get install binutils libproj-dev gdal-bin -y