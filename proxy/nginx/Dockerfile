FROM lsioarmhf/nginx-armhf

LABEL maintainer="Rafael Bubach"

# Update packages and install software
# RUN echo 'deb http://repo.ajenti.org/ng/debian main main ubuntu' >> /etc/apt/sources.list
# RUN wget http://repo.ajenti.org/debian/key -O- | apt-key add -
# RUN apt-get update
# RUN apt-get install ajenti -y
RUN apk install gcc python-devel python-pip libxslt-devel libxml2-devel libffi-devel openssl-devel libjpeg-turbo-devel libpng-devel dbus-python
RUN pip install 'setuptools>=0.6rc11' 'pip>=6' wheel
RUN pip install ajenti-panel ajenti.plugin.dashboard ajenti.plugin.settings ajenti.plugin.plugins
# RUN service ajenti restart

EXPOSE 80
EXPOSE 443
EXPOSE 8000