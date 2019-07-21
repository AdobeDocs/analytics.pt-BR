---
description: 'Etapas do processo de implementação '
keywords: Implementação do Analytics
seo-description: 'Etapas do processo de implementação '
seo-title: Aceitação de implementação
solution: Analytics
title: Aceitação de implementação
topic: Desenvolvedor e implementação
uuid: 6 f 7 ec 56 e -9 e 4 f -4 dc 8-b 534-92 b 1580 b 5 b 47
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Aceitação de implementação

Etapas do processo de implementação 

As etapas a seguir realçam o processo de implementação.

1. O consultor Adobe reúne os requisitos do relatório e cria um plano de coleta de dados baseado nesses requisitos.

   O plano de coleta de dados inclui definições de variável, regras VISTA necessárias e JavaScript personalizado, correlação de dados e todas as configurações de cada conjunto de relatórios. O cliente preenche o questionário de implementação.
1. Os recursos técnicos do lado do cliente implementam o código, o JavaScript específico do site e as variáveis do lado do servidor.
1. O consultor Adobe lida com os problemas técnicos durante a implementação e auxiliam nas descobertas de solução, conforme necessário.
1. Os recursos técnicos do lado do cliente testam a implementação.

   Testers log in to [!DNL Analytics] and verifying all variables ( *`page name`*, *`channel`*, *`server`*, *`events`*, *`campaign`*, econversion variables, custom traffic variables, *`products`*, and all other variables).
1. O cliente notifica a Adobe que a implementação foi concluída.

   O cliente fornece uma amostra de validação (amostra de dados) para o consultor Adobe validar a precisão dos dados. (Conjuntos de relatórios gerados por VISTA são validados com a comparação das métricas apropriadas. É necessário firmar um acordo do cliente com a Adobe antecipadamente, no momento da criação da regra VISTA, sobre as métricas que serão validadas.)
1. O cliente envia por fax (ou assina online) uma Aceitação e Contrato de Implementação referentes aos sites apropriados.
1. Depois do recebimento da aceitação, o consultor Adobe ativa a certificação das Práticas recomendadas da Adobe - Verificação da implementação na interface.
1. Opcionalmente, o cliente pode contratar com a Adobe serviços de monitoramento de páginas principais dos sites implementados (geralmente são as páginas primárias, homepages e páginas críticas de entrada).

   Este software de monitoramento é descrito em um documento separado, mas acompanha páginas carregando e executando a página e, em seguida, comparando a solicitação de imagem com uma linha de base armazenada em um banco de dados. Se forem detectadas quaisquer diferenças, o software notificará a equipe especificada da Adobe (AM/IE) e o cliente por email.

Os itens a seguir ajudam a garantir uma implementação bem-sucedida:

* Um documento de práticas recomendadas voltado para o cliente e explicando os processos detalhadamente.
* O documento de validação que o cliente usa para testar a implementação.
* Um formulário de Aceitação e Contrato de Implementação para o cliente assinar.
* Um aplicativo de monitoramento que valida continuamente as tags.
* Uma relação com a Accenture para ajudar com o teste de implementação.
* Utilitários e/ou ferramentas para comparação de exibição de páginas e/ou pedidos. Essas comparações podem ser bastante difíceis.
* Um método ou processo para obter rapidamente o log de depuração de um determinado dia, por ID do conjunto de relatórios.

