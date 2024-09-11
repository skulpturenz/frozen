FROM golang:alpine AS base

RUN go install github.com/mitranim/gow@latest
RUN apk add git bash shadow gnupg curl python3 py3-pip bash-completion && echo '/bin/bash' | chsh `whoami`
RUN git config --global pager.branch false

FROM base

RUN apk add libc6-compat && curl -fsSL https://get.pulumi.com/ | sh
ENV PATH=$PATH:/root/.pulumi/bin

RUN apk add doctl
