FROM nfcore/base:1.8

LABEL authors="maxime.garcia@scilifelab.se" \
    description="Docker image containing fusion-inspector for nfcore/rnafusion pipeline"

COPY environment.yml /
RUN conda env create -f /environment.yml && conda clean -a
ENV PATH /opt/conda/envs/rnafusion-fusion-inspector-dev/bin:$PATH
RUN conda env export --name rnafusion-fusion-inspector-dev > rnafusion-fusion-inspector-dev.yml

RUN ln -s /lib/x86_64-linux-gnu/libcrypt.so.1 /lib/x86_64-linux-gnu/libcrypto.so.1.0.0