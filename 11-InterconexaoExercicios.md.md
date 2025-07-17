
# Organização e Arquitetura de Computadores  
## Lista de Estudos – Barramentos

---

### 1. Multiplexação em Barramentos
- O que caracteriza essa técnica?
R: A Técnica de Multiplexação em barramentos serve para usar as mesmas linha de dados para múltiplas finalidades, como exemplo podemos citar que informações de endereços e dados podem ser transmitidas pelo mesmo conjunto de linhas, usando a linha de controle Adress Valid

- Qual vantagem ela oferece?
R: Quando usamos a técnica de Multiplexação podemos usar menos linhas, economizando espaço e custo na arquitetura
---

### 2. Árbitro de Barramento
- Qual a sua função?
R: A arbitração é responsável pelo controle do uso do barramento em que pode designar um dispositivo como mestre e iniciar uma transferência de dados com outro dispositivo escravo
- Quais as formas de implementação?
R: Centralizado: um único dispostivo chamado de controlador ou arbitro de Barramento é responsável por alocar tempo no barramento, podendo ser um módulo separado ou parte do processador. Distribuído: Não existe controlador central e cada módulo contém lógica de controle de acesso


---

### 3. Tipos de Transferência (conferir)
- Que tipos de transferências um barramento deve suportar?
R: O barramento deve suportar transferências da:
Memoria -> Processador e Processador -> Memória
E/S para Processador e Processador -> E/S
E/S -> Memória


---

### 4. E/S Mapeada em Memória (conferir)
- O que significa esse conceito?
R: Uso de barramento de expansão para isolar o trafego da memória em comparação com o processador do trafego de E/s (bem errada)

---

### 5. Grupos Funcionais de Linhas (conferir oq impacta no barramento de controle a qtdade de linhas)
- Quais são os grupos presentes?
R: Linha de controle, enderaçamento, dados e energia
- Qual o impacto do número de linhas em cada grupo?
R: No barramento de dados, a quantidade de linhas determina a quantidade de bits que podem ser transferidos de uma só vez, caracterizando a largura do barramento de dados, no de endereço a largura máxima define a capacidade de memória maxima possível do sistema, no de controle a quantidade de linhas impacta na quantidade de sinais que o sistema precisa

---

### 6. Processador de 32 bits com instruções de 32 bits
- a) Qual a quantidade de palavras endereçáveis?
R: Como o processador tem 32 bits logo temos 4 Bytes (8 bits cada)  assim podemos usar 3 bytes para endereçamento que representa 24 bits, logo o processador pode endereçar 2^24 = **16.777.216 palavras** (ou 16M palavras).
- b) Qual a capacidade total da memória?
R: Para o cálculo da capacidade usamos a seguinte formula
Capacidade=2^24×4 bytes de endereçamento=16.777.216×4 bytes=67.108.864 bytes


---

### 7. Barramento de Endereço
- Computador com palavras de 16 bits e memória de 2048 bytes.
- Quantas linhas de endereço são necessárias?
R: -   **Tamanho da memória:** 2048 bytes, **Tamanho de cada palavra:** 16 bits = 2 bytes (pois 1 byte = 8 bits), assim 24048 / 2 = 1024 e para endereção 1024 palavras são necessarios 2^10= 1024 então são necessários 10 linhas

---

### 8. Microprocessador de 32 bits, barramento de 16 bits e clock de 8 MHz
- Qual a taxa máxima de transferência de dados?
- O que melhora mais o desempenho: dobrar a frequência ou aumentar a largura do barramento?

---

### 9. Arquitetura de Barramento Múltiplo
- Qual o benefício dessa arquitetura em relação à de barramento único?
R: A vantagem da arquietetura de Barramento Múltiplo é que temos o uso da Hierarquia de barramentos em que se muitos componentes estiverem conectados ao barramento, teremos o desempenho prejudicado, ademais o barramento pode se tornar um gargalo à medida que a demanda de transferência de dados agregada se aproxima da capacidade do barramento, assim dividimos em 
barramento local: conecta CPU a memoria cache
expansão: permite aceitar variedade de dispositivos de E/S e, ao mesmo tempo, isolar o tráfego memória e de sistema.

---

### 10. Ponte Norte e Ponte Sul
- Para que servem na placa-mãe?
R: É uma implementação da Hierarquia de barramentos em que a ponte norte lida com a comunicação de alta velocidade entre o processador, a memória RAM e a placa de vídeo, enquanto a ponte sul gerencia as operações de entrada e saída (I/O) mais lentas, como discos rígidos, portas USB e outros periféricos

---

## Questões Estilo Concurso/POSCOMP

---

### 1. Comunicação com a Ponte Sul
- São barramentos que mantêm comunicação com a ponte sul, **EXCETO**:
  - a) USB  
  - b) PATA  
  - c) PCI Express  (esta pois é uma operação de alta velocidade)
  - d) SATA  
  - e) PCI  

---

### 2. Barramento Frontal
- Qual a principal característica do barramento frontal de um microcomputador?
e) uma via de ligação entre o processador e a memória RAM

---

### 3. Barramento PCI
- Análise de afirmações:
  - I. Conecta periféricos.
  - II. Conecta apenas placas de vídeo.
  - III. Conecta memória principal à placa-mãe.
c) I-V; II-F; III-V.
---

### 4. Transmissão Simultânea
- Verdadeiro ou falso: Dois dispositivos transmitindo ao mesmo tempo terão seus sinais sobrepostos e distorcidos.
R: Verdadeiro


---

### 5. Afirmativas sobre Barramentos
- I. Barramento local conecta processador aos circuitos primordiais.
- II. Barramento local é padronizado para todos os processadores.
- III. ISA e PCI são barramentos de expansão.
- IV. Barramento local se divide em dados, endereço e E/S.

---

### 6. Sobre Barramentos de Computador
- I. Barramentos transportam dados, relógio e endereços, mas não controle.
- II. Barramentos dificultam a adição de novos periféricos.
- III. Protocolo de barramento governa a comunicação.
- IV. Barramentos de memória sempre ligados à CPU.

---

### 7. Julgamento de Afirmativas
- ( ) Linhas de controle, dados e endereço.  
- ( ) Síncrono é melhor para dispositivos com taxas distintas.  
- ( ) Arbitração pode ser centralizada ou distribuída.  
- ( ) Largura do barramento de endereço determina quantidade de bits transferidos.  
- ( ) Barramento multiplexado reduz disputa de acesso.

---

### 8. Hierarquia de Barramentos
- Verdadeiro ou falso: Hierarquia de barramentos melhora o desempenho.

---

### 9. Largura do Barramento de Dados
- Se o barramento tem 32 bits:
  - a) Limita instruções a 32 bits
  - b) Limita dados a 32 bits
  - c) Limita a ambos
  - d) Requer dois acessos para instruções de 64 bits
  - e) Requer acesso à memória estendida

---

### 10. Barramentos Síncronos
- Verdadeiro ou falso: Melhor desempenho entre dispositivos com tempos distintos.
