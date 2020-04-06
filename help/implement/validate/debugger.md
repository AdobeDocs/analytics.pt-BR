---
title: Adobe Experience Cloud Debugger herdado
description: Instale o Adobe Experience Cloud Debugger herdado. Este depurador inspeciona as tags do Analytics, Target, Advertising Cloud, Serviço de identidade, DTM e Launch.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Adobe Experience Cloud Debugger herdado

>[!IMPORTANT] Essa ferramenta de depuração não será mais mantida. Em vez disso, a Adobe recomenda usar a [extensão do Chrome do Adobe Experience Cloud Debugger](https://docs.adobe.com/content/help/pt-BR/debugger/using/experience-cloud-debugger.html).

The [!UICONTROL Legacy Debugger] inspects tags for most Adobe Experience Cloud services. Usar o depurador permite ver quais dados são enviados para a Adobe em qualquer página do site. Use essas informações para solucionar problemas ou validar a implementação de sua organização.

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

Se não quiser usar a [extensão do Chrome](https://docs.adobe.com/content/help/pt-BR/debugger/using/experience-cloud-debugger.html), o bookmarklet do depurador herdado poderá ser usado.

1. Clique nos três pontos no canto superior direito e acesse Marcadores > Gerenciador de marcadores. Você também pode pressionar `Ctrl` + `Shift` + `O` (Windows) ou `Cmd` + `Shift` + `O` (Mac).
2. Na parte superior direita do gerenciador de marcadores, clique nos três pontos e em &#39;Adicionar novo marcador&#39;.
3. No campo Nome, rotule-o como &quot;Adobe Experience Cloud Debugger&quot; e cole o trecho de código no campo do URL.
4. Use o gerenciador de marcadores para colocar seu novo bookmarklet no local desejado.

#### Firefox

1. Clique nas três linhas na parte superior direita e acesse Biblioteca > Marcadores > Mostrar todos os marcadores. Você também pode pressionar `Ctrl` + `Shift` + `B` (Windows) ou `Cmd` + `Shift` + `B` (Mac).
2. Clique em Organizar > Novo marcador.
3. No campo Nome, rotule-o como &quot;Adobe Experience Cloud Debugger&quot; e cole o trecho de código no campo Local. Os campos Tags e Palavra-chave não são obrigatórios.
4. Use a janela da biblioteca para colocar seu novo bookmarklet no local desejado.

#### Edge

O Edge não tem a capacidade de criar manualmente um bookmarklet, mas um URL do marcador pode ser editado em um bookmarklet.

1. Clique no ícone de estrela no lado direito do campo de URL para marcar a página atual.
2. Nomeie o marcador &quot;Adobe Experience Cloud Debugger&quot; e salve-o no local desejado.
3. Clique no ícone de estrela com linhas para abrir a barra Favoritos.
4. Clique com o botão direito do mouse no marcador recém-criado e selecione &#39;Editar URL&#39;.
5. Cole o trecho de código no campo de texto e pressione Enter.

#### Safari

O Safari não tem a capacidade de criar manualmente um bookmarklet, mas um URL do marcador pode ser editado em um bookmarklet.

1. Clique no ícone Compartilhar na parte superior direita, que abre uma janela modal de marcadores.
2. Nomeie o marcador &quot;Adobe Experience Cloud Debugger&quot; e salve-o no local desejado.
3. Clique em Marcadores > Editar marcadores e localize o marcador recém-criado.
4. Clique com o botão direito do mouse > Editar endereço e cole o trecho de código no campo de texto.

## Usar o depurador herdado

Navegue até a página desejada no site e clique no bookmarklet. Uma janela pop-up é exibida mostrando os dados enviados para a Adobe.

>[!NOTE] Determinados plug-ins de bloqueio de anúncios e de pop-ups podem interferir no carregamento da janela do depurador. Verifique se há pop-ups bloqueados no seu navegador e os ative para que o depurador funcione corretamente.

O depurador tem várias opções disponíveis, todas personalizam como os dados são exibidos. Nenhuma dessas opções afeta a coleta de dados.

* **Produtos da Experience Cloud exibidos:** mostra ou oculta solicitações de imagem de cada produto da Experience Cloud.
* **Decodificação de URL:** o URL decodifica a solicitação de imagem para corresponder ao que é exibido no relatório. A Adobe recomenda deixar essa caixa marcada.
* **Atualização automática**: atualiza automaticamente a pop-up a cada poucos segundos para verificar se há mais solicitações de imagem na página. Se precisar copiar/colar o conteúdo no depurador, desative a atualização automática para que a seleção seja mantida.
* **Formato amigável:** alterna o formato de exibição entre rótulos úteis e cadeias de consulta brutas em uma solicitação de imagem. Consulte [Parâmetros de consulta de coleta de dados](query-parameters.md) para obter mais informações.

Para salvar as opções de exibição padrão do depurador, clique com o botão direito do mouse no link &quot;Adobe Debugger&quot;, no canto superior direito, e copie o endereço do link. Edite o bookmarklet do depurador atual e cole o trecho de código atualizado no campo URL.
