FROM continuumio/miniconda3:latest

RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get autoremove -y && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# install conda package
RUN conda update -y conda && \
    conda install -y -c conda-forge \
    jupyterlab \
    rdkit && \
    conda clean -i -t -y

WORKDIR /mnt/workspace

# default command
CMD ["jupyter", "lab", "--ip=0.0.0.0", "--allow-root", "--LabApp.token=''"]
