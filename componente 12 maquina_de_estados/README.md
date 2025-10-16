# Máquina de Estados (Flip-Flop JK)

A **máquina de estados** é um circuito **sequencial** capaz de armazenar e alterar seu estado interno em função de **entradas** e de seu **estado anterior**.  
Neste projeto, a máquina é implementada utilizando um **flip-flop JK**, que representa a forma mais simples de uma máquina de estados finitos.

<p align="center">
  <img src="./imagens%20c12/maquina_estados.png" alt="Máquina de estados implementada com flip-flop JK">
</p>

---

## 1. Objetivo do Circuito

O objetivo do circuito é **demonstrar o funcionamento básico de uma máquina de estados**, utilizando um **flip-flop JK** como elemento de memória e controle de transição entre estados.  

Essa máquina é capaz de **alternar entre dois estados (0 e 1)** conforme as condições aplicadas às entradas **J** e **K**, sendo um excelente exemplo introdutório ao estudo de sistemas sequenciais.

---

## 2. Estrutura do Circuito

O circuito é composto por:

- **Um flip-flop JK**, que representa a memória da máquina de estados;  
- **Entradas J e K**, que determinam as condições de transição entre os estados;  
- **Um sinal de clock**, responsável por sincronizar as mudanças de estado;  
- **Uma saída Q**, que representa o estado atual da máquina.

---

### 2.1 Entradas e Saídas

**Entradas:**
- **J:** Controla a transição do estado 0 para o estado 1.  
- **K:** Controla a transição do estado 1 para o estado 0.  
- **Clock:** Sincroniza a mudança de estado.

**Saída:**
- **Q:** Indica o estado atual da máquina (0 ou 1).

---

## 3. Tabela de Funcionamento do Flip-Flop JK

| J | K | Próximo Estado (Qₙ₊₁) | Descrição |
|---|---|------------------------|------------|
| 0 | 0 | Qₙ | Mantém o estado atual |
| 0 | 1 | 0 | Reseta o estado |
| 1 | 0 | 1 | Seta o estado |
| 1 | 1 | 𝑄̅ₙ | Alterna o estado (toggle) |

---

## 4. Funcionamento da Máquina de Estados

1. A máquina inicia em um estado definido (por exemplo, **Q = 0**).  
2. Conforme as entradas **J** e **K** variam, o flip-flop altera seu estado de acordo com a tabela anterior.  
3. O **sinal de clock** determina o momento exato em que as mudanças ocorrem, garantindo o comportamento sequencial.  
4. O **estado de saída (Q)** pode ser utilizado para acionar outros circuitos ou indicar o estado atual da máquina.

---

## 5. Diagrama de Estados

A máquina de estados implementada com um único flip-flop JK possui dois estados possíveis:

| Estado Atual | Entradas (J,K) | Próximo Estado | Ação |
|---------------|----------------|----------------|------|
| 0 | 1,0 | 1 | Seta o flip-flop |
| 1 | 0,1 | 0 | Reseta o flip-flop |
| 0 ou 1 | 1,1 | Alterna | Inverte o estado atual |
| 0 ou 1 | 0,0 | Mantém | Nenhuma mudança |

Visualmente, o comportamento pode ser descrito como um **autômato de dois estados**:

[Estado 0] ⇄ [Estado 1]
↑ ↓
Mantém

---

## 6. Aplicações

- **Divisores de frequência** (toggle do flip-flop);  
- **Contadores binários básicos**;  
- **Geradores de sinais periódicos**;  
- **Sistemas de controle sequencial simples**;  
- **Estudo e simulação de máquinas de estados finitos (FSMs)**.

---

## 7. Observações Finais

- O **flip-flop JK** é um dos elementos fundamentais para o estudo de circuitos sequenciais.  
- A implementação como **máquina de estados** demonstra claramente como um sistema pode “lembrar” do passado (estado anterior).  
- Com múltiplos flip-flops JK interligados, é possível criar **máquinas de estados mais complexas**, como contadores, registradores e controladores de processo.

---
