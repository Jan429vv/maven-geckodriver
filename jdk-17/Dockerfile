FROM maven:3.9.6-eclipse-temurin-17

# Firefox
ARG FIREFOX_VERSION=128.0
RUN apt-get update -qqy \
    && apt-get install -y --no-install-recommends libgtk-3-0 libx11-xcb1 libdbus-glib-1-2 libxt6 libasound2 bzip2 \
    && wget -q -O /tmp/firefox.tar.bz2 https://download-installer.cdn.mozilla.net/pub/firefox/releases/$FIREFOX_VERSION/linux-x86_64/en-US/firefox-$FIREFOX_VERSION.tar.bz2 \
    && tar xjf /tmp/firefox.tar.bz2 -C /opt \
    && rm /tmp/firefox.tar.bz2 \
    && mv /opt/firefox /opt/firefox-$FIREFOX_VERSION \
    && ln -s /opt/firefox-$FIREFOX_VERSION/firefox /usr/bin/firefox \
    && rm -rf /var/lib/apt/lists/*

# Geckodriver
ARG GECKODRIVER_VERSION=v0.34.0
RUN wget -q -O /tmp/geckodriver.tar.gz https://github.com/mozilla/geckodriver/releases/download/$GECKODRIVER_VERSION/geckodriver-$GECKODRIVER_VERSION-linux64.tar.gz \
    && tar xzf /tmp/geckodriver.tar.gz -C /opt \
    && rm /tmp/geckodriver.tar.gz \
    && mv /opt/geckodriver /opt/geckodriver-$GECKODRIVER_VERSION \
    && ln -s /opt/geckodriver-$GECKODRIVER_VERSION /usr/bin/geckodriver
