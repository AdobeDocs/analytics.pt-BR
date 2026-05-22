---
title: Depurador herdado
description: Instale o Depurador herdado. Este depurador inspeciona as tags do Analytics, Target, Advertising, Serviço de identidade e tags de coleta de dados.
feature: Implementation Basics
exl-id: 8fd07285-f702-4770-81bd-5f856561f4a9
role: Admin, Developer, Leader, User
TQID: 'https://experienceleague.adobe.com/UzZipOHP99eBzygkSajbyuPsWsRM-MvfVf5Myv2CSmA'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
subfeature_v2:
  - id: e992d880-33bc-4949-a648-aa7d410276cd
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 301a0341e725ca15f1700046528ea5f42969add4
workflow-type: tm+mt
source-wordcount: 681
ht-degree: 75%

---

# Depurador herdado

>[!IMPORTANT]
>
>Essa ferramenta de depuração não será mais mantida. Em vez disso, a Adobe recomenda usar a [Extensão Chrome do Adobe CX Enterprise Debugger](https://experienceleague.adobe.com/pt-br/docs/experience-platform/debugger/home).

O [!UICONTROL Depurador herdado] inspeciona as marcas da maioria dos serviços do Adobe CX Enterprise. Usar o depurador permite ver quais dados são enviados para a Adobe em qualquer página do site. Use essas informações para solucionar problemas ou validar a implementação de sua organização.

## Instalação do Debugger herdado

Crie um bookmarklet do JavaScript para instalar o depurador.

### Etapa 1: Copiar código do bookmarklet

Copie o código a seguir na área de transferência:

```JavaScript
javascript:void(window.open("","stats_debugger","width=800,height=800,location=0,menubar=0,status=1,toolbar=0,resizable=1,scrollbars=1").document.write("<script language=\"JavaScript\" id=dbg src=\"https://www.adobetag.com/d1/digitalpulsedebugger/live/DPD.js\"></"+"script>"+"<script language=\"JavaScript\">window.focus();</script>"));
```

### Etapa 2: Colar o código do bookmarklet em um marcador

Cada navegador tem diferentes maneiras de manipular marcadores, mas o conceito é o mesmo. Um marcador é criado com o nome desejado e o código do bookmarklet como o URL.

#### Chrome

Se não quiser usar a [extensão do Chrome](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=pt-BR), o bookmarklet do depurador herdado poderá ser usado.

1. Clique nos três pontos no canto superior direito e acesse Marcadores > Gerenciador de marcadores. Você também pode pressionar `Ctrl` + `Shift` + `O` (Windows) ou `Cmd` + `Shift` + `O` (Mac).
2. Na parte superior direita do gerenciador de marcadores, clique nos três pontos e em &#39;Adicionar novo marcador&#39;.
3. No campo Nome, rotule-o como &quot;Depurador herdado&quot; e cole o trecho de código no campo URL.
4. Use o gerenciador de marcadores para colocar seu novo bookmarklet no local desejado.

#### Firefox

1. Clique nas três linhas na parte superior direita e acesse Biblioteca > Marcadores > Mostrar todos os marcadores. Você também pode pressionar `Ctrl` + `Shift` + `B` (Windows) ou `Cmd` + `Shift` + `B` (Mac).
2. Clique em Organizar > Novo marcador.
3. No campo Nome, rotule-o como &quot;Depurador herdado&quot; e cole o trecho de código no campo Local. Os campos Tags e Palavra-chave não são obrigatórios.
4. Use a janela da biblioteca para colocar seu novo bookmarklet no local desejado.

#### Edge

O Edge não tem a capacidade de criar manualmente um bookmarklet, mas um URL do marcador pode ser editado em um bookmarklet.

1. Clique no ícone de estrela no lado direito do campo de URL para marcar a página atual.
2. Nomeie o marcador como &quot;Depurador herdado&quot; e salve-o no local desejado.
3. Clique no ícone de estrela com linhas para abrir a barra Favoritos.
4. Clique com o botão direito do mouse no marcador recém-criado e selecione &#39;Editar URL&#39;.
5. Cole o trecho de código no campo de texto e pressione Enter.

#### Safari

O Safari não tem a capacidade de criar manualmente um bookmarklet, mas um URL do marcador pode ser editado em um bookmarklet.

1. Clique no ícone Compartilhar na parte superior direita, que abre uma janela modal de marcadores.
2. Nomeie o marcador como &quot;Depurador herdado&quot; e salve-o no local desejado.
3. Clique em Marcadores > Editar marcadores e localize o marcador recém-criado.
4. Clique com o botão direito do mouse > Editar endereço e cole o trecho de código no campo de texto.

## Usar o depurador herdado

Navegue até a página desejada no site e clique no bookmarklet. Uma janela pop-up é exibida mostrando os dados enviados para a Adobe.

>[!NOTE]
>
>Determinados plug-ins de bloqueio de anúncios e de pop-ups podem interferir no carregamento da janela do depurador. Verifique se há pop-ups bloqueados no seu navegador e os ative para que o depurador funcione corretamente.

O depurador tem várias opções disponíveis, todas personalizam como os dados são exibidos. Nenhuma dessas opções afeta a coleta de dados.

* **[!UICONTROL Produtos do Experience Cloud exibidos]**: mostra ou oculta solicitações de imagem de cada produto do CX Enterprise.
* **[!UICONTROL Decodificação de URL]**: a URL decodifica a solicitação de imagem para corresponder ao que é exibido no relatório. A Adobe recomenda deixar essa caixa marcada.
* **[!UICONTROL Atualização Automática]**: atualiza automaticamente a pop-up a cada poucos segundos para verificar se há mais solicitações de imagem na página. Se precisar copiar/colar o conteúdo no depurador, desative a atualização automática para que a seleção seja mantida.
* **[!UICONTROL Formato Amigável]**: alterna o formato de exibição entre rótulos úteis e cadeias de consulta brutas em uma solicitação de imagem. Consulte [Parâmetros de consulta de coleta de dados](query-parameters.md) para obter mais informações.

Para salvar as opções de exibição padrão do depurador, clique com o botão direito do mouse no link &quot;Adobe Debugger&quot;, no canto superior direito, e copie o endereço do link. Edite o bookmarklet do depurador atual e cole o trecho de código atualizado no campo URL.
