
FROM oven/bun:1-alpine AS deps
WORKDIR /app
COPY package.json bun.lock ./
RUN bun install --frozen-lockfile --production
COPY . .
RUN bun run build
USER bun
EXPOSE 3000
CMD ["bun", "start"]