# -Azure-Cognitive-Search-Utilizando-AI-Search-para-indexa-o-e-consulta-de-Dados
Teste 4 do Bootcamp Azure Fundamentals AI 900 da DIO


<h1> Pesquisa Cognitiva do Azure</h1><br>

<h3>O que é mineração de conhecimento?</h3>
<br>
- O dados são bloqueados em documentos, PDFs, notas manuscritas, etc.
<br>
- A mineração de conhecimento encontra insights em escala
<br>
- O Azure Cognitive Search é a plataforma de mineração de conhecimento alimentada por IA do Azure.
<br>
<br>
<h3>Soluções de Pesquisa Cognitiva do Azure</h3>

<h3>Ingestação de dados:</h3>
 - Azure Blob Storage Containers<br>
 - Azure Data Lake Storage Gen2<br>
 - Azure Table Storage<br>
<br>
<h3>Enriquecimento e índice de IA:</h3>
Permite uma compreensão mais progunda;<br>
Visão, Procesamento de Linguagem Natural, etc;<br>
A indexação torna o conteúdo pesquisável.<br>
<br>
<h3>Enriquecimento de IA</h3>
Pesquisa Cognitiva do Azure<br>
O enriquecimento de IA torna o conteúdo mais útil para fins de pesquisa.<br>
O conteúdo enriquecido é criado por conjutnos de habilidades, como:<br>
 - Reconhecer entidades no texto<br>
 - Traduzir texto<br>
 - Avalie o sentimento<br>
<br>


**DESAFIO**<br>
Para criar Azure AI Search:<br>

Abrir a assinatura do Azure, criar um novo recurso e dar um nome excluviso para ele, selecionar assinatura, grupo de recursos, localização e no Pricing tier, selecionar o nível básico (Basic).
Após, clicar em Review + create e aguarda a finalização.
<br>
Em seguida, é necessário criar um recurso de IA. Para isso é necessário ir em Criar recurso (create a resource), clicar em IA + Machine Learning, em seguida clicar em Serviços Cognitivos(Azure AI Services), clicar em Criar(create) e novamente preenche os dados como no passo anterior, selecionando no Pricing tier, a opção Standard S0 e marcar a caixinha no final da página. Para finalizar clicar em Review + create.
<br>
Para criar uma conta de armazenamento, é necessário ir em Storage accounts, clicar em Create(criar), preencher as opções correspondentes ao laborário: assinatura, resource group, storage account name(precisa ser um nome único entre 3 e 24 caracteres), região, performance (é necessário ticar Standard) e redundância (marcar a primeira opção da lista - LRS). Concluído o processo, basta clicar em Review + create, sem a necessidade de preencher os demais campos das abas apresentadas no menu superior.
<br>
Após criar o storage, basta selecioná-lo, clicar em configurações e permitir o acesso anônimo de Blob (ele vem desabilitado e precisa habilitar a opção) para então, salvar as configurações.
Em Data storage, seleciona Containers, clica em + Container e escolhe a opção de Container anônimo (na documentação, o nome sugerido foi Coffee-Reviews, porém a plataforma só aceita letras minúsculas e sem traço). Feita a alteração, clica em Create.
<br>
Após criar o Storage account, será necessário carregar com arquivos disponibilizados na documentação (baixar pasta zipada e extrair os arquivos na máquina para fazer o upload na plataforma). Após carregar os arquivos clica em Storage accounts, no topo da página e no buscador, ainda na parte superior, pesquisa por AI Search, clica nele e seguida em importar dados. Para tal, é necessário seguir o passa a passo que se encontra na documentação (https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/11-ai-search.html), para preencher alguns campos de conexão, ou seja será necessário apontar aonde estão os documentos e os tipos de informações que quer dos documentos, para que a busca possa retornar uma pesquisa.
<br>

![Imagem do WhatsApp de 2024-04-14 à(s) 23 50 26_49b3fc0b](https://github.com/Edivania88Duarte/-Azure-Cognitive-Search-Utilizando-AI-Search-para-indexa-o-e-consulta-de-Dados/assets/120994730/073ef210-87d0-4706-9e3d-76ae7c38e411)

<br>
<h3>Passo a passo para importar dados:</h3><br>
<br>
Na página Conectar-se aos seus dados , na lista Fonte de Dados , selecione Azure Blob Storage . Preencha os detalhes do armazenamento de dados com os seguintes valores:<br>
Fonte de dados : Armazenamento de Blobs do Azure<br>
Nome da fonte de dados : coffee-customer-data<br>
Dados a extrair : Conteúdo e metadados<br>
Modo de análise : Padrão<br>
Cadeia de conexão : *Selecione Escolha uma conexão existente . Selecione sua conta de armazenamento, selecione o contêiner de avaliações de café e clique em Selecionar <br>
Autenticação de identidade gerenciada : Nenhuma<br>
Nome do contêiner : esta configuração é preenchida automaticamente depois que você escolhe uma conexão existente<br>
Pasta Blob : deixe em branco<br>
Descrição : Avaliações sobre Fourth Coffee Shops.<br>


![Imagem do WhatsApp de 2024-04-16 à(s) 23 39 28_4b19cebb](https://github.com/Edivania88Duarte/-Azure-Cognitive-Search-Utilizando-AI-Search-para-indexa-o-e-consulta-de-Dados/assets/120994730/1dcab40d-59b1-4793-a7ee-f1ddb52c4e86)

<br>


![Imagem do WhatsApp de 2024-04-16 à(s) 23 52 05_254fc710](https://github.com/Edivania88Duarte/-Azure-Cognitive-Search-Utilizando-AI-Search-para-indexa-o-e-consulta-de-Dados/assets/120994730/4688987d-4bd5-4706-b603-1bc000e2ed33)

<br>
<br>
<h3>Objetivo geral da aplicação:</h3><br>
Extrai os campos de metadados do documento e o conteúdo da fonte de dados.<br>
Executa o conjunto de habilidades cognitivas para gerar campos mais enriquecidos.<br>
Mapeia os campos extraídos para o índice.<br>
<br>


![Imagem do WhatsApp de 2024-04-17 à(s) 00 05 17_1b4a20d5](https://github.com/Edivania88Duarte/-Azure-Cognitive-Search-Utilizando-AI-Search-para-indexa-o-e-consulta-de-Dados/assets/120994730/a18f227a-5aa4-40ca-a408-8fc51bafabc3)

<br>

<h3> Lins importantes: </h3> <br>
https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/11-ai-search.html
