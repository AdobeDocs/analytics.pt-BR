---
description: O processamento de regras simplifica a coleta de dados e o gerenciamento do conteúdo conforme é enviado para os relatórios.
subtopic: Processing rules
title: Visão geral das regras de processamento
feature: Admin Tools
uuid: 6b4ee7c9-2b86-47a6-b64c-c8d644fff67d
exl-id: 0244aba2-4345-463a-8528-d4dcd2f872ff
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 68%

---

# Visão geral das regras de processamento

O processamento de regras simplifica a coleta de dados e o gerenciamento do conteúdo conforme é enviado para os relatórios. As regras de processamento ajudam a simplificar a interação com grupos de TI e desenvolvedores da Web por fornecerem uma interface para:

* Definir um evento na página de visão geral do produto
* Preencher a campanha com um parâmetro de string de consulta
* Concatenar categoria e nome de página em um prop para facilitar o relatório
* Copiar uma eVar em um prop para ver novos caminhos
* Limpar seções do site com erros de ortografia
* Puxar termos de pesquisa internos ou uma ID de campanha da string de consulta para uma eVar

>[!VIDEO](https://video.tv.adobe.com/v/26124/?quality=12&learn=on)

## Permissões das regras de processamento {#section_8A4846688050453784DAE4D89355169A}

Os administradores têm direitos para usar as regras de processamento **por padrão**. Os administradores também podem conceder esses direitos a outros usuários através da interface de Ferramentas administrativas. Para obter instruções, consulte []

![](assets/processing-rules.png)

>[!IMPORTANT]
>
>Como as regras de processamento afetam permanentemente os dados do Analytics, o Adobe recomenda que os administradores recebam treinamentos certificados no Adobe Analytics e se familiarizem com todas as fontes de dados dos conjuntos de relatórios (sites padrão, sites móveis, aplicativos móveis, API de inserção de dados etc). O conhecimento das variáveis de dados de contexto e as variáveis padrão preenchidas em várias plataformas ajudará a impedir a exclusão ou alteração acidental dos dados.

## Usar dados de contexto para simplificar a coleção de dados {#section_09EEA03612D24C15839631AA9E9668D8}

As variáveis de dados de contexto são um tipo de variável que está disponível apenas para as regras de processamento. Para utilizar as variáveis de dados de contexto, os pares de dados chave/valor são enviados por meio da sua implementação e as regras de processamento são utilizadas para capturar esses valores nas variáveis padrão do Analytics. Isso dispensa os programadores de compreender exatamente qual prop e/ou eVar deve conter qual valor.

```js
s.contextData['author'] = "Robert Munch";
s.contextData['section'] = "Books";
s.contextData['genre'] = "Youth";
```

Depois de definido no código, você pode definir regras de processamento para atribuir valores a variáveis. Por exemplo:

1. Mapear `author` para `eVar2`
2. Mapear `section` para `prop1` e `eVar3`
3. Se `author` e `section` existirem, defina `event5`

Consulte [contextData](/help/implement/vars/page-vars/contextdata.md) no guia do usuário Implementar para obter mais informações.

## Usar regras de processamento para transformar dados de ocorrência e eventos de acionador  {#section_8284E72E999244E091CD7FB1A22342B6}

Regras de processamento podem monitorar valores recebidos para transformar erros de ortografia comuns e definir eventos com base nos dados relatados. Props podem ser copiados em eVars, valores podem ser concatenados para relatórios e eventos podem ser definidos.

## Uso das variáveis de dados de contexto em relatórios  {#section_BD098BC503024A0B8703596628071134}

Após definir os dados de contexto na implementação, é necessário copiá-los para variáveis, como eVars para uso em relatórios.

Consulte [Copiar uma variável de dados de contexto para um eVar](processing-rules-examples/processing-rules-copy-context-data.md) e [Definir um evento usando uma variável de dados de contexto](processing-rules-examples/processing-rules-copy-context-data-event.md) para obter mais informações.
