![image](https://upload.wikimedia.org/wikipedia/commons/a/a5/Logo_hotmart.png)

**Hotmart Challenge for Data Analyst Role**

**A Hotmart**  é uma empresa global de tecnologia e educação, líder em produtos digitais, com sede em Amsterdã, na Holanda, e escritórios no Brasil, Estados Unidos, Espanha, Colômbia, México e França

**“Quais Insights foram gerados em análise ao Dataset fornecido?”**

Nessa avaliação, eles desejam que seja mostrado a linha de pensamento durante a condução de uma pesquisa/análise. Por ela representar muito o dia a dia de um Analista de Dados na Hotmart, por isso, é muito importante saberem como será respondido aa perguntas de negócio.

Sendo assim, minha tarefa será gerar Insights sobre os dados no dataset que foi disponibilizado. Não existe uma forma única de chegar a uma solução, nem um número mínimo ou máximo de insights para serem gerados, mas, foram separadas algumas perguntas que seriam interessantes de serem respondidas.

# Contexto

Na Hotmart, possuímos três principais personas que integram nosso negócio: os produtores, os afiliados e os compradores. 

- **Produtores** são pessoas que criam produtos digitais na Hotmart, como cursos de idiomas, ebooks de receitas culinárias, audiolivros, softwares, dentre muitos outros exemplos.  
- **Afiliados** são pessoas que promovem produtos dos produtores em troca de uma comissão na venda, que varia de produto para produto, e de afiliado para afiliado.  
- **Compradores** são pessoas que adquirem um ou mais produtos digitais. 

Uma venda é feita por um afiliado quando alguém clica em um link de afiliados. Eles geralmente fazem a promoção desses produtos em redes sociais, vídeos, anúncios, etc.

Já uma venda é feita por um produtor quando alguém tem acesso direto ao seu produto, sem intermediação do afiliado. Por exemplo, pessoas que seguem o Whindersson Nunes no Youtube e entraram em seu site oficial para adquirir seu produto, ou clicaram no link do produto sem código de afiliação. 

***"Projeto Fictício"***

# Ferramentas Utilizadas

- Python
- Jupyter Notebook
- Sklearn
- Pandas
- Seaborn
- Matplotlib
- DateTime
- Mysql.connector


# Premissas do Negócio
- Quando a compra for feita diretamente pelo produtor, ou seja, quando não houver afiliado intermediando a compra, o campo affiliate_commission_percentual terá valor 0, e o campo affiliate_id será igual ao producer_id;
- No campo purchase_origin nós apenas consideramos o host do site. Isso quer dizer que, se uma pessoa veio do site www.meuproduto.com/promocoes, esse campo só irá retornar o valor www.meuproduto.com

# Lista de Atributos:

| Atributos                        | Explicação                                                      |
| -------------------------------- | ------------------------------------------------------------ |
| purchase_id                      | Identificação da compra na Hotmart;                                   |
| product_id                       | Identificação do produto na Hotmart;       |
| affiliate_id                     | Identificação do afiliado na Hotmart;                         |
| producer_id                      | Identificação do produtor na Hotmart;                       |
| buyer_id                         | Identificação do comprador na Hotmart; |
| purchase_date                    | Data e hora em que a compra foi realizada; |
| product_creation_date            | Data e hora em que o produto foi criado na Hotmart; |
| product_category                 | Categoria do produto na Hotmart. Exemplo: e-book, software, curso online, e-tickets, etc.; |
| product_niche                    | Nicho de mercado que o produto faz parte. Exemplo: educação, saúde e bem-estar, sexualidade, etc.;|
| purchase_value                   | Valor da compra. Esse dado, assim como nicho e categoria foi codificado para manter a confidencialidade. O valor apresentado no dataset é o z-score do valor real;          |
| affiliate_commission_percentual  | Percentual de comissão que o afiliado receberá da compra; |
| purchase_device                  | Tipo de dispositivo utilizado no momento da compra, como: Desktop, Mobile, Tablet, ou Outros; |
| purchase_origin                  | Endereço do site do qual a pessoa veio antes da compra. Por exemplo, se uma pessoa veio do Facebook, Youtube, ou até mesmo de outra página no site oficial do produto; |     
| is_origin_page_social_network    | Informa se essa compra veio de uma URL do Facebook, Youtube, Instagram, Pinterest, ou Twitter  |

***Informação disponibilizada pela própria Hotmart para o Case técnico***

# Estratégia da solução

**Passo 01**  – Descrição dos Dados: Etapa onde renomeamos colunas, verificamos dimensões, tipos, checa-se dados faltantes e os preenche, também se verifica os tipos, os dados números e categóricos.

**Passo 02** – Filtragem de Dados: Etapa onde filtramos dados para serem analisados por modelos, um exemplo foi a retirada da primeira linha que datava compra de 1970 e tinha valores nulo.

**Passo 03** – Feature Engineering: Etapa onde criamos hipóteses, análises estáticas para criação de novas features para verificar o fenômeno, agentes e atributos. A partir deles, começamos a criar hipóteses para serem validadas depois.

**Passo 04** – Análise Exploratória de dado: Etapa mais importante do projeto, onde ganhamos experiência de negócio, validamos hipóteses e percebemos quais variáveis serão importantes para o modelo.

**Passo 05** – Preparação de dados: Etapa onde preparamos os dados para os modelos de aprendizado de máquina, Rescaling, Enconding, PCA, UMAP, Nature Transformation, entre outras transformações.

**Passo 06** – Feature Selection – Etapa onde se seleciona os atributos mais relevantes para o projeto

**Passo 07** – Machine Learning Modelling – Etapa onde se treina os modelos de aprendizado de máquina.



# Data Insights

- Foram 1247083 compras que tiveram afiliados como intermediário no processo da compra e 352746 compras  não tiveram afiliados como intermediário 

- O Produtor 19736962 foi o que mais vendeu produtos. Totalizando 319129 produtos consumidos no espaço de tempo de 6 meses. 

- Os nichos de produtos que mais vendem são produtos relacionado a Gerenciamento de ansiedade, Negociação, Finanças pessoais, Habilidades de Apresentação 

-  Em análise dos gráficos da soma de produtos vendidos por nicho destaco 3 nichos que poderiam passar por campanhas de marketing para impulsionar as vendas. São eles: Carreiras, Online Youtube Video Creation e Online Course Creation. Pois os nichos em maior crescimento são aqueles dentro de carreiras, comportamento humano e desenvolvimento pessoal.

- Em análise ao grafico de vendas por mês identificamos que a maioria dos produtos comprados estão abaixo da média de preço. Com exeção ao mês de março que teve maior periodo de venda. 

- Possívelmente relacionado aos feriados do mês de fevereiro, ele é o mês com menor compra. Nos faz inferir que não é o melhor momento para criação de conteudo.

- As três categorias de produtos mais consumidas na plataforma são: Livro Fisico, Workshop e Podcasts.


#  Conclusão

Para o primeiro ciclo do CRISP-DM conseguimos gerar insights e features que possam responder as perguntas do negócio. Porém, no segundo ciclo buscaremos nos aprofundar na preparação do dataset com as features corretas e preparadas para que possamos clusterizar os dados e gerarmos melhores insights 

#  Próximos Passos

Iniciar um segundo ciclo para analisar o problema buscando abordagens diferentes, tendo em vista principalmente as produtores  com o comportamento difíceis de serem previsto.

Possíveis pontos para serem abordados no segundo ciclo:

- **Utilizar novos atributos.**

- **Entender os fenomenos dos produtores que ficaram fora do padrão da maioria.**

- **Com o primeiro ciclo podemos trazer alguns insight e manipular o dado para prepará-lo para o modelo de clusterização K-means que será útilizado. Buscarei gerar dois modelos para poder realizar as comparações, provavelmente irei utilizar o K-means e o Cluster Hierarquico passarei pelo Fine Tunning e efetuarei a análise de performance dos modelos**
