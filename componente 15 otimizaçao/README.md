# Otimização Lógica Utilizando Mapas de Karnaugh — Somador Completo

Este projeto tem como objetivo **resolver um problema de otimização lógica** por meio do uso de **Mapas de Karnaugh**, aplicando a técnica a um **somador completo (Full Adder)**.  

O somador completo é um circuito digital **combinacional** que realiza a soma de **três bits de entrada**: dois bits de dados (`A` e `B`) e um **carry de entrada** (`Cin`).  
O circuito gera dois resultados: a **soma (S)** e o **carry de saída (Cout)**.  

<p align="center">
  <img src="./imagens%20c15/nao_otimizado.png" alt="Somador completo não otimizado">
</p>

---

## 1. Objetivo do Projeto

O objetivo é demonstrar o processo de **simplificação de expressões booleanas** utilizando **mapas de Karnaugh (K-maps)**, reduzindo o número de portas lógicas necessárias e tornando o circuito mais eficiente em termos de área e tempo de propagação.

---

## 2. Estrutura do Circuito

O circuito do **somador completo** possui:

- **Entradas:**  
  - `A` — primeiro bit a ser somado.  
  - `B` — segundo bit a ser somado.  
  - `Cin` — carry (vai-um) de entrada.

- **Saídas:**  
  - `S` — resultado da soma dos bits.  
  - `Cout` — carry gerado pela soma.

---

## 3. Expressões Não Otimizadas (Forma Original)

A partir da **tabela verdade** do somador completo, temos:

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

Com base nessa tabela, obtemos as **expressões booleanas não simplificadas**:

\[
S = \overline{A}\,\overline{B}\,Cin + \overline{A}\,B\,\overline{Cin} + A\,\overline{B}\,\overline{Cin} + A\,B\,Cin
\]

\[
Cout = A\,B + A\,Cin + B\,Cin
\]

Essas expressões representam o circuito **não otimizado**, mostrado na imagem anterior.

---

## 4. Otimização com Mapas de Karnaugh

A simplificação é feita através de **Mapas de Karnaugh de 3 variáveis**, tanto para a saída `S` quanto para `Cout`.

### 4.1 Mapa de Karnaugh — Saída S

Após agrupar os mintermos correspondentes (1s na tabela), a expressão simplificada resulta em:

\[
S = A \oplus B \oplus Cin
\]

ou seja, a soma é representada por **três portas XOR** em cascata.

### 4.2 Mapa de Karnaugh — Saída Cout

Da mesma forma, simplificando o mapa de `Cout`, obtém-se:

\[
Cout = (A \cdot B) + (A \cdot Cin) + (B \cdot Cin)
\]

Essa expressão já é a **forma mínima**, pois não há redundâncias possíveis.

---

## 5. Circuito Otimizado

Após aplicar a simplificação, obtemos o **circuito otimizado** com menor número de portas lógicas e menor complexidade.

<p align="center">
  <img src="./imagens%20c15/otimizado.png" alt="Somador completo otimizado com mapas de Karnaugh">
</p>

---

## 6. Comparação: Antes e Depois da Otimização

| Aspecto | Não Otimizado | Otimizado |
|----------|---------------|------------|
| Quantidade de termos lógicos | 4 produtos para S | 3 XORs (simplificados) |
| Tipo de portas | AND, OR, NOT | XOR, AND, OR |
| Número de componentes | Maior | Menor |
| Atraso de propagação | Mais alto | Reduzido |
| Consumo lógico | Alto | Baixo |

---

## 7. Aplicações

- **Unidades Lógicas e Aritméticas (ULA)** em microprocessadores;  
- **Somadores acumuladores**;  
- **Contadores e processadores digitais**;  
- **Projetos de circuitos otimizados** para FPGAs e ASICs.

---
