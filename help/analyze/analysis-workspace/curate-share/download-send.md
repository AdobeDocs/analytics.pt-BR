---
description: É possível baixar projetos salvos ou não salvos em formatos PDF e CSV.
title: Baixar arquivos PDF ou CSV
uuid: 8af5f3d7-5870-4ed6-8a9f-ef290a48ef5f
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Baixar arquivos PDF ou CSV

É possível baixar projetos salvos ou não salvos em formatos PDF e CSV.

O nome do arquivo PDF ou CSV corresponde ao nome atual do projeto. Para projetos não salvos, o arquivo baixado inclui as mudanças não salvas no projeto. Observe que não é possível programar projetos não salvos em PDF ou CSV.

> [!NOTE] Também oferecemos suporte à visualização de Fallout no formato CSV.

> [!NOTE] Quando renderizamos um projeto em PDF, apenas renderizamos o que está na página. Se um projeto tiver visualizações e painéis com tamanhos personalizados, é necessário alterá-los para terem tamanhos automáticos (botão no canto superior direito) para que não haja truncamento de conteúdo.

1. Criar ou abrir um projeto
1. Click **[!UICONTROL Project]** &gt; **[!UICONTROL Download CSV (or Download PDF).]**

On April 11, 2019, several changes were made to **[!CSV downloads]** (and **[!Copy to Clipboard]**) from Analysis Workspace to remove formatting from exported data.
* O separador de milhares não está mais incluído. (Além disso, o separador decimal continuará a ser incluído, e vai aderir ao formato definido em **[!UICONTROL Componentes &gt; Configurações de relatórios &gt; Separador de milhar]**).
* Nenhum símbolo de moeda é exibido.
* Nenhum símbolo de porcentagem é exibido.
* As porcentagens estão em formato decimal; Por exemplo, 75% é representado como 0,75.
* O tempo é mostrado em segundos.
* As tabelas de coorte mostram apenas valores brutos; as porcentagens são removidas.
* Se um número for inválido, uma célula vazia será exibida.

>[!NObservação:]
>
> Os valores numéricos que usam uma vírgula como separador decimal continuarão a ser citados no CSV exportado.
