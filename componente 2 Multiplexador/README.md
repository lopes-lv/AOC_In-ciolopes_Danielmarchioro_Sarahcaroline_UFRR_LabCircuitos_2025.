# Multiplexador 4x1

O multiplexador (MUX) é um circuito digital combinacional que seleciona **uma entre várias entradas de dados** e a direciona para **uma única saída**, de acordo com o valor das linhas de seleção.

<p align="center">
  <img src="./imagens%20c2/multiplexador.png" alt="MUX">
</p>

---

## 1. Objetivo do Circuito

O objetivo do multiplexador é **selecionar um dos sinais de entrada** para ser enviado à saída, **com base no valor das entradas de seleção**.  
Ele funciona como uma "chave digital", permitindo o controle de qual dado será transmitido.

---

## 2. Estrutura do Circuito

### 2.1 Entradas e Saídas
**Entradas:**
- **I0, I1, I2, I3:** Entradas de dados (4 sinais possíveis).  
- **S0 e S1:** Entradas de seleção, definem qual entrada será enviada à saída.  

**Saída:**
- **Y:** Saída única do multiplexador, que mostra o valor da entrada selecionada.

---

## 3. Componentes Principais

- **Portas AND:** Cada combinação de seleção ativa uma das quatro portas AND, correspondendo a uma entrada de dados.  
- **Portas NOT:** Usadas para inverter os sinais de seleção, permitindo gerar todas as combinações possíveis de S1 e S0.  
- **Porta OR:** Combina as saídas das portas AND, garantindo que apenas o sinal da entrada selecionada apareça na saída final.

---

## 4. Tabela de Seleção

| S1 | S0 | Entrada selecionada |
|----|----|----------------------|
| 0  | 0  | I0 |
| 0  | 1  | I1 |
| 1  | 0  | I2 |
| 1  | 1  | I3 |

---

## 5. Aplicações

- Seleção de dados em sistemas digitais.  
- Roteamento de sinais em processadores e controladores lógicos.  
- Implementação de funções lógicas complexas.  
- Controle de fluxo de dados em sistemas de comunicação.

---

Projeto desenvolvido em Logisim / Digital.
