---
description: É possível baixar projetos salvos ou não salvos em formatos PDF e CSV.
title: Baixar arquivos PDF ou CSV
uuid: 8af5f3d7-5870-4ed6-8a9f-ef290a48ef5f
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Baixar arquivos PDF ou CSV

É possível baixar projetos salvos ou não salvos em formatos PDF e CSV.

O nome do arquivo PDF ou CSV corresponde ao nome atual do projeto. Para projetos não salvos, o arquivo baixado inclui as mudanças não salvas no projeto. Observe que não é possível programar projetos não salvos em PDF ou CSV.

> [!NOTE] A visualização do fallout também está disponível no formato CSV.

> [!NOTE] Quando renderizamos um projeto para PDF, somente incluímos o que está na página. Se um projeto tiver visualizações e painéis com tamanhos personalizados, é necessário alterá-los para terem tamanhos automáticos (botão no canto superior direito) para que não haja truncamento de conteúdo.

1. Criar ou abrir um projeto.
1. Clique em **[!UICONTROL Projeto]** &gt; **[!UICONTROL Baixar CSV (ou Baixar PDF).]**

Em 11 de abril de 2019, foram feitas várias alterações nos **[!CSV downloads]** (e em **[!CCopiar para área de transferência]**) do Analysis Workspace para remover a formatação dos dados exportados.
* O separador de milhares já não está incluído. (Além disso, o separador decimal continuará a ser incluído, e vai aderir ao formato definido em **[!UICONTROL Componentes &gt; Configurações de relatórios &gt; Separador de milhar]**).
* Nenhum símbolo de moeda é exibido.
* Nenhum símbolo de porcentagem é exibido.
* As porcentagens estão em formato decimal. Por exemplo, 75% é representado como 0,75.
* O tempo é mostrado em segundos.
* As tabelas de coorte mostram apenas valores brutos; as porcentagens foram removidas.
* Se um número for inválido, é exibida uma célula vazia.

>[!NObservação:]
>
> os valores numéricos que usam vírgula como separador decimal continuarão a ser incluídos entre aspas no CSV exportado.
