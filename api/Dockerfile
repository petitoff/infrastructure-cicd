FROM node:20

WORKDIR /usr/src/app

RUN npm install -g pnpm @nestjs/cli

# Copy application dependency manifests to the container image.
COPY package.json pnpm-lock.yaml ./

# Install app dependencies
RUN pnpm install --frozen-lockfile

COPY . .

RUN pnpm run build

CMD [ "node", "dist/main.js" ]