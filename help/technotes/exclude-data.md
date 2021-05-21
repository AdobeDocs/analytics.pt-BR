---
title: Excluir dados no Adobe Analytics
description: Saiba mais sobre os vários métodos de exclusão de dados antes e depois da coleção de dados.
exl-id: dee5bf3b-8bb3-48eb-908d-b4a981f17bfb
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '352'
ht-degree: 100%

---

# Excluir dados no Adobe Analytics

A exclusão de dados é usada com frequência para impedir que os esforços de teste de sua organização preencham os dados de produção ou para impedir que dados indesejados inflem indevidamente os relatórios. Use qualquer um dos métodos a seguir para excluir dados do Adobe Analytics, dependendo do caso de uso.

## Excluir dados após a coleção de dados

Os métodos a seguir são maneiras de excluir dados nos relatórios do Analytics depois que os servidores de coleção de dados do Adobe recebem solicitações de imagem. Os dados excluídos por meio desses métodos ainda contam para chamadas de servidor faturáveis.

* **Excluir por IP**: o Adobe Analytics oferece a funcionalidade básica de excluir dados de endereços IP ou intervalos em um conjunto de relatórios. Consulte [Excluir por IP](/help/admin/admin/exclude-ip.md) no Guia do usuário do administrador.
* **Regras de bot**: as regras de bot recebem tráfego de strings conhecidas do agente do usuário do bot e as excluem dos relatórios do Analytics. Os dados excluídos por meio de regras de bot são colocados no relatório Bots. Regras de bot personalizadas podem ser criadas para excluir dados adicionais. Consulte [Regras de bot](/help/admin/admin/bot-removal/bot-rules.md) no Guia do usuário administrador.
* **Regras VISTA**: dependendo das necessidades da sua organização, as ocorrências que correspondem aos seus requisitos são enviadas para outro conjunto de relatórios dedicado ao recebimento de dados excluídos. As regras VISTA geralmente são usadas em relação a endereços IP, mas não estão limitadas a eles. Você pode usar qualquer dimensão para incluir ou excluir dados em conjuntos de relatórios. As regras VISTA estão sujeitas a custos adicionais; entre em contato com o gerente de conta da sua organização para obter detalhes.
* **Cookies de recusa**: todos os visitantes do seu site podem recusar voluntariamente o rastreamento no Adobe Analytics visitando uma página específica do seu servidor de rastreamento. Consulte [Implementar links de opção de não participação](/help/implement/js/opt-out.md) no guia do usuário de implementação.

>[!TIP]
>
>As regras de processamento não podem excluir dados ou enviar dados para outro conjunto de relatórios. No entanto, determinadas variáveis podem ser definidas condicionalmente e um segmento pode ser usado para excluir esses dados do relatório.

## Excluir dados pré-coleção de dados

Se você quiser impedir que determinadas ocorrências cheguem aos servidores de coleção de dados do Analytics, use a variável [`abort`](/help/implement/vars/config-vars/abort.md). Esse sinalizador impede o envio da solicitação de imagem. Chamadas de servidor faturáveis não são aumentadas para solicitações de imagem anuladas, já que não chegam aos servidores de coleção de dados da Adobe.
