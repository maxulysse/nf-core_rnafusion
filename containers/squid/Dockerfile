FROM nfcore/base:1.8

LABEL authors="maxime.garcia@scilifelab.se" \
    description="Docker image containing squid for nfcore/rnafusion pipeline"

COPY environment.yml /
RUN conda env create -f /environment.yml && conda clean -a
ENV PATH /opt/conda/envs/rnafusion-squid-dev/bin:$PATH
RUN conda env export --name rnafusion-squid-dev > rnafusion-squid-dev.yml

RUN wget https://raw.githubusercontent.com/Kingsford-Group/squid/master/utils/AnnotateSQUIDOutput.py -O /AnnotateSQUIDOutput.py \
    && chmod +x /AnnotateSQUIDOutput.py \
    && ln -s /AnnotateSQUIDOutput.py /usr/local/bin \
    && ln -s /opt/conda/envs/rnafusion-squid-dev/bin/python3 /bin/python 

RUN ln -s /lib/x86_64-linux-gnu/libcrypt.so.1 /lib/x86_64-linux-gnu/libcrypto.so.1.0.0
