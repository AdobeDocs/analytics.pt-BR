---
description: Instale o Adobe Experience Cloud Debugger legado. Este depurador inspeciona as tags para o Analytics, Target, Advertising Cloud, Identity Service, DTM e Launch.
title: Depurador herdado da Adobe Experience Cloud
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Depurador herdado da Adobe Experience Cloud

> [!IMPORTANT] Essa ferramenta de depuração não é mais mantida. A Adobe recomenda usar a extensão [do Chrome do depurador da](https://docs.adobe.com/content/help/en/debugger/using/experience-cloud-debugger.html)Adobe Experience Cloud.

O [!UICONTROL Legacy Debugger] inspeciona tags para a maioria dos serviços da Adobe Experience Cloud. O uso do depurador permite que você veja quais dados são enviados para a Adobe em qualquer página específica do site. Você pode usar essas informações para solucionar problemas ou validar a implementação de sua organização.

## Instalação do Depurador Herdado

Crie um bookmarklet JavaScript para instalar o depurador.

### Etapa 1: Copiar código do bookmarklet

Copie o seguinte código para a área de transferência:

```JavaScript
javascript:void(window.open("","stats_debugger","width=800,height=800,location=0,menubar=0,status=1,toolbar=0,resizable=1,scrollbars=1").document.write("<script language=\"JavaScript\" id=dbg src=\"https://www.adobetag.com/d1/digitalpulsedebugger/live/DPD.js\"></"+"script>"+"<script language=\"JavaScript\">window.focus();</script>"));
```

### Etapa 2: Colar o código do bookmarklet em um marcador

Cada navegador tem diferentes maneiras de manipular marcadores, mas o conceito é o mesmo. Um marcador é criado com o nome desejado e o código do marcador como o URL.

#### Chrome

Se você insistir em não usar a extensão [do](https://docs.adobe.com/content/help/en/debugger/using/experience-cloud-debugger.html)cromo, o bookmarklet do depurador herdado poderá ser usado.

1. Clique nos três pontos no canto superior direito e vá até Marcadores &gt; Gerenciador de marcadores. Você também pode pressionar `Ctrl` + `Shift` + `O` (Windows) ou `Cmd` + `Shift` + `O` (Mac).
2. Na parte superior direita do gerenciador de marcadores, clique nos três pontos e clique em 'Adicionar novo marcador'.
3. No campo Nome, rotule-o como "Adobe Experience Cloud Debugger" e cole o trecho de código no campo URL.
4. Use o gerenciador de marcadores para colocar seu novo bookmarklet no local desejado.

#### Firefox

1. Clique nas três linhas na parte superior direita e vá até Biblioteca &gt; Marcadores &gt; Mostrar todos os marcadores. Você também pode pressionar `Ctrl` + `Shift` + `B` (Windows) ou `Cmd` + `Shift` + `B` (Mac).
2. Clique em Organizar &gt; Novo marcador.
3. No campo Nome, rotule-o como "Adobe Experience Cloud Debugger" e cole o trecho de código no campo Local. Os campos Tags e Palavra-chave não são obrigatórios.
4. Use a janela da biblioteca para colocar seu novo bookmarklet no local desejado.

#### Edge

O Edge não tem a capacidade de criar manualmente um bookmarklet, mas um URL de marcador pode ser editado.

1. Clique no ícone de estrela no lado direito do campo URL para marcar a página atual.
2. Nomeie o marcador "Adobe Experience Cloud Debugger" e salve-o no local desejado.
3. Clique no ícone de estrela com linhas para abrir a barra Favoritos.
4. Clique com o botão direito do mouse no marcador recém-criado e selecione 'Editar URL'.
5. Cole o trecho de código no campo de texto e pressione Enter.

#### Safari

O Safari não tem a capacidade de criar manualmente um bookmarklet, mas um URL de marcador pode ser editado.

1. Clique no ícone Compartilhar na parte superior direita, que abre uma janela modal de marcadores.
2. Nomeie o marcador "Adobe Experience Cloud Debugger" e salve-o no local desejado.
3. Clique em Marcadores &gt; Editar marcadores e localize o marcador recém-criado.
4. Clique com o botão direito do mouse &gt; Editar endereço e cole o trecho de código no campo de texto.

## Uso do depurador herdado

Para usar o depurador, navegue até a página desejada em seu site e clique no bookmarklet. Uma janela pop-up é exibida mostrando os dados enviados para a Adobe.

> [!NOTE] Determinados plug-ins de bloqueio de anúncios e bloqueadores de pop-ups podem interferir no carregamento da janela do depurador. Verifique se há pop-ups bloqueados no seu navegador e permita que o depurador funcione corretamente.

O depurador tem várias opções disponíveis, todas personalizadas como os dados são exibidos. Nenhuma dessas opções afeta a coleta de dados.

* **** Produtos da Experience Cloud exibidos: Mostra ou oculta solicitações de imagem para cada produto da Experience Cloud.
* **** Decodificação de URL: O URL decodifica a solicitação de imagem para corresponder ao que é exibido no relatório. A Adobe recomenda deixar essa caixa marcada.
* **** Atualização automática: Atualiza automaticamente o pop-up a cada poucos segundos para verificar se há mais solicitações de imagem na página. Se precisar copiar/colar o conteúdo no depurador, desative a atualização automática para que sua seleção permaneça.
* **** Formato amigável: Alterna o formato de exibição entre rótulos úteis e strings de consulta brutas em uma solicitação de imagem. Consulte Parâmetros [de consulta de coleta de](../js-implementation/data-collection/query-parameters.md) dados para obter mais informações.

Para salvar as opções de exibição padrão do depurador, clique com o botão direito do mouse no link "Adobe Debugger" no canto superior direito e copie o endereço do link. Edite o bookmarklet do depurador atual e cole o trecho de código atualizado no campo URL.
