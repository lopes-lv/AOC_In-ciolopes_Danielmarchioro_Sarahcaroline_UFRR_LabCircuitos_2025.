# Detector de Números Primos

O **detector de números primos** é um circuito digital **combinacional** projetado para identificar quando um número binário de **4 bits** representa um **número primo**.  

O circuito verifica o valor de entrada e ativa a saída somente quando o número corresponde a um dos números primos dentro do intervalo de 0 a 15.  

<p align="center">
  <img src="./imagens%20c17/detector_primo.png" alt="Detector de números primos">
</p>

---

## 1. Objetivo do Circuito

O objetivo do circuito é **reconhecer automaticamente números primos** dentro de uma faixa de 4 bits (0 a 15) e gerar uma **saída igual a 1** quando o número de entrada for primo.  

Os números primos entre 0 e 15 são:  
**2, 3, 5, 7, 11, 13.**

---

## 2. Estrutura do Circuito

O circuito é formado por:
- **Entradas binárias A, B, C e D**, que representam o número de 4 bits (0000 a 1111);  
- **Portas lógicas NOT, AND e OR**, responsáveis por identificar as combinações de bits correspondentes aos números primos;  
- **Uma saída lógica única**, que indica se o número é primo (1) ou não (0).

---

### 2.1 Entradas e Saídas

**Entradas:**
- **A (MSB), B, C, D (LSB):** representam o número binário de 4 bits.

**Saída:**
- **Saída:** indica `1` quando o número é primo, e `0` caso contrário.

---

## 3. Princípio de Funcionamento

O circuito combina **portas AND** para detectar os números binários que correspondem aos valores primos e **porta OR** para unir todos esses resultados.  

As combinações de entrada que ativam a saída são:

| Decimal | Binário | Primo? |
|----------|----------|--------|
| 0 | 0000 | Não |
| 1 | 0001 | Não |
| 2 | 0010 | ✔ Sim |
| 3 | 0011 | ✔ Sim |
| 4 | 0100 | Não |
| 5 | 0101 | ✔ Sim |
| 6 | 0110 | Não |
| 7 | 0111 | ✔ Sim |
| 8 | 1000 | Não |
| 9 | 1001 | Não |
| 10 | 1010 | Não |
| 11 | 1011 | ✔ Sim |
| 12 | 1100 | Não |
| 13 | 1101 | ✔ Sim |
| 14 | 1110 | Não |
| 15 | 1111 | Não |

---

### 3.1 Expressão Lógica da Saída

A função booleana pode ser representada pela soma das combinações (forma canônica de soma de produtos):

\[
S = \Sigma(2, 3, 5, 7, 11, 13)
\]

Expandindo a expressão em termos de variáveis A, B, C, D:

\[
S = (\overline{A}\,\overline{B}\,C\,\overline{D}) + (\overline{A}\,\overline{B}\,C\,D) + (\overline{A}\,B\,\overline{C}\,D) + (\overline{A}\,B\,C\,D) + (A\,\overline{B}\,C\,D) + (A\,B\,\overline{C}\,D)
\]

---

## 4. Descrição do Funcionamento

1. As **entradas binárias** são aplicadas simultaneamente às portas lógicas.  
2. Cada **porta AND** representa um número primo específico.  
3. Quando a combinação de entrada coincide com um número primo, a saída dessa porta AND é `1`.  
4. Todas as saídas das portas AND são combinadas por uma **porta OR**, resultando em uma única saída que indica se o número é primo.  

---

## 5. Aplicações

- **Sistemas de identificação e validação digital**;  
- **Circuitos lógicos educacionais** e **laboratórios de aprendizado de lógica digital**;  
- **Módulos de verificação numérica** em controladores digitais;  
- **Processamento de dados binários** em microcontroladores e FPGA.

---
