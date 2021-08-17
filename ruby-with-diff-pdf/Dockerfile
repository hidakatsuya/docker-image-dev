FROM ruby:3.0.2

ENV DIFF_PDF_VERSION=0.5

WORKDIR /tmp

RUN apt-get update && \
    apt-get install --no-install-recommends -y build-essential xvfb libpoppler-glib-dev poppler-utils libwxgtk3.0-dev && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

RUN curl -L https://github.com/vslavik/diff-pdf/releases/download/v$DIFF_PDF_VERSION/diff-pdf-$DIFF_PDF_VERSION.tar.gz -o diff-pdf-$DIFF_PDF_VERSION.tar.gz && \
    tar zxf diff-pdf-$DIFF_PDF_VERSION.tar.gz && \
    cd diff-pdf-$DIFF_PDF_VERSION && \
    ./bootstrap && \
    ./configure && \
    make && \
    make install && \
    cd /tmp && rm -rf diff-pdf-$DIFF_PDF_VERSION.tar.gz diff-pdf-$DIFF_PDF_VERSION

RUN mkdir /src

WORKDIR /src
VOLUME /src
