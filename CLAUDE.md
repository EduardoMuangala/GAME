# GAME — Protótipo "Ratodoku" (mecânica principal do Meowdoku)

> Contexto: teste cronometrado (4h) de "Vibe Coder" para a Infinity Games.
> Jogo de referência escolhido: **Meowdoku** (puzzle lógico tipo Sudoku, atualmente Top 1 nos EUA, Google Play).
> Tema adaptado para este protótipo: **rato** 🐭 em vez de gato (personagem principal / peça do jogo).

---

## 1. Porque este jogo

- Está no Top 1 do ranking de popularidade (EUA, Play Store), mesmo não sendo o mais rentável do mercado.
- Prioridade do negócio: **atenção e retenção primeiro**, monetização depois — um jogo de puzzle curto, viciante, fácil de pegar e difícil de parar de jogar, é um bom candidato a gerar retenção antes de se pensar em como extrair valor dela.

## 2. Mecânica principal (a replicar no protótipo)

Jogo de lógica tipo Sudoku simplificado:

- Grelha **6×6**, dividida em blocos **2×3**.
- 6 símbolos distintos (aqui: variações/poses do rato 🐭).
- Regras:
  - cada símbolo aparece **uma única vez** por linha;
  - uma única vez por coluna;
  - uma única vez por bloco 2×3.
- O jogador toca numa célula vazia, escolhe um símbolo num painel, e o jogo valida em tempo real (destaca conflitos).
- Vitória quando a grelha está completa e sem conflitos.
- Elementos de retenção replicados: temporizador visível, animação/ecrã de vitória, botão "Novo puzzle" (jogabilidade infinita / replay imediato).

### Decisão de tema
- Personagem/peça central: **rato** (🐭) em vez de gato, com variações visuais simples (expressões/poses) para distinguir os 6 símbolos — mantém a mecânica idêntica ao Meowdoku, mudando só a skin.

## 3. Âmbito do protótipo (o que entra e o que não entra)

**Entra (fiel ao essencial da mecânica):**
- Grelha 6×6 com blocos 2×3, geração de puzzle válido, validação em tempo real, deteção de vitória, temporizador, "novo puzzle".

**Não entra (fora do âmbito de 4h):**
- Progressão de níveis/dificuldade, loja, anúncios, som, multiplayer, conta de utilizador, backend.

## 4. Stack técnica

- HTML + CSS + JS puro, um único ficheiro `index.html` (sem build, sem dependências) — compatível com deploy estático imediato.
- Deploy: **GitHub Pages** a partir deste repositório (`EduardoMuangala/GAME`), branch `main`.

## 5. Plano de passos (sequência de trabalho)

1. [x] Repositório `GAME` criado e clonado.
2. [x] Escolha do jogo de referência (Meowdoku) e da mecânica principal.
3. [ ] Confirmar tema final (rato) e ajustar o protótipo existente (trocar emojis/skin de gato → rato, atualizar textos/título).
4. [ ] Rever o protótipo (grelha 6×6, validação, timer, vitória) — ajustar o que for preciso.
5. [ ] Commit + push para `main`.
6. [ ] Ativar GitHub Pages no repositório e obter o link público.
7. [ ] Testar o link publicado (sem localhost).
8. [ ] Gravar vídeo de ~3 min: jogo a funcionar, jogo de inspiração e porquê, resposta "ampliar ou descartar?".
9. [ ] Escrever as 5 respostas curtas.
10. [ ] Preparar registo de prompts completo (esta conversa).
11. [ ] Enviar tudo para `hr@infinitygames.io`.

## 6. Notas para a próxima sessão/IA

- Não avançar para implementação sem confirmação explícita do dono do projeto nos pontos ainda em aberto.
- Língua do projeto e commits: **português**.
- Existe um ficheiro `index.html` já rascunhado no repositório (ainda não commitado) com a mecânica em tema "gato" — serve de base, mas tem de ser adaptado para o tema "rato" antes do commit.
