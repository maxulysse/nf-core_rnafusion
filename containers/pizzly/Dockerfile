FROM nfcore/base:1.8

LABEL authors="maxime.garcia@scilifelab.se" \
    description="Docker image containing pizzly for nfcore/rnafusion pipeline"

COPY environment.yml /
RUN conda env create -f /environment.yml && conda clean -a
ENV PATH /opt/conda/envs/rnafusion-pizzly-dev/bin:$PATH
RUN conda env export --name rnafusion-pizzly-dev > rnafusion-pizzly-dev.yml