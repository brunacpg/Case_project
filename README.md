# **Definição do Problema**

## **Objetivo**
O objetivo deste projeto é aplicar técnicas de Processamento de Linguagem Natural (NLP) para analisar as avaliações dos consumidores da Amazon. Isso inclui:
1. **Análise de Sentimentos**: Identificar se as avaliações expressam satisfação ou insatisfação (polaridade positiva ou negativa).
2. **Extração de Tópicos**: Descobrir os principais temas abordados nas avaliações (ex.: qualidade, preço, entrega).

Essa análise ajudará a entender os fatores que contribuem para boas ou más avaliações, oferecendo insights valiosos que podem ser usados para melhorar a experiência do cliente e os produtos.

## **Descrição do Problema**
Os consumidores frequentemente compartilham suas opiniões em plataformas como a Amazon, onde deixam feedbacks detalhados sobre produtos. Essas avaliações contêm informações valiosas, mas não estruturadas, que podem ser usadas para responder a questões como:
- Quais fatores levam à satisfação ou insatisfação dos clientes?
- Como as avaliações se correlacionam com a pontuação geral dos produtos?
- Quais palavras-chave ou tópicos são mais comuns em avaliações positivas e negativas?

Para explorar essas questões, utilizaremos técnicas modernas de NLP, como análise de sentimentos e modelagem de tópicos, em conjunto com o dataset disponível.

## **Premissas e Hipóteses**
- **Premissas**:
  - Avaliações com pontuação alta (4 ou 5) representam satisfação, enquanto pontuações baixas (1 ou 2) indicam insatisfação.
  - Os textos das avaliações contêm informações mais detalhadas sobre o que os consumidores gostam ou não nos produtos.
- **Hipóteses**:
  - Palavras relacionadas a "qualidade", "preço" e "funcionalidade" aparecem com frequência em avaliações positivas.
  - Problemas de "durabilidade" ou "descrições enganosas" são mencionados em avaliações negativas.

## **Restrições e Condições**
- **Tamanho do dataset**: Este conjunto de dados contém 568.454 avaliações, o que é suficiente para análises robustas, mas pode exigir estratégias de amostragem ou otimização de recursos.
- **Foco na análise textual**: As colunas `Summary` e `Text` serão as principais fontes de informações textuais. A coluna `Score` será usada como rótulo para classificação de sentimentos.
- **Restrições técnicas**: Trabalhar com dados textuais pode ser computacionalmente caro. Usaremos estratégias otimizadas e modelos pré-treinados para eficiência.

## **Descrição do Dataset**
- **Total de Registros**: 28.423
- **Total de Colunas**: 10
- **Atributos Disponíveis**:
  1. **Id**: Identificador único da avaliação.
  2. **ProductId**: Identificador do produto avaliado.
  3. **UserId**: Identificador do usuário que escreveu a avaliação.
  4. **ProfileName**: Nome do perfil do usuário.
  5. **HelpfulnessNumerator**: Número de pessoas que acharam a avaliação útil.
  6. **HelpfulnessDenominator**: Total de pessoas que avaliaram a utilidade do feedback.
  7. **Score**: Nota dada ao produto (1 a 5).
  8. **Time**: Data da avaliação em formato timestamp.
  9. **Summary**: Resumo curto da avaliação.
  10. **Text**: Texto completo da avaliação, com detalhes sobre a opinião do cliente.

## **Processamento de Linguagem Natural**
- **Análise de Sentimentos**:
  - Transformaremos as avaliações textuais (`Text`) em um problema de classificação, usando `Score` como variável alvo.
  - Exemplo: 4 e 5 → Positivo, 1 e 2 → Negativo, e 3 → Neutro ou descartado.
- **Extração de Tópicos**:
  - Descobriremos os tópicos mais frequentes nas avaliações (ex.: "qualidade", "entrega") 
