# Unidade Lógica e Aritmética (ULA) de 8 Bits

## Introdução
A **Unidade Lógica e Aritmética (ULA)** é um dos blocos fundamentais em sistemas digitais e microprocessadores. Ela é responsável por realizar operações **lógicas** e **aritméticas** sobre dados binários, sendo controlada por sinais que determinam qual operação deve ser executada.

Este projeto apresenta o desenvolvimento de uma **ULA de 8 bits**, implementada com base em portas lógicas básicas, deslocadores e somadores, permitindo a execução de diversas operações de forma combinacional.

---

## Objetivo
Projetar e implementar uma **ULA de 8 bits** capaz de realizar as seguintes operações:
- **AND**  
- **OR**  
- **NOT**  
- **NOR**  
- **NAND**  
- **XOR**  
- **SHIFT à esquerda (2 bits)**  
- **SHIFT à direita (2 bits)**  
- **SOMA**  
- **SUBTRAÇÃO**

---

## Descrição do Circuito

A imagem a seguir apresenta o **circuito completo da ULA de 8 bits**:

<div align="center">
  <img src="./imagens c10/ula.png" alt="ULA de 8 bits" />
</div>

O circuito é composto por múltiplos blocos funcionais correspondentes a cada operação. As entradas **A** e **B** são vetores de 8 bits, e a saída é selecionada através de um **multiplexador**, que escolhe o resultado da operação desejada conforme o código de controle.

---

## Estrutura da ULA

A ULA foi construída de forma modular, utilizando os seguintes componentes:

| Componente | Imagem | Função |
|------------|--------|--------|
| **AND** | <img src="./imagens c10/and.png" alt="AND" /> | Realiza a operação lógica AND entre A e B. |
| **OR** | <img src="./imagens c10/or.png" alt="OR" /> | Executa a operação lógica OR entre A e B. |
| **NOT** | <img src="./imagens c10/not.png" alt="NOT" /> | Inverte os bits da entrada A. |
| **NOR** | <img src="./imagens c10/nor.png" alt="NOR" /> | Realiza a operação lógica NOR entre A e B. |
| **NAND** | <img src="./imagens c10/nand.png" alt="NAND" /> | Realiza a operação lógica NAND entre A e B. |
| **XOR** | <img src="./imagens c10/xor.png" alt="XOR" /> | Executa a operação lógica XOR entre A e B. |
| **Deslocador Esquerda** | <img src="./imagens c10/deslocador_bit_esquerda.png" alt="Deslocador Esquerda" /> | Desloca os bits de A ou B 2 posições à esquerda. |
| **Deslocador Direita** | <img src="./imagens c10/deslocador_bit_direita.png" alt="Deslocador Direita" /> | Desloca os bits de A ou B 2 posições à direita. |
| **Somador 8 bits** | <img src="./imagens c10/somador_8bits.png" alt="Somador 8 bits" /> | Executa a soma binária entre A e B. |
| **Subtrator 8 bits** | <img src="./imagens c10/subtrator_8bits.png" alt="Subtrator 8 bits" /> | Calcula a diferença entre A e B. |

---

## Funcionamento

1. As entradas **A** e **B** são aplicadas simultaneamente a todos os módulos (AND, OR, XOR, etc.).  
2. Cada bloco gera seu respectivo resultado parcial.  
3. Um **multiplexador** seleciona qual saída será direcionada à saída principal da ULA, de acordo com o código de operação.  
4. O circuito também conta com deslocadores que permitem operações de **shift** à direita ou à esquerda de 2 bits, úteis em cálculos aritméticos ou manipulação de dados.  
5. O **somador e subtrator** utilizam lógica combinacional baseada em somadores completos (full adders).

---

## Código de Controle (Operações)

| Código (binário) | Operação | Descrição |
|------------------:|:--------:|:---------|
| 0000 | AND | Operação lógica entre A e B |
| 0001 | OR | Operação lógica entre A e B |
| 0010 | NOT | Inversão de A |
| 0011 | NOR | Negação do resultado de OR |
| 0100 | NAND | Negação do resultado de AND |
| 0101 | XOR | Soma lógica entre A e B |
| 0110 | SHIFT ESQ | Desloca A 2 bits à esquerda |
| 0111 | SHIFT DIR | Desloca A 2 bits à direita |
| 1000 | SOMA | Soma binária entre A e B |
| 1001 | SUBTRAÇÃO | Diferença binária entre A e B |

---

## Exemplos de Operações (8 bits)

- **AND**:  
  A = `10101100`  
  B = `11001010`  
  Saída = `10001000`

- **SHIFT ESQ (A << 2)**:  
  A = `00011011` → Saída = `01101100` (bits deslocados para esquerda, zeros preenchendo LSB)

- **SOMA**:  
  A = `00000101` (5)  
  B = `00000011` (3)  
  Saída = `00001000` (8)

- **SUBTRAÇÃO (A - B)**:  
  A = `00001010` (10)  
  B = `00000011` (3)  
  Saída = `00000111` (7)

---

## Observações de Projeto

- O uso de um **multiplexador** central permite que todas as operações sejam calculadas em paralelo e selecionadas por um único sinal de controle, simplificando a interface.  
- Deslocamentos podem ser implementados por fios e conexões diretas (para deslocamento fixo de 2 bits) ou por um bloco de deslocamento rotativo/logicamente parametrizável para maior flexibilidade.  
- Para operação em sistema real, recomenda-se adicionar buffers e controle de enable/tri-state quando for conectar a barramentos compartilhados.  
- Operações aritméticas devem considerar flags adicionais (carry, zero, overflow) se for necessário para controle em níveis superiores do sistema.

---

## Conclusão

O projeto da **ULA de 8 bits** atende aos requisitos especificados, fornecendo um conjunto amplo de operações lógicas e aritméticas com implementação modular e clara. A arquitetura permite expansão (novas operações, flags, controle condicional) e é adequada para implementação em protótipos com portas discretas, CIs lógicos ou em FPGA.

---
