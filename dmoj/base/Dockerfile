FROM python:3.11-slim-bullseye

RUN apt-get update && \
    apt-get install -y \
        git gcc g++ make curl gettext wget \
        libxml2-dev libxslt1-dev zlib1g-dev \
        mariadb-client libmariadb-dev \
        libjpeg-dev debconf-utils pkg-config && \
    curl -fsSL https://deb.nodesource.com/setup_20.x | bash - && \
    apt-get install -y nodejs && \
    apt-get autoremove -y && \
    rm -rf /var/lib/apt/lists/*

COPY repo/requirements.txt repo/additional_requirements.txt repo/package.json repo/package-lock.json ./
RUN npm install && \
    pip3 install -r requirements.txt -r additional_requirements.txt
