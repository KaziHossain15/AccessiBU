FROM node:22-bookworm-slim WORKDIR /app

COPY package.json package-lock.json ./
RUN npm ci

COPY . .

# Build static web bundle
RUN npx expo export --platform web

# Install lightweight HTTP server
RUN npm install -g serve

EXPOSE 8081

ENV EXPO_NO_TELEMETRY=1
CMD ["serve", "-s", "dist", "-l", "8081"]
