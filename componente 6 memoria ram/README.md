# Memória RAM de 8 Bits

A **memória RAM (Random Access Memory)** é um tipo de memória **volátil**, utilizada para **armazenamento temporário de dados** durante a execução de operações lógicas ou aritméticas em sistemas digitais.  
Diferente da ROM, seu conteúdo **pode ser alterado** durante o funcionamento, permitindo tanto **operações de escrita (write)** quanto **de leitura (read)**.

<p align="center">
  <img src="./imagens%20c6/memoria_ram.png" alt="Circuito completo da memória RAM de 8 bits">
</p>

---

## 1. Objetivo do Circuito

O circuito representa uma **memória RAM de 4 palavras de 8 bits**, controlada por sinais de **seleção, escrita e limpeza**.  
Cada palavra é armazenada em um **registrador de 8 bits**, e o acesso à memória é controlado por um **decodificador de endereços**.

---

## 2. Estrutura da Memória RAM

O sistema é composto por três blocos principais:

1. **Decodificador de endereços:** seleciona qual registrador será habilitado para leitura ou escrita.  
2. **Registradores de 8 bits:** armazenam os dados binários, controlados por flip-flops tipo D.  
3. **Circuito de controle:** gerencia as operações de escrita (`WE`), limpeza (`clear`) e reinicialização (`preset`).

---

### 2.1 Entradas e Saídas

**Entradas:**
- **Sel (A1, A0):** Entradas de endereço binário para selecionar o registrador ativo.  
- **WE (Write Enable):** Define o modo de operação:
  - `1` → Habilita escrita (os dados de entrada são armazenados).  
  - `0` → Habilita leitura (os dados armazenados são enviados à saída).  
- **Clear:** Limpa todo o conteúdo da memória (zera todos os registradores).  
- **Preset:** Inicializa os registradores com valores pré-definidos (caso implementado).  
- **Entrada de dados (D[7:0]):** Dados a serem escritos na memória.

**Saída:**
- **Saída (Q[7:0]):** Palavra de 8 bits armazenada no registrador selecionado.

---

## 3. Decodificador de Endereços

O **decodificador** é o elemento responsável por ativar **somente uma linha de memória** de acordo com o endereço binário informado.  
No circuito, é utilizado um **decodificador de 2 entradas e 4 saídas**, suficiente para selecionar 4 registradores distintos.

<p align="center">
  <img src="./imagens%20c6/decodificador.png" alt="Decodificador de endereços da memória RAM">
</p>

| Entradas (Sel) | Linha Ativada | Registrador Selecionado |
|----------------|----------------|--------------------------|
| 00 | 1ª linha | R1 |
| 01 | 2ª linha | R2 |
| 10 | 3ª linha | R3 |
| 11 | 4ª linha | R4 |

Cada linha de saída do decodificador é conectada ao **sinal de habilitação** de um registrador.

---

## 4. Registrador de 8 Bits

Cada **registrador de 8 bits** é implementado utilizando **8 flip-flops tipo D** conectados em paralelo.  
Os flip-flops armazenam individualmente cada bit da palavra, e suas saídas são combinadas para formar o valor binário completo.

<p align="center">
  <img src="./imagens%20c6/registrador_8_bits.png" alt="Registrador de 8 bits implementado com flip-flops tipo D">
</p>

### Funcionamento:
- Quando **WE = 1** e o registrador está **selecionado pelo decodificador**, o dado presente na **entrada de dados (D[7:0])** é armazenado.  
- Quando **WE = 0**, o conteúdo armazenado é mantido e disponibilizado na **saída (Q[7:0])**.  
- Os sinais **clear** e **preset** permitem zerar ou inicializar os flip-flops conforme necessário.

---

## 5. Funcionamento do Circuito Completo

<p align="center">
  <img src="./imagens%20c6/memoria_ram.png" alt="Circuito completo da memória RAM de 8 bits">
</p>

1. O **seletor (Sel)** define qual registrador será acessado.  
2. O **decodificador** ativa somente o registrador correspondente ao endereço.  
3. Se **WE = 1**, os dados de entrada são **armazenados** nesse registrador.  
4. Se **WE = 0**, os dados previamente armazenados são **enviados à saída**.  
5. Os sinais **clear** e **preset** controlam o estado inicial da memória.

---

## 6. Operações da Memória

| Operação | WE | Ação |
|-----------|----|------|
| Escrita   | 1  | Armazena o valor de D[7:0] no registrador selecionado |
| Leitura   | 0  | Envia o conteúdo armazenado para a saída |
| Clear     | X  | Zera todos os registradores |
| Preset    | X  | Inicializa os registradores com valores predefinidos |

---

## 7. Aplicações

- **Armazenamento temporário** de dados em sistemas digitais.  
- Implementação de **memórias de trabalho** em processadores e microcontroladores.  
- Simulação de **bancos de registradores** em arquiteturas de CPU.  
- Implementação de **buffers de dados** em sistemas embarcados.

---

## 8. Observações Finais

- O circuito pode ser expandido para **8 palavras ou mais**, bastando adicionar novos registradores e um **decodificador com mais entradas**.  
- A memória RAM é **volátil** — seus dados são perdidos quando o sistema é desligado.  
- O uso de flip-flops tipo D garante **armazenamento estável** e **controle preciso** das operações de leitura e escrita.

