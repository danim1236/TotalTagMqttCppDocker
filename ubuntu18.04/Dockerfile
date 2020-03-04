FROM ubuntu:18.04

RUN apt-get update
RUN apt-get install -y git
RUN apt-get install -y g++
RUN apt-get install -y libssl-dev
RUN apt-get install -y doxygen
RUN apt-get install -y make
RUN apt-get install -y cmake
RUN apt-get clean
    
RUN cd ~ && \
    git clone https://github.com/eclipse/paho.mqtt.c.git && \
    cd paho.mqtt.c && \
    make && \
    make html && \
    make install
    
RUN cd ~ && \
    git clone https://github.com/danim1236/TotalTagMqttCpp.git && \
    cd TotalTagMqttCpp && \
    git submodule update --init --recursive && \
    mkdir cmake-build && \
    cd cmake-build/ && \
    cmake .. && \
    cmake --build . && \
    cp ./TotalTagMqttCpp /usr/local/bin/
    
    
CMD ["/usr/local/bin/TotalTagMqttCpp"]
