# Estágio 1: Build
FROM node:18-slim AS builder
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
# Simula o build da aplicação
RUN mkdir dist && echo "console.log('Serviço Rodando');" > dist/main.js

# Estágio 2: Runtime Seguro
FROM node:18-slim
# Cria usuário não-root por segurança
RUN useradd -m devopsuser
USER devopsuser
WORKDIR /app
COPY --from=builder /app/dist ./dist
COPY --from=builder /app/node_modules ./node_modules

EXPOSE 3000
CMD ["node", "dist/main.js"]