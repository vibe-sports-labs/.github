# 🚀 Evolução das Ideias
## ⚙️ 1. Smart Preferences & Matching Customizado (Antigo: Preferências)
Em vez de apenas um menu estático de filtros, transforme isso em um motor de recomendação que molda a HomeScreen.

Match Perfeito por Gênero: Filtros estritos para partidas Mistas, Masculinas ou Femininas, garantindo inclusão, segurança e conforto para todos os atletas.

Hub de Modalidades Favoritas: O usuário define a ordem de prioridade (ex: 1º Beach Tennis, 2º Futebol Society, 3º Vôlei). O mapa e a listagem priorizam automaticamente esses Pins na inicialização.

Alerta de Vagas de Emergência: Se uma partida do esporte favorito do usuário estiver quase começando perto dele e faltar apenas 1 jogador (o famoso "fura-bolo"), ele recebe uma notificação push prioritária.

## 🛡️ 2. Gestão de Clãs & Equipes (Antigo: Criar Time)
Transformar o "Time" em uma entidade viva no MongoDB, quase como um "Clã" de videogame.

Perfil do Elenco: Nome, escudo/logo customizado, estatísticas coletivas (vitórias, derrotas, saldo de gols) e lista de membros com cargos (Capitão, Tesoureiro, Jogador).

Agenda de Confrontos (Desafios): Um time pode lançar um desafio público no mapa para outro time aceitar. O app cria a partida automaticamente com as duas equipes vinculadas.

Feed do Elenco (Mural): Espaço interno para posts de avisos, fotos do pós-jogo e resenha, integrado ao sistema de notificações para avisar quando o Capitão publicar algo importante.

## 🏆 3. Sistema de Leveling, Conquistas e MVP (Gamificação)
Manter o atleta engajado através de recompensas visuais e evolução de perfil.

Avaliação Pós-Jogo (Rating): Ao término de uma partida, os jogadores votam anonimamente nos atributos uns dos outros (ex: Pontualidade, Fair Play, Habilidade) e elegem o "Craque do Jogo" (MVP).

Nível do Atleta: Cada partida jogada concede XP. O usuário evolui de nível (ex: Nível 1: Amador ➔ Nível 50: Lenda da Quadra), exibindo medalhas exclusivas no perfil.

Badges de Conquista: Desbloqueio de insígnias por marcos atingidos (ex: 🏆 "Dono da Noite" - Jogar 5 partidas após as 22h; 🌧️ "Inabalável" - Jogar uma partida sob chuva/inverno rigoroso em Curitiba).

## 💰 4. Split de Custos Automático (Fintech)
Resolver a maior dor de cabeça de quem organiza jogos: cobrar o dinheiro da quadra.

Racha Vibe: Ao criar a partida e definir o valor de reserva da quadra, o backend calcula automaticamente a divisão por jogador.

Inscrição Condicional ao Pix: O jogador só garante a vaga e o Pin dele muda para "Confirmado" no banco de dados após o webhook do Gateway de Pagamento confirmar a liquidação do Pix do valor do racha. O dinheiro fica retido e é repassado direto para o organizador ou para a arena.

## 📊 5. Gestão de Estatísticas Avançadas da Partida (Vibe Stats)
Levar a experiência do videogame para a vida real.

Súmula Digital: O organizador ou um mesário consegue abrir uma tela rápida durante ou após o jogo para computar: Gols/Pontos, Assistências, Cartões e Faltas.

Histórico Consolidado: O perfil do usuário passa a exibir gráficos de performance (ex: "Artilheiro do mês com 12 gols", "Média de 3 assistências por jogo").

## 🤝 6. Perfil "Dono de Arena" (Monetização B2B)
Ativar o lado corporativo do MVP, permitindo que os complexos esportivos usem o Vibe como sistema de gestão próprio.

Dashboard da Quadra: Tela para donos de ginásios e arenas cadastrarem seus horários disponíveis, preços por hora e receberem pagamentos automáticos de reservas direto pelo app.

Mural de Mensagens da Arena: Permite que a quadra dispare avisos ou promoções de horários ociosos (ex: "Quadra 2 livre hoje às 14h com 30% de desconto") para todos os usuários que favoritaram aquela localização.
