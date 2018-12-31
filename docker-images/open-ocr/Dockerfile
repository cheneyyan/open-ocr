FROM ubuntu:14.04

RUN apt-get update

# Get git & gcc & golang & tesseract-ocr packages & language data.
RUN apt-get install -y \
git \
gcc \
golang-1.10 \
libleptonica-dev \
libtesseract3 \
libtesseract-dev \
tesseract-ocr \
tesseract-ocr-eng \
tesseract-ocr-chi-sim \
tesseract-ocr-chi-tra 

RUN ln -s /usr/lib/go-1.10/bin/go /usr/bin/go
#ln -s /usr/share/tesseract-ocr/tessdata /usr/local/share/tessdata

ENV GOPATH /opt/go

# go get open-ocr
# build open-ocr-httpd binary and copy it to /usr/bin
# build open-ocr-worker binary and copy it to /usr/bin
RUN mkdir -p $GOPATH && \
go get -u -v -t github.com/cheneyyan/open-ocr && \
cd $GOPATH/src/github.com/cheneyyan/open-ocr/cli-httpd && go build -v -o open-ocr-httpd && cp open-ocr-httpd /usr/bin && \
cd $GOPATH/src/github.com/cheneyyan/open-ocr/cli-worker && go build -v -o open-ocr-worker && cp open-ocr-worker /usr/bin
