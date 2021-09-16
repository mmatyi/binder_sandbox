# Copyright (c) Jupyter Development Team.
# Distributed under the terms of the Modified BSD License.
ARG OWNER=jupyter
ARG BASE_CONTAINER=$OWNER/minimal-notebook
# FROM jupyter/scipy-notebook
FROM $BASE_CONTAINER

LABEL maintainer="Jupyter Project <jupyter@googlegroups.com>"

USER root

# R pre-requisites
RUN apt-get update --yes && \
    apt-get install --yes --no-install-recommends \
    fonts-dejavu \
    unixodbc \
    unixodbc-dev \
    python3-notebook \ 
    jupyter \ 
    jupyter-core \
    python-ipykernel  \
    gfortran \
    gcc && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

USER ${NB_UID}

# R packages including IRKernel which gets installed globally.
# r-e1071: dependency of the caret R package
