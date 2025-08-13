---
description: É possível importar (upload) dados de classificações por meio do navegador. Esse método restringe o upload de seus dados de classificação a um único conjunto de relatórios
title: Importação de navegador
feature: Classifications
exl-id: 5bef1f6d-9b27-464d-8343-472f300a7437
source-git-commit: 4eea524bf95c9b6bc9ddc878c8c433bc1e60daee
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 99%

---

# Importação do navegador (herdado)

{{classification-importer-deprecation}}

É possível importar (upload) dados de classificações por meio do navegador. Esse método restringe o upload de seus dados de classificação a um único conjunto de relatórios

## Importação de navegador {#concept_314FB3D5FD5A439B9CFEDE37A3337BA7}

É possível importar (upload) dados de classificações por meio do navegador. Esse método restringe o upload de seus dados de classificação a um único conjunto de relatórios

**[!UICONTROL Administração]** > **[!UICONTROL Importador de classificação]**

## Importação do navegador de classificações - Descrições do campo {#section_F628C47081DA4026A4D30E3D3454B1DA}

| Elemento | Descrição |
| --- | --- |
| Selecione o Conjunto de relatórios | O conjunto de relatórios em que deseja importar os dados de classificações. O arquivo de dados de importação deve corresponder ao formato do conjunto de dados no conjunto de relatórios. |
| Conjunto de dados a ser classificado | O conjunto de dados que receberá as classificações. A lista suspensa inclui todos os relatórios em seus conjuntos de relatórios configurados para classificação. |
| Selecionar o arquivo para importar | Permite navegar para localizar o arquivo de dados de importação que deseja fazer upload.  Observação: o tamanho do arquivo para upload é de 1 MB. |
| Substituir dados em conflito | Substitui automaticamente dados existentes que estejam em conflito com os dados importados.<br>**Importante**: essa opção não está disponível para conjuntos de relatórios habilitados para a Nova arquitetura de classificação. |
| Fazer download automático do arquivo de classificação após a importação ser concluída | Faz o download automático de um arquivo delimitado por tabulação que representa o conjunto de dados com os dados de classificações carregados recentemente. A Adobe gera este arquivo automaticamente para você se a importação criar IDs únicas ou se ocorrerem erros.<br>**Importante**: essa opção não está disponível para conjuntos de relatórios habilitados para a Nova arquitetura de classificação. |


## Importar classificações pelo navegador {#task_D7D51CB6FB35437AB68599B1B23FEAC1}

1. Clique em **[!UICONTROL Administração]** > **[!UICONTROL Importador de classificação]**.
1. Clique em **[!UICONTROL Exportar arquivo]**.
1. Configure os campos **[!UICONTROL Importação de navegador]**.
1. Clique em **[!UICONTROL Exportar arquivo]**.
1. Observe as mensagens de processamento na janela de status.
1. (Condicional) Se você selecionou **[!UICONTROL Baixar automaticamente o arquivo de classificação quando a importação estiver concluída]**, especifique onde deseja armazenar o arquivo resultante depois que o processamento terminar. Observe que essa opção não está disponível para conjuntos de relatórios habilitados para a Nova arquitetura de classificação.

>Uma importação bem-sucedida exibe imediatamente as alterações apropriadas em uma exportação. No entanto, as alterações de dados nos relatórios levam até quatro horas quando se usa uma importação de navegador e até 24 horas quando se usa uma importação FTP.
