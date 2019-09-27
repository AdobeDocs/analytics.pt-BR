---
description: Os Downloads de arquivo ajudam você a entender com que frequência seus visitantes baixam arquivos do site. Exemplos de downloads de arquivo podem ser documentos de processador de palavra, planilhas, arquivos de áudio, arquivos de filme, manuais do usuário e assim por diante. Isso inclui ambos arquivos sendo salvos e abertos diretamente do navegador, assim como arquivos salvos no computador do usuário. O relatório mostra o nome do arquivo sendo baixado, inclusive o URL completo necessário para acessar o arquivo.
seo-description: Os Downloads de arquivo ajudam você a entender com que frequência seus visitantes baixam arquivos do site. Exemplos de downloads de arquivo podem ser documentos de processador de palavra, planilhas, arquivos de áudio, arquivos de filme, manuais do usuário e assim por diante. Isso inclui ambos arquivos sendo salvos e abertos diretamente do navegador, assim como arquivos salvos no computador do usuário. O relatório mostra o nome do arquivo sendo baixado, inclusive o URL completo necessário para acessar o arquivo.
seo-title: Downloads de Arquivos
solution: Analytics
title: Downloads de Arquivos
topic: Relatórios
uuid: 897fc221-aa30-4eac-aca6-bccb76adaf71
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Downloads de Arquivos

Os Downloads de arquivo ajudam você a entender com que frequência seus visitantes baixam arquivos do site. Exemplos de downloads de arquivo podem ser documentos de processador de palavra, planilhas, arquivos de áudio, arquivos de filme, manuais do usuário e assim por diante. Isso inclui ambos arquivos sendo salvos e abertos diretamente do navegador, assim como arquivos salvos no computador do usuário. O relatório mostra o nome do arquivo sendo baixado, inclusive o URL completo necessário para acessar o arquivo.

**Navegação**

**[!UICONTROL Relatórios]** &gt; Conteúdo **** do site &gt; **[!UICONTROL Links]** &gt; Downloads **[!UICONTROL de arquivo]**

Se este relatório não estiver disponível no local padrão, verifique com os administradores do seu que podem ter alterado a estrutura do menu padrão para melhor servir as necessidades exclusivas da sua organização.

Use esse relatório para:

* Determine os arquivos que são transferidos por download com mais frequência do site.
* Entenda se certos arquivos que são transferidos por download com mais frequência durante períodos de tempo específicos.
* Valide se todos os formatos para um dado documento são obrigatórios.

   Por exemplo, talvez você esteja no momento traduzindo seus manuais de usuário para doze idiomas e disponibilizando-os pelo site. Com o relatório de download de arquivo, você pode saber com que frequência cada versão do manual do usuário é transferida por download e pode avaliar o valor de continuar traduzindo o manual do usuário para todos os doze idiomas.

**Solução de problemas**

Os relatórios de marketing capturam informações sobre arquivos transferidos por download de qualquer página do site que contenha o código JavaScript. No entanto, algumas variáveis devem estar presentes e configuradas corretamente para que as informações de download do arquivo possam ser relatadas. Se o relatório não estiver exibindo os dados, ou não mostra os valores esperados, siga as etapas abaixo para validar sua implementação.

1. No site, localize o arquivo global JavaScript. Geralmente, esse arquivo é nomeado como [!DNL s_code.js], mas pode ter sido renomeado. If it has been renamed, you can search the JavaScript files on your site for the value , which is a part of the JavaScript code.*`s.account`*

1. No arquivo, localize a variável [s.trackDownloadLinks](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_trackdownllinks.html). Certifique-se de configurar como *verdadeiro*

1. Localize a variável [s.linkDownloadFileTypes](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_linkdownfiletypes.html). Certifique-se de que todas as extensões de arquivo desejadas estão presentes nesta lista. If necessary, add missing extensions like [!DNL .zip], [!DNL .pdf], and so on.)

Se essas variáveis aparentarem estar configuradas corretamente, mas o [!UICONTROL Relatório de downloads de arquivo] não estiver recebendo dados, os usuários suportados de sua empresa devem entrar em contato com o Atendimento ao cliente.
