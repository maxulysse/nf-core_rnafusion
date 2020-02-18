FROM nfcore/base:1.8

LABEL authors="maxime.garcia@scilifelab.se" \
    description="Docker image containing ericscript for nfcore/rnafusion pipeline"

COPY environment.yml /
RUN conda env create -f /environment.yml && conda clean -a
ENV PATH /opt/conda/envs/rnafusion-ericscript-dev/bin:$PATH
RUN conda env export --name rnafusion-ericscript-dev > rnafusion-ericscript-dev.yml

RUN ln -s /lib/x86_64-linux-gnu/libreadline.so.7.0 /lib/x86_64-linux-gnu/libreadline.so.6
RUN sed -i 's/system("R.*CheckDB.R");/#&/' /opt/conda/envs/ericscript_v0.5.5/bin/ericscript.pl
RUN echo 1 > /opt/conda/envs/ericscript_v0.5.5/share/ericscript-0.5.5-3/lib/data/_resources/.flag.dbexists