
# Organização e Arquitetura de Computadores
## Aula 2 – Estruturas de Interconexão  
**Prof. Guilherme Galante**

---

## Estruturas de Interconexão

- Um computador é uma rede de módulos básicos:
  - CPU
  - Memória
  - E/S
- É preciso haver caminhos para a conexão dos módulos
- **Estrutura de interconexão**: Coleção de caminhos que conecta os diversos módulos.
- Trocas que precisam ser feitas entre os módulos são importantes para a estrutura.

---

## Transferências de Informações

A estrutura de interconexão deve admitir os seguintes tipos de transferências:

- Memória → CPU: CPU **lê** uma instrução ou dado.
- CPU → Memória: CPU **escreve** uma unidade de dados
- E/S → CPU: CPU **lê dados** de um dispositivo de E/S por meio de um módulo de E/S
- Processador → E/S: CPU **envia dados** para o dispositivo de E/S
- E/S ↔ Memória: troca direta de dados usando **DMA**

---

## Implementações de Interconexão

  1. **Barramentos**
  2. **Interconexões ponto a ponto com transferência de dados em pacotes**

---

## Barramentos

- Caminho de comunicação que conecta dois ou mais dispositivos
- Meio de transmissão **compartilhado**
- Um sinal transmitido por qualquer dispositivo está disponível para
recepção **por todos os outros dispositivos conectados**
- Se **dois dispositivos transmitirem ao mesmo tempo**, **sinais** serão **sobrepostos e distorcidos**
- **Apenas um dispositivo** pode transmitir com sucesso por vez
- **Barramento de sistema**:  Conecta os principais componentes do computador

---

## Estrutura do Barramento

- Conjunto de 50 a centenas de linhas
- Cada linha tem função específica:
  - **Dados**
  - **Endereço**
  - **Controle**
  - (Energia)

---

## Barramento de Dados

- Conjunto: **barramento de dados**
- Pode conter 32, 64, 128+ linhas
- Determina **largura** do barramento ou seja quantos bits podem ser transferidos de uma só vez
- Exemplo:
  - Barramento 32 bits
  - Instrução 64 bits → Necessita 2 acessos/ciclo

---

## Barramento de Endereços

- Usado para designar **origem/destino** dos dados no barramento de dados
- Determina **capacidade máxima de memória**
- Endereça portas de E/S também:
	- bits de ordem mais alta são usados para selecionar um
módulo em particular no barramento
	- bits de ordem mais baixa selecionam um local de memória
ou porta de E/S dentro do módulo

---

## Barramento de Controle

- Controla **uso das linhas de dados e endereços**
- Compartilhado por todos os componentes
- Os sinais de controle transmitem informações de comando e
sincronização entre os módulos do sistema
	- Os sinais de comando especificam operações a serem
realizadas
	- Os sinais de sincronização indicam a validade da informação
de dados e endereço
- Linhas de controle típicas:
  - Escrita/Leitura de memória e E/S
  - Acknowledgement (ACK)
  - Requisição/Concessão de barramento
  - Requisição/Acknowledgement de interrupção
  - Clock e Reset
  
---

## Operação do Barramento

- Módulo que deseja enviar dados precisa:
  1. Obter o uso do barramento
  2. Transferir os dados
 - Se um módulo quiser requisitar dados de outro módulo, ele precisa:
	  1. Obter o uso do barramento
	  2. Transferir uma requisição ao outro módulo pelas linhas de controle e endereço apropriadas
	  3. Esperar que esse segundo módulo envie os dados

---

## Organização Física

- Condutores elétricos paralelos
- Conectam todos os componentes
- Pode haver barramentos:
  - No chip (CPU ↔ Cache)
  - Na placa (CPU ↔ RAM, E/S)

---

## Hierarquia de Barramentos

- Muitos dispositivos → prejuízo de desempenho
- Solução: **hierarquia de barramentos**
  - Barramento local: CPU ↔ Cache
  - Barramento do sistema: RAM
  - Barramentos de expansão: E/S
  - Alta performance com barramentos dedicados

---

## Exemplos Práticos

- **Ponte Norte e Sul** (obsoleto)
- **Chipset unificado** (Intel e AMD)
- **Alder Lake**

---

## Elementos de Projeto

- **Tipo**:
  - Dedicado (linhas fixas)
  - Multiplexado (linhas reutilizadas) para múltiplas finalidades: menos linhas, logo economiza custo
	  - Exemplos: Informações de endereço e dados podem ser transmitidas pelo mesmo conjunto de linhas usando uma linha de controle Address Valid 
- **Arbitração**:
  - Centralizada: Unico disposito é responsável por alocar tempo no barramento
  - Distribuída: Cada módulo contém lógica de controle de acesso
- **Temporização**:
  - Síncrona (determinada com clock)
  - Assíncrona (depende de eventos anteriores)

---

## Largura do Barramento

- Dados: mais bits por vez → mais desempenho
- Endereços: maior capacidade de endereçamento

---

## Interconexão Ponto a Ponto

- Barramentos possuem restrições elétricas encontradas com o aumento da frequência dos sincronizados largos
- Menor latência, maior escalabilidade
- Exemplo: **Intel QPI (QuickPath Interconnect)**

---

## Intel QPI

- Substitui o FSB
- Comunicação ponto a ponto
- Protocolo em camadas
- Transmissão por pacotes
- Camadas: Física, Link, Roteamento, Protocolo
- Alta velocidade: 16~32 GB/s bidirecional

---

## Barramentos de Expansão

- Canal entre dispositivos e o processador
- Exemplos:
  - ISA, EISA, VLB, AGP, PCI, PCIe

---

## PCI (Peripheral Component Interconnect)

- Interface paralela, 32 ou 64 bits
- Temporização síncrona
- Arbitração centralizada
- Plug-and-play
- Largura de banda:
  - 133 MB/s a 1,0 Gb/s (32b)
  - 533 MB/s a 4,2 Gb/s (64b)

---

## PCIe (PCI-Express)

- Interconexão ponto a ponto
- Interface **serial**
- Alta taxa para redes e GPUs
- Escalável: x1, x2, ..., x16, x32

---

## Arquitetura PCIe

- Protocolos em camadas, como QPI
- Conectores variáveis
- Altas taxas de transmissão (bidirecional)

