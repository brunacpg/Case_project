# MVP - Análise de Sentimentos e Extração de Tópicos das Avaliações da Amazon

## 1. Definição do Problema

### 1.1 Objetivo
O objetivo deste projeto é aplicar técnicas de **Processamento de Linguagem Natural (NLP)** para analisar as avaliações dos consumidores da Amazon. As análises incluem:

- **Análise de Sentimentos**: Identificar a polaridade das avaliações (positiva, neutra ou negativa).
- **Extração de Tópicos**: Descobrir os principais temas abordados nas avaliações (ex.: qualidade, preço, entrega).

Esses insights poderão ser usados para:
- Melhorar a experiência do cliente.
- Oferecer feedback direto para aprimorar produtos e serviços.

**Métricas de sucesso sugeridas**:
1. **Análise de Sentimentos**: Obter pelo menos 85% de precisão na classificação.
2. **Extração de Tópicos**: Identificar ao menos 3 tópicos principais com uma relevância acima de 70%.

---

### 1.2 Descrição do Problema
Os consumidores frequentemente compartilham opiniões detalhadas em avaliações na Amazon, mas essas informações são não estruturadas e difíceis de analisar em escala. Usaremos técnicas de NLP para responder a perguntas como:
- Quais fatores levam à satisfação ou insatisfação dos clientes?
- Quais palavras-chave são mais comuns em avaliações positivas e negativas?
- Como as avaliações se correlacionam com a pontuação geral dos produtos?

---

### 1.3 Premissas e Hipóteses

**Premissas**:
1. Avaliações com pontuação alta (4 ou 5) representam satisfação, enquanto pontuações baixas (1 ou 2) indicam insatisfação.
2. Textos das avaliações contêm informações valiosas sobre aspectos específicos dos produtos.

**Hipóteses**:
1. Palavras relacionadas a "qualidade", "preço" e "funcionalidade" aparecem frequentemente em avaliações positivas.
2. Problemas de "durabilidade" ou "descrições enganosas" são recorrentes em avaliações negativas.

**Validação das Hipóteses**:
- Realizaremos uma análise de frequência de palavras em cada categoria de sentimento.
- Compararemos os tópicos extraídos com as hipóteses iniciais.

---

### 1.4 Restrições e Condições

- **Tamanho do Dataset**: Contém 28.423 avaliações, sendo necessário considerar estratégias de amostragem.
- **Recursos Computacionais**: Modelos NLP podem ser computacionalmente caros. Priorizaremos eficiência com técnicas como:
  - **TF-IDF** para vetorização de texto.
  - **Modelos pré-treinados** para reduzir o custo computacional.
  - **Amostragem** para trabalhar com dados menores durante a prototipação.

---

### Conclusão da Estrutura
Essa estrutura segue corretamente o objetivo de um MVP para análise de sentimentos e extração de tópicos com NLP.
- Está alinhada com os requisitos de um projeto acadêmico ou prático.
- Permite aprofundar nas etapas de análise e validação com modelos.

## Bloco 2: Carregar e Preparar os Dados

### Explicação

Carregamos o dataset e realizamos o pré-processamento:
- Filtramos as colunas relevantes (`Score` e `Text`).
- Removemos valores nulos e duplicados.
- Excluímos avaliações neutras (`Score == 3`).
- Mapeamos as pontuações para rótulos binários:
  - `0` (negativo)
  - `1` (positivo).
- Exibimos a distribuição dos sentimentos.

### Código

```python
# 1. Carregar e preparar os dados
df = pd.read_csv('amostra.csv')

# Contar as linhas antes do tratamento
initial_count = len(df)

# Filtrar colunas relevantes
df = df[['Score', 'Text']]

# Remover valores nulos e duplicados
df.dropna(inplace=True)
df.drop_duplicates(inplace=True)

# Contar as linhas após o tratamento
final_count = len(df)
print(f"Linhas removidas: {initial_count - final_count}")
print(f"Linhas restantes: {final_count}")

# Excluir avaliações neutras
df = df[df['Score'] != 3]

# Mapear Score para Sentimento (0: Negativo, 1: Positivo)
df['Sentiment'] = df['Score'].map({1: 0, 2: 0, 4: 1, 5: 1})

# Exibir a distribuição de sentimentos
print(f"Linhas removidas: {initial_count - final_count} (antes: {initial_count}, depois: {final_count})")
print("\nDistribuição dos Sentimentos:")
print(df['Sentiment'].value_counts())

df['Sentiment'].value_counts().plot(kind='bar', title='Distribuição dos Sentimentos', figsize=(6,4))
plt.xlabel('Sentimento')
plt.ylabel('Quantidade')
plt.show()
```

### Resultado

![Distribuição dos Sentimentos](https://raw.githubusercontent.com/brunacpg/MVP-Machine-Learning/main/distribuicao_sentimentos.png)




