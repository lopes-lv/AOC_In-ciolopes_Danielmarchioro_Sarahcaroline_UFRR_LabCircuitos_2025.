# Extensor de 4 para 8 Bits

O **extensor de 4 para 8 bits** é um circuito **combinacional** utilizado para **aumentar a largura de um barramento de dados**, expandindo uma palavra binária de **4 bits** para **8 bits**.  

Esse tipo de circuito é comumente empregado em sistemas digitais quando é necessário compatibilizar sinais entre componentes de diferentes tamanhos de barramento, preservando o valor original e preenchendo os bits adicionais de forma controlada (geralmente com zeros ou com sinal).

<p align="center">
  <img src="./imagens%20c11/extensor.png" alt="Extensor de 4 para 8 bits">
</p>

---

## 1. Objetivo do Circuito

O objetivo do circuito é **receber um número binário de 4 bits** e **gerar uma saída de 8 bits**, mantendo os 4 bits originais nas posições menos significativas e completando os bits mais significativos com zeros.  

Assim, o circuito permite que dados de 4 bits sejam utilizados em dispositivos ou módulos que trabalham com palavras de 8 bits.

---

## 2. Estrutura do Circuito

O circuito é composto por:

- **Uma entrada de 4 bits**, representando o valor original;  
- **Um conjunto de fios diretos**, conectando os bits de entrada às quatro posições menos significativas da saída (bits 0 a 3);  
- **Conexões fixadas em nível lógico 0 (terra)**, conectadas aos bits mais significativos (bits 4 a 7), de modo a completar o barramento de 8 bits.

---

### 2.1 Entradas e Saídas

**Entradas:**
- **E[3:0]:** Palavra binária de 4 bits.

**Saídas:**
- **S[7:0]:** Palavra binária expandida para 8 bits.

---

## 3. Funcionamento

O funcionamento do circuito é simples e direto:

1. Os **quatro bits da entrada** são transferidos diretamente para as **quatro posições menos significativas da saída (S0 a S3)**.  
2. As **quatro posições mais significativas (S4 a S7)** são fixadas em nível lógico baixo (`0`).  
3. Dessa forma, o valor de saída corresponde exatamente ao valor de entrada, mas em formato de 8 bits.

### Exemplo:

| Entrada (4 bits) | Saída (8 bits) |
|------------------|----------------|
| 0000 | 00000000 |
| 0001 | 00000001 |
| 0101 | 00000101 |
| 1010 | 00001010 |
| 1111 | 00001111 |

---

## 4. Aplicações

- **Interligação de sistemas digitais** com barramentos de diferentes tamanhos (4 bits → 8 bits);  
- **Expansão de dados** para compatibilidade com memórias ou registradores de maior largura;  
- **Conversão de formatos binários** em processadores e microcontroladores;  
- **Pré-processamento de sinais digitais** para circuitos aritméticos e lógicos de maior capacidade.

---

## 5. Variações Possíveis

- **Extensão por sinal (Sign Extension):** em sistemas que utilizam números binários com sinal (complemento de dois), o bit mais significativo (bit de sinal) pode ser replicado nas novas posições mais altas, em vez de preenchê-las com zero.  
- **Extensão por zero (Zero Extension):** utilizada neste circuito, onde todos os bits adicionados são zeros.

---

## 6. Observações Finais

- Este circuito é **puramente combinacional**, não possuindo elementos de memória.  
- A implementação é simples e eficiente, sendo frequentemente utilizada em **interfaces de barramento** e **operações lógicas de baixo nível**.  
- A expansão garante compatibilidade entre dispositivos de diferentes larguras de dados sem alterar o valor numérico da informação original.

---
