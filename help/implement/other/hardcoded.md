---
title: Implementar com solicitações de imagem codificadas
description: Implementar o Adobe Analytics usando uma tag de imagem HTML (solicitação de imagem codificada)
translation-type: tm+mt
source-git-commit: e758c070f402113b6d8a9069437b53633974a3e9
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 66%

---


# Implementar com solicitações de imagem codificadas

As bibliotecas do AppMeasurement fornecidas pelas Adobe compilam as variáveis presentes na página e, em seguida, as enviam como uma solicitação de imagem para a Adobe. Você pode ignorar totalmente as bibliotecas do AppMeasurement e enviar manualmente uma solicitação de imagem para a Adobe. Esse método exige a formulação manual da solicitação de imagem e a cadeia de caracteres de consulta.

Esse método de implementação pode ser usado em qualquer plataforma que exibe imagens de fontes externas. Ele não depende do JavaScript.

>[!NOTE]
>
>Embora as solicitações de imagem codificadas sejam fáceis de configurar, elas são difíceis de depurar, manter e dimensionar em projetos maiores. Verifique se as solicitações de imagem codificadas são a melhor opção para você antes de continuar.

## Sintaxe de solicitação de imagem

Veja a seguir um exemplo de solicitação de imagem codificada usando HTML:

```html
<img src="https://example.sc.omtrdc.net/b/ss/examplersid/1?AQB=1&g=http%3A%2F%2Fexample.com&pageName=Example%20hardcoded%20hit&v1=Example%20value&AQE=1"/>
```

* `https://` designa o protocolo Faça a correspondência do protocolo usado na solicitação de imagem com o protocolo que o resto do site usa.
* `example.sc.omtrdc.net` é o valor contido na variável [`trackingServer`](/help/implement/vars/config-vars/trackingserver.md).
* `/b/ss/` está incluído em todas as solicitações de imagem. Ele faz parte da estrutura de arquivos de imagens armazenadas nos servidores de coleta de dados da Adobe.
* `examplersid` é a ID do conjunto de relatórios para a qual você deseja enviar dados.
* `/1/` é a origem da ocorrência. Consulte `hit_source` em [Referência da coluna de dados](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md) no guia do usuário Exportar. Controla a ordem usada por cookies e outros métodos para identificar visitantes.
* Todos os dados após o delimitador da cadeia de caracteres de consulta (`?`) são os que você deseja incluir nos relatórios. Consulte [Parâmetros de consulta de coleta de dados](../validate/query-parameters.md) para obter a lista completa de parâmetros que podem ser incluídos em uma solicitação de imagem.

## Solicitações de imagem codificada no Microsoft Outlook

Como a maioria dos emails se baseia em HTML, é possível rastrear emails abertos e enviar esses dados para a Adobe Analytics. Se sua organização optar por usar esse método, observe o seguinte:

* Cada renderização de email pode incrementar uma chamada de servidor faturável.
* Somente clientes de email que suportam HTML e permitem imagens são rastreados. Alguns clientes de email, como o Microsoft Outlook, bloqueiam imagens externas por padrão. Esses e-mails não são rastreados até que o recipient opte por baixar imagens externas.

Para compor um email do Outlook que inclui uma solicitação de imagem:

1. Abra um editor HTML. Se um editor HTML não estiver disponível, um editor de texto simples também funcionará.
2. Em um novo arquivo HTML, insira uma `<img>` tag de solicitação de imagem codificada encapsulada em uma `<body>` tag.
3. Salve o arquivo HTML.
4. Abra o Microsoft Outlook e componha um email.
5. Vá para a guia Inserir e clique em **Anexar arquivo**. Selecione seu arquivo HTML de solicitação de imagem.
6. Clique no menu pop-up ao lado de Inserir e selecione **Inserir como texto**. Se você clicar no botão Inserir sem o menu pop-up, o arquivo HTML se tornará um anexo, o que não funciona.

Seu email não parece mudar, pois a solicitação de imagem é um pixel transparente 1x1. Se você quiser ver a solicitação de imagem para fins de teste, modifique o arquivo HTML para incluir uma borda, texto adicional ou outro conteúdo.

## Perguntas frequentes

Saiba mais sobre perguntas comuns usando solicitações de imagem codificadas.

### Os parâmetros da cadeia de caracteres de consulta fazem distinção entre maiúsculas e minúsculas?

Sim. Verifique se os parâmetros da cadeia de caracteres de consulta correspondem exatamente ou se eles não foram registrados. Por exemplo, `pagename` não é um parâmetro de cadeia de caracteres de consulta válido, mas `pageName` é.

### É possível incluir espaços na cadeia de caracteres de consulta?

Os valores de cada parâmetro de cadeia de caracteres de consulta deve ser codificado em URL. A codificação de URL converte caracteres que normalmente são ilegais em URLs de caracteres legais. Por exemplo, um caractere de espaço é convertido em `%20`. Certifique-se de que qualquer caractere que não seja alfanumérico esteja codificado no URL. A Adobe decodifica automaticamente os valores de URL quando as solicitações de imagem atingem os servidores de coleta de dados.

Consulte [Referência de codificação de URL HTML](https://www.w3schools.com/tags/ref_urlencode.asp) em W3Schools para obter mais informações sobre como funciona a codificação de URL.

### Qual é o número máximo de caracteres que um único valor pode ter?

Cada variável tem um tamanho máximo diferente. A maioria das variáveis de tráfego tem até 100 bytes, enquanto a maioria das variáveis de conversão tem até 255 bytes. Quando uma solicitação de imagem atinge os servidores de coleta de dados, a Adobe trunca automaticamente esses valores para a duração máxima.
