---
title: Visão geral da implementação do JavaScript do Código H
description: Saiba mais sobre o fluxo de trabalho para implementar o Código H no site.
feature: Implementation Basics
exl-id: cf83d8fe-a3b1-4e65-a86a-7eeaf555651b
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 100%

---

# Visão geral da implementação do JavaScript do Código H

>[!IMPORTANT]
>
>Essa versão da coleta de dados não é mais compatível. Atualize para [tags na Adobe Experience Platform](../../launch/overview.md) ou [AppMeasurement para JavaScript](../overview.md).

É necessário ter acesso aos servidores de hospedagem para implementar com êxito uma página com código para coletar dados. As etapas a seguir oferecem orientações para a implementação básica do Código H do Analytics.

>[!NOTE]
>
>Você já deve ter uma cópia existente do `s_code.js` para seguir essas instruções. A Adobe não oferece mais uma opção para baixar o Código H no Gerenciador de código.

1. **Atualizar variáveis do arquivo JS principal**: edite o arquivo `s_code.js` e verifique se as seguintes variáveis foram atualizadas:
   * `s_account` contém a ID do conjunto de relatórios para a qual você deseja enviar dados. Consulte
   * `s.trackingServer` contém os cookies de localização armazenados. Consulte [trackingServer](../../vars/config-vars/trackingserver.md).
1. **Hospede o arquivo `s_code.js` no site**: geralmente, esse arquivo reside em outros scripts no servidor da Web.
1. **Referência `s_code.js` em todas as páginas**: verifique se todas as páginas individuais chamam o arquivo JavaScript principal, e faça isso dentro da tag HTML `<body>` (não na tag `<head>`).

   >[!TIP]
   >
   >O código H exige que o script `s_code.js` seja chamado dentro da tag `<body>`. Isso é diferente de outros métodos de implementação, a maioria dos quais requer referências de script na tag `<head>`.
1. **Definir variáveis específicas da página em cada página**: cada página deve ter variáveis individuais definidas, como nome de página ou eVars. As variáveis individuais geralmente são definidas com uma tag `<script>` em linha em cada página.
1. **Usar o depurador para verificar a coleta de dados**: baixe e instale o [Experience Cloud Debugger](../../validate/debugger.md) para garantir que os dados sejam enviados para a Adobe e que as variáveis de página sejam definidas corretamente.

## Armazenamento em cache

O arquivo JavaScript é armazenado em cache no navegador do visitante depois que é carregado inicialmente, e também é feito o download não mais do que uma ver por sessão. O download não ocorre em todas as páginas, embora o arquivo seja usado por todas as páginas do site. Na maioria dos sites, os usuários têm em média mais do que algumas visualizações de página por sessão. Portanto, a transferência do JavaScript usado várias vezes neste arquivo pode resultar em menos download de dados em geral.

## Compactação do Código H

Se você estiver preocupado com o tamanho de download do arquivo `s_code.js`, a Adobe recomenda compactar o arquivo `s_code.js` usando GZIP. O GZIP é compatível com todos os principais navegadores e oferece melhor desempenho do que a compactação JavaScript. Consulte [Apache Module mod_deflate](https://httpd.apache.org/docs/current/mod/mod_deflate.html) na documentação do Apache.
