FROM node:16.13.1

WORKDIR /usr/src/app

RUN npm i pnpm -g --loglevel notice --force

COPY package.json .

COPY apps/widget ./apps/widget

COPY libs/dal ./libs/dal
COPY libs/sdk ./libs/sdk
COPY libs/testing ./libs/testing
COPY libs/shared ./libs/shared

COPY tsconfig.json .
COPY tsconfig.base.json .

COPY nx.json .
COPY pnpm-workspace.yaml .
COPY pnpm-lock.yaml .



RUN pnpm install

CMD [ "pnpm", "start:docker:widget" ]
