---
description: É possível baixar projetos salvos ou não salvos em formatos PDF e CSV.
seo-description: É possível baixar projetos salvos ou não salvos em formatos PDF e CSV.
seo-title: Baixar arquivos PDF ou CSV
title: Baixar arquivos PDF ou CSV
uuid: 8 af 5 f 3 d 7-5870-4 ed 6-8 a 9 f-ef 290 a 48 ef 5 f
translation-type: tm+mt
source-git-commit: b9e57162fae605719d7d85aad52a29165cb63fe4

---


# Baixar arquivos PDF ou CSV

É possível baixar projetos salvos ou não salvos em formatos PDF e CSV.

O nome do arquivo PDF ou CSV corresponde ao nome atual do projeto. Para projetos não salvos, o arquivo baixado inclui as mudanças não salvas no projeto. Observe que não é possível programar projetos não salvos em PDF ou CSV.

>[!NOTE]
>
>Também oferecemos suporte à visualização de fallout no formato CSV.

>[!NOTE]
>
>Quando renderizamos um projeto em PDF, renderizaremos o que está na página. Se um projeto tiver visualizações e painéis com tamanhos personalizados, é necessário alterá-los para terem tamanhos automáticos (botão no canto superior direito) para que não haja truncamento de conteúdo.

1. Criar ou abrir um projeto
1. Click **[!UICONTROL Project]** &gt; **[!UICONTROL Download CSV (or Download PDF).]**

On April 11, 2019, several changes were made to **[!CSV downloads]** (and **[!Copy to Clipboard]**) from Analysis Workspace to remove formatting from exported data.
* O separador de milhares não está mais incluído. (Além disso, o separador decimal continuará a ser incluído, e vai aderir ao formato definido em **[!UICONTROL Componentes &gt; Configurações de relatórios &gt; Separador de milhar]**).
* Nenhum símbolo de moeda é exibido.
* Nenhum símbolo de porcentagem é mostrado.
* As porcentagens estão em forma decimal; Por exemplo, 75% é representado como 0.75.
* O tempo é mostrado em segundos.
* Tabelas de coorte mostram apenas valores brutos; as porcentagens são removidas.
* Se um número for inválido, uma célula vazia será exibida.

>[!Note:]
>
> Valores numéricos que usam uma vírgula como separador decimal continuarão a ser citados no CSV exportado.