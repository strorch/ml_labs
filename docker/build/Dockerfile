FROM continuumio/anaconda3:2024.06-1

WORKDIR /opt/notebooks

ADD hello_tf.yml /opt/notebooks

RUN /opt/conda/bin/conda env create -f /opt/notebooks/hello_tf.yml

RUN pip install tensorflow

RUN activate hello-tf

EXPOSE 8888

CMD ["/opt/conda/bin/jupyter", "notebook", "--notebook-dir=/opt/notebooks", "--ip='*'", "--port=8888", "--no-browser", "--allow-root"]