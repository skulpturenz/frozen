FROM node:lts-alpine AS base

RUN apk add git bash shadow gnupg curl bash-completion && echo '/bin/bash' | chsh `whoami`
RUN git config --global pager.branch false

FROM base

RUN sed -i '2s/^# *//' /etc/apk/repositories && apk update && apk add openjdk21 doctl

RUN bash -c "corepack enable pnpm && pnpm config set store-dir /home/node/.local/share/pnpm/store"
