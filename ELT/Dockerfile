FROM python:3.8-slim

RUN apt-get update && apt-get install -y \
    wget \
    gnupg \
    lsb-release

# Add the PostgreSQL repository
RUN sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list'
RUN wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | apt-key add -

# Install PostgreSQL client tools for version 17
RUN apt-get update && apt-get install -y \
    postgresql-client-17

COPY elt_script.py .

CMD ["python","elt_script.py"]


