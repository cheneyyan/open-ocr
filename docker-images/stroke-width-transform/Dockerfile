FROM ubuntu:14.04

# get the software proprerties common gcc and git
RUN apt-get update && apt-get install -y \
git \
gcc

RUN apt-get install -y \
libopencv-core2.4 && \
libopencv-core-dev && \
libboost1.55-all-dev && \
libopencv-flann2.4 && \
libopencv-flann-dev && \
libopencv-imgproc2.4 && \
libopencv-imgproc-dev && \
libopencv-photo2.4 && \
libopencv-photo-dev && \
libopencv-video2.4 && \
libopencv-video-dev && \
libopencv-features2d2.4 && \
libopencv-features2d-dev && \
libopencv-objdetect2.4 && \
libopencv-objdetect-dev && \
libopencv-calib3d2.4 && \
libopencv-calib3d-dev && \
libopencv-ml2.4 && \
libopencv-ml-dev && \
libopencv-contrib2.4 && \
libopencv-contrib-dev && \
libopencv-highgui2.4 && \
libopencv-highgui-dev

RUN cd /opt && git clone https://github.com/tleyden/DetectText.git && \
cd /opt/DetectText && g++ -o DetectText TextDetection.cpp FeaturesMain.cpp -lopencv_core -lopencv_highgui -lopencv_imgproc -I/opt/DetectText && \
cd /opt/DetectText && cp DetectText /usr/local/bin