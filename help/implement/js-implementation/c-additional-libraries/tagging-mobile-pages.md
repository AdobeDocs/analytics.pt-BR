---
description: O código de rastreamento remoto é inserido na página, no formulário de uma tag de imagem gerada por servidor.
keywords: Analytics Implementation;mobile tracking;mobile protocols;prevent caching;alt tag;default image type
title: Como marcar páginas para protocolos móveis
topic: Developer and implementation
uuid: 5788beaf-f309-4918-a99c-a3e591668205
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Como marcar páginas para protocolos móveis

O código de rastreamento remoto é inserido na página, no formulário de uma tag de imagem gerada por servidor.

O código de rastreamento remoto é inserido na página, no formulário de uma tag de imagem gerada por servidor. Devido à incompatibilidade das linguagens de script como JavaScript e WMLScript em dispositivos móveis, o beacon de rastreamento não pode ser gerado dinamicamente por uma linguagem de script.

Embora a imagem do beacon móvel seja de 2x2 pixels, para garantir o suporte a todos os dispositivos móveis, você deve definir as propriedades de altura e largura como 5. Por exemplo:

```
<img sr c="https://metric.mydomain.com/b/ss/<Report_Suite_Name>/5/<random_number>?pageName=" alt="" width="5" height="5"/>
```

## Uso de um número aleatório para impedir o armazenamento em cache {#section_BF5C344A16034C439C8704632CF673A7}

Embora servidores da Adobe instruam os navegadores a não armazenarem em cache o beacon de rastreamento, nem todos os navegadores seguem essa instrução. Para impedir o armazenamento do beacon em cache, é recomendável que o servidor da Web gere dinamicamente um número aleatório no caminho de URL da imagem. Isso garantirá mais precisão na geração de relatórios. O número aleatório deverá estar na última seção do caminho, como mostrado aqui:

```js
<img src="https://rsid.112.2O7.net/b/ss/rsid/5/H.5--WAP/12345?pageName=" />.
```

## Incluir uma tag ALT {#section_FBD8B2FD1EA0429580C2B933DA300B07}

Alguns navegadores móveis exigem que todas as imagens tenham o texto alt incluídos na tag da imagem. O exemplo a seguir mostra como o atributo ALT deve aparecer na tag da imagem:

```js
<img src="https://rsid.112.2O7.net/b/ss/rsid/5/H.5--WAP/12345?pageName=" alt=""/>.
```

É importante que o /5/ sempre apareça corretamente no caminho. Ele é usado pelos servidores da Adobe para identificar dispositivos móveis. Se o /1/ padrão for usado, os servidores da Adobe tentarão definir um cookie no dispositivo móvel.

## Alterar o tipo de imagem padrão {#section_2F969909010D4A64BF6E092A32ABADB7}

Se o tipo de imagem padrão não é suportado em um dispositivo específico, nenhum dado é retornado. Para evitar isso, você pode forçar o servidor de coleção de dados da Adobe a retornar um tipo de gráfico específico compatível com o dispositivo móvel. O código após o nome do conjunto de relatórios especifica o tipo de imagem:

* `/5/` retorna o tipo de imagem padrão.
* `/5.1/` ou `/1/` sempre retornam uma imagem GIF.

* `/5.5/` sempre retorna uma imagem WBMP.

Consulte [Identificação de visitantes usando protocolos móveis](/help/implement/js-implementation/c-unique-visitors/visid-mobile.md).
