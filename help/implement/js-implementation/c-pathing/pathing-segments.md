---
description: A segmentação de caminhos por tipo de usuário é uma solicitação comum para tentar compreender como tipos específicos de usuários transitam em seu site.
keywords: Implementação do Analytics
seo-description: A segmentação de caminhos por tipo de usuário é uma solicitação comum para tentar compreender como tipos específicos de usuários transitam em seu site.
seo-title: Caminhos de segmento por tipo de usuário
solution: Analytics
title: Caminhos de segmento por tipo de usuário
topic: Desenvolvedor e implementação
uuid: 5 c 298 f 39-381 d -453 b-a 608-109 e 3276 b 361
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# Caminhos de segmento por tipo de usuário

A segmentação de caminhos por tipo de usuário é uma solicitação comum para tentar compreender como tipos específicos de usuários transitam em seu site.

É possível concatenar o tipo de usuário e o nome da página em uma [!UICONTROL sprop] e ativar a definição de caminho na [!UICONTROL sprop].

For example, let's say you have two user types: _Registered_ users and _Non-Registered_ users. Você deverá diferenciar esses dois tipos de usuário em cada página e colocar esses valores na sua [!UICONTROL sprop] designada. Quando você preenche a prop, ela deve ser exibida como abaixo:

```js
 s.prop1=”Registered : “ + s.pageName;
```

Se o usuário for registrado e tiver visitado a página inicial, o valor na prop será exibido desta forma:

```js
 “Registered : Home Page”
```

Se eles clicarem em outra página chamada de "Página 2", o valor nessa página será exibido desta forma:

```js
 “Registered : Page 2”
```

Com a [!UICONTROL Definição de caminho] ativada, você verá esses dois valores seguidamente. Se você quiser saber como usuários registrados se movem da página inicial, localize o valor "Registered : Home Page" em um dos relatórios de caminho e veja as páginas seguintes que eles visitaram. Nesse caso, eles foram para a "Página 2".
