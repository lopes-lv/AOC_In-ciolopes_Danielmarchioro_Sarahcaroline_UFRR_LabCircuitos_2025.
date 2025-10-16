# Flip-Flops Tipo D e JK

Os flip-flops são circuitos digitais usados como unidades de memória, capazes de armazenar 1 bit de informação. Eles operam com base em sinais de entrada e em um sinal de clock, que determina o momento em que o dado é registrado ou alterado.

---

## Flip-Flop Tipo D

### Função
O flip-flop tipo D armazena o valor presente na entrada D no instante do pulso de clock. Quando o clock é ativado, o valor de D é transferido para a saída Q.

### Entradas e Saídas
- **D (Data):** Bit de entrada a ser armazenado.  
- **Clock:** Controla o momento da amostragem.  
- **Preset:** Força a saída Q = 1.  
- **Clear:** Força a saída Q = 0.  
- **Q / Q̅:** Saída normal e saída inversa.

### Aplicações
Registradores, memórias básicas, máquinas de estados e deslocadores de bits.

---

## Flip-Flop Tipo JK

### Função
O flip-flop tipo JK é uma evolução do tipo SR. As entradas J e K controlam o comportamento da saída Q de acordo com a tabela abaixo:

| J | K | Ação sobre Q |
|---|---|---------------|
| 0 | 0 | Mantém o estado anterior |
| 0 | 1 | Reseta (Q = 0) |
| 1 | 0 | Seta (Q = 1) |
| 1 | 1 | Inverte (toggle) |

### Entradas e Saídas
- **J / K:** Entradas de controle do estado.  
- **Clock:** Controla quando o estado muda.  
- **Preset:** Força a saída Q = 1.  
- **Clear:** Força a saída Q = 0.  
- **Q / Q̅:** Saída normal e saída inversa.

### Aplicações
Contadores binários, controladores de estado e divisores de frequência.

---

## Objetivo do Circuito
Criar sistemas sequenciais capazes de armazenar e controlar estados de forma sincronizada com o clock.

---

Projeto desenvolvido no Logisim.
