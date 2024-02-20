FROM mcr.microsoft.com/devcontainers/universal:focal

RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends git zsh vim

ADD ./environment.yml .
RUN conda env create -n adsenv -y -f environment.yml \
	&& conda init zsh \
    && conda init bash
RUN chsh -s /usr/bin/zsh codespace