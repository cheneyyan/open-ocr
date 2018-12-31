FROM cheneyyan/stroke-width-transform

ENV GOPATH /opt/go && mkdir -p $GOPATH

# get the software proprerties common golang gcc and git
RUN apt-get update && apt-get install -y \
golang

# since we are gonna install open-ocr, we need all the tesseract / leptonica deps
RUN apt-get install -y \
libleptonica-dev \
libtesseract3 \
libtesseract-dev \
tesseract-ocr-eng

# go get open-ocr
# build open-ocr-preprocessor binary and copy it to /usr/bin
RUN go get -u -v github.com/cheneyyan/open-ocr && \
cd $GOPATH/src/github.com/cheneyyan/open-ocr/cli-preprocessor && go build -v -o open-ocr-preprocessor && cp open-ocr-preprocessor /usr/bin