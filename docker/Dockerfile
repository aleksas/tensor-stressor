FROM tensorflow/tensorflow:1.12.0-py3

# Install prerequisites
RUN apt-get clean && apt-get update && apt-get install -y locales git

# Set the locale
RUN locale-gen en_US.UTF-8
ENV LC_CTYPE en_US.UTF-8

# Update pip and install t2t
RUN pip install -U pip && pip install --no-cache-dir \
        tensor2tensor

WORKDIR "/root"

# Checkout repo
RUN git clone https://github.com/aleksas/tensor-stressor

WORKDIR "/root/tensor-stressor"

EXPOSE 6006
EXPOSE 8888

CMD ["/bin/bash"]