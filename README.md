# MVP - Análise de Sentimentos e Extração de Tópicos das Avaliações da Amazon

## 1. Definição do Problema

### 1.1 Objetivo
O objetivo deste projeto é aplicar técnicas de **Processamento de Linguagem Natural (NLP)** para analisar as avaliações dos consumidores da Amazon. As análises incluem:

- **Análise de Sentimentos**: Identificar a polaridade das avaliações (positiva, neutra ou negativa).
- **Extração de Tópicos**: Descobrir os principais temas abordados nas avaliações (ex.: qualidade, preço, entrega).

Esses insights poderão ser usados para:

- Melhorar a experiência do cliente.
- Oferecer feedback direto para aprimorar produtos e serviços.

**Métricas de sucesso sugeridas:**
- **Análise de Sentimentos**: Obter pelo menos 85% de precisão na classificação.
- **Extração de Tópicos**: Identificar ao menos 3 tópicos principais com uma relevância acima de 70%.

---

### 1.2 Descrição do Problema
Os consumidores frequentemente compartilham opiniões detalhadas em avaliações na Amazon, mas essas informações são não estruturadas e difíceis de analisar em escala. Usaremos técnicas de NLP para responder a perguntas como:

- Quais fatores levam à satisfação ou insatisfação dos clientes?
- Quais palavras-chave são mais comuns em avaliações positivas e negativas?
- Como as avaliações se correlacionam com a pontuação geral dos produtos?

---

### 1.3 Premissas e Hipóteses

**Premissas:**
- Avaliações com pontuação alta (4 ou 5) representam satisfação, enquanto pontuações baixas (1 ou 2) indicam insatisfação.
- Textos das avaliações contêm informações valiosas sobre aspectos específicos dos produtos.

**Hipóteses:**
- Palavras relacionadas a "qualidade", "preço" e "funcionalidade" aparecem frequentemente em avaliações positivas.
- Problemas de "durabilidade" ou "descrições enganosas" são recorrentes em avaliações negativas.

**Validação das Hipóteses:**
- Realizaremos uma análise de frequência de palavras em cada categoria de sentimento.
- Compararemos os tópicos extraídos com as hipóteses iniciais.

---

### 1.4 Restrições e Condições

**Tamanho do Dataset:**
- Contém **28.423 avaliações**, sendo necessário considerar estratégias de amostragem.

**Recursos Computacionais:**
- Modelos NLP podem ser computacionalmente caros. Priorizaremos eficiência com técnicas como:
  - **TF-IDF** para vetorização de texto.
  - Modelos pré-treinados para reduzir o custo computacional.
  - Amostragem para trabalhar com dados menores durante a prototipação.

---

## Conclusão da Estrutura

- Essa estrutura segue corretamente o objetivo de um **MVP** para análise de sentimentos e extração de tópicos com NLP.
- Está alinhada com os requisitos de um projeto acadêmico ou prático.
- Permite aprofundar nas etapas de análise e validação com modelos.
