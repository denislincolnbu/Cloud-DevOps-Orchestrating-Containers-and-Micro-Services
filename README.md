# 🚀 Projeto Loja Veloz - Modernização e Orquestração

Este repositório contém a solução completa para o desafio de Cloud DevOps da Loja Veloz. O foco foi a modernização da plataforma "Pedidos Veloz", implementando conteinerização, orquestração com Kubernetes, automação de pipelines e estratégias de escalabilidade resilientes.

## 📋 Estrutura do Projeto

* **api-gateway/ e pedidos-service/**: Dockerfiles estruturados com multi-stage build e execução com usuário não-root para máxima segurança.
* **k8s/**: Manifestos de produção incluindo Deployments (Nginx Alpine), Services, Secrets e HPA.
* **.github/workflows/**: Pipeline automatizado de CI/CD para integração e entrega contínua.
* **docker-compose.yml**: Configuração para ambiente de desenvolvimento local (API, PostgreSQL e RabbitMQ).

## 🛠️ Como Executar (Ambiente Local)

Para subir a infraestrutura completa de desenvolvimento:
```bash
docker-compose up --build

###

Acesse o painel do RabbitMQ em: http://localhost:15672 (User/Pass: guest).

☸️ Orquestração e Escalabilidade (Kubernetes)
A solução foi desenhada para suportar picos de tráfego massivos:

Metrics Server: Implementado para monitoramento de recursos em tempo real no cluster.

Auto-scaling (HPA): Configurado para escalar de 2 a 10 réplicas automaticamente quando a CPU ultrapassa 10%, garantindo resposta imediata.

Resiliência: Uso de Readiness e Liveness probes para autorrecuperação de serviços falhos.

Imagens Otimizadas: Uso de nginx:alpine para garantir deploys ultrarrápidos e baixo consumo de memória.

🔄 Pipeline CI/CD e Observabilidade
Pipeline: Executa estágios de Build, Testes e Security Scan (vulnerabilidades) antes de cada deploy.

Telemetria: Baseada nos três pilares (Métricas, Logs e Traces) para rastreabilidade total de falhas.

📺 Vídeo Pitch (Demonstração)
Assista à demonstração prática do HPA escalando os pods sob carga: 👉 https://youtu.be/UOy0Hq1RYeU
