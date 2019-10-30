---
description: A segmentação de caminhos por tipo de usuário é uma solicitação comum para tentar compreender como tipos específicos de usuários transitam em seu site.
keywords: Implementação do Analytics
seo-description: A segmentação de caminhos por tipo de usuário é uma solicitação comum para tentar compreender como tipos específicos de usuários transitam em seu site.
seo-title: Segmentar caminhos por tipo de usuário
solution: Analytics
title: Segmentar caminhos por tipo de usuário
topic: Desenvolvedor e implementação
uuid: 5c298f39-381d-453b-a608-109e3276b361
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Segmentar caminhos por tipo de usuário

A segmentação de caminhos por tipo de usuário é uma solicitação comum para tentar compreender como tipos específicos de usuários transitam em seu site.

É possível concatenar o tipo de usuário e o nome da página em uma [!UICONTROL sprop] e ativar a definição de caminho na [!UICONTROL sprop].

Por exemplo, digamos que você tenha dois tipos de usuário: _Registrados_ e _Não registrados_. Você deverá diferenciar esses dois tipos de usuário em cada página e colocar esses valores na sua [!UICONTROL sprop] designada. Quando você preenche a prop, ela deve ser exibida como abaixo:

```js
 s.prop1="Registered : " + s.pageName;
```

Se o usuário for registrado e tiver visitado a página inicial, o valor na prop será exibido desta forma:

```js
 "Registered : Home Page"
```

Se eles clicarem em outra página chamada de "Página 2", o valor nessa página será exibido desta forma:

```js
 "Registered : Page 2"
```

Com a [!UICONTROL Definição de caminho] ativada, você verá esses dois valores seguidamente. Se você quiser saber como usuários registrados se movem da página inicial, localize o valor "Registered : Home Page" em um dos relatórios de caminho e veja as páginas seguintes que eles visitaram. Nesse caso, eles foram para a "Página 2".
