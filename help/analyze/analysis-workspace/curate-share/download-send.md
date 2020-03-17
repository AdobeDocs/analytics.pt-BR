---
description: É possível baixar projetos salvos ou não salvos em formatos PDF e CSV.
title: Baixar arquivos PDF ou CSV
uuid: 8af5f3d7-5870-4ed6-8a9f-ef290a48ef5f
translation-type: tm+mt
source-git-commit: 08d564f7fb06b94c2010515ea4a1dcbb2e6e2815

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
1. Clique em **[!UICONTROL Project]** > **[!UICONTROL Download CSV (or Download PDF).]**

Em 11 de abril de 2019, foram feitas várias alterações nos **[!CSV downloads]** (e em **[!CCopiar para área de transferência]**) do Analysis Workspace para remover a formatação dos dados exportados.
* O separador de milhares já não está incluído. (The decimal separator will continue to be included, and will adhere to the format defined under **[!UICONTROL Components > Report Settings > Thousands Separator]**).
* Nenhum símbolo de moeda é exibido.
* Nenhum símbolo de porcentagem é exibido.
* As porcentagens estão em formato decimal. Por exemplo, 75% é representado como 0,75.
* O tempo é mostrado em segundos.
* As tabelas de coorte mostram apenas valores brutos; as porcentagens foram removidas.
* Se um número for inválido, é exibida uma célula vazia.

>[!NObservação:]
>
> os valores numéricos que usam vírgula como separador decimal continuarão a ser incluídos entre aspas no CSV exportado.
