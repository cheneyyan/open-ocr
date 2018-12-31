FROM fsyanyong/stroke-width-transform

# since we are gonna install open-ocr, we need all the tesseract / leptonica deps
RUN apt-get install -y \
golang \
libleptonica-dev \
libtesseract3 \
libtesseract-dev \
tesseract-ocr-eng

ENV GOPATH /opt/go

# go get open-ocr
# build open-ocr-preprocessor binary and copy it to /usr/bin
RUN mkdir -p $GOPATH && \
go get -u -v github.com/cheneyyan/open-ocr && \
cd $GOPATH/src/github.com/cheneyyan/open-ocr/cli-preprocessor && go build -v -o open-ocr-preprocessor && cp open-ocr-preprocessor /usr/bin