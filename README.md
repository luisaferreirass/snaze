# 🐍 Snaze — A Snake Trapped in a Maze

Snaze é uma simulação em modo texto do clássico jogo **Snake**, com um diferencial: a cobra está presa dentro de um **labirinto**.  
O projeto foi desenvolvido em **C++** como parte da disciplina **Programming I (DIM0176)** da **Universidade Federal do Rio Grande do Norte (UFRN)**.

O principal objetivo é implementar uma **inteligência artificial** capaz de conduzir a cobra até os alimentos de forma segura, evitando colisões com paredes e com o próprio corpo.

---

## 🎮 Funcionalidades

- Leitura de níveis a partir de arquivos de texto
- Suporte a múltiplos níveis em um único arquivo
- Sistema de vidas e pontuação
- Geração aleatória de alimentos em posições válidas
- Dois tipos de controle da cobra:
  - **Random** (movimento aleatório)
  - **Backtracking** (IA baseada em busca)
- Simulação em tempo real no terminal
- Mensagens de status do jogo:
  - Colisão
  - Fim de nível
  - Vitória
  - Derrota

---

## 🧠 Inteligência Artificial

O modo **backtracking** utiliza uma estratégia de busca para encontrar uma sequência válida de movimentos que leve a cobra até o alimento, considerando:

- As paredes do labirinto
- As paredes invisíveis
- O corpo da própria cobra
- A simulação do movimento do corpo durante a busca

Caso não seja encontrado um caminho válido até o alimento, o sistema automaticamente passa a sugerir movimentos aleatórios.

---

## 📥 Entrada

Os níveis do jogo são definidos em arquivos `.txt`.  
Cada nível contém:

- Dimensões do tabuleiro
- `#` → parede
- `.` → parede invisível
- `&` → posição inicial da cobra

Um arquivo pode conter **um ou mais níveis**, que serão jogados sequencialmente.

---

## 📤 Saída

Durante a execução, o programa exibe no terminal:

- Representação textual do labirinto
- Posição da cobra e do alimento
- Número de vidas restantes
- Pontuação atual
- Quantidade de alimentos restantes
- Nível atual

Mensagens adicionais são exibidas quando:
- A cobra colide
- Um nível é finalizado
- O jogo é vencido ou perdido

## ⚙️ Como executar

### Compilação
```bash
make
./build/snaze
```

### Opções de linha de comando

| Opção | Descrição | Padrão |
|-------|-----------|--------|
| `--help` | Exibe a ajuda do programa | - |
| `--fps <valor>` | Define os frames por segundo | 24 |
| `--lives <valor>` | Número de vidas da cobra | 5 |
| `--food <valor>` | Quantidade total de alimentos no jogo | 10 |
| `--playertype <tipo>` | Tipo de IA: `random` ou `backtracking` | random |

### Exemplos de uso
```bash
# Executar com configurações padrão
./build/snaze

# Executar com IA backtracking e 3 vidas
./build/snaze --playertype backtracking --lives 3

# Executar com 60 FPS e 20 alimentos
./build/snaze --fps 60 --food 20
```

---

## 📁 Estrutura do projeto
```
snaze/
├── src/              # Arquivos de implementação (.cpp)
├── include/          # Arquivos de cabeçalho (.h)
├── data/             # Arquivos de configuração de níveis
├── build/            # Executável compilado
├── Makefile          # Script de compilação
├── README.md         # Documentação principal
└── author.md         # Informações do autor
```


