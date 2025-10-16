# Porta Lógica XOR (OU Exclusivo)

A porta XOR (Exclusive OR) é um circuito lógico que **retorna nível lógico alto (1)** apenas quando **as entradas são diferentes**.  
Ela é muito usada em operações aritméticas (como somadores) e em circuitos de comparação lógica.

<p align="center">
  <img src="./imagens%20c3/porta_XOR.png" alt="XOR">
</p>

---

## 1. Objetivo do Circuito

A porta XOR tem como função **comparar duas entradas lógicas** e gerar uma saída que indica se elas são diferentes.  
Quando as duas entradas são iguais (00 ou 11), a saída é **0**.  
Quando são diferentes (01 ou 10), a saída é **1**.

---

## 2. Estrutura do Circuito

### 2.1 Entradas e Saída
**Entradas:**
- **A**
- **B**

**Saída:**
- **Y**

### 2.2 Expressão Lógica
\[
Y = A \oplus B = \overline{A}B + A\overline{B}
\]

---

## 3. Tabela Verdade

| A | B | Y |
|---|---|---|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

---

## 4. Implementação com Portas Básicas

A porta XOR pode ser construída usando:
- **2 portas AND**
- **2 portas NOT**
- **1 porta OR**

De forma que:
\[
Y = (A \cdot \overline{B}) + (\overline{A} \cdot B)
\]

---

## 5. Aplicações

- **Somadores de 1 bit** (a saída XOR representa a soma sem carry).  
- **Comparadores lógicos**, para detectar diferença entre bits.  
- **Criptografia e codificação**, em operações de bitwise XOR.  
- **Circuitos aritméticos**, como parte de ALUs e multiplexadores.

---

Projeto desenvolvido em Logisim / Digital.
