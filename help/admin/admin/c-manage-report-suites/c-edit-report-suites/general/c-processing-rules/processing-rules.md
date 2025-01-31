---
description: O processamento de regras simplifica a coleta de dados e o gerenciamento do conteúdo conforme é enviado para os relatórios.
subtopic: Processing rules
title: Visão geral das regras de processamento
feature: Processing Rules
role: Admin
exl-id: 0244aba2-4345-463a-8528-d4dcd2f872ff
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 97%

---

# Visão geral das regras de processamento

O processamento de regras simplifica a coleta de dados e o gerenciamento do conteúdo conforme é enviado para os relatórios. As regras de processamento ajudam a simplificar a interação com grupos de TI e desenvolvedores da Web por fornecerem uma interface para:

* Definir um evento na página de visão geral do produto
* Preencher a campanha com um parâmetro de string de consulta
* Concatenar categoria e nome de página em um prop para facilitar o relatório
* Copiar uma eVar em um prop para ver novos caminhos
* Limpar seções do site com erros de ortografia
* Puxar termos de pesquisa internos ou uma ID de campanha da string de consulta para uma eVar



>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Visão geral das regras de processamento](https://video.tv.adobe.com/v/26124/?quality=12&learn=on){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]


## Permissões de regras de processamento {#section_8A4846688050453784DAE4D89355169A}

Os administradores têm o direito de usar as regras de processamento **por padrão**. Administradores também podem conceder esses direitos a outros usuários através da interface de Ferramentas administrativas. Para obter instruções, consulte []

![Regras de processamento](assets/processing-rules.png)

## Usar dados de contexto para simplificar a coleção de dados {#section_09EEA03612D24C15839631AA9E9668D8}

As variáveis de dados de contexto são um tipo de variável disponível somente para regras de processamento. Para utilizar as variáveis de dados de contexto, os pares de dados chave/valor são enviados por meio da sua implementação e as regras de processamento são utilizadas para capturar esses valores nas variáveis padrão do Analytics. Isso dispensa os programadores de compreender exatamente qual prop e/ou eVar deve conter qual valor.

```js
s.contextData['author'] = "Robert Munch";
s.contextData['section'] = "Books";
s.contextData['genre'] = "Youth";
```

Depois de definido no código, é possível definir regras de processamento para atribuir valores a variáveis. Por exemplo:

1. Mapear `author` para `eVar2`
2. Mapear `section` para `prop1` e `eVar3`
3. Se `author` e `section` existirem, defina `event5`

Consulte [contextData](/help/implement/vars/page-vars/contextdata.md) no guia de implementação do usuário para obter mais informações.

## Usar regras de processamento para transformar dados de ocorrência e acionar eventos {#section_8284E72E999244E091CD7FB1A22342B6}

Regras de processamento podem monitorar valores recebidos para transformar erros de ortografia comuns e definir eventos com base nos dados relatados. Props podem ser copiados em eVars, valores podem ser concatenados para relatórios e eventos podem ser definidos.

## Uso das variáveis de dados de contexto em relatórios {#section_BD098BC503024A0B8703596628071134}

Após definir as variáveis de dados de contexto na implementação, é necessário copiá-las para variáveis como eVars, para utilização em relatórios.

Consulte [Copiar uma variável de dados de contexto para um eVar](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md) e [Definir um evento usando uma variável de dados de contexto](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data-event.md) para obter mais informações.

## Limitações conhecidas

**Uso de quilates (^) nas regras de processamento.** Se você quiser usar quilates nas regras de processamento como delimitadores ou para outros fins, cada quilate deve ser representado por dois quilates. Por exemplo, representar um único quilate como ^^, um quilate duplo como ^^^, etc.