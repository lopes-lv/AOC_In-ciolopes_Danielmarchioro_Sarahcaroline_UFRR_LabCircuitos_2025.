# Banco de Registradores

O **Banco de Registradores** é um conjunto de **registradores interligados**, projetado para armazenar e disponibilizar **dados temporários** em sistemas digitais, como **CPUs e processadores**.  
Seu funcionamento é baseado no uso de **flip-flops tipo D**, **decodificadores** e **multiplexadores**, permitindo **leitura e escrita seletiva** em registradores específicos.

<p align="center">
  <img src="./imagens%20c7/Banco_registradores.png" alt="Circuito completo do banco de registradores">
</p>

---

## 1. Objetivo do Circuito

O circuito tem como objetivo **armazenar múltiplos valores binários** em registradores independentes, possibilitando o **acesso controlado** a um registrador específico através de **endereçamento** e **seleção de leitura e escrita**.

---

## 2. Estrutura do Banco de Registradores

O sistema é composto por quatro blocos principais:

1. **Decodificador de 2 bits:** seleciona qual registrador será habilitado para escrita.  
2. **Flip-Flops tipo D:** elementos básicos de armazenamento que compõem cada registrador.  
3. **Multiplexador 4x1:** seleciona qual registrador terá seu valor exibido na saída.  
4. **Registradores:** unidades de armazenamento compostas por flip-flops tipo D conectados em paralelo.

---

### 2.1 Entradas e Saídas

**Entradas:**
- **Sel (A1, A0):** Seleciona o registrador ativo para leitura ou escrita.  
- **WE (Write Enable):** Define o modo de operação:
  - `1` → Habilita escrita no registrador selecionado.  
  - `0` → Desabilita escrita, permitindo apenas leitura.  
- **Clock:** Controla o momento em que os dados são armazenados.  
- **D (entrada de dados):** Valor binário a ser escrito no registrador.

**Saídas:**
- **Q (saída):** Exibe o conteúdo do registrador selecionado pelo multiplexador.

---

## 3. Decodificador de 2 Bits

O **decodificador** recebe um código binário de 2 bits e **ativa uma única linha de saída**, correspondente ao registrador selecionado.  
Esse componente é essencial para **controlar qual registrador** será atualizado durante uma operação de escrita.

<p align="center">
  <img src="./imagens%20c7/Decodificador2bits.png" alt="Decodificador de 2 bits usado no banco de registradores">
</p>

| Entradas (A1 A0) | Saída Ativa | Registrador Selecionado |
|------------------|-------------|--------------------------|
| 00 | 1ª linha | R0 |
| 01 | 2ª linha | R1 |
| 10 | 3ª linha | R2 |
| 11 | 4ª linha | R3 |

---

## 4. Flip-Flop Tipo D

O **flip-flop tipo D** é o elemento fundamental de armazenamento binário.  
Cada flip-flop armazena **um único bit**, e vários deles combinados formam um registrador.

<p align="center">
  <img src="./imagens%20c7/flip_flop_D.png" alt="Flip-flop tipo D usado no projeto">
</p>

### Funcionamento:
- O valor da **entrada D** é armazenado na **borda de subida do clock**, caso o **sinal de habilitação** esteja ativo.  
- A saída **Q** mantém o último valor armazenado até a próxima atualização.

---

## 5. Multiplexador 4x1

O **multiplexador 4x1** é responsável por **selecionar qual registrador** terá seu valor enviado à saída do banco.  
As **entradas de seleção (A1, A0)** definem qual das quatro entradas de dados será encaminhada.

<p align="center">
  <img src="./imagens%20c7/multiplexador4x1.png" alt="Multiplexador 4x1 do banco de registradores">
</p>

### Tabela de Seleção:
| Seleção (A1 A0) | Saída |
|------------------|--------|
| 00 | D0 |
| 01 | D1 |
| 10 | D2 |
| 11 | D3 |

---

## 6. Registrador

Cada **registrador** é composto por **flip-flops tipo D** que armazenam os bits de um dado binário.  
Eles são controlados por sinais de **clock** e **habilitação**, que determinam **quando** o valor é atualizado.

<p align="center">
  <img src="./imagens%20c7/registrador.png" alt="Registrador do banco de registradores">
</p>

### Funcionamento:
- Quando **WE = 1** e o **decodificador** seleciona o registrador, o valor na entrada é **armazenado** nos flip-flops.  
- Quando **WE = 0**, o valor armazenado é **mantido** até que uma nova escrita ocorra.  
- O **multiplexador 4x1** seleciona qual saída de registrador será exibida no terminal **Q**.

---

## 7. Funcionamento do Circuito Completo

<p align="center">
  <img src="./imagens%20c7/Banco_registradores.png" alt="Circuito completo do banco de registradores">
</p>

1. O **decodificador** ativa apenas o registrador selecionado por **Sel (A1, A0)**.  
2. O **sinal WE** define se haverá **escrita** (`1`) ou **leitura** (`0`).  
3. Os **flip-flops tipo D** armazenam os dados binários quando ocorre o pulso de **clock**.  
4. O **multiplexador 4x1** define qual registrador terá seu valor enviado à **saída Q**.  

---

## 8. Aplicações

- Implementação de **bancos de registradores** em **CPUs e microcontroladores**.  
- **Armazenamento intermediário** em unidades de processamento digital.  
- **Buffers de dados** e **pipelines** em sistemas embarcados.  
- Simulação de **arquiteturas RISC e CISC** em ambientes de ensino.

---

## 9. Observações Finais

- O circuito pode ser **expandido** facilmente para 8, 16 ou mais registradores, bastando ampliar o **decodificador** e o **multiplexador**.  
- O uso de **flip-flops tipo D** garante **armazenamento estável** e **atualização sincronizada**.  
- O projeto demonstra claramente os princípios de **endereçamento, seleção e controle** de dados em sistemas digitais.
