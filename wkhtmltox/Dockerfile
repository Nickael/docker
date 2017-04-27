FROM debian:jessie
MAINTAINER Nickaël RAKOTONINDRINA <rakoto_n@etna-alternance.net>

# installing dependencies

RUN apt-get update
RUN apt-get upgrade -y
RUN apt-get install -y \
  wget \
  tar \
  xz-utils

# downloading wkhtmltox from remote repos

RUN wget https://downloads.wkhtmltopdf.org/0.12/0.12.4/wkhtmltox-0.12.4_linux-generic-amd64.tar.xz
RUN tar -xvJf wkhtmltox-0.12.4_linux-generic-amd64.tar.xz
RUN mv -vf wkhtmltox /opt

# adding wkhtmltox to bin path

RUN ln -s /opt/wkhtmltox/bin/wkhtmltopdf /usr/bin/wkhtmltopdf
RUN ln -s /opt/wkhtmltox/bin/wkhtmltoimage /usr/bin/wkhtmltoimage

ENTRYPOINT ["wkhtmltopdf"]

CMD ["-h"]
