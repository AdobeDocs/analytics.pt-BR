---
title: Como definir configurações para o Report Builder no Adobe Analytics
description: Descreve como definir as configurações de modo offline, idioma, data de início e solução de problemas.
role: Admin
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: d158ad45-d467-4355-b091-f015bde7a243
source-git-commit: ec14dde5b0e91a9fcfb217a811d36af2eea5f772
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 83%

---

# Configurações do Report Builder

Use o painel **Configurações** para definir as configurações no nível do aplicativo, como o idioma exibido pela interface ou se deseja, ou não, trabalhar no modo off-line. As configurações são aplicadas imediatamente e são definidas para todas as sessões futuras até serem alteradas.

Para alterar as configurações do Report Builder

1. Clique no ícone de **Configurações**.

1. Faça alterações para Ativar o modo offline, selecione um Idioma ou ative as configurações do log de Solução de problemas.

1. Clique em **Aplicar**.

   ![configurações de Report Builder.](./assets/image38.png)

## Modo offline

Ao criar e editar um bloco de dados no modo off-line, os dados não são recuperados. Em vez disso, os dados de simulação são usados para que você possa criar e editar rapidamente um bloco de dados sem esperar a execução da solicitação. Quando você voltar a ficar online, o comando *Atualizar bloco de dados* ou o comando *Atualizar todos os blocos de dados* atualiza os blocos de dados criados com os dados reais.

Para ativar o modo off-line

1. Clique no ícone de **[!UICONTROL Configurações]**.

1. Selecione **[!UICONTROL Habilitar modo offline]e**.

1. Insira um número inteiro positivo no **[!UICONTROL Exibir dados de métrica como]** campo.

1. Clique em **[!UICONTROL Aplicar]**.

## Idioma

Você pode escolher o idioma para a interface do Report Builder. Todos os idiomas suportados pelo Adobe Analytics estão disponíveis.

Para selecionar o idioma usado na interface do Report Builder

1. Clique em Configurações.

1. Selecione um idioma no menu suspenso **[!UICONTROL Idioma]**.

   Painel de intervalo de datas ![Report Builder mostrando a lista Idioma com inglês selecionado.](./assets/image39.png)

1. Clique em **[!UICONTROL Aplicar].**

## Solução de problemas

Use a configuração Solução de problemas para registrar todos os dados do cliente/servidor em um arquivo local. Use essa opção para ajudar a resolver tíquetes de suporte.

Para habilitar a opção Solução de Problemas, selecione **[!UICONTROL Registrar bloco de dados do Report Builder no console da Web]**.
