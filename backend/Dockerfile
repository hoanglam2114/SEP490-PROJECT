FROM node:20-alpine

WORKDIR /app

# Copy package files
COPY package.json ./

# Install all deps (including devDeps for build)
RUN npm install

# Copy source
COPY . .

# Build TypeScript
RUN npm run build

# Remove devDependencies after build
RUN npm prune --production

EXPOSE 3000

CMD ["node", "dist/index.js"]
