FROM ubuntu

ENV GOPATH /opt/go && mkdir -p $GOPATH

# get the software proprerties common golang gcc and git
RUN apt-get update && apt-get install -y \
git \
golang \
gcc

# We need to install the software properties common before doing add-apt-repository, otherwise it will give an error: add-apt-repository: not found
RUN apt-get install -y software-properties-common && \
add-apt-repository ppa:alex-p/tesseract-ocr && \
apt-get update

# Get tesseract-ocr packages && Get language data.
RUN apt-get install -y \
libleptonica-dev \
libtesseract4 \
libtesseract-dev \
tesseract-ocr \
tesseract-ocr-ara \
tesseract-ocr-bel \
tesseract-ocr-ben \
tesseract-ocr-bul \
tesseract-ocr-ces \
tesseract-ocr-dan \
tesseract-ocr-deu \
tesseract-ocr-ell \
tesseract-ocr-fin \
tesseract-ocr-fra \
tesseract-ocr-heb \
tesseract-ocr-hin \
tesseract-ocr-ind \
tesseract-ocr-isl \
tesseract-ocr-ita \
tesseract-ocr-jpn \
tesseract-ocr-kor \
tesseract-ocr-nld \
tesseract-ocr-nor \
tesseract-ocr-pol \
tesseract-ocr-por \
tesseract-ocr-ron \
tesseract-ocr-rus \
tesseract-ocr-spa \
tesseract-ocr-swe \
tesseract-ocr-tha \
tesseract-ocr-tur \
tesseract-ocr-ukr \
tesseract-ocr-vie \
tesseract-ocr-chi-sim \
tesseract-ocr-chi-tra \
tesseract-ocr-eng

# go get open-ocr
# build open-ocr-httpd binary and copy it to /usr/bin
# build open-ocr-worker binary and copy it to /usr/bin
RUN go get -u -v -t github.com/cheneyyan/open-ocr && \
cd $GOPATH/src/github.com/cheneyyan/open-ocr/cli-httpd && go build -v -o open-ocr-httpd && cp open-ocr-httpd /usr/bin && \
cd $GOPATH/src/github.com/cheneyyan/open-ocr/cli-worker && go build -v -o open-ocr-worker && cp open-ocr-worker /usr/bin