# dio-ai-search
# Azure Cognitive Search: Utilizando AI Search para indexação e consulta de Dados.
## Projeto que utiliza os serviços do Azure AI Search como demonstração de uso de ferramentas de indexação, pesquisa e inteligência em documentos, de modo a explicitar o valor que é entregue com essa solução do Azure. Para isso, deve-se ter em mente:
  - Como criar recursos do Azure
  - Como extrair dados de uma fonte de dados
  - Como usar as habilidades de IA no enriquecimento de dados.
  - Como usar o indexador do Azure no portal do Azure
  - Como consultar por índices de pesquisas criados.
  - Como revisar os resultados salvos em um Armazém de Conhecimento

## **I - Recursos do Azure:**
  - Um recurso do **Azure AI Search** para gerenciamento da indexação e da consulta.
  - Um recurso do **Azure AI services** para provisão de habilidades de IA nas pesquisas e insights que se fizerem necessários.
  - Uma **Storage account** com contêineres de blob para armazenar documentos diversos necessários à solução pretendida.
### 1. Criar um recurso do Azure AI Search:
  - Entre no portal do Azure: <https://portal.azure.com/?azure-portal=true#home>
  - Clique no botão ![image](https://github.com/user-attachments/assets/64665468-0c9c-40ab-8ff4-b159ed67946b), pesquise "Azure AI Search" e crie um recurso Azure AI Search com as seguintes configurações:
    ![image](https://github.com/user-attachments/assets/2ed19d13-8573-43aa-97fe-837b0200b482).
    - **Subscription**: sua assinatura do Azure.
    - **Resource group**: selecione ou crie um grupo de recursos com um nome exclusivo.
    - **Service name**: um nome exclusivo.
    - **Location**: escolha qualquer região disponível.
    - **Pricing tier**: Basic
    - Selecione ![image](https://github.com/user-attachments/assets/b596b83b-5d66-411a-8b81-2569db92a5fc) e, depois de ver a resposta ![image](https://github.com/user-attachments/assets/48201f89-4d76-40c3-9a4e-b522aad5fe23), selecione ![image](https://github.com/user-attachments/assets/b1766d5a-4052-447b-92ba-b1352c17ebb0).
  - Após a conclusão da implantação, selecione ![image](https://github.com/user-attachments/assets/42c42968-6b25-4015-acb9-19ef788098e9). Na página de visão geral do **Azure AI Search**, você pode adicionar índices, importar dados e pesquisar índices criados.
### 2. Criar um recurso de serviços de IA do Azure:
  - Retorne a home page do portal do Azure. Clique no botão ![image](https://github.com/user-attachments/assets/64665468-0c9c-40ab-8ff4-b159ed67946b), pesquise "Azure AI services" ![image](https://github.com/user-attachments/assets/6e23a489-3f66-49bc-b10d-d96b23ce9d63).
  - Selecione criar um plano de serviços de IA do Azure. Você será levado a uma página para criar um recurso de serviços de IA do Azure. Configure os seguintes campos:
    - **Subscription**: sua assinatura do Azure.
    - **Resource group**: selecione o grupo de recursos que foi criado anteriormente.
    - **Service name**: um nome exclusivo.
    - **Location**: escolha o mesmo que foi usado na criação do recurso anterior.
    - **Pricing tier**: Standard S0.
    - por último, marque essa opção ![image](https://github.com/user-attachments/assets/0230dff7-236e-44cd-a187-7618c767b994), dando o aceite aos termos de uso estabelecidos pelo Azure.
    - Selecione ![image](https://github.com/user-attachments/assets/b596b83b-5d66-411a-8b81-2569db92a5fc) e, depois de ver a resposta ![image](https://github.com/user-attachments/assets/48201f89-4d76-40c3-9a4e-b522aad5fe23), selecione ![image](https://github.com/user-attachments/assets/b1766d5a-4052-447b-92ba-b1352c17ebb0).
  - Aguarde a conclusão da implantação.
### 3. Criar um recurso de Storage Account:
  - Retorne a home page do portal do Azure. Clique no botão ![image](https://github.com/user-attachments/assets/64665468-0c9c-40ab-8ff4-b159ed67946b), pesquise "Storage Account" ![image](https://github.com/user-attachments/assets/de3e0093-69a3-4aef-bb4c-509f19b68e92)
  - Crie um recurso de conta de armazenamento com as seguintes configurações:
    - **Subscription**: sua assinatura do Azure.
    - **Resource group**: selecione o grupo de recursos que foi criado anteriormente.
    - **Storage account name**: um nome exclusivo.
    - **Location**: escolha o mesmo que foi usado na criação do recurso anterior.
    - **Performancer**: Standard.
    - **Redundancy:** Locally redundant storage (LRS).
  - Clique em ![image](https://github.com/user-attachments/assets/a56ed7d0-9605-4aae-91a6-aa895a469920) e, em seguida, clique em ![image](https://github.com/user-attachments/assets/534e176b-5e3f-485d-9425-36d97611cd5d). Aguarde a conclusão da implantação e vá para o recurso implantado.
  - Na conta de Armazenamento do Azure criada, no painel de menu à esquerda, selecione ![image](https://github.com/user-attachments/assets/b3ee7ece-cb58-4f45-834f-7860a405d48a) que está abaixo de ![image](https://github.com/user-attachments/assets/703dae48-1aea-4d84-968d-62ede7798dd9).
  - Altere o valor de ![image](https://github.com/user-attachments/assets/5e0e01c7-9f4c-4c7c-8233-d6ea229425ff) para ![image](https://github.com/user-attachments/assets/44d5bc82-14ed-44df-a289-d08765644b30), feito isso selecione Salvar.

## **II - Carregar os documentos no Armazenamento do Azure:**
  - Considerando que os documentos usados serão armamzenados no storage account criado anteriormente, vá para esse recurso e no painel de menu à esquerda, selecione **Containers**: 
