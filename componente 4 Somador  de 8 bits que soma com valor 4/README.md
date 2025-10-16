# Somador de 8 Bits com Soma Constante de 4

O **somador de 8 bits** é um circuito combinacional capaz de realizar a **adição binária** entre dois números de 8 bits.  
Neste caso específico, o circuito **soma constantemente o valor `00000100` (decimal 4)** à entrada **A**, produzindo uma saída de 8 bits com o resultado dessa operação.

<p align="center">
  <img src="./imagens%20c4/somador_de_8_bits_com_numero_4.png" alt="Somador de 8 bits com número 4">
</p>

---

## 1. Objetivo do Circuito

O objetivo do circuito é **realizar a soma de um número binário de 8 bits (entrada A)** com o valor **fixo 4 (00000100)**, gerando como saída o resultado binário correspondente.  
Esse tipo de circuito é útil em sistemas digitais que necessitam **incrementar um valor fixo** constantemente, como contadores, endereçadores e processadores.

---

## 2. Estrutura do Circuito

O circuito é composto por **oito somadores bit a bit (full adders)** conectados em série, formando um **somador completo de 8 bits**.  
Cada somador processa um bit da entrada A e o bit correspondente do número constante 00000100.

---

### 2.1 Entradas e Saídas

**Entrada:**
- **A[7:0]:** Palavra binária de 8 bits a ser somada com o valor constante 00000100.

**Saída:**
- **S[7:0]:** Resultado da soma (A + 00000100).  
- **Cout:** Bit de carry (vai-um) da soma do bit mais significativo (indicativo de overflow).

---

## 3. Componentes Principais

### 3.1 Somador Bit a Bit (Full Adder)

O **somador completo** (ou **somador bit a bit**) é o bloco básico que realiza a soma de **dois bits de entrada** e um **bit de carry de entrada**, produzindo:
- Um **bit de soma (S)**;
- Um **bit de carry de saída (Cout)**.

<p align="center">
  <img src="./imagens%20c4/somador_bit_a_bit.png" alt="Somador bit a bit">
</p>

A tabela verdade do somador completo é:

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

---

### 3.2 Estrutura do Somador de 8 Bits

O somador completo de 8 bits é construído pela **interligação de 8 somadores bit a bit**, onde o **carry de saída de cada estágio** é conectado ao **carry de entrada do estágio seguinte**.  
A única diferença neste circuito é que o **segundo bit (bit 2)** recebe o valor 1 correspondente ao **número fixo 4 (00000100)**, enquanto os demais bits do número constante são 0.

---

## 4. Funcionamento do Circuito

1. A entrada **A[7:0]** é aplicada aos somadores.  
2. O valor **00000100** é aplicado à outra entrada do somador.  
3. Cada somador bit a bit realiza a soma local considerando o carry de entrada.  
4. O resultado final **S[7:0]** representa **A + 4**.  
5. Caso o resultado ultrapasse 8 bits, o **carry de saída (Cout)** é ativado.

---

## 5. Aplicações

- Incrementadores de contadores digitais.  
- Atualização de endereços em memórias.  
- Operações aritméticas simples em microprocessadores.  
- Circuitos de controle que exigem aumento constante de valores binários.  

---

## 6. Observação

O circuito pode ser facilmente adaptado para **somar qualquer valor constante**, bastando alterar as entradas fixas correspondentes aos bits desejados.
