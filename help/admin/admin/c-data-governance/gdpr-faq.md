---
description: Perguntas frequentes sobre governança de dados do Adobe Analytics
title: Perguntas frequentes sobre governança de dados
feature: Data Governance
role: Admin
exl-id: 57399c1b-cf08-405b-8c1b-9d23e4c38716
source-git-commit: 43c39b99cbae3e714b7f017dec14dd02fa350790
workflow-type: ht
source-wordcount: '2042'
ht-degree: 100%

---

# Perguntas frequentes

+++ **Como o Adobe Analytics lida com solicitações de acesso e exclusão de usuários finais (titulares de dados) validadas pelos clientes (controladores de dados)?**

Quando várias regras de privacidade de dados (GDPR, CCPA) entram em vigor, o Adobe Analytics permite o processamento de solicitações verificadas enviadas pelos controladores de dados à API da privacidade de dados da Experience Cloud, para permitir um processo mais automatizado. A API da privacidade de dados da Adobe foi desenvolvida para ajudar a processar as solicitações de direitos individuais (por exemplo, solicitações de acesso e exclusão) dos dados de clientes armazenados nas soluções da Adobe Experience Cloud. Ela é flexível e escalável de acordo com o número de solicitações de acesso e exclusão de dados que sua empresa recebe dos titulares de dados.

Além disso, a API do Privacy Service permite que o cliente verifique o status de atendimento das solicitações de acesso e exclusão de dados. Para obter mais detalhes, consulte a documentação da [API do Privacy Service](https://developer.adobe.com/experience-platform-apis/references/privacy-service/).

+++

+++ **Quem é responsável por receber, aceitar e atender às solicitações de privacidade de dados de usuários finais?**

O controlador de dados tem a responsabilidade exclusiva de receber e aceitar solicitações. O controlador de dados valida a identidade do titular de dados e, em seguida, atende à solicitação. Parte dessa responsabilidade pode envolver informar a Adobe sobre as IDs de titulares de dados que podem estar associadas aos dados armazenados no Adobe Analytics.

Como processadora de dados, a Adobe deve fornecer uma assistência razoável ao controlador para processar as solicitações verificadas dentro de um período de tempo aceitável.

+++

+++ **Como os clientes da Adobe (controladores de dados) saberão quais solicitações de privacidade de dados mapear para quais IDs do Adobe Analytics para o processamento da privacidade de dados?**

Os controladores de dados determinam como resolver a identidade de solicitações dos titulares de dados. Considere a implantação da tag de recuperação de ID da privacidade de dados da Adobe. Suas equipes de desenvolvimento economizam tempo usando nossa tag de recuperação de ID da privacidade de dados para capturar IDs de usuário (IDs de cookies). Em seguida, elas podem usar nossa API de privacidade de dados para enviar essas IDs de usuários às soluções relevantes da Adobe Experience Cloud para o processamento de solicitações de privacidade de dados. A API da privacidade de dados pode oferecer suporte a uma grande variedade de IDs de clientes em várias soluções da Adobe.

Se um titular de dados enviar uma solicitação junto com um identificador (variável personalizada: prop ou eVar), o Adobe Analytics verificará todo o histórico retido dos dados coletados para o identificador especificado. Para obter mais detalhes sobre como configurar as IDs personalizadas armazenadas em props ou eVars do Analytics, consulte [a documentação do Analytics sobre namespaces](/help/admin/admin/c-data-governance/data-labeling/gdpr-namespaces.md).

+++

+++ **Como a governança de dados do Adobe Analytics pode ajudar no processamento de solicitações de privacidade de dados?**

A governança de dados é uma nova ferramenta do Adobe Analytics que fornece aos controladores de dados a capacidade de aplicar controles e classificações nos seus dados do Analytics. Essa nova ferramenta permite que os clientes da Adobe personalizem o processamento de suas solicitações de acesso e exclusão de dados da Privacidade de dados. No console de Governança de dados, os administradores podem definir as configurações desejadas que devem ser aplicadas a várias colunas de dados que existentes no Adobe Analytics. Assim que esses rótulos forem definidos, a Adobe honrará e processará qualquer solicitação de acesso e exclusão de downstream de acordo com as configurações de rótulo desejadas pelos clientes. É responsabilidade do controlador de dados consultar seus representantes legais a fim de revisar essas configurações de rótulo.

A ferramenta de governança de dados contém os seguintes rótulos de dados:

* **Rótulos de dados de identidade**: usados para classificar os dados que podem identificar um indivíduo, seja diretamente ou em combinação com outros dados. (Nenhum, I1, I2)

* **Rótulos de dados confidenciais**: usados para classificar dados que podem ser definidos como confidenciais pela legislação aplicável. (Nenhum, S1, S2) Observe que, atualmente, o uso de dados confidenciais no Adobe Analytics é geralmente proibido, exceto para dados de localização geográfica precisos, obtidos adequadamente de acordo com a legislação aplicável, que podem ser considerados dados confidenciais em algumas jurisdições.

* **Rótulos de dados da privacidade de dados**: usados para definir os campos que podem conter identificadores pessoais para uso em solicitações de privacidade de dados ou que devem ser removidos como parte de uma solicitação de exclusão da privacidade de dados. Em alguns casos, esses rótulos podem se sobrepor aos rótulos de identidade e dados confidenciais.

Para obter mais informações sobre rótulos de governança de dados, consulte [Rótulos de privacidade de dados para variáveis do Analytics](/help/admin/admin/c-data-governance/data-labeling/gdpr-labels.md).

+++

+++ **Como posso validar se as solicitações do Privacy Service estão funcionando corretamente para excluir dados do Adobe Analytics?**

Normalmente, os clientes do Analytics configuram alguns conjuntos de relatórios de teste para verificar a funcionalidade antes que ela seja disponibilizada para o público em geral. Sites ou aplicativos em pré-produção enviam dados a esses conjuntos de relatórios de teste/desenvolvimento/controle de qualidade para avaliar o funcionamento do código quando este for lançado, antes que o tráfego real seja enviado para os conjuntos de relatórios de produção.

No entanto, com uma configuração normal, o processamento de solicitação do GDPR não pode ser testado primeiro nesses conjuntos de relatórios de teste, antes de aplicar solicitações a conjuntos de relatórios de produção. O motivo disso é que uma solicitação de privacidade de dados é aplicada automaticamente a todos os conjuntos de relatórios na organização da Experience Cloud, o que geralmente engloba todos os conjuntos de relatórios da sua empresa.

Ainda assim, há algumas maneiras de testar o processamento da privacidade de dados antes de aplicá-la a todos os seus conjuntos de relatórios:

* Uma opção é configurar uma Organização da Experience Cloud separada que contenha somente conjuntos de relatórios de teste. Use essa organização da Experience Cloud para realizar testes de Privacidade de dados e sua organização normal da Experience Cloud para processamentos de Privacidade de dados.

* Outra opção é atribuir namespaces diferentes a IDs nos conjuntos de relatórios de teste, os quais devem se diferenciar daqueles em seus conjuntos de relatórios de produção. Por exemplo, você pode adicionar prefixos “qa-” a cada namespace nos conjuntos de relatórios de teste. Ao enviar solicitações de Privacidade de dados com apenas namespaces com o prefixo &quot;qa&quot;, essas solicitações só são executadas em relação aos conjuntos de relatórios de teste. Posteriormente, quando você enviava solicitações sem o prefixo &quot;qa&quot;, elas eram aplicadas aos conjuntos de relatórios de produção. **Essa é a abordagem recomendada, a menos que você use os namespaces de visitorId, AAID, ECID ou customVisitorId. Esses namespaces são codificados e não é possível especificar nomes alternativos para eles em seus conjuntos de relatórios de teste.**

+++

+++ **Como começar a preparação para a privacidade de dados com o Adobe Analytics?**

Para obter uma apresentação passo a passo de preparação das regras da privacidade de dados, consulte [Fluxo de trabalho da privacidade de dados do Adobe Analytics](/help/admin/admin/c-data-governance/an-gdpr-workflow.md).

+++

+++ **Como os controladores de dados devem lidar com o consentimento relacionado ao engajamento do usuário?**

O GDPR e a CCPA são boas oportunidades para reconsiderar suas estratégias e práticas de gerenciamento de consentimento. Isso inclui determinar quando o consentimento é necessário e pensar na proposta de valor para o usuário. Considere a proposta de valor para a privacidade do cliente, que pode ajudar a impulsionar a conversão e a fidelidade. O espaço de gerenciamento de consentimento (por exemplo, ferramentas, padrões, práticas recomendadas) está evoluindo rapidamente e é uma área a ser observada. Para minimizar o impacto no engajamento do usuário, os controladores devem trabalhar com os fornecedores neste espaço, bem como com seus consultores jurídicos, para garantir que estejam seguindo as leis e orientações emergentes sobre consentimento e cookies. Uma boa estratégia é considerar a “privacidade experiencial” usando uma experiência sobre a marca que seja contextualmente relevante e que defina a proposta de valor de suas atividades de coleta de dados.

Como controlador de dados, você é responsável por obter o consentimento explícito de seus titulares de dados antes de coletar dados sobre eles (possivelmente incluindo dados do Adobe Analytics) e por implementar um [mecanismo de recusa](https://www.adobe.com/br/privacy/opt-out.html#customeruse) no seu site. Isso permite que seus titulares de dados possam recusar as coletas de dados futuras da Adobe Experience Cloud.

+++

+++ **Como os controladores de dados devem lidar com a retenção de dados relacionada à privacidade de dados?**

Os dados pessoais geralmente não devem ser retidos por mais tempo do que o necessário para atingir o propósito para o qual foram coletados. Os termos gerais da Adobe aplicam um plano de retenção de dados padrão de 25 meses, a menos que um termo de retenção de dados diferente seja acordado por contrato. Os clientes precisam definir sua política de retenção de dados antes que a Adobe possa processar uma solicitação de privacidade de dados.

A politica de retenção de dados atual de cada conjunto de relatórios é exibida na nova interface do administrador da governança de dados. Os clientes devem entrar em contato com o representante da Adobe caso precisem ajustar as políticas de retenção de dados. Consulte as [Perguntas frequentes sobre a retenção de dados do Adobe Analytics](https://experienceleague.adobe.com/pt-br/docs/analytics/technotes/data-retention).

+++

+++ **Um cliente pode reduzir ou estender um período de retenção de dados padrão?**

Os clientes podem solicitar que seus dados sejam excluídos antes de 25 meses, entrando em contato com o Atendimento ao cliente. Os clientes também podem estender a retenção de dados além de 25 meses, comprando uma extensão. As extensões estão disponíveis em incrementos de 1 (um) ano adicional até um máximo de 8 anos adicionais (10 anos no total). Essas extensões podem exigir termos de contrato atualizados e taxas adicionais.

+++

+++ **Quais critérios de privacidade devem ser considerados por um controlador de dados ao exportar dados pessoais do Adobe Analytics?**

Se um cliente usar os feeds de dados para exportar os dados do Adobe Analytics para o Data Warehouse de sua empresa ou para outros sistemas fora da Adobe, é responsabilidade do cliente (o controlador de dados) garantir que as solicitações de exclusão sejam aplicadas aos dados. Isso também se aplica às implementações locais do Adobe Data Workbench, nas quais um feed de dados em execução do Adobe Analytics preenche os dados do Data Workbench. A Adobe pode fornecer ferramentas para ajudar a encontrar e excluir os registros de determinados tipos de feeds de dados, incluindo aqueles usados para o Data Workbench, mas ainda é responsabilidade do cliente (controlador de dados) garantir que os dados sejam excluídos de forma consistente com suas próprias políticas internas de exclusão e retenção de dados.

Considere também casos em que os funcionários baixaram relatórios do Adobe Analytics que continham dados pessoais. Esses relatórios podem precisar ser atualizados ou excluídos se uma solicitação de exclusão relacionada à privacidade de dados for recebida envolvendo uma ID que está presente no relatório. Os clientes devem trabalhar com o departamento jurídico de suas empresas para determinar os períodos de retenção e os requisitos de privacidade e segurança que devem ser aplicados a esses tipos de documentos.

+++

+++ **Alguns dados que não deveríamos coletar foram enviados para o Adobe Analytics por acidente. Podemos usar a API da privacidade de dados para eliminar esses dados?**

A [API de dados do Privacy Service](https://developer.adobe.com/experience-platform-apis/references/privacy-service/) foi fornecida para ajudar a atender à solicitações de privacidade de dados, que são sensíveis ao tempo. A Adobe não oferece suporte à utilização dessa API para outros propósitos, visto que isso poderia afetar a pontualidade da Adobe no que diz respeito ao atendimento de solicitações de privacidade de dados de alta prioridade iniciadas por usuários, provenientes de outros clientes da Adobe.

Pedimos que você não use a API da privacidade de dados para outros propósitos, como eliminar dados enviados por acidente para grandes grupos de visitantes. Além disso, esteja ciente de que os usuários que têm uma ocorrência excluída (atualizada ou em anonimato) como o resultado de uma solicitação de exclusão da Privacidade de dados terão as informações de estado redefinidas. A próxima vez que o visitante retornar ao site, ele será um novo visitante. Todas as atribuições de eVar serão iniciadas novamente, assim como informações como números de visita, referenciadores, primeira página visitada etc. Esse efeito colateral não é desejável para situações em que você deseja limpar campos de dados, e realça o motivo pelo qual a API da Privacidade de dados é imprópria para este uso.

Entre em contato com a equipe de contas da Adobe para coordenar com a nossa equipe de consultores de arquitetura e engenharia uma análise mais aprofundada e fornecer um nível de iniciativa para remover qualquer problemas de PII ou de dados.

+++

+++ **Nossa equipe jurídica determinou que os valores que temos coletado em uma variável durante anos não estão mais de acordo com nossa política de privacidade atualizada. Podemos usar a API da privacidade de dados para eliminar todos os valores dessa variável?**

A [API de dados do Privacy Service](https://developer.adobe.com/experience-platform-apis/references/privacy-service/) foi fornecida para ajudar a atender solicitações de privacidade de dados, que são sensíveis ao tempo. A Adobe não oferece suporte à utilização dessa API para outros propósitos, visto que isso poderia afetar a pontualidade da Adobe no que diz respeito ao atendimento de solicitações de privacidade de dados de alta prioridade iniciadas por usuários, provenientes de outros clientes da Adobe. Pedimos que você não use a API da privacidade de dados para outros propósitos, como eliminar dados enviados por acidente para grandes grupos de visitantes.

Além disso, esteja ciente de que os usuários que têm uma ocorrência excluída (atualizada ou em anonimato) como o resultado de uma solicitação de exclusão da Privacidade de dados terão as informações de estado redefinidas. A próxima vez que o visitante retornar ao site, ele será um novo visitante. Todas as atribuições de eVar serão iniciadas novamente, assim como informações como números de visita, referenciadores, primeira página visitada etc. Esse efeito colateral não é desejável para situações em que você deseja limpar campos de dados, e realça o motivo pelo qual a API da Privacidade de dados é imprópria para este uso.

Entre em contato com a equipe de contas da Adobe para coordenar com a nossa equipe de consultores de arquitetura e engenharia uma análise mais aprofundada e fornecer um nível de iniciativa para remover qualquer problemas de PII ou de dados.

+++

Recursos adicionais da Privacidade de dados:

* [Termos comuns do GDPR](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_commonterms.pdf)
* [Pacote de atendimento](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_carepackage.pdf) da Privacidade de dados da Experience Cloud
* [Publicação do blog](https://theblog.adobe.com/experiential-privacy-an-investment-opportunity-for-the-experience-business/) sobre privacidade experiencial
