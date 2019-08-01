---
description: Para ativar a integração, você deve concluir o assistente de integração Qualtrics na interface dos Conectores de dados
seo-description: Para ativar a integração, você deve concluir o assistente de integração Qualtrics na interface dos Conectores de dados
seo-title: Conclusão do Assistente de integração da Adobe
solution: Analytics
subtopic: Qualtrics
title: Conclusão do Assistente de integração da Adobe
topic: Conectores de dados
uuid: e 065 fba 4-1 fe 1-4 e 25-9 c 45-6 c 52 dc 20 f 81 e
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Completing the Adobe Integration Wizard{#completing-the-adobe-integration-wizard}

Para ativar a integração, você deve concluir o assistente de integração Qualtrics na interface dos Conectores de dados

1. Navegue até conectores de dados e inicie o assistente de integração Qualtrics. ([Ajuda dos conectores de dados](http://microsite.omniture.com/t2/help/en_US/genesis/)).
1. Selecione o conjunto de relatórios que deseja usar para essa integração e forneça um nome.

   Preencha o assistente de integração, fornecendo as informações descritas nas etapas a seguir. 1. **Wizard Step 1**

   | Email Address | O endereço de email principal do contato. |
   |---|---|
   | Descrição | (Opcional) Descrição para essa configuração de integração. |
   | ID da organização Qualtrics | [Pesquisar a ID da organização Qualtrics](../../qualtrics-overview/qualtrics-org-id.md#task-47ea30d6dcd24893986a5e5b8dcf5e96) |
   | Adobe sitecatalyst Token | [Geração do token Qualtrics Adobe Analytics](../../qualtrics-overview/qualtrics-token.md#task-e32eacbc91614008b84e6b2f0b92d372) |

1. ** Assistente de etapa 2 - Mapeamentos de variáveis**

   | Lista de respostas Qualtrics | Selecione uma variável de lista disponível em seu conjunto de relatórios. (Talvez seja necessário habilitar uma nova listvar no Gerenciador de conjunto de relatórios.) |
   |---|---|
   | ID de resposta Qualtrics | Selecione uma evar ou prop disponível de seu conjunto de relatórios. (Talvez seja necessário habilitar uma nova listvar no Gerenciador de conjunto de relatórios.) |
   | Servidor de rastreamento | Forneça a configuração do servidor de rastreamento (domínio) usada para rastrear os dados do Adobe Analytics. Use the `trackingServerSecure` tracking server if it differs from your standard tracking server setting. |
   | Envios de Pesquisa Qualtrics | Selecione um evento disponível em seu conjunto de relatórios (pode ser necessário ativar um novo evento no Gerenciador de conjunto de relatórios). |

1. **Etapa 3 do assistente**: Nada necessário, somente informativo.

   Resultado da etapa 1. ** Etapa 4 do assistente - Exportar configurações**

   | eVar | Selecione até cinco de suas evars para expor para exportar para Qualtrics |
   |---|---|
   | Eventos  | Selecione até cinco de seus eventos personalizados para expor para exportar para Qualtrics |
   | Props | Selecione até cinco de suas props para expor para exportar para Qualtrics |
   | Solicitações de acesso | Marque a caixa para qualquer uma das métricas e dimensões padrão que você deseja exportar para Qualtrics. The `visitor_id` is required to allow the export to function properly. |

1. **Etapa 5 do assistente**: Revise a configuração e clique **[!UICONTROL em Ativar agora]**.
