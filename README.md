# Projeto: Priorizando Hipóteses e Análise de Teste A/B

*Você é **analista** em uma grande loja online. Você e sua equipe de marketing **compilaram uma lista de hipóteses** para ajudar a **aumentar a receita**. As listas são:*

1. **Adicione dois novos canais** para atrair tráfego. Isso trará **30% mais usuários**
2. **Lance** seu próprio **serviço de entrega**. Isso **reduzirá o tempo de entrega**
3. **Adicione blocos de recomendação de produtos** ao site da loja. Isso **aumentará a conversão e o tamanho médio da compra**
4. **Altere a estrutura da categoria**. Isso **aumentará a conversão**, pois os usuários encontrarão os produtos que desejam mais rapidamente
5. **Altere a cor de fundo** na página principal. Isso **aumentará o envolvimento do usuário**
6. **Adicione uma página de avaliação do cliente**. Isso **aumentará o número de pedidos**
7. **Mostre banners com ofertas e promoções atuais** na página principal. Isso **aumentará a conversão**
8. **Adicione um formulário de inscrição** a todas as páginas principais. Isso ajudará você a compilar uma **lista de e-mails**
9. **Lance uma promoção** que ofereça aos usuários **descontos em seus aniversários**

*O teste de hipóteses requer financiamento substancial, enquanto os recursos de que você dispõe podem ser limitados. Isso é algo natural de acontecer. Portanto, você deve ser capaz de **determinar** quais hipóteses precisam ser **testadas** e quais hipóteses devem ser **removidas** primeiro. Para maximizar o crescimento nas principais métricas de negócios, as hipóteses formuladas devem ser **priorizadas**.*

*Seu supervisor deseja que você implemente uma **estrutura para priorizar** hipóteses. Impacto, confiança e esforço ou **ICE**, para abreviar, estão entre os métodos mais populares usados ​​para priorizar problemas. Há também uma versão modificada do ICE, chamada **RICE**.*

*RICE consiste em quatro componentes, a saber:*
- **Reach** — quantos **muitos** usuários serão afetados pela atualização que você deseja introduzir
- **Impact** — quão **fortemente** a atualização **afetará** os usuários, sua experiência e sua satisfação com o produto
- **Confidence** — quão **confiante** você está de que seu produto **influenciará** os usuários na maneira como você o apresenta
- **Effort** — quanto **custa** testar uma hipótese

*Durante a sessão de brainstorming, todos os departamentos envolvidos deram a sua avaliação de cada parâmetro para cada hipótese. A média desses valores é calculada em uma escala de 1 a 10 e compilada em /datasets/hypotheses_us.csv.*

*Após priorizar as hipóteses, a equipe de UX Research conduzirá os testes A/B com base na hipótese selecionada e os resultados serão compilados em /datasets/orders_us.csv e /datasets/visits_us.csv.*

**Instruções do projeto**

1. ***Priorizando Hipóteses***

- *O arquivo hypotheses_us.csv contém nove hipóteses para aumentar a receita de uma loja online com Alcance, Impacto, Confiança e Esforço predefinidos para cada uma das hipóteses. suas tarefas são:*
    - Implementar uma estrutura `ICE` para priorizar hipóteses. Classifique essas hipóteses em ordem decrescente de prioridade.
    - Implementar uma estrutura `RICE` para priorizar hipóteses. Classifique essas hipóteses em ordem decrescente de prioridade.
    - Indica a mudança na prioridade da hipótese quando `RICE` foi aplicado em substituição a `ICE`. Forneça uma explicação para a mudança.

2. ***Análise de testes A/B***
- Descrever **renda acumulada por grupo**. Faça as conclusões e suposições.
- Desenhe um **tamanho médio cumulativo do pedido por grupo**. Faça as conclusões e suposições.
- Desenhe uma **diferença relativa** para o **tamanho médio cumulativo do pedido** do **grupo B em comparação com o grupo A**. Faça conclusões e suposições.
- Calcule a **taxa de conversão de cada coorte** como a proporção entre pedidos e número de visitas por dia.
- **Gráfico das taxas de conversão diárias** de ambos os grupos e explique as diferenças. Faça as conclusões e suposições.
- Crie um **gráfico de dispersão para o número de pedidos por usuário**. Faça as conclusões e suposições.
- Calcule os **95º e 99º percentis** para o **número de pedidos por usuário**. Determine o ponto em que um ponto de dados se transforma em uma anomalia.
- Crie um **gráfico de dispersão para a receita do pedido**. Faça as conclusões e suposições.
- Calcule os **percentis 95 e 99** para a **receita do pedido**. Determine o ponto em que um ponto de dados se transforma em uma anomalia.
- Encontre a **significância estatística das diferenças de conversão** entre grupos usando **dados brutos**. Faça as conclusões e suposições.
- Encontre a **significância estatística da diferença no tamanho médio dos pedidos** entre grupos usando **dados brutos**. Faça as conclusões e suposições.
- Encontre a **significância estatística das diferenças de conversão** entre grupos usando **dados filtrados**. Faça as conclusões e suposições.
- Encontre a **significância estatística da diferença no tamanho médio dos pedidos** entre grupos usando **dados filtrados**. Faça as conclusões e suposições.
- Tome uma **decisão** com base nos resultados do teste. As decisões possíveis são:
    - **Pare de testar**, bem como **considere um dos grupos como líder**.
    - **Interromper o teste**, bem como **concluir que não há diferença** entre os dois grupos.
    - **Continue testando**.

**Dicionário de dados**
**A tabela de hipóteses:**
- `Hypotheses` — breves descrições das hipóteses
- `Reach` — alcance do usuário, em uma escala de um a dez
- `Impact` — impacto sobre os usuários, em uma escala de um a dez
- `Confidence` — confiança na hipótese, em uma escala de um a dez
- `Effort` — os recursos necessários para testar uma hipótese, numa escala de um a dez. Quanto maior o valor do `Esforço`, mais recursos serão necessários para o teste.

**A tabela de pedidos:**
- `transactionId` — identificador de pedido
- `visitorId` — identificador do usuário que fez o pedido
- `date` — data do pedido
- `revenue` — receita do pedido
- `group` — o grupo de testes A/B ao qual o usuário pertence

**A tabela de visitas:**
- `date` — data
- `group` — grupo de testes A/B
- `visits` — o número de visitas na data especificada para o grupo de teste A/B especificado

**Conclusões**
**Visão geral do dataframe df_hypotheses:**
- *O dataframe consiste em cinco colunas:`hypothesis`, `reach`, `impact`, `confidence` e `effort`, com 9 linhas cada, sem diferença significativa entre média e mediana, sem duplicatas, dados faltantes ou valores discrepantes.*

**Visão geral do dataframe df_orders:**
- *O dataframe contém cinco colunas: `transaction_id`, `visitor_id`, `date`, `revenue` e `group`, com 1.197 linhas cada, após remover os dados empilhados, agora o dataframe tem 1.016 linhas em cada coluna. As colunas são do tipo int64, datetime64[ns], float64 e object. O nome das colunas `transactionId` e `visitorId` foi alterado, e a coluna `date` foi convertida de objeto para datahora. Não foram encontradas duplicatas, dados ausentes ou valores discrepantes.*

**Visão geral do dataframe df_visits:**
- *O dataframe contém três colunas: `date`, `group` e `visits`, com 62 linhas cada. A coluna `data` foi convertida de objeto para datahora e não há valores discrepantes na coluna `visitas`.*

- Tanto os dados brutos como os dados filtrados mostraram diferenças estatisticamente significativas em termos de conversões entre coortes.
- Nem os dados brutos nem os dados filtrados mostraram quaisquer diferenças estatisticamente significativas em termos de tamanho médio dos pedidos entre os grupos.
- Um gráfico que mostra as diferenças de conversão entre os grupos mostra que os resultados do grupo B são melhores. O que foi comprovado por um aumento de 16\%.
- Um gráfico que mostra a diferença no tamanho médio dos pedidos entre os grupos mostra que os resultados do grupo B são superiores aos do grupo A. A presença de anomalias pode ter distorcido os resultados, mas um método para filtrar esse valor discrepante mostra que há um declínio de 3\% comparado ao grupo A.

*Este teste A/B foi feito para testar a hipótese 3, que é:*

- Adicione blocos de recomendação de produtos ao site da loja. Isso aumentará a conversão e o tamanho médio da compra.

*Com base nestes factos, pode-se concluir que este teste correu parcialmente bem. Há uma probabilidade de que o segmento B seja melhor que o segmento A. Portanto, recomendamos continuar o teste por mais um mês para que possamos obter mais dados.*
