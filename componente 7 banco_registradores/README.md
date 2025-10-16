# Banco de Registradores de 8 Bits

O **banco de registradores de 8 bits** é um circuito digital **sequencial** utilizado para armazenar e recuperar informações binárias de forma controlada.  
Ele é composto por **8 registradores de 8 bits** e **dois multiplexadores 8x1 de 8 bits**, permitindo que diferentes posições de memória interna sejam acessadas conforme um endereço binário e sinais de controle de **leitura (READ)** e **escrita (WRITE)**.

<p align="center">
  <img src="./imagens c7/main.png" alt="Banco de Registradores de 8 bits">
</p>

---

## 1. Objetivo do Circuito

O objetivo do circuito é **armazenar dados temporários** em registradores e permitir a **leitura ou gravação** em um endereço específico, com controle total sobre qual registrador está sendo acessado.

Ele serve como **memória interna** para sistemas digitais, **ULAs**, **processadores** e **controladores lógicos**, possibilitando manipulação de dados intermediários com rapidez e simplicidade.

---

## 2. Estrutura do Circuito

O circuito é composto por três blocos principais:

- **Registradores de 8 bits:** armazenam os dados binários de entrada.  
- **Multiplexadores 8x1 de 8 bits:** selecionam qual registrador será lido ou escrito.  
- **Sinais de controle (READ e WRITE):** determinam a operação ativa no ciclo de clock.

<p align="center">
  <img src="./imagens c7/multiplexador.png" alt="Multiplexador 8x1 de 8 bits">
</p>

Cada registrador possui entradas e saídas conectadas aos multiplexadores, que, com base no endereço de 3 bits, definem qual registrador será acessado.

---

### 2.1 Entradas e Saídas

**Entradas:**
- **IN[7:0]:** Dados de 8 bits a serem armazenados.  
- **ADDR[2:0]:** Endereço do registrador (0 a 7).  
- **WRITE:** Ativa a escrita dos dados na posição selecionada.  
- **READ:** Ativa a leitura do registrador selecionado.  

**Saídas:**
- **OUT[7:0]:** Dados de 8 bits lidos do registrador ativo.  

---

## 3. Funcionamento do Banco de Registradores

1. **Escrita:**  
   Quando o sinal **WRITE** está ativo, o conteúdo presente na entrada **IN** é armazenado no registrador indicado por **ADDR**.

2. **Leitura:**  
   Quando o sinal **READ** está ativo, o valor armazenado no registrador selecionado é enviado para a saída **OUT**.

3. **Manutenção:**  
   Quando nem WRITE nem READ estão ativos, os registradores mantêm seus valores atuais, preservando os dados até uma nova operação.

<p align="center">
  <img src="./imagens c7/flip_flop_d.png" alt="Flip-flop D usado no registrador">
</p>

---

## 4. Estrutura Interna do Registrador

Cada registrador é formado por **8 flip-flops tipo D**, responsáveis por armazenar individualmente cada bit.  
O controle de **Enable** garante que apenas o registrador selecionado seja alterado durante a escrita.

<p align="center">
  <img src="./imagens c7/flip_flop_jk.png" alt="Registrador de 1 Byte com Enable">
</p>

---

## 5. Funcionamento Lógico Simplificado

A operação geral pode ser descrita pelas seguintes regras:

\[
\text{Se WRITE = 1: } R[ADDR] = IN
\]

\[
\text{Se READ = 1: } OUT = R[ADDR]
\]

\[
\text{Se WRITE = 0 e READ = 0: } R[n] = R[n]
\]

Essas expressões descrevem o comportamento básico de leitura, escrita e retenção de dados em cada registrador.

---

## 6. Aplicações

O **Banco de Registradores de 8 Bits** é amplamente utilizado em:

- **ULAs (Unidades Lógicas e Aritméticas);**
- **Processadores e Microcontroladores;**
- **Memórias de trabalho temporário (RAM interna);**
- **Sistemas de controle digital e automação.**

---

## 7. Observações Finais

- O uso de **multiplexadores** facilita o acesso seletivo aos registradores.  
- A arquitetura modular permite expansão para **16 ou 32 registradores**.  
- Pode ser integrado facilmente com **ULAs** e **circuitos de controle** para formar uma **arquitetura de processador simples**.  
- A utilização de **flip-flops D** garante estabilidade e confiabilidade no armazenamento dos bits.

---
