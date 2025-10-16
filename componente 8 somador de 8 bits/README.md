# Somador de 8 Bits

O **somador de 8 bits** é um circuito digital **combinacional** responsável por realizar a **adição binária** entre dois números de 8 bits, gerando um resultado de 8 bits e um sinal de **overflow** quando ocorre um transbordamento do bit mais significativo.  

Ele é construído a partir da interligação de **somadores completos de 1 bit (Full Adders)**, formando uma estrutura encadeada onde o **carry (vai-um)** de cada estágio é propagado para o próximo bit mais significativo.

<p align="center">
  <img src="./imagens%20c8/somador_de_8_bits.png" alt="Somador completo de 8 bits">
</p>

---

## 1. Objetivo do Circuito

O objetivo do circuito é **somar dois números binários de 8 bits** (`Entrada A` e `Entrada B`) e gerar:
- Uma **saída de 8 bits** representando a soma;
- Um **bit de overflow**, indicando se houve transbordamento (resultado maior que 255).

---

## 2. Estrutura do Circuito

O circuito é composto por:
- **8 somadores completos de 1 bit**, conectados em série;
- **Linhas de entrada A e B** (8 bits cada);
- **Linhas de carry (vai-um)** entre cada somador;
- **Uma saída de overflow** vinda do último carry.

---

### 2.1 Entradas e Saídas

**Entradas:**
- **A[7:0]:** Primeira palavra binária (8 bits).  
- **B[7:0]:** Segunda palavra binária (8 bits).  

**Saídas:**
- **S[7:0]:** Resultado da soma binária.  
- **Overflow:** Indica transbordamento (quando a soma ultrapassa 8 bits).  

---

## 3. Somador Bit a Bit (1 Bit)

O **somador de 1 bit** é a unidade básica do circuito.  
Ele realiza a soma de dois bits (`A` e `B`) e de um **carry de entrada** (`Cin`), produzindo:
- Um **bit de soma (S)**;  
- Um **carry de saída (Cout)**.

<p align="center">
  <img src="./imagens%20c8/somador_bit_a_bit.png" alt="Somador de 1 bit (Full Adder)">
</p>

### 3.1 Tabela Verdade do Somador de 1 Bit

| A | B | Cin | S | Cout |
|---|---|------|---|------|
| 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 1 | 1 | 0 |
| 0 | 1 | 0 | 1 | 0 |
| 0 | 1 | 1 | 0 | 1 |
| 1 | 0 | 0 | 1 | 0 |
| 1 | 0 | 1 | 0 | 1 |
| 1 | 1 | 0 | 0 | 1 |
| 1 | 1 | 1 | 1 | 1 |

### 3.2 Expressões Lógicas

- **Soma:**  
  \[
  S = A \oplus B \oplus Cin
  \]
- **Carry de saída:**  
  \[
  Cout = (A \cdot B) + (A \cdot Cin) + (B \cdot Cin)
  \]

Essas expressões são implementadas com portas lógicas **XOR**, **AND** e **OR**.

---

## 4. Somador Completo de 8 Bits

O somador completo de 8 bits é formado pela **ligação em cascata** de oito somadores de 1 bit.  
Cada somador processa um par de bits correspondentes de A e B e o carry gerado pelo estágio anterior.

<p align="center">
  <img src="./imagens%20c8/somador_de_8_bits.png" alt="Somador completo de 8 bits">
</p>

### Funcionamento:

1. O primeiro somador (bit 0) recebe `A0`, `B0` e `Cin = 0`.  
2. O carry gerado (`Cout0`) é enviado ao segundo somador (bit 1).  
3. Esse processo se repete até o oitavo somador (bit 7).  
4. O **carry do último estágio (Cout7)** é utilizado como **bit de overflow**.  
5. A **saída final (S[7:0])** representa o resultado da soma.

---

## 5. Exemplo de Operação

| Entrada A | Entrada B | Resultado (S) | Overflow |
|------------|------------|----------------|-----------|
| 00000101 (5) | 00000011 (3) | 00001000 (8) | 0 |
| 11111111 (255) | 00000001 (1) | 00000000 (0) | 1 |
| 01111111 (127) | 01111111 (127) | 11111110 (254) | 0 |

---

## 6. Aplicações

- **Unidades Lógicas e Aritméticas (ULA)** em processadores.  
- **Somadores acumuladores** (AC) em sistemas digitais.  
- **Controle de endereço e contadores** em memórias.  
- **Operações de incremento/decremento** em circuitos de controle.  

---

## 7. Observações Finais

- O **overflow** é essencial para detectar erros de soma em operações aritméticas com números binários limitados.  
- O circuito pode ser facilmente **expandido** para 16 ou 32 bits adicionando mais estágios de somadores.  
- A implementação com portas lógicas básicas permite a construção em **nível de hardware** sem o uso de componentes integrados complexos.

---

