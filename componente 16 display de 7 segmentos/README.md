# Decodificador de 7 Segmentos

O **decodificador de 7 segmentos** é um circuito digital **combinacional** projetado para converter uma **entrada binária de 4 bits** (0 a 15) nos **sinais de controle necessários** para acionar um **display de 7 segmentos**, exibindo números e letras em **formato hexadecimal (0–F)**.  

Esse tipo de circuito é amplamente utilizado em **painéis digitais**, **temporizadores**, **calculadoras**, **contadores** e outros dispositivos de exibição numérica.

<p align="center">
  <img src="./imagens%20c16/display.png" alt="Decodificador de 7 segmentos (formato hexadecimal)">
</p>

---

## 1. Objetivo do Circuito

O objetivo do circuito é **converter um número binário de 4 bits (de 0000 a 1111)** em sinais lógicos que acendem os **segmentos corretos (a até g)** de um display de 7 segmentos, de forma que o símbolo exibido corresponda ao número ou letra representado pela entrada.

---

## 2. Estrutura do Circuito

O circuito é composto por:
- **Entradas binárias A, B, C, D** (4 bits), representando números de 0 a 15;  
- **Sete saídas lógicas (a, b, c, d, e, f, g)**, cada uma responsável por um segmento do display;  
- **Portas lógicas** (AND, OR, NOT, NAND, NOR) responsáveis por gerar as combinações adequadas para acionar cada segmento de acordo com a entrada binária.

---

### 2.1 Entradas e Saídas

**Entradas:**
- **A (MSB), B, C, D (LSB):** representam um número binário de 4 bits, variando de 0000 (0) a 1111 (15).

**Saídas:**
- **a, b, c, d, e, f, g:** controlam os sete segmentos do display.

| Segmento | Função |
|-----------|---------|
| a | Parte superior |
| b | Lado superior direito |
| c | Lado inferior direito |
| d | Parte inferior |
| e | Lado inferior esquerdo |
| f | Lado superior esquerdo |
| g | Barra central |

---

## 3. Princípio de Funcionamento

O decodificador recebe uma entrada de 4 bits e aciona os segmentos correspondentes para exibir o **símbolo hexadecimal equivalente**:

| Entrada (Binário) | Saída (Hex) | Segmentos acesos |
|--------------------|-------------|------------------|
| 0000 | 0 | a b c d e f |
| 0001 | 1 | b c |
| 0010 | 2 | a b d e g |
| 0011 | 3 | a b c d g |
| 0100 | 4 | b c f g |
| 0101 | 5 | a c d f g |
| 0110 | 6 | a c d e f g |
| 0111 | 7 | a b c |
| 1000 | 8 | a b c d e f g |
| 1001 | 9 | a b c d f g |
| 1010 | A | a b c e f g |
| 1011 | b | c d e f g |
| 1100 | C | a d e f |
| 1101 | d | b c d e g |
| 1110 | E | a d e f g |
| 1111 | F | a e f g |

---

## 4. Expressões Lógicas Simplificadas

Cada segmento pode ser representado por uma **expressão booleana** obtida a partir de mapas de Karnaugh (K-map).  
Por exemplo:

\[
a = \overline{B} \, \overline{D} + A \, \overline{C} + B \, C + A \, \overline{B}
\]
\[
b = A \, \overline{B} + \overline{A} \, B \, \overline{C} + B \, \overline{D}
\]
\[
g = A \, B + \overline{A} \, C + B \, \overline{C} + C \, \overline{D}
\]

*(Essas expressões são exemplos genéricos e podem variar conforme a otimização do circuito.)*

---

## 5. Funcionamento Visual

O display de 7 segmentos possui **LEDs individuais** organizados de modo a formar dígitos.  
O decodificador controla quais LEDs acendem conforme o valor binário de entrada.  

Por exemplo:
- Entrada `0101` (5) → segmentos `a, c, d, f, g` acesos.  
- Entrada `1101` (D) → segmentos `b, c, d, e, g` acesos.

---

## 6. Tipos de Displays

- **Anodo comum:** todos os anodos dos LEDs são conectados ao Vcc; os segmentos são acionados com nível lógico **0 (LOW)**.  
- **Catodo comum:** todos os catodos são conectados ao GND; os segmentos são acionados com nível lógico **1 (HIGH)**.

O tipo do display define a polaridade das saídas do decodificador.

---

## 7. Aplicações

- **Painéis de exibição numérica** (contadores, cronômetros, relógios digitais);  
- **Instrumentos de medição eletrônicos**;  
- **Conversores binário-decimal e binário-hexadecimal**;  
- **Interfaces homem-máquina** simples e visuais.

---
