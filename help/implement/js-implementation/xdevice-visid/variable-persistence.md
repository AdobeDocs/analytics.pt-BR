---
description: Quando os perfis do visitante forem combinados depois de serem associados com a mesma variável de ID do visitante, a atribuição não será alterada no conjunto de dados histórico.
keywords: Implementação do Analytics
seo-description: Quando os perfis do visitante forem combinados depois de serem associados com a mesma variável de ID do visitante, a atribuição não será alterada no conjunto de dados histórico.
seo-title: Atribuição e persistência
solution: Analytics
title: Atribuição e persistência
topic: Desenvolvedor e implementação
uuid: 5dd706be-83f6-498a-a856-e3c5af995348
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# Atribuição e persistência

>[!IMPORTANT]
>
>Esse método de identificação de visitantes entre dispositivos não é mais recomendado. Consulte a Documentação [do Device Co-op da](https://marketing.adobe.com/resources/help/en_US/mcdc/)Adobe Experience Cloud.

Quando os perfis do visitante forem combinados depois de serem associados com a mesma variável de ID do visitante, a atribuição não será alterada no conjunto de dados histórico.

* Quando a variável `s.visitorID` for definida e enviada para uma ocorrência, o sistema verificará se outros perfis de visitantes possuem uma ID do visitante similar. 
* Se existir, o perfil do visitante que já está no sistema é usado a partir desse ponto, e o perfil do visitante anterior não é mais usado.
* Se nenhuma ID do visitante similar for encontrada, um novo perfil será criado.

Quando um visitante não-autenticado acessar seu site pela primeira vez, o Adobe Analytics atribuirá e a ele um perfil de visitante. Conforme exibido em [Visitante exclusivo e Contagem de visitas](/help/implement/js-implementation/xdevice-visid/xdevice-connecting.md#section_70330AB6724C4E419A4BD0BDD54641AC), um novo perfil é criado durante a autenticação. Quando o novo perfil é criado, uma visita é encerrada e uma nova é iniciada.

**Durante a primeira conexão de dados**

O exemplo abaixo mostra como os dados são enviados para o Adobe Analytics quando um cliente é autenticado pela primeira vez, em um dispositivo inédito:

* `eVar16` expira em 1 dia e `evar17` expira ao final da visita.

* A coluna `post_visitor_id` representa o perfil gerenciado pelo Adobe Analytics.
* As colunas `post_evar16` e `post_evar17` exibem a persistência de eVars.

* `cust_visid` representa um valor definido em `s.visitorID`.

* Cada fileira corresponde a uma "ocorrência", uma solicitação enviada para os servidores do Adobe Analytics responsáveis pela coleta de dados.

![](assets/xdevice_first.jpg)

Na primeira conexão de dados com um valor `s.visitorID` inédito (o `u999` acima), o novo perfil foi criado. Valores persistentes do antigo perfil são transferidos para o novo perfil.

* eVars definidas para expirar ao final da visita não são copiadas para o perfil autenticado. Observe que o valor `car` acima não é persistente.
* eVars definidas para expirar por outras medidas serão copiadas para o perfil autenticado. Observe que o valor `apple` é persistente.
* Para as eVars persistentes, nenhuma métrica Instance é gravada. Isso significa que, ao usar a identificação de visitantes de dispositivo cruzado, é possível visualizar relatórios nos quais a métrica Unique Visits é maior para um valor eVar do que a métrica Instance.

**Sobre conexões subsequentes de dados**

O exemplo abaixo mostra os dados são enviados para o Adobe Analytics quando o usuário realiza a autenticação em um novo dispositivo logo após ter feito o mesmo em outro dispositivo:

![](assets/xdevice-subsequent.jpg)

Quando o cliente autentica a sua ID e ela corresponde ao perfil já "autenticado" - `2947539300`. O perfil usado no início da visita (`5477766334477`) não é mais usado e nenhum dado seu é persistente.

* Os dados de segmentação geográfica são registrados com base na primeira ocorrência da visita e não são alterados para uma visita única, independentemente do dispositivo usado. Isso significa que os dados de segmentação geográfica não costumam ser incluídos na conexão subsequente de dados em um novo dispositivo.
* Colunas de tecnologia como navegador, sistema operacional e intensidade de cor são gravadas na primeira ocorrência de uma visita. Assim como os valores de segmentação geográfica, eles não serão copiados para o perfil costurado.
* Um Canal de marketing como Direto ou Interno, que geralmente é configurado de modo a não sobrescrever outro canal, fará exatamente isso em uma conexão subsequente de dados que possui uma autenticação para o dispositivo (tal como a autenticação exibida em [Visitante exclusivo e Contagem de visitas](/help/implement/js-implementation/xdevice-visid/xdevice-connecting.md#section_70330AB6724C4E419A4BD0BDD54641AC)).

**Casos especiais**

Em outros casos, os dados não são persistentes do perfil não-autenticado para o perfil autenticado.

* Se um usuário é novo em seu site (primeira visita em um dispositivo diferente), ele será autenticado aproximadamente 3 minutos após a sua chegada - e nenhum valor será persistente ao perfil autenticado.

