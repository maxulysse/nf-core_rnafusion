FROM nfcore/base:1.8

LABEL authors="maxime.garcia@scilifelab.se" \
    description="Docker image containing arriba for nfcore/rnafusion pipeline"

COPY environment.yml /
RUN conda env create -f /environment.yml && conda clean -a
ENV PATH /opt/conda/envs/rnafusion-arriba-dev/bin:$PATH
RUN conda env export --name rnafusion-arriba-dev > rnafusion-arriba-dev.yml