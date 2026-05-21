---
description: É possível importar (carregar) dados de classificações usando o navegador. Esse método limita o upload dos dados de classificação para um único conjunto de relatórios
title: Importação de navegador
feature: Classifications
exl-id: 5bef1f6d-9b27-464d-8343-472f300a7437
TQID: https://experienceleague.adobe.com/iFVW-d9C12dj6TXnUlA3-zVF0oBAWpJwg1JK8LqzF-s
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 354
ht-degree: 29%

---

# Importação do navegador (herdado)

{{classification-importer-deprecation}}

É possível importar (carregar) dados de classificações usando o navegador. Esse método limita o upload dos dados de classificação para um único conjunto de relatórios

## Importação de navegador {#concept_314FB3D5FD5A439B9CFEDE37A3337BA7}

É possível importar (carregar) dados de classificações usando o navegador. Esse método limita o upload dos dados de classificação para um único conjunto de relatórios

**[!UICONTROL Administração]** > **[!UICONTROL Importador de classificação]**

## Importação do navegador de classificações - Descrições do campo {#section_F628C47081DA4026A4D30E3D3454B1DA}

| Elemento | Descrição |
| --- | --- |
| Selecione o Conjunto de relatórios | O conjunto de relatórios para o qual você deseja importar os dados de classificação. O arquivo de dados de importação deve corresponder ao formato do conjunto de dados no conjunto de relatórios. |
| Conjunto de dados a ser classificado | O conjunto de dados para receber as classificações. A lista suspensa inclui todos os relatórios nos seus conjuntos de relatórios configurados para classificações. |
| Selecione o arquivo a ser importado | Permite navegar para localizar o arquivo de dados de importação que deseja fazer upload.  Observação: o tamanho do arquivo para upload é de 1 MB. |
| Substituir dados em conflitos | Substitui automaticamente os dados existentes que estão em conflito com os dados importados.<br>**Importante**: essa opção não está disponível para conjuntos de relatórios habilitados para a Nova Arquitetura de Classificação. |
| Baixar automaticamente o arquivo de classificação quando a importação estiver concluída | Baixa automaticamente um arquivo delimitado por tabulação que representa o conjunto de dados com os dados de classificação carregados recentemente. O Adobe gera automaticamente esse arquivo se a importação criar IDs exclusivas ou se ocorrerem erros.<br>**Importante**: essa opção não está disponível para conjuntos de relatórios habilitados para a Nova Arquitetura de Classificação. |


## Importar classificações pelo navegador {#task_D7D51CB6FB35437AB68599B1B23FEAC1}

1. Clique em **[!UICONTROL Administração]** > **[!UICONTROL Importador de classificação]**.
1. Clique em **[!UICONTROL Exportar arquivo]**.
1. Configure os campos **[!UICONTROL Importação de navegador]**.
1. Clique em **[!UICONTROL Exportar arquivo]**.
1. Observe as mensagens de processamento na janela de status.
1. (Condicional) Se você selecionou **[!UICONTROL Baixar automaticamente o arquivo de classificação quando a importação estiver concluída]**, especifique onde deseja armazenar o arquivo resultante depois que o processamento terminar. Observe que essa opção não está disponível para conjuntos de relatórios habilitados para a Nova arquitetura de classificação.

>Uma importação bem-sucedida exibe imediatamente as alterações apropriadas em uma exportação. No entanto, as alterações de dados em relatórios demoram até quatro horas ao usar uma importação de navegador e até 24 horas ao usar uma importação de FTP.
