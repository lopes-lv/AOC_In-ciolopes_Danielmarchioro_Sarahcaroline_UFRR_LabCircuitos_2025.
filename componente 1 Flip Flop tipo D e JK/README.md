# Flip Flop Tipo D 

Tem a capacidade de guardar seu último estado podendo assim guardar um bit sendo ele 0 ou 1, quando colocamos a entrada dele para 1 a saída Q dele será alterada para 1 também é a ~Q para zero onde essas duas saídas sempre são opostas e o flip flop faz essa mudança na descida do clock, temos também as entradas de  clear e preset onde o clear vai alterar a entrada Q para 0 independente da entrada ou do clock e o preset ira alterar a saída Q para 1 também seguindo a mesma ideia do clear onde será independente da entrada ou clock 



**Aplicações:** Uso para armazenar um bit sendo essencial para a construção de unidades de memoria 

---

# 1. Objetivo do Circuito

Demostrar o funcionamento de um flip flop do tipo D com clear e preset 
---

## 2. Estrutura do Circuito

### 2.1 Entradas e Saídas
**Entradas:**
- **Clock:** é um sinal de temporização que controla o momento exato em que o flip-flop muda seu estado
- **Clear:** força a saida Q para zero e a ~Q para 1 .
- **Preset:** força a saida Q para 1 e a ~Q para 0.

**Saídas:**
- **Q e ~Q** 


### 2.2 Componentes Principais

- 6 portas NAND.
- 6 pinos de entrada.
- 2 pinos para vizualizamos a saida 
### **Funções dos componentes:**
- Os flip-flops armazenam cada bit da contagem. Um flip-flop T alterna seu estado sempre que sua entrada T está ativa no pulso de clock.
- As portas AND decidem quando cada flip-flop superior deve alternar, com base no estado dos bits inferiores.
- Pinos com display permitem ver a saída em tempo real.

---

## 3. Funcionamento do Circuito

