FROM nfcore/base:1.8

LABEL authors="maxime.garcia@scilifelab.se" \
    description="Docker image containing star-fusion for nfcore/rnafusion pipeline"

COPY environment.yml /
RUN conda env create -f /environment.yml && conda clean -a
ENV PATH /opt/conda/envs/rnafusion-star-fusion-dev/bin:$PATH
RUN conda env export --name rnafusion-star-fusion-dev > rnafusion-star-fusion-dev.yml

# ctat-genome-lib-builder
RUN cd /opt/conda/envs/rnafusion-star-fusion-dev/ && \
    wget https://github.com/NCIP/ctat-genome-lib-builder/archive/2830cd708c5bb9353878ca98069427e83acdd625.zip && \
    unzip 2830cd708c5bb9353878ca98069427e83acdd625.zip && \
    cd ctat-genome-lib-builder-2830cd708c5bb9353878ca98069427e83acdd625 && \
    rm /opt/conda/envs/rnafusion-star-fusion-dev/bin/prep_genome_lib.pl

ENV PATH /opt/conda/envs/rnafusion-star-fusion-dev/ctat-genome-lib-builder-2830cd708c5bb9353878ca98069427e83acdd625/:$PATH

RUN ln -s /opt/conda/envs/rnafusion-star-fusion-dev/lib/libssl.so /opt/conda/envs/rnafusion-star-fusion-dev/lib/libssl.so.1.0.0 && \
    ln -s /opt/conda/envs/rnafusion-star-fusion-dev/lib/libcrypto.so /opt/conda/envs/rnafusion-star-fusion-dev/lib/libcrypto.so.1.0.0
