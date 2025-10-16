# Detector de Paridade Ímpar

O **detector de paridade ímpar** é um circuito digital **combinacional** utilizado para verificar se uma palavra binária possui um **número ímpar de bits iguais a 1**.  

Esse tipo de circuito é amplamente empregado em sistemas de **transmissão de dados** e **verificação de erros**, garantindo a integridade das informações trocadas entre dispositivos digitais.

<p align="center">
  <img src="./imagens%20c14/detector.png" alt="Detector de paridade ímpar">
</p>

---

## 1. Objetivo do Circuito

O objetivo do circuito é **indicar quando o número de bits 1 em uma sequência binária é ímpar**.  

A saída do detector é:
- **1 (ativo)** → quando o número de bits 1 é ímpar;  
- **0 (inativo)** → quando o número de bits 1 é par.

---

## 2. Estrutura do Circuito

O circuito é composto essencialmente por **portas lógicas XOR (OU-exclusivo)**, que possuem a seguinte característica fundamental:

\[
\text{Saída} = 1 \text{ se e somente se o número de entradas em nível lógico alto (1) for ímpar.}
\]

Assim, ao conectar várias portas XOR em série, é possível determinar a **paridade ímpar** de um conjunto de bits.

---

### 2.1 Entradas e Saídas

**Entradas:**
- Conjunto de bits de entrada (por exemplo, A₀, A₁, A₂, A₃).

**Saída:**
- **P (Paridade Ímpar):** bit que indica se o número de bits 1 na entrada é ímpar.

---

## 3. Princípio de Funcionamento

A **porta XOR** possui a seguinte tabela verdade para duas entradas:

| A | B | Saída (A ⊕ B) |
|---|---|----------------|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

Quando aplicada a mais de duas entradas, o comportamento se mantém:  
- A saída é **1** se o número de bits em nível lógico alto for **ímpar**;  
- A saída é **0** se o número for **par**.

---

### 3.1 Exemplo para 4 Bits

Considere uma entrada de **4 bits**: A₃, A₂, A₁, A₀.  
A expressão lógica do detector de paridade ímpar é:

\[
P = A_3 \oplus A_2 \oplus A_1 \oplus A_0
\]

---

### 3.2 Tabela Verdade

| A₃ | A₂ | A₁ | A₀ | Nº de 1’s | P (Saída) |
|----|----|----|----|------------|------------|
| 0 | 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 0 | 1 | 1 | 1 |
| 0 | 0 | 1 | 0 | 1 | 1 |
| 0 | 1 | 0 | 0 | 1 | 1 |
| 1 | 0 | 0 | 0 | 1 | 1 |
| 0 | 0 | 1 | 1 | 2 | 0 |
| 0 | 1 | 0 | 1 | 2 | 0 |
| 1 | 0 | 0 | 1 | 2 | 0 |
| 1 | 1 | 1 | 0 | 3 | 1 |
| 1 | 1 | 1 | 1 | 4 | 0 |

A saída é **1** sempre que há um número ímpar de bits em nível lógico alto.

---

## 4. Aplicações

- **Verificação de erros em transmissão de dados (bit de paridade)**;  
- **Controle de integridade em memórias digitais**;  
- **Sistemas de codificação e decodificação**;  
- **Circuitos de diagnóstico e segurança de dados**.

---

## 5. Observações Finais

- O **detector de paridade ímpar** pode ser facilmente convertido em **detector de paridade par**, invertendo a saída.  
- O circuito é **simples, eficiente e escalável**, podendo operar com qualquer número de bits.  
- Em aplicações práticas, o detector é frequentemente implementado com **portas XOR integradas (como o CI 7486)**.

---
