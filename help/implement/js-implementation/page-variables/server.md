---
description: As variáveis de página populam diretamente um relatório, como pageName, Propriedades de lista, Variáveis de lista, entre outros.
keywords: Analytics Implementation
subtopic: Variables
title: Variáveis de página
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# servidor

A variável é usada para mostrar o domínio de uma página da Web (para mostrar a quais domínios as pessoas vão) ou o servidor que atende a página (para uma referência rápida de balanceamento de carga).


<!-- 

server.xml

 -->

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| 100 bytes | servidor | Servidores | "" |

Se seu site tiver mais que um domínio atendendo o mesmo conteúdo, a variável *`server`* poderá ser usada para rastrear quais desses domínios os visitantes estão usando. O JavaScript a seguir preencherá o domínio da página na variável do servidor.

```js
s.server=window.location.hostname
```

Se você estiver usando a variável do servidor para oferecer uma orientação rápida sobre balanceamento de carga, poderá inserir um nome ou número de servidor na variável do servidor. Considere o exemplo a seguir:

```js
s.server="server 14"
```

Embora o relatório [!UICONTROL Servidores Mais Populares] possam ser usados como referência rápida para o balanceamento de carga, ele não é uma medida precisa de carga do servidor. Por exemplo, o tráfego do botão voltar não aumenta a carga de servidor, mas é mostrado nos relatórios. O relatório não mostra quais servidores estão promovendo imagens ou downloads grandes.

**Sintaxe e valores possíveis** {#section_48E4B9BFEBFF4409A246D86EC0C0FB13}

```js
s.server="server_name"
```

Não há limitações na variável *`server`* além das limitações padrão de variáveis.

**Exemplos** {#section_78B9EE3C27FB491384869E3D0BD503D6}

```js
s.server="server 18" 
s.server=window.location.hostname 
```

**Configurações** {#section_969DB379D5BD469FBEE8D505D3000E49}

Nenhum

**Armadilhas, dúvidas e dicas** {#section_42A28F9B01574F38891D9D54B411D8FE}

A variável *`server`* pode ser usada para mostrar quais domínios são mais populares ou quais servidores estão promovendo mais páginas.

