FROM ubuntu:16.04

RUN apt-get update

RUN apt-get install -y build-essential
RUN apt-get install -y cmake git libgtk2.0-dev pkg-config libavcodec-dev libavformat-dev libswscale-dev
RUN apt-get install -y python-dev python-numpy libtbb2 libtbb-dev libjpeg-dev libpng-dev libtiff-dev libjasper-dev libdc1394-22-dev

RUN mkdir ~/opencv && cd ~/opencv && \
git clone https://github.com/Itseez/opencv.git && \
git clone https://github.com/Itseez/opencv_contrib.git && \
cd opencv && mv ../opencv_contrib ./ && \
mkdir build && cd build && \
cmake -D CMAKE_BUILD_TYPE=Release -D OPENCV_EXTRA_MODULES_PATH=../opencv_contrib/modules -D CMAKE_INSTALL_PREFIX=/usr/local .. && \
make -j5 && \
make install

RUN apt-get install -y tesseract-ocr libtesseract-dev libleptonica-dev
RUN pip install pytesseract xlsxwriter pdf2image
