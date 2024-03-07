<div align="center">
 <h1>Cognitive Search utilizando AI Search para indexação e consulta de dados 📅</h1>
</div>

 <p align="center">
  <a href="#Tecnologias">Tecnologias</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#Documentação">Documentação</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#Desafio">Desafio</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#License">License</a></p>

![_3d9eff06-1251-4392-847d-5533e24672dc](https://github.com/augustomiller/AI-Search_index/assets/990877/67d9c7fe-3336-494d-8464-a5407b2c729b)


## Desafio

Vamos imaginar que você trabalha para a Fourth Coffee, uma rede nacional de cafés.

- Fomos solicitado a ajudar a construir uma solução de mineração de conhecimento que facilite a busca de insights sobre as experiências dos clientes.

- Então decidimos criar um índice do Azure AI Search usando dados extraídos de avaliações de clientes.

### Estratégia 💡

    -- Criar um serviço de Inteligencia Artificial
    -- Fazer o link com a automação do IA Search
    -- Direcionar o resultado para um repositório

## Tecnologias

- [Azure Search](https://learn.microsoft.com/pt-br/azure/search/)
- [Microsoft Copilot](https://copilot.microsoft.com/)
- [VS Code](https://code.visualstudio.com/)
- [Bash](https://www.gnu.org/software/bash/)
- [Git](https://git-scm.com/)

## Documentação

- [Azure Speech Studio Doc](https://learn.microsoft.com/pt-br/azure/search/)
- [Microsoft Copilot Doc](https://learn.microsoft.com/en-us/microsoft-copilot-studio/)
- [VS Code Doc](https://code.visualstudio.com/Docs)
- [Bash Doc](https://www.gnu.org/software/bash/manual/bash.html)
- [Git Doc](https://git-scm.com/doc)
- [Markdown Doc](https://google.github.io/styleguide/docguide/style.html)


## Que recursos vamos precisar para solucionar esse problema 🤔

1 - Criar um novo Azure AI Search em AI services...

    -- Escolher um nome esclusivo para ele
    -- Na opção "Pricing Tier" selecionar "Basic"
    -- Location = East US

2 - Criar um recurso de IA (+ Create a resource)

    -- "+ Create a resource" -> "AI + Machine Learning" -> "Azure  AI Services"(create)

3 - Criar uma conta de armazenamento (Storage accounts)

    -- "Storage accounts" -> "+ Create"
    -- Em Create a storage account ...
        -- Aba Basics
            -- Subscription: Assinatura de Plataforma MSDN
            -- Resource Group: LAB_AI_900
            -- Storage account name: lab_ai_06070009
            -- Region: (US) East US
            -- Performance: Standart
            -- Redudancy: Locally-redundance storage (LRS)
    -- Clicar no botão "Review" -> "Create"

4 - Selecione o Storage criado (lab_ai_06070009)

    -- No painel esquerdo selecione "Containers"
    -- E clique em "+ Create" (Vamos criar um novo contaniner)
        -- Name: coffee-reviews ou coffeereviews
        -- Public access level: Container (anonymous read access for containers and blobs)
        -- Advanced: no changes

5 - Vamos pegar as revisões dos usuários no seguinte link: https://aka.ms/mslearn-coffee-reviews

6 - No portal do Azure selecione o container coffee-reviews e logo após selecione a opção "Upload"

    -- E agora selecione os arquivos das revisões que baixamos anteriormente.

## Até o momento:
 
### Criamos um mecanismo de busca, um recurso de inteligencia artificial e um sorage account com as informações necessárias.

7 - Agora vamos no nosso mecanismo de busca AI Search - na página Connect to your data, na lista Data Source, selecione Azure Blob Storage. 

Conclua os detalhes do armazenamento de dados com os seguintes valores:

    -- Data Source: Azure Blob Storage
    -- Data source name: coffee-customer-data
    -- Data to extract: Content and metadata
    -- Parsing mode: Default
    -- Connection string: *Select Choose an existing connection. Select your storage -- account, select the coffee-reviews container, and then click Select.
    -- Managed identity authentication: None
    -- Container name: this setting is auto-populated after you choose an existing connection.
    -- Blob folder: Leave this blank.
    -- Description: Reviews for Fourth Coffee shops.

8 - Selecione Next: Add cognitive skills (Optional)

9 - Em Attach Cognitive Services selecione seu Azure AI services resource.

10 - E em Add enrichments:
    -- Mude o Skillset name para coffee-skillset
    -- Selecione o checkbox Enable OCR and merge all text into merged_content field

![_4de59358-f93c-43e9-92de-2803f650b842](https://github.com/augustomiller/AI-Search_index/assets/990877/11d0df84-8c9b-463d-afa3-8865ed82206a)

11 - Vamos importar os dados
    -- Em nosso mecanismo de busca(AI Search) selecionamos a aba "Import data"
    -- Selecionamos onde está os dados cognitivos
    -- A estratégia e ter uma pesquisa que retorne uma consulta

### Verificando se a pesquisa está ON

![pesquisa_on](https://github.com/augustomiller/AI-Search_index/assets/990877/554ef1ce-f499-4ee2-a589-1fc3838fc59b)


### Verificando o feedback da caidad de Chicago

![chicago](https://github.com/augustomiller/AI-Search_index/assets/990877/228da15f-350b-408e-ad80-b92c4fca60d8)

## Qual é a estratégia?

  - Criar um serviço de Inteligencia Artificial
  - Fazer o link com a automação do IA Search
  - Direcionar o resultado para um repositório

#### Para mais detalhes: [Documentação da IA do Azure Search](https://learn.microsoft.com/pt-br/azure/search/)

#### Fonte sugerida: [Explore an Azure AI Search index](https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/11-ai-search.html#learn-more)


## License

<div align="center">
  
<p>This project is licensed under the MIT License. See the
  <a href="https://mit-license.org/">
    <img src="https://img.shields.io/static/v1?label=license&message=MIT&color=5965E0&labelColor=121214" alt="License"></a> file for details.</p>
<p>Made with&nbsp;💙 &nbsp;by Augusto Miller</p>
  
<div>