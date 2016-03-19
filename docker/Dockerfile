FROM jupyter/datascience-notebook

MAINTAINER Martin Ames Harrison <martinmartinharrisonharrison@gmail.com>

USER root

RUN apt-get update && apt-get upgrade -y

RUN apt-get -y install python-pip libpq-dev python-dev

#python development tools & other personal
RUN ["/bin/bash", "-c", "source activate python2 && \
pip install pep8 &&\
source deactivate"]
RUN ["/bin/bash", "-c", "source activate python2 && \
pip install pip-tools &&\
source deactivate"]
RUN ["/bin/bash", "-c", "source activate python2 && \
pip install pyyaml &&\
source deactivate"]
RUN ["/bin/bash", "-c", "source activate python2 && \
pip install tabulate && \
source deactivate"]
RUN ["/bin/bash", "-c", "source activate python2 && \
pip install --upgrade --no-cache-dir https://get.dato.com/GraphLab-Create/1.7.1/richiezitomer@gmail.com/A143-EC30-47C6-CE26-CFE4-38ED-1DFC-169F/GraphLab-Create-License.tar.gz && \
source deactivate"]
RUN apt-get -y install openconnect

#aws
RUN ["/bin/bash", "-c", "source activate python2 && \
pip install boto && \
source deactivate"]
RUN ["/bin/bash", "-c", "source activate python2 && \
pip install boto3 &&\
source deactivate"]
RUN ["/bin/bash", "-c", "source activate python2 && \
pip install s4cmd && \
source deactivate"]

#ftp
RUN ["/bin/bash", "-c", "source activate python2 && \
pip install pysftp && \
source deactivate"]


#mysql connectors and high-level tools
RUN ["/bin/bash", "-c", "source activate python2 && \
pip install PyMySQL && \
source deactivate"]
RUN ["/bin/bash", "-c", "source activate python2 && \
pip install -Iv http://cdn.mysql.com/Downloads/Connector-Python/mysql-connector-python-1.2.3.zip#md5=6d42998cfec6e85b902d4ffa5a35ce86 && \
source deactivate"]
RUN ["/bin/bash", "-c", "source activate python2 && \
pip install dataset &&\
source deactivate"]
RUN ["/bin/bash", "-c", "source activate python2 && \
apt-get -y install libmysqlclient-dev && \
pip install MySQL-python && \
source deactivate"]
RUN ["/bin/bash", "-c", "source activate python2 && \
pip install format-sql && \
source deactivate"]
RUN ["/bin/bash", "-c", "source activate python2 && \
pip install db.py && \
source deactivate"]
RUN ["/bin/bash", "-c", "source activate python2 && \
pip install -U sqlalchemy && \
source deactivate"]
RUN ["/bin/bash", "-c", "source activate python2 && \
pip install psycopg2 && \
source deactivate"]
RUN ["/bin/bash", "-c", "source activate python2 && \
git clone https://github.com/coleifer/peewee.git -b master"]
WORKDIR peewee
RUN ["/bin/bash", "-c", "source activate python2 && \
python setup.py install"]
WORKDIR /home/jovyan/work
RUN rm -r peewee

#since 2/14
RUN ["/bin/bash", "-c", "source activate python2 && \
wget http://prdownloads.sourceforge.net/ta-lib/ta-lib-0.4.0-src.tar.gz && \
tar -xzf ta-lib-0.4.0-src.tar.gz && \
cd ta-lib && \
./configure --prefix=/usr && \
make && \
sudo make install && \
pip install ta-lib && \
cd .. && \
rm -rf ta-lib/ ta-lib-0.4.0-src.tar.gz && \
source deactivate"]

#lexical analysis dependencies
RUN ["/bin/bash", "-c", "source activate python2 && \
pip install nltk && \
source deactivate"]
RUN ["/bin/bash", "-c", "source activate python2 && \
python -m nltk.downloader averaged_perceptron_tagger && \
source deactivate"]

#snowflake connector
RUN ["/bin/bash", "-c", "source activate python2 && \
apt-get install -y libffi-dev && \
pip install snowflake-connector-python && \
pip uninstall -y cryptography && \
pip install cryptography && \
source deactivate"]
