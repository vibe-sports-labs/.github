# ⚡ Vibe-Sports-Labs

> Conectando atletas e simplificando a gestão de partidas esportivas.

Bem-vindo à organização oficial do **Vibe**, um ecossistema desenvolvido para entusiastas de esportes que buscam praticidade na organização de partidas, desde o racha de futebol até o beach tennis.

## 🚀 Diferenciais Técnicos
Para garantir uma experiência fluida (real-time) e sem perda de dados, o projeto utiliza padrões de arquitetura modernos:
* Transactional Outbox Pattern: Garante a consistência entre o banco de dados (MongoDB) e o sistema de mensageria (RabbitMQ), assegurando que cada inscrição gere uma notificação confiável.
* Geospatial Indexing: Consultas de alta performance baseadas em GeoJSON para encontrar partidas em um raio específico do usuário.
* Event-Driven Architecture: Processamento assíncrono para notificações push, encerramento de inscrições e fluxos de pagamento.

## 🏗️ Stack Tecnológica
* Mobile: Flutter (Android/iOS)
* Backend: Kotlin + Spring Boot 3.x
* Database: MongoDB (Replica Set para Transações e Change Streams)
* Message Broker: RabbitMQ
* Cache/Locks: Redis

## 🗺️ Roadmap de Engenharia
- [ ] Setup do Monolito Modular (Spring Boot + Mongo)
- [ ] Implementação do MatchService com índices Geoespaciais
- [ ] Engine de Mensageria com Outbox Pattern
- [ ] MVP Flutter: Listagem de partidas por geolocalização
- [ ] Integração com Gateway de Pagamentos (Pix)

## MVP
- Tela de Login
- Cadastro pelo google e facebook
- Bottom Menu - Tela Mapa
  - botão Listagem de partidas proximas
  - botão criar partida
  - tela detalhar informações partida (inscrever na partida)
- Bottom Menu - Tela Perfil (Deslogar, alterar do perfil, suporte, notificacoes, informações)
- Notificações
- Chat dentro do estádio/quadra/ginásio
- Criar estádio/quadra/ginásio (back)

## Ideias
- Menu - Preferencias (priorizar tipo de esporte, escolher genero para praticar esporte)
- Criar time (logo, nome, jogadores, jogos, eventos que vão participar, posts)
