# Análise de Sentimentos e Tópicos nas Avaliações da Amazon

## **Definição do Problema**
O objetivo deste projeto é analisar as avaliações dos clientes da Amazon para identificar padrões de satisfação e insatisfação. A análise ajudará a compreender os fatores que levam a avaliações positivas ou negativas, oferecendo insights valiosos para melhorar produtos e serviços.

### **Premissas e Hipóteses**
- Avaliações com alta polaridade (positivas) contêm fatores que contribuem para a satisfação dos clientes, como qualidade, preço acessível ou entrega rápida.
- Avaliações negativas destacam problemas recorrentes, como falhas no produto, atrasos na entrega ou descrições enganosas.
- A polaridade das avaliações está associada à qualidade do produto, representada pela nota atribuída pelos usuários.

### **Restrições e Condições**
- Este projeto usa apenas os textos das avaliações, ignorando dados adicionais como categorias de produtos ou imagens.
- Focamos exclusivamente em duas classes: avaliações positivas e negativas. Avaliações neutras (pontuação 3) são descartadas.

### **Descrição do Dataset**
- **Origem**: Dataset de polaridade das avaliações da Amazon.
- **Atributos Principais**:
  - `polarity`: Polaridade da avaliação (1 = Negativo, 2 = Positivo).
  - `title`: Título da avaliação.
  - `text`: Corpo da avaliação.
- **Tamanho**:
  - Treinamento: 1.800.000 registros por classe.
  - Teste: 200.000 registros por classe.
