---
description: É possível baixar projetos salvos ou não salvos em formatos PDF e CSV.
title: Baixar arquivos PDF ou CSV
uuid: 8af5f3d7-5870-4ed6-8a9f-ef290a48ef5f
translation-type: tm+mt
source-git-commit: 422b69a9f671bbd3c4e8f033916296cbdf7f27d9
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 61%

---


# Baixar arquivos PDF ou CSV

É possível baixar projetos salvos ou não salvos em formatos PDF e CSV.

O nome do arquivo PDF ou CSV corresponde ao nome atual do projeto. Para projetos não salvos, o arquivo baixado inclui as mudanças não salvas no projeto. Observe que não é possível programar projetos não salvos em PDF ou CSV.

Lembre-se:

* A visualização do fallout também está disponível no formato CSV.
* Quando renderizamos um projeto para PDF, somente incluímos o que está na página. Se um projeto tiver visualizações e painéis com tamanhos personalizados, é necessário alterá-los para terem tamanhos automáticos (botão no canto superior direito) para que não haja truncamento de conteúdo.
* Os PDFs baixados no navegador podem levar vários minutos para serem exportados. Isso ocorre porque precisamos executar novamente o projeto inteiro em nossos servidores antes de renderizá-lo no formato PDF. Recomendamos não sair do projeto até que o PDF seja baixado no seu navegador. No entanto, você pode continuar fazendo alterações no projeto enquanto espera.
* Estamos cientes de que, se você tiver projetos muito longos da Workspace, os PDFs serão exportados como uma página gigante, em vez de como um documento paginado. Estamos trabalhando em uma melhoria na exportação de PDF do Workspace que permitirá a paginação.

1. Criar ou abrir um projeto.
1. Clique em **[!UICONTROL Projeto]** > **[!UICONTROL Baixar CSV (ou PDF).]**

On April 11, 2019, several changes were made to **[!UICONTROL CSV downloads]** (and **[!UICONTROL Copy to Clipboard]**) from Analysis Workspace to remove formatting from exported data.
* The  **[!UICONTROL Thousands Separator]** is no longer included. (Além disso, o separador decimal continuará a ser incluído, e vai aderir ao formato definido em **[!UICONTROL Componentes > Configurações de relatórios > Separador de milhar]**).
* Nenhum símbolo de moeda é exibido.
* Nenhum símbolo de porcentagem é exibido.
* As porcentagens estão em formato decimal. Por exemplo, 75% é representado como 0,75.
* O tempo é mostrado em segundos.
* As tabelas de coorte mostram apenas valores brutos; as porcentagens foram removidas.
* Se um número for inválido, é exibida uma célula vazia.
* Nenhum arredondamento é aplicado (mesmo se especificado na métrica calculada) - os valores brutos são mostrados.

>[!NObservação:]
>
> os valores numéricos que usam vírgula como separador decimal continuarão a ser incluídos entre aspas no CSV exportado.
