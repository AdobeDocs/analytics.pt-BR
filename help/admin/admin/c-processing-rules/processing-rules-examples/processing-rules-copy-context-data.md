---
description: As regras de processamento são usadas para mover valores das variáveis de Dados de contexto para props e eVars.
solution: Analytics
subtopic: Processing rules
title: Copiar uma variável de dados de contexto para uma eVar
topic: Admin tools
uuid: 1beaec4c-71e9-49ce-b154-78408cc532a3
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Copiar uma variável de dados de contexto para uma eVar

As regras de processamento são usadas para mover valores de variáveis de dados de contexto para props e eVars. Sem regras de processamento, as variáveis de dados de contexto não têm significado e não preenchem nenhum relatório no Analytics.

A lista de [!UICONTROL variáveis de contexto] contém todas as variáveis que foram enviadas para o conjunto de relatórios nos últimos 30 dias. If you know the context data variable name but have not sent it into the current report suite, you can add a value by typing the variable name and clicking **[!UICONTROL Add variable name context data]**:

![Adicionar](assets/add-context-variable.png)

O exemplo a seguir pega a variável de dados de `search_term` contexto e coloca seu valor em `eVar3`:

![Defina](assets/set-context-data.png)

O exemplo acima funciona perfeitamente quando há apenas algumas eVars a serem preenchidas. Se sua organização tiver centenas de variáveis de dados de contexto que cada uma precisa de sua própria eVar, você poderá usar declarações condicionais. Dezenas de declarações condicionais podem se encaixar em uma única regra de processamento, permitindo que sua organização preencha todas as eVars em um conjunto de relatórios sem entrar no limite de regras de processamento de 150 regras.

O exemplo a seguir é preenchido `prop7` com a variável de dados de contexto `testhierarchy`, mas somente se `testhierarchy` for definido:

![Condicional](assets/add-conditional.png)

Para obter mais informações sobre como implementar variáveis de dados de contexto, consulte Variáveis [de dados de](/help/implement/js-implementation/c-variables/context-data-variables.md) contexto no guia Implementar usuário.
