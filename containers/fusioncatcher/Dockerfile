FROM nfcore/base:1.8

LABEL authors="maxime.garcia@scilifelab.se" \
    description="Docker image containing fusioncatcher for nfcore/rnafusion pipeline"

COPY environment.yml /
RUN conda env create -f /environment.yml && conda clean -a
ENV PATH /opt/conda/envs/rnafusion-fusioncatcher-dev/bin:$PATH
RUN conda env export --name rnafusion-fusioncatcher-dev > rnafusion-fusioncatcher-dev.yml
