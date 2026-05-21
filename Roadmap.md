# ⚽ Vibe Sports Lab — MVP & Engineering Roadmap

Este documento consolida o planejamento estratégico de engenharia e os requisitos do Produto Mínimo Viável (MVP) para o **Vibe Sports Lab**. O ecossistema foi projetado de forma totalmente desacoplada, utilizando **Spring Boot** no ecossistema de Backend e **Kotlin Multiplatform (KMP)** no ecossistema de Frontend, garantindo máxima performance, segurança e consistência no compartilhamento de lógica de negócio entre plataformas (Android e iOS).

---

## 🏗️ 1. Core Architecture & Infra (Base)

* **[x] Setup do Monolito Modular:** Inicialização do ecossistema Spring Boot + infraestrutura de coleções estruturadas no MongoDB.
* **[ ] Migração do Ecossistema Mobile:** Setup e inicialização do projeto base em **Kotlin Multiplatform (KMP)** + Compose Multiplatform, mitigando de forma definitiva gargalos históricos de compilação/sincronização de dependências nativas (`gradlew` / Kotlin compiler).
* **[x] Módulo de Segurança Unificado:** Integração ponta a ponta do Firebase Auth SDK (Mobile) com o `FirebaseFilter` no Spring Security via tokens portadores (*Bearer Tokens*).
* **[ ] Engine de Mensageria (Eventos):** Arquitetura para distribuição resiliente de notificações e processamento assíncrono utilizando o padrão **Transactional Outbox Pattern** para mitigar perda de dados em falhas de rede.

---

## 💻 2. Backend Sprint (Spring Boot & MongoDB)

* **[x] Geo-Location Engine:** Implementação final do `MatchService` utilizando indexação geoespacial nativa do MongoDB (`2dsphere`) para viabilizar buscas dinâmicas por raio de distância através do endpoint `/api/v1/matches/nearby`.
* **[ ] Cadastro de Arenas:** API estruturada para criação, persistência e gerenciamento de complexos esportivos, estádios, quadras e ginásios parceiros (`POST /api/v1/venues`).
* **[ ] Real-Time Messaging Core:** Setup e configuração de servidores de WebSockets embutidos no ciclo de vida do Spring Boot para sustentar as salas de chat dinâmicas de cada partida.
* **[ ] Gateway de Pagamentos:** Integração segura com parceiros de pagamento para liquidação automatizada de reservas de quadras e taxas de inscrição via **Pix**.

---

## 📱 3. Frontend Sprint (KMP & Compose Multiplatform)

### 🔑 Autenticação & Entrada
* **Tela de Login:** Interface moderna e otimizada (Paleta Dark/Neon) com fluxo de autenticação social utilizando **Google Sign-In** e **Facebook Auth**.
* **Backdoor de Suporte:** Mecanismo oculto de engenharia (*Easter Egg* acionado por 5 cliques consecutivos no logotipo) para forçar o estado de *User Impersonation* em ambiente de homologação. O aplicativo injeta chaves estritas de cabeçalho (`X-Impersonate-User` e `X-Admin-Secret`) permitindo depuração em tempo real direto na API do Spring Boot.

### 🗺️ Hub Central (Bottom Menu Navigation)
Componente de navegação inferior estruturado para gerenciar e persistir o estado de duas abas de domínio principais:

#### Aba 1: Tela do Mapa (Geolocalização)
* **Mapa Interativo:** Exibição em tempo real de partidas e quadras próximas na região de Curitiba através de marcadores personalizados (*Pins*), alimentados dinamicamente via consumo assíncrono do endpoint `/nearby`.
* **Alternador de Visão (Toggle):** Gatilho na interface para transicionar instantaneamente os dados geográficos do mapa para uma listagem vertical clássica baseada em componentes performáticos (*Cards*).
* **Fluxo de Criação:** Formulário ou modal interativo para parametrização e publicação de novas partidas (`POST /api/v1/matches`).
* **Detalhes do Evento:** Tela rica consolidando informações gerais do jogo, dados do organizador, vagas restantes e o botão de ação rápida para inscrição imediata na partida (`PATCH /join`).

#### Aba 2: Tela de Perfil (Central do Atleta)
* **Identificação Cadastral:** Renderização assíncrona da imagem de perfil do atleta, e-mail e nome completo.
* **Painel de Configurações:** Sub-menus dedicados a:
    * *Alterar dados do perfil* (telefone, posição preferencial, nível técnico).
    * *Central de Notificações* (configuração de preferências).
    * *Suporte Técnico* (canal direto de atendimento).
    * *Informações Legais* (versão estável e termos de uso do ecossistema).
    * *Logout*: Gatilho para limpeza de cache e tokens de sessão de forma segura.

### 💬 Engajamento em Tempo Real
* **Chat de Arena:** Interface de mensagens em tempo real acoplada de forma exclusiva ao identificador do complexo esportivo/partida, utilizando conexões persistentes via `ktor-client-websockets`.
* **Push Notifications:** Receptores em primeiro e segundo plano para processar notificações instantâneas enviadas via Firebase Cloud Messaging (FCM) sobre alterações de horários, confirmações ou convites em aberto.
