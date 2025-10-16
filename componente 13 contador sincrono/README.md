# Contador Síncrono

O **contador síncrono** é um circuito digital **sequencial** que realiza a **contagem binária** de forma ordenada, em resposta a pulsos de clock aplicados simultaneamente a todos os flip-flops do sistema.  

Diferentemente dos **contadores assíncronos**, em que o clock é propagado de um flip-flop para outro em cascata, o contador síncrono garante que **todas as transições ocorram ao mesmo tempo**, resultando em maior precisão e velocidade.

<p align="center">
  <img src="./componente%20c13/contador_sincrono.png" alt="Contador síncrono">
</p>

---

## 1. Objetivo do Circuito

O objetivo do circuito é **gerar uma sequência binária crescente** (ou decrescente, dependendo da configuração), de forma síncrona, a partir de pulsos de clock.  

Cada flip-flop representa um bit do contador, e a combinação dos estados desses bits forma o número binário contado.

---

## 2. Estrutura do Circuito

O circuito é composto por:
- **Flip-flops tipo JK** (ou D, dependendo da implementação), acionados por um **clock comum**;  
- **Portas lógicas AND, OR e NOT**, responsáveis por determinar quando cada flip-flop deve alternar de estado;  
- Entradas de **preset** e **clear**, que permitem inicializar ou zerar o contador.

---

### 2.1 Entradas e Saídas

**Entradas:**
- **Clock:** sinal que sincroniza todas as transições do contador.  
- **Preset:** define o estado inicial dos flip-flops (coloca o contador em 1).  
- **Clear:** reinicia o contador para o valor zero.  

**Saídas:**
- **Q₀, Q₁, Q₂, Q₃:** representam os bits do contador (do menos significativo ao mais significativo).  
- Cada saída indica um bit da contagem binária em curso.

---

## 3. Princípio de Funcionamento

1. Todos os flip-flops recebem o **mesmo pulso de clock**, garantindo a comutação simultânea.  
2. A **lógica combinacional** formada por portas AND, OR e NOT define quais flip-flops devem mudar de estado em cada ciclo.  
3. O **primeiro flip-flop (Q₀)** alterna a cada pulso de clock.  
4. Os demais flip-flops alternam somente quando todos os anteriores estão em nível lógico alto (1), o que forma a contagem binária.

---

### 3.1 Sequência de Contagem (para 4 bits)

| Clock | Q₃ | Q₂ | Q₁ | Q₀ | Valor Decimal |
|--------|----|----|----|----|----------------|
| 0 | 0 | 0 | 0 | 0 | 0 |
| 1 | 0 | 0 | 0 | 1 | 1 |
| 2 | 0 | 0 | 1 | 0 | 2 |
| 3 | 0 | 0 | 1 | 1 | 3 |
| 4 | 0 | 1 | 0 | 0 | 4 |
| 5 | 0 | 1 | 0 | 1 | 5 |
| 6 | 0 | 1 | 1 | 0 | 6 |
| 7 | 0 | 1 | 1 | 1 | 7 |
| 8 | 1 | 0 | 0 | 0 | 8 |
| 9 | 1 | 0 | 0 | 1 | 9 |
| ... | ... | ... | ... | ... | ... |

Após atingir o valor máximo (`1111` = 15), o contador retorna a `0000`, reiniciando o ciclo.

---

## 4. Vantagens do Contador Síncrono

- **Alta velocidade de operação**, pois todos os flip-flops mudam simultaneamente.  
- **Eliminação de atrasos de propagação**, comuns em contadores assíncronos.  
- **Maior precisão temporal**, ideal para aplicações que exigem sincronismo entre múltiplos circuitos.  
- **Facilidade de expansão** para mais bits com mínima alteração lógica.

---

## 5. Aplicações

- **Divisores de frequência** em circuitos de clock;  
- **Temporizadores e cronômetros digitais**;  
- **Sistemas de contagem e medição** em controle industrial;  
- **Controladores sequenciais** em máquinas de estado;  
- **Conversores digitais e multiplexadores**.

---

## 6. Observações Finais

- O **preset** e o **clear** são úteis para inicializar o contador em estados específicos.  
- A **lógica combinacional** deve ser cuidadosamente projetada para garantir a contagem correta.  
- Contadores síncronos podem ser **crescentes (up)**, **decrescentes (down)** ou **bidirecionais (up/down)**, dependendo da lógica empregada.  
- Este circuito é uma das bases para a construção de **contadores programáveis e temporizadores digitais**.

---
