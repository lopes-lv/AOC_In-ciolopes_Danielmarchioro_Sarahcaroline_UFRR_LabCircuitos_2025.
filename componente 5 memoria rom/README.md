# Memória ROM de 8 Palavras

A **memória ROM (Read Only Memory)** é um circuito digital **combinacional** utilizado para **armazenar informações fixas**, ou seja, dados que **não podem ser alterados durante o funcionamento do sistema**.  
No projeto a seguir, a ROM é composta por **4 palavras de 8 bits** (podendo ser expandida para 8 palavras), e utiliza um **decodificador** responsável por selecionar qual palavra será enviada à saída conforme o **endereço binário aplicado**.

<p align="center">
  <img src="./imagens%20c5/memoria_rom.png" alt="Memória ROM de 8 palavras">
</p>

---

## 1. Objetivo do Circuito

O objetivo do circuito é **ler o conteúdo armazenado em uma posição específica de memória**, de acordo com o **endereço fornecido pelo seletor**.  
Assim, quando o usuário altera o valor do seletor, o decodificador ativa a linha correspondente e o dado gravado naquela posição é disponibilizado na saída.

---

## 2. Estrutura do Circuito

O circuito da ROM é composto por dois blocos principais:

1. **Decodificador de endereços:** seleciona qual linha de memória será ativada conforme o valor binário do seletor.  
2. **Matriz de memória:** armazena os dados fixos (as palavras da ROM), e envia a palavra selecionada para a saída.

---

### 2.1 Entradas e Saídas

**Entradas:**
- **Sel (A1, A0):** Entradas de seleção (endereços). Definem qual linha de memória será ativada.  
  - Exemplo: `00`, `01`, `10`, `11` → selecionam respectivamente **Mem1**, **Mem2**, **Mem3** e **Mem4**.

**Saída:**
- **D[7:0]:** Palavra de 8 bits correspondente ao endereço selecionado.

---

## 3. Componentes Principais

### 3.1 Decodificador de Endereços

O **decodificador** é responsável por transformar as **entradas binárias do seletor** em **sinais de ativação exclusivos** para cada linha de memória.  
No exemplo abaixo, é usado um **decodificador de 2 para 4**, capaz de ativar uma das quatro memórias disponíveis.

<p align="center">
  <img src="./imagens%20c5/decodificador.png" alt="Decodificador de endereços">
</p>

| Entradas (Sel) | Linha Ativada | Memória Selecionada |
|----------------|----------------|----------------------|
| 00 | 1ª linha | Mem 1 |
| 01 | 2ª linha | Mem 2 |
| 10 | 3ª linha | Mem 3 |
| 11 | 4ª linha | Mem 4 |

Cada linha ativada pelo decodificador corresponde a uma **palavra específica armazenada na ROM**.

---

### 3.2 Matriz de Memória (Blocos de Dados)

Cada **bloco de memória** contém **8 bits fixos** representando uma palavra armazenada.  
Essas palavras podem representar instruções, constantes ou dados binários.  
Quando o decodificador ativa uma linha, o conteúdo desse bloco é enviado à saída, enquanto as outras permanecem inativas.

No circuito da imagem, isso é representado pelos **quatro blocos retangulares de 8 bits** (00000000), com suas saídas unidas por portas lógicas de controle.

---

## 4. Funcionamento do Circuito Completo

<p align="center">
  <img src="./imagens%20c5/memoria_rom.png" alt="Circuito completo da ROM">
</p>

1. O **seletor (Sel)** fornece um endereço binário de 2 bits.  
2. O **decodificador** converte esse endereço em um sinal ativo em apenas uma das quatro linhas.  
3. A linha ativada habilita o bloco correspondente da **memória ROM**.  
4. O **conteúdo binário fixo** desse bloco é transmitido para a **saída D[7:0]**.  
5. Todas as demais memórias permanecem desativadas, garantindo uma única saída válida.

Exemplo prático:  
- Se o seletor for `10`, o decodificador ativa a **Mem 3**, e o valor armazenado nela é exibido na saída.

---

## 5. Aplicações

- Armazenamento de **constantes e tabelas fixas** (por exemplo, caracteres ASCII).  
- **Implementação de funções lógicas** complexas em hardware.  
- **Programas fixos** em sistemas embarcados.  
- **ROMs de instruções** em microprocessadores e controladores lógicos programáveis.

---

## 6. Observações Finais

- A ROM apresentada é de **4 palavras**, mas o princípio é o mesmo para **ROMs de 8, 16 ou mais palavras**.  
- O número de **entradas do decodificador** cresce com o log₂ do número de palavras.  
  - Exemplo:  
    - 2 entradas → 4 palavras  
    - 3 entradas → 8 palavras  
- O circuito é **combinacional puro**: não há elementos de armazenamento dinâmico (como flip-flops).  
