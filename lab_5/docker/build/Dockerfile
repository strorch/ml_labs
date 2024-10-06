FROM continuumio/anaconda3:2024.06-1

# Install system dependencies needed for Poetry and Python build tools
RUN apt-get update && apt-get install -y \
    curl \
    build-essential \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*


WORKDIR /opt/notebooks

ADD hello_tf.yml /opt/notebooks

RUN /opt/conda/bin/conda env create -f /opt/notebooks/hello_tf.yml

RUN pip install tensorflow

RUN activate hello-tf

EXPOSE 8888

CMD ["/opt/conda/bin/jupyter", "notebook", "--notebook-dir=/opt/notebooks", "--ip='*'", "--port=8888", "--no-browser", "--allow-root"]