# Estágio Único para teste rápido
FROM node:18-slim

# Cria usuário não-root por segurança conforme o relatório 
RUN useradd -m devopsuser
USER devopsuser
WORKDIR /app

# Cria um arquivo de execução fictício sem precisar de npm install
RUN mkdir dist && echo "console.log('Serviço Pedidos Veloz Ativo');" > dist/main.js

EXPOSE 3000
CMD ["node", "dist/main.js"]