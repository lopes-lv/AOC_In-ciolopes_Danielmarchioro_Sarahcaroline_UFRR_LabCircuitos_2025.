# Detector de Sequência Binária "101"

O **detector de sequência binária "101"** é um circuito digital **sequencial** projetado para identificar a ocorrência da sequência específica de bits `1-0-1` em um fluxo contínuo de dados binários.  

Esse tipo de circuito é amplamente utilizado em sistemas de **comunicação digital**, **controle lógico** e **processamento de sinais**, onde é necessário detectar padrões específicos de bits em uma sequência.

<p align="center">
  <img src="./imagens%20c9/detector.png" alt="Detector de sequência binária 101">
</p>

---

## 1. Objetivo do Circuito

O objetivo do circuito é **detectar automaticamente a sequência "101"** presente na entrada de dados serial e ativar a **saída de detecção** (bit igual a `1`) sempre que a sequência for reconhecida.

---

## 2. Estrutura do Circuito

O circuito é composto por:
- **Três flip-flops tipo D (FF-D)** conectados em série, formando um **registrador de deslocamento (shift register)**;
- **Portas lógicas AND, OR e NOT** responsáveis por verificar a combinação de bits correspondente à sequência "101";
- **Uma saída (detector)** que indica quando a sequência foi identificada.

---

### 2.1 Entradas e Saídas

**Entrada:**
- **Entrada de Dados (Serial):** fluxo contínuo de bits binários (0 ou 1).

**Saídas:**
- **Detector:** sinal lógico que vale `1` quando a sequência "101" é detectada.  
- **Saídas intermediárias dos flip-flops (Q₁, Q₂, Q₃):** armazenam os três últimos bits recebidos.

---

## 3. Princípio de Funcionamento

1. A **entrada de dados serial** é aplicada ao primeiro flip-flop D, sendo amostrada a cada pulso de **clock**.
2. A cada ciclo de clock, o bit mais recente entra no primeiro flip-flop e os anteriores são deslocados para os seguintes.
3. Assim, os três flip-flops contêm sempre os **três últimos bits recebidos**.
4. As saídas dos flip-flops são analisadas pelas **portas lógicas** para verificar se a combinação é igual a **"101"**:
   - Q₃ = 1  
   - Q₂ = 0  
   - Q₁ = 1  
5. Quando essa combinação ocorre, a saída **Detector** é ativada (`1`).

---

### 3.1 Expressão Lógica da Detecção

A expressão lógica da saída pode ser escrita como:

\[
\text{Detector} = Q_3 \cdot \overline{Q_2} \cdot Q_1
\]

Onde:
- \( Q_3, Q_2, Q_1 \) são as saídas dos flip-flops;
- \( \overline{Q_2} \) representa a negação de \( Q_2 \).

---

## 4. Descrição Passo a Passo

| Ciclo de Clock | Entrada | Estado (Q₃ Q₂ Q₁) | Detector |
|----------------|----------|--------------------|-----------|
| 1 | 1 | 1 0 0 | 0 |
| 2 | 0 | 1 0 0 | 0 |
| 3 | 1 | 1 0 1 | **1** |
| 4 | 0 | 0 1 0 | 0 |
| 5 | 1 | 1 0 1 | **1** |

O detector aciona (`1`) toda vez que o padrão **"101"** aparece nos três últimos bits recebidos.

---

## 5. Tipos de Implementação

O circuito pode ser implementado de duas formas principais:

- **Detector Sobreposto (Overlapping):**  
  Permite que bits de uma sequência detectada participem da próxima (como no exemplo mostrado).

- **Detector Não-Sobreposto (Non-Overlapping):**  
  Recomeça a análise após cada detecção, ignorando sobreposições.

---

## 6. Aplicações

- **Reconhecimento de padrões binários** em comunicações seriais;  
- **Controle de sistemas digitais** baseados em sequências de bits;  
- **Filtros de sinal digital** para detecção de eventos;  
- **Protocolos de comunicação** com códigos de sincronização específicos.

---
