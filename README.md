# Desafio War Estruturado – Tema 1 (C)

Versão simples e didática do jogo *War* (inspirado em Risk), implementada em C.
Feito para exercício: usa `struct`, funções bem separadas, controle de fluxo e I/O de terminal.

## Objetivo
Conquistar todos os territórios antes da CPU.

## Como funciona (regras simplificadas)
- Mapa com 6 territórios: **Amazônia, Nordeste, CentroOeste, Sudeste, Sul, Pantanal**.
- Dois jogadores: **VOCÊ** (PLAYER) e **CPU**.
- Cada território tem um dono e um número de exércitos.
- Cada turno:
  1. **Reforços**: recebe `floor(n_territorios/2)` reforços (mínimo 1). Reforços são distribuídos 1 a 1 pelo jogador.
  2. **Ataque**: o jogador pode atacar territórios adversários adjacentes enquanto quiser (precisa ter pelo menos 2 exércitos no território atacante).
     - Ataque usa dados: atacante até 3 dados (limitado por `armies - 1`), defensor até 2 dados.
     - Compara-se dados em ordem decrescente; para cada comparação, o maior vence (quem perde perde 1 exército).
     - Ao zerar os exércitos do defensor, o território passa a ser conquistado.
  3. **Turno da CPU**: CPU recebe reforços e faz ataques simples (limitados para agilizar).

> Observação: mecânicas são propositalmente simplificadas para manter o desafio curto e focado em estruturação de código.

## Arquivos
- `war.c` — código fonte em C (arquivo único).

## Como compilar
No Linux / macOS / WSL com GCC:
```bash
gcc -std=c99 -Wall -O2 war.c -o war
./war
