---
description: A função s_gi() é usada para criar ou encontrar sua instância de AppMeasurement por ID de conjunto de relatórios. Internamente, o AppMeasurement rastreia cada instância criada e s_gi() retorna a instância existente para um conjunto de relatórios, se existir. Se uma instância não existe, uma nova instância é criada e retornada.
keywords: Implementação do Analytics
seo-description: A função s_gi() é usada para criar ou encontrar sua instância de AppMeasurement por ID de conjunto de relatórios. Internamente, o AppMeasurement rastreia cada instância criada e s_gi() retorna a instância existente para um conjunto de relatórios, se existir. Se uma instância não existe, uma nova instância é criada e retornada.
seo-title: A função s_gi()
solution: Analytics
title: A função s_gi()
topic: Desenvolvedor e implementação
uuid: a77de90e-c60e-4946-90cf-deaf8aa3d755
translation-type: tm+mt
source-git-commit: 506c670e4b2903cc71bb6880cd74c3392bbc751c

---


# A função s_gi()

A função s_gi() é usada para criar ou encontrar sua instância de AppMeasurement por ID de conjunto de relatórios. Internamente, o AppMeasurement rastreia cada instância criada e s_gi() retorna a instância existente para um conjunto de relatórios, se existir. Se uma instância não existe, uma nova instância é criada e retornada.

We recommend calling `s_gi()` before setting variables and making tracking calls throughout your page code. Isso garante que o objeto correto é usado para efetuar a chamada de rastreamento no caso da variável s ser substituída inadvertidamente.

## Como usar vários conjuntos de relatórios {#section_F2F3B76E7AFD4B4B91CDC8BBEB34BBC5}

O objeto retornado varia com base nas IDs de conjunto de relatórios enviadas. Por exemplo, se você efetuar a seguinte chamada inicial para `s_gi()`:

```
var s=s_gi('rsid1,rsid2')
```

A tabela a seguir descreve o que é retornado por chamadas subsequentes:

| **Chamada subsequente para s_gi** | **Descrição do objeto retornado** |
|---|---|
| `s=s_gi('rsid1,rsid2')` | O mesmo objeto mencionado anteriormente. |
| `s=s_gi('rsid1')` | Uma cópia do objeto criado anteriormente, mas não o original. |
| `s=s_gi('rsid1,rsid3')` | Uma cópia do objeto criado anteriormente, mas não o original. |
| `s=s_gi('rsid3')` | Um novo objeto vazio, sem variáveis de configuração definidas (ou seja, linkTrackVars está vazio, como linkDownloadFileTypes). |
