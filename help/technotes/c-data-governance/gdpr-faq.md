---
description: Perguntas frequentes sobre governança de dados do Adobe Analytics
title: Perguntas frequentes sobre governança de dados
feature: Data Governance
exl-id: 57399c1b-cf08-405b-8c1b-9d23e4c38716
source-git-commit: e26e04e965554f0e9e7f06f0129175f1d24a3f23
workflow-type: tm+mt
source-wordcount: '2076'
ht-degree: 52%

---

# Perguntas frequentes

+++ **Como o Adobe Analytics suporta as solicitações de acesso e exclusão dos usuários finais (titulares de dados) validadas pelos clientes (controladores de dados)?**

Quando várias regras da Privacidade de dados (GDPR, CCPA) entrarem em vigor, o Adobe Analytics suportará o processamento de solicitações verificadas, enviadas pelos Controladores de dados para a API da Privacidade de dados do Experience Cloud, para permitir um processo mais automatizado. A API da Privacidade de dados da Adobe foi projetada para ajudar a processar as solicitações de direitos individuais (por exemplo, o acesso e a exclusão de solicitações) para os dados de clientes armazenados nas soluções da Adobe Experience Cloud. Ele é flexível e escalável de acordo com o número de solicitações de acesso e exclusão de dados recebidos pela sua empresa dos titulares de dados.

Além disso, a API do Privacy Service permite que o cliente verifique o status de como as solicitações de acesso e exclusão de dados estão sendo atendidas. Para obter mais detalhes, consulte a [](https://developer.adobe.com/experience-platform-apis/references/privacy-service/)Documentação da API do Privacy Service.

+++

+++ **Quem é responsável por receber, aceitar e atender às solicitações de Privacidade de dados de usuários finais?**

O Controlador de dados tem a responsabilidade exclusiva de receber e aceitar solicitações. O Controlador de dados valida a identidade do Titular de dados e, em seguida, atende à solicitação. Parte dessa responsabilidade pode envolver o contato do Adobe com as IDs dos titulares de dados que podem estar associadas aos dados armazenados no Adobe Analytics.

Como Processador de dados, o Adobe deve fornecer assistência razoável ao Controlador para processar as solicitações verificadas dentro de um período de tempo aceitável.

+++

+++ **Como os clientes da Adobe (controladores de dados) saberão quais solicitações de Privacidade de dados mapear para quais IDs do Adobe Analytics para o processamento da Privacidade de dados?**

Os controladores de dados determinam como resolver a identidade de solicitações dos titulares de dados. Considere a implantação da Tag de recuperação de ID da Privacidade de dados da Adobe. Suas equipes de desenvolvimento economizam tempo usando nossa tag de recuperação de ID da Privacidade de dados para capturar IDs de usuário (IDs de cookies). Em seguida, eles podem usar nossa API da Privacidade de dados para enviar essas IDs de usuário para as soluções relevantes no Adobe Experience Cloud para o processamento de solicitações de Privacidade de dados. A API da Privacidade de dados pode oferecer suporte a uma grande variedade de IDs de clientes em várias soluções da Adobe.

Se um Titular de dados enviar uma solicitação junto com um identificador (variável personalizada: prop ou eVar), o Adobe Analytics verificará todo o histórico retido dos dados coletados para o identificador especificado. Para obter mais detalhes sobre como configurar as IDs personalizadas armazenadas em props ou eVars do Analytics, consulte o [Documentação do Analytics sobre namespaces](/help/technotes/c-data-governance/data-labeling/gdpr-namespaces.md).

+++

+++ **Como a Governança de dados do Adobe Analytics pode ajudar no processamento de solicitações de Privacidade de dados?**

A Governança de dados é uma nova ferramenta no Adobe Analytics que fornece aos Controladores de dados a capacidade de aplicar controles e classificações de dados em seus dados do Analytics. Essa nova ferramenta permite que os clientes da Adobe personalizem o processamento de suas solicitações de acesso e exclusão de dados da Privacidade de dados. No console de Governança de dados, os administradores podem definir as configurações desejadas que devem ser aplicadas a várias colunas de dados que existentes no Adobe Analytics. Assim que esses rótulos forem definidos, a Adobe honrará e processará qualquer solicitação de acesso e exclusão de downstream de acordo com as configurações de rótulo desejadas pelos clientes. É de responsabilidade do Controlador de dados analisar e consultar seus representantes legais em relação a essas configurações de rótulo.

A ferramenta de Governança de dados contém os seguintes rótulos de dados:

* **Rótulos de dados de identidade**: Usado para classificar dados que podem identificar um indivíduo diretamente ou em combinação com outros dados. (Nenhum, I1, I2)

* **Rótulos de dados sensíveis**: Usada para classificar dados que podem ser definidos como confidenciais pela legislação aplicável. (Nenhum, S1, S2) Observe que, atualmente, o uso de dados confidenciais no Adobe Analytics é geralmente proibido, exceto para dados de localização geográfica precisos, obtidos adequadamente de acordo com a legislação aplicável, que podem ser considerados dados confidenciais em algumas jurisdições.

* **Rótulos de dados da privacidade de dados**: Usado para definir os campos que podem conter identificadores pessoais para uso em solicitações de Privacidade de dados ou que devem ser removidos como parte de uma solicitação de exclusão da Privacidade de dados. Em alguns casos, esses rótulos podem se sobrepor aos rótulos de identidade e dados confidenciais.

Para obter mais informações sobre rótulos de Governança de dados, consulte [Rótulos da Privacidade de dados para variáveis do Analytics](/help/technotes/c-data-governance/data-labeling/gdpr-labels.md).

+++

+++ **Como posso validar se as solicitações do Privacy Service estão funcionando corretamente para excluir dados do Adobe Analytics?**

Normalmente, os clientes do Analytics configuram alguns conjuntos de relatórios de teste para verificar a funcionalidade antes que ela seja disponibilizada para o público em geral. Sites ou aplicativos de pré-produção enviam dados para esses conjuntos de relatórios de teste/desenvolvimento/QA para avaliar como as coisas funcionarão quando o código for lançado antes que o tráfego real seja enviado para os conjuntos de relatórios de produção.

No entanto, com uma configuração normal, o processamento de solicitação de GDPR não pode ser testado primeiro nesses conjuntos de relatórios de teste, antes de aplicar solicitações a conjuntos de relatórios de produção. Isso ocorre porque uma solicitação de Privacidade de dados é aplicada automaticamente a todos os conjuntos de relatórios na organização do Experience Cloud, que geralmente engloba todos os conjuntos de relatórios da sua empresa.

Ainda assim, há algumas maneiras de testar o processamento da Privacidade de dados antes de aplicá-la a todos os seus conjuntos de relatórios:

* Uma opção é configurar uma Organização da Experience Cloud separada que contenha somente conjuntos de relatórios de teste. Use essa organização da Experience Cloud para realizar testes de Privacidade de dados e sua organização normal da Experience Cloud para processamentos de Privacidade de dados.

* Outra opção é atribuir namespaces diferentes à IDs nos conjuntos de relatórios de teste, em comparação com aqueles em seus conjuntos de relatórios de produção. Por exemplo, você pode adicionar prefixos “qa-” a cada namespace nos conjuntos de relatórios de teste. Ao enviar solicitações de Privacidade de dados com apenas namespaces com o prefixo &quot;qa&quot;, essas solicitações só são executadas em relação aos conjuntos de relatórios de teste. Posteriormente, quando você enviava solicitações sem o prefixo &quot;qa&quot;, elas eram aplicadas aos conjuntos de relatórios de produção. **Essa é a abordagem recomendada, a menos que você use os namespaces visitorId, AAID, ECID ou customVisitorId. Esses namespaces são codificados e não é possível especificar nomes alternativos para eles em seus conjuntos de relatórios de teste.**

+++

+++ **Como começar a preparação para a Privacidade de dados com o Adobe Analytics?**

Para obter uma apresentação passo a passo de preparação das regras da Privacidade de dados, consulte [Fluxo de trabalho da Privacidade de dados do Adobe Analytics](/help/technotes/c-data-governance/an-gdpr-workflow.md).

+++

+++ **Como os Controladores de dados devem lidar com o consentimento relacionado ao envolvimento do usuário?**

O GDPR e a CCPA são boas oportunidades para reconsiderar suas estratégias e práticas de gerenciamento de consentimento. Isso inclui determinar quando o consentimento é necessário e pensar na proposta de valor para o usuário. Considere a proposta de valor para a privacidade do cliente, que pode ajudar a impulsionar a conversão e a fidelidade. O espaço de gerenciamento de consentimento (por exemplo, ferramentas, padrões, práticas recomendadas) está evoluindo rapidamente e é uma área a ser observada. Para minimizar o impacto no engajamento do usuário, os Controladores devem trabalhar com os fornecedores neste espaço, bem como com seus advogados legais, para garantir que estejam seguindo as leis e orientações emergentes sobre consentimento e cookies. Considere a “privacidade experiencial” usando uma experiência sobre a marca, relevante contextualmente, que define a proposta de valor de suas atividades de coleta de dados.

Você, como o Controlador de dados, é responsável por obter consentimento explícito de seus Titulares de dados antes de coletar dados sobre eles (possivelmente incluindo dados do Adobe Analytics) e por implementar uma [mecanismo de opção](https://www.adobe.com/br/privacy/opt-out.html#customeruse) no seu site. Isso permite que os titulares de dados optem por cancelar a coleta de dados futura da Adobe Experience Cloud.

+++

+++ **Como os Controladores de dados devem lidar com a retenção de dados relacionada à Privacidade de dados?**

De um modo geral, os dados pessoais não devem ser conservados por mais tempo do que o necessário para atingir o objetivo para o qual foram recolhidos. Os termos gerais de retenção de dados aplicam-se por padrão a 5 meses, a menos que um termo diferente seja acordado por contrato. Os clientes devem definir sua política de retenção de dados antes que o Adobe possa processar uma solicitação de Privacidade de dados.

A politica de retenção de dados atual de cada conjunto de relatórios é exibida na nova interface do usuário do administrador da Governança de dados. Os clientes devem entrar em contato com o representante do Adobe caso precisem ajustar a política de retenção de dados. Consulte [Perguntas frequentes sobre a retenção de dados do Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/technotes/data-retention.html?lang=en).

+++

+++ **Um cliente pode reduzir ou estender o período padrão da retenção de dados?**

Os clientes podem solicitar que seus dados sejam excluídos antes de 25 meses, ligando para o Atendimento ao cliente. Os clientes também podem estender a retenção de dados além de 25 meses, comprando uma extensão. As extensões estão disponíveis em incrementos de 1 ano adicional, até um máximo de 8 anos adicionais (10 anos no total). Essas extensões exigirão termos de contrato atualizados e taxas adicionais.

+++

+++ **Quais critérios de privacidade devem ser considerados por um Controlador de dados ao exportar dados pessoais do Adobe Analytics?**

Se um cliente usar os feeds de dados para exportar os dados do Adobe Analytics para o Data warehouse corporativo ou para outros sistemas fora da Adobe, é responsabilidade do Cliente (o controlador de dados) garantir que as solicitações de exclusão sejam aplicadas aos dados. Isso também se aplica às implementações locais do Adobe Data Workbench, em que um feed de dados do Adobe Analytics em andamento preenche os dados do Data Workbench. A Adobe pode fornecer ferramentas para ajudar a encontrar e excluir os registros de determinados tipos de feeds de dados, incluindo aqueles usados para o Data Workbench, mas ainda é responsabilidade do Cliente (controlador de dados) garantir que os dados sejam excluídos de forma consistente com suas próprias políticas internas de exclusão e retenção de dados.

Considere também os casos em que os funcionários baixaram relatórios do Adobe Analytics que contêm dados pessoais. Esses relatórios podem precisar ser atualizados ou excluídos se uma solicitação de exclusão relacionada à Privacidade de dados for recebida com uma ID presente no relatório. Os clientes devem trabalhar com o departamento jurídico da própria empresa para determinar os períodos de retenção e os requisitos de privacidade e segurança que devem ser aplicados a esses tipos de documentos.

+++

+++ **Alguns dados que não deveríamos coletar foram enviados para o Adobe Analytics por acidente. Podemos usar a API da Privacidade de dados para limpar esses dados?**

O [API de Privacy Service de dados](https://developer.adobe.com/experience-platform-apis/references/privacy-service/) O foi fornecido para ajudar a atender à solicitações de Privacidade de dados, que são sensíveis ao tempo. O uso dessa API para outros propósitos não é suportado pela Adobe e pode afetar a capacidade da Adobe de fornecer solicitações de Privacidade de dados iniciadas por usuários com inversão de alta prioridade para outros clientes da Adobe.

Pedimos que você não use a API da Privacidade de dados para outros propósitos, como limpar dados enviados por acidente para grandes grupos de visitantes. Além disso, esteja ciente de que os usuários que têm uma ocorrência excluída (atualizada ou em anonimato) como o resultado de uma solicitação de exclusão da Privacidade de dados terão as informações de estado redefinidas. A próxima vez que o visitante retornar ao site, ele será um novo visitante. Todas as atribuições de eVar serão iniciadas novamente, assim como informações como números de visita, referenciadores, primeira página visitada etc. Esse efeito colateral não é desejável para situações em que você deseja limpar campos de dados, e realça o motivo pelo qual a API da Privacidade de dados é imprópria para este uso.

Entre em contato com o Gerente de conta (CSM) para coordenar com nossa equipe de consultoria de Arquiteto de engenharia para revisão adicional e para empenhar esforços para remover qualquer problema de PII ou dados.

+++

+++ **Nossa equipe jurídica determinou que os valores que temos coletado em uma variável por anos não estão mais em acordo com nossa política de privacidade atualizada. Podemos usar a API da Privacidade de dados para limpar todos os valores dessa variável?**

O [API de Privacy Service de dados](https://developer.adobe.com/experience-platform-apis/references/privacy-service/) O foi fornecido para ajudar a atender à solicitações de Privacidade de dados, que são sensíveis ao tempo. O uso dessa API para outros propósitos não é suportado pela Adobe e pode afetar a capacidade da Adobe de fornecer solicitações de Privacidade de dados iniciadas por usuários com inversão de alta prioridade para outros clientes da Adobe. Pedimos que você não use a API da Privacidade de dados para outros propósitos, como limpar dados enviados por acidente para grandes grupos de visitantes.

Além disso, esteja ciente de que os usuários que têm uma ocorrência excluída (atualizada ou em anonimato) como o resultado de uma solicitação de exclusão da Privacidade de dados terão as informações de estado redefinidas. A próxima vez que o visitante retornar ao site, ele será um novo visitante. Todas as atribuições de eVar serão iniciadas novamente, assim como informações como números de visita, referenciadores, primeira página visitada etc. Esse efeito colateral não é desejável para situações em que você deseja limpar campos de dados, e realça o motivo pelo qual a API da Privacidade de dados é imprópria para este uso.

Entre em contato com seu Gerente de conta (CSM) para coordenar com nossa equipe de consultores de Arquitetura e engenharia para analisar e fornecer um nível de esforço e remover qualquer problemas de PII ou de dados.

+++

Recursos adicionais da Privacidade de dados:

* [Termos comuns do GDPR](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_commonterms.pdf)
* [Pacote de atendimento](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_carepackage.pdf) da Privacidade de dados da Experience Cloud
* [Publicação do blog](https://theblog.adobe.com/experiential-privacy-an-investment-opportunity-for-the-experience-business/) sobre privacidade experiencial
