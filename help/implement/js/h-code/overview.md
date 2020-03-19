---
title: Visão geral da implementação do JavaScript do Código H
description: Saiba mais sobre o fluxo de trabalho para implementar o Código H no site.
translation-type: ht
source-git-commit: 664d0cde8b8b17c86b47858611d459026aab0bef

---


# Visão geral da implementação do JavaScript do Código H

> [!IMPORTANT] Essa versão da coleta de dados não é mais compatível. Atualize para o [Adobe Experience Platform Launch](../../launch/overview.md) ou para o [AppMeasurement para JavaScript](../overview.md).

É necessário ter acesso aos servidores de hospedagem para implementar com êxito uma página com código para coletar dados. As etapas a seguir oferecem orientações para a implementação básica do Código H do Analytics.

> [!NOTE] Você já deve ter uma cópia existente do `s_code.js` para seguir essas instruções. A Adobe não oferece mais uma opção para baixar o Código H no Gerenciador de código.

1. **Atualizar variáveis do arquivo JS principal**: edite o arquivo `s_code.js` e verifique se as seguintes variáveis foram atualizadas:
   * `s_account` contém a ID do conjunto de relatórios para a qual você deseja enviar dados. Consulte
   * `s.trackingServer` contém os cookies de localização armazenados. Consulte [trackingServer](../../vars/config-vars/trackingserver.md).
2. **Hospede o arquivo`s_code.js`no site**: geralmente, esse arquivo reside em outros scripts no servidor da Web.
3. **Referência`s_code.js`em todas as páginas**: verifique se todas as páginas individuais chamam o arquivo JavaScript principal, e faça isso dentro da tag HTML `<body>` (não na tag `<head>`).
   > [!TIP] O código H exige que o script `s_code.js` seja chamado dentro da tag `<body>`. Isso é diferente de outros métodos de implementação, a maioria dos quais requer referências de script na tag `<head>`.
4. **Definir variáveis específicas da página em cada página**: cada página deve ter variáveis individuais definidas, como nome de página ou eVars. As variáveis individuais geralmente são definidas com uma tag `<script>` em linha em cada página.
5. **Usar o depurador para verificar a coleta de dados**: baixe e instale o [Experience Cloud Debugger](../../validate/debugger.md) para garantir que os dados sejam enviados para a Adobe e que as variáveis de página sejam definidas corretamente.

## Armazenamento em cache

O arquivo JavaScript é armazenado em cache no navegador do visitante depois que é carregado inicialmente, e também é feito o download não mais do que uma ver por sessão. O download não ocorre em todas as páginas, embora o arquivo seja usado por todas as páginas do site. Na maioria dos sites, os usuários têm em média mais do que algumas visualizações de página por sessão. Portanto, a transferência do JavaScript usado várias vezes neste arquivo pode resultar em menos download de dados em geral.

## Compactação do Código H

Se você estiver preocupado com o tamanho de download do arquivo `s_code.js`, a Adobe recomenda compactar o arquivo `s_code.js` usando GZIP. O GZIP é compatível com todos os principais navegadores e oferece melhor desempenho do que a compactação JavaScript. Consulte [Apache Module mod_deflate](http://httpd.apache.org/docs/current/mod/mod_deflate.html) na documentação do Apache.
