FROM ubuntu:18.04

RUN opkg update
RUN opkg install -y git
RUN opkg install -y g++
RUN opkg install -y libssl-dev
RUN opkg install -y doxygen
RUN opkg install -y make
RUN opkg install -y cmake
RUN opkg clean
    
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
