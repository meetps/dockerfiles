FROM tensorflow/tensorflow:1.4.0-gpu-py3

MAINTAINER Meet P Shah <meetshah1995@gmail.com>

RUN rm -rf /var/lib/apt/lists/* \
    /etc/apt/sources.list.d/cuda.list \
    /etc/apt/sources.list.d/nvidia-ml.list

# python packages
RUN pip --no-cache-dir install --upgrade setuptools && \
    pip --no-cache-dir install --upgrade Cython opencv-python cffi easydict pyyaml

# config & cleanup
RUN ldconfig && \
    apt-get clean && \
    apt-get autoremove && \
    rm -rf /var/lib/apt/lists/* /tmp/* ~/*

# Expose ports 
# 6006 for tensorbard, 
# 443 for visdom
# 8888 for jupyter notebooks
EXPOSE 443 6006 8888

CMD ["/bin/bash"]