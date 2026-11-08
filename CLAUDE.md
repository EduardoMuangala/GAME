# GAME — Protótipo "PassengerDoku" (mecânica principal do Meowdoku)

> Contexto: teste cronometrado (4h) de "Vibe Coder" para a Infinity Games.
> Jogo de referência escolhido: **Meowdoku** (puzzle lógico tipo Sudoku, atualmente Top 1 nos EUA, Google Play).
> Tema adaptado para este protótipo: **passageiro de transportes públicos** 🚆 (em vez de rato/gato).

---

## 1. Porque este jogo

- Está no Top 1 do ranking de popularidade (EUA, Play Store), mesmo não sendo o mais rentável do mercado.
- Prioridade do negócio: **atenção e retenção primeiro**, monetização depois — um jogo de puzzle curto, viciante, fácil de pegar e difícil de parar de jogar, é um bom candidato a gerar retenção antes de se pensar em como extrair valor dela.

## 2. Mecânica principal (a replicar no protótipo)

Jogo de lógica tipo Sudoku simplificado:

- Grelha **6×6** ("carruagem"), dividida em blocos **2×3**.
- 6 símbolos distintos (aqui: passageiros em 6 cores).
- Regras:
  - cada passageiro aparece **uma única vez** por linha;
  - uma única vez por coluna;
  - uma única vez por bloco 2×3.
- O jogador toca num lugar vazio, escolhe um passageiro num painel, e o jogo valida em tempo real (destaca conflitos).
- Vitória quando a carruagem está completa e sem conflitos.
- Elementos de retenção: temporizador, combo, estrelas, cards de conquista, ecrã de vitória com confetti, "Novo puzzle" (jogabilidade infinita / replay imediato).

### Decisão de tema e posicionamento de negócio (pivot de 2ª sessão)
- **Personagem/peça central: passageiro de comboio/metro/autocarro** (🚆), em vez de rato/gato.
- **Porquê este pivot:** Portugal tem um público alargado e recorrente de utilizadores de transportes públicos (comboio, metro, autocarro). Um tema "passageiro" não é só estético — define um **público-alvo concreto e um canal de distribuição físico a pensar a longo prazo**: se o jogo vier a ser publicado, há um encaixe natural para parcerias ou publicidade dentro de comboios, metros e autocarros (ecrãs, QR codes, cartazes), ligando o tema do jogo ao local onde o jogador real o experimenta.
- Mantém a mecânica idêntica ao Meowdoku — muda-se a skin e a narrativa de marca, não a lógica.
- Os 6 símbolos continuam distinguíveis por **cor + forma + número** (nunca só cor), preservando o cuidado de acessibilidade já decidido na sessão anterior.

## 3. Âmbito do protótipo (o que entra e o que não entra)

**Entra (fiel ao essencial da mecânica, + camada de gamificação):**
- Grelha 6×6 com blocos 2×3, geração de puzzle válido, validação em tempo real, deteção de vitória, temporizador, dificuldade (fácil/médio/difícil), "novo puzzle".
- Gamificação: combo em tempo real, pontuação com bónus/penalização, 1-3 estrelas por resultado, cards de conquista, perfil persistente (estrelas totais, jogos jogados).
- UX: splash inicial animado, tutorial interativo de 5 passos (com spotlight real sobre a UI, reabrível a qualquer momento via botão "Ver tutorial" sem perder o progresso nem o tempo do puzzle atual), modais de confirmação para ações destrutivas (sair / recomeçar).
- **Progressão de veículos:** a mesma mecânica ganha um "casco" visual diferente por nível — Carruagem (nível 1, sempre disponível), Avião (nível 2, desbloqueia aos 15 ⭐ acumuladas), Navio (nível 3, desbloqueia aos 30 ⭐). Cada veículo tem cor própria, janelas com forma distinta (retangular/oval/vigia redonda) e crachá de identificação (ex: "Voo PD-204"). Pensado para, no futuro, expandir ainda mais meios de transporte como forma de progressão de longo prazo.
- **A grelha também cresce por nível** (não é só estética): Carruagem = 4×4 (blocos 2×2, mais fácil/pequena — boa entrada para quem não joga Sudoku), Avião = 6×6 (blocos 2×3, o tamanho original), Navio = 8×8 (blocos 2×4, maior e mais difícil, com os 8 passageiros/cores disponíveis). O tamanho da célula, do painel e os limiares de estrelas (tempo) escalam automaticamente consoante a grelha, para o Navio não ser penalizado só por ter mais casas a preencher.

- **Internacionalização (i18n):** interface traduzível, hoje em PT/EN/FR, com arquitetura pensada para crescer até 10+ idiomas sem mudar código — só acrescentar entradas ao dicionário. Seletor de bandeiras (🇵🇹/🇬🇧/🇫🇷) no menu; a escolha fica persistente entre sessões.

**Não entra (fora do âmbito de 4h):**
- Loja, anúncios reais, som, multiplayer, conta de utilizador, backend.

## 4. Stack técnica

- HTML + CSS + JS puro, um único ficheiro `index.html` (sem build, sem dependências).
- Arquitetura em módulos dentro do mesmo ficheiro: `Storage`, `Profile`, `Game` (lógica pura), `UI` (renderização), `FX` (feedback visual), `Modal` (confirmações), `Tutorial`, `Controller` (fluxo).
- Bibliotecas externas via CDN: GSAP (animações/transições de ecrã), canvas-confetti (celebração na vitória — servido via jsdelivr, não cdnjs: a versão do cdnjs falha com "module is not defined" em `<script>` simples), Google Fonts "Fredoka".
- Deploy: **Vercel**, importado diretamente do repositório `EduardoMuangala/GAME`, branch `main` (deploy automático a cada push).
- Link público: **https://game-alpha-one-18.vercel.app/**

## 5. Plano de passos (sequência de trabalho)

1. [x] Repositório `GAME` criado e clonado.
2. [x] Escolha do jogo de referência (Meowdoku) e da mecânica principal.
3. [x] Protótipo construído com design acessível (cor + forma + número, nunca só cor).
4. [x] Mecânica completa: grelha 6×6, blocos 2×3, dificuldade, validação em tempo real, timer, pontuação, vitória com confetti.
5. [x] UX completa: splash inicial, tutorial interativo de 5 passos com spotlight real.
6. [x] Gamificação: combo, estrelas, cards de conquista, perfil persistente, modais de confirmação.
7. [x] Pivot de tema: rato → **passageiro de transportes públicos** (posicionamento de público/distribuição a longo prazo).
8. [x] Deploy no Vercel e link público obtido; deploy automático a cada push.
9. [x] Botão "Ver tutorial" sempre disponível durante o jogo (reabre sem perder progresso nem tempo).
10. [x] Progressão de veículos (Carruagem → Avião → Navio) com casco visual próprio e desbloqueio por estrelas.
11. [x] Grelha cresce por nível de veículo (4×4 → 6×6 → 8×8), com tutorial, estrelas e UI a escalarem automaticamente.
12. [x] Internacionalização: PT/EN/FR com seletor de idioma persistente, arquitetura extensível a 10+ idiomas.
13. [ ] Testar o link publicado (sem localhost) — confirmar fluxo completo no browser real do dono do projeto.
14. [ ] Gravar vídeo de ~3 min: jogo a funcionar, jogo de inspiração e porquê, resposta "ampliar ou descartar?".
15. [ ] Escrever as 5 respostas curtas (mencionar o raciocínio de público-alvo via transportes públicos, a progressão de veículos e a i18n como ganchos de retenção/alcance a longo prazo).
16. [ ] Preparar registo de prompts completo (esta conversa).
17. [ ] Enviar tudo para `hr@infinitygames.io`.

## 6. Notas para a próxima sessão/IA

- Língua do projeto e commits: **português**.
- Cada push para `main` dispara deploy automático no Vercel — não é preciso nenhum passo manual de deploy a partir daqui.
- Chaves de `localStorage` usadas: `passengerdoku_profile` (estrelas totais, jogos jogados, melhor combo, veículo selecionado) e `passengerdoku_tutorial_seen` (evita repetir o tutorial automaticamente, mas não impede reabri-lo manualmente). Chaves antigas (`ratodoku_*`) ficaram órfãs em navegadores que já tinham aberto a versão anterior — sem impacto, apenas dados obsoletos.
- Catálogo de veículos em `VEHICLES` (dentro do `<script>`): acrescentar um novo nível é só adicionar um objeto `{ id, icon, unlockStars, size, blockR, blockC }` (nome/crachá/frase de vitória vivem no `I18N`, não aqui) e as duas regras CSS `.vehicle-shell.veh-<id>` (cor do casco) + `.vehicle-shell.veh-<id> .vehicle-windows span` (forma da janela). `size × size` tem de ser divisível em blocos `blockR × blockC` (ex: 8 = 2×4) e `PASSENGERS` precisa de ter pelo menos `size` cores — hoje tem 8, chega até um hipotético nível 4 de 8×8 com blocos diferentes, mas não mais do que isso sem acrescentar cores novas.
- **I18N (`const I18N` no `<script>`):** `I18N.langs` é a lista mostrada no seletor (código, bandeira, rótulo); `I18N.dict.<code>` tem todas as chaves de texto do jogo. Acrescentar um idioma novo = copiar um bloco inteiro de `dict` (ex: `dict.en`) e traduzir os valores — nenhuma outra mudança de código é precisa. `I18N.t(key, vars)` faz a interpolação de `{var}`; `I18N.setLang(code)` troca o idioma ativo, persiste em `localStorage` (`passengerdoku_lang`) e re-renderiza o que estiver visível. Texto gerado dinamicamente (tutorial, modais, conquistas, nomes/crachás de veículo) já usa sempre `I18N.t(...)` — ao adicionar uma funcionalidade nova com texto visível, a chave tem de ir para os três blocos do `dict` (pt/en/fr), nunca escrita diretamente em português no meio do código.
