---
title: Exibir as notas de versão atuais do Adobe Analytics
description: Notas de versão mais recentes do Analytics
source-git-commit: e19299820a03783215d8425b937a0935311d9e7b
workflow-type: tm+mt
source-wordcount: '868'
ht-degree: 98%

---


# Notas de versão mais recentes da Adobe Analytics

**Janeiro de 2022**

Saiba mais sobre as atualizações de versão mais recentes para [produtos Adobe Experience Cloud](https://business.adobe.com/br/products/adobe-experience-cloud-products.html). Obtenha a documentação de autoajuda, os tutoriais e os cursos mais recentes da Experience League.

## Novos recursos no Adobe Analytics {#aa-features}

| Recurso | Descrição | Data Alvo |
| ----------- | ---------- | ------- |
| N/D |  | Consulte [Disponibilidade geral](https://experienceleague.adobe.com/docs/analytics/technotes/releases.html?lang=pt-BR) |

{style=&quot;table-layout:auto&quot;}

## Correções no Adobe Analytics e no Customer Journey Analytics {#aa-fixes}

* Correção de um problema no Analysis Workspace em que a ID de público-alvo estava ausente dos itens de dimensão. (AN-262038; AN-279315)
* Correção de um problema que impedia os usuários de carregarem um arquivo salvo no [!DNL Target] projeto no Espaço de trabalho. (AN-277461; AN-275825; AN-266397)
* Correção de um problema em que os recursos não ativados estavam visíveis na interface do usuário. (AN-262006)
* Correção de um problema que ocorria ao alterar a data usando o campo de data no Espaço de trabalho. Isso resultou na [!UICONTROL Hora de Término] alterando de 23h 59min para 12h. (AN-277269; AN-277481)
* Correção de um problema que causava a quebra do segmento na interface do usuário ao adicionar novos segmentos a um segmento já carregado. (AN-260827)
* Correção de um problema em que os usuários não conseguiam acessar projetos compartilhados do Espaço de trabalho. (AN-267529)
* Adição de uma mensagem de erro que mostra quando um intervalo de datas em andamento tem uma data de início posterior à data de término. (AN-270488)
* Correção de vários problemas dos feeds de dados. (AN-275876; AN-270512; AN-277284; AN-277290; AN-274893; AN-274606; AN-269651)
* Correção de um problema com intervalos de datas em gráficos que ignoravam filtros de datas em tabelas. (AN-263999)
* Correção de um problema em que os relatórios agendados eram enviados antecipadamente devido ao Horário de verão. (AN-276410; AN-276305)
* Correção de um problema com o download do projeto para `.csv` falha no arquivo no Espaço de trabalho. (AN-275834)

### Outras correções no Adobe Analytics

AN-253294; AN-254976; AN-255377; AN-255561; AN-258550; AN-259336; AN-263935; AN-265094; AN-269441; AN-269486; AN-269855; AN-271166; AN-271588; AN-272088; AN-272249; AN-272859; AN-272873; AN-272885; AN-273229; AN-273913; AN-274237; AN-274472; AN-274491; AN-274619; AN-274766; AN-275248; AN-275259; AN-275271; AN-275315; AN-275388; AN-275418; AN-275597; AN-275643; AN-275650; AN-275651; AN-275675; AN-275682; AN-275704; AN-275711; AN-275796; AN-275834; AN-275923; AN-275941; AN-276044; AN-276125; AN-276157; AN-276397; AN-276597; AN-276789; AN-276834; AN-276861; AN-276870; AN-276963; AN-276975; AN-277000; AN-277044; AN-277093; AN-277200; AN-277215; AN-277271; AN-277281; AN-277362; AN-277419; AN-277492; AN-277498; AN-277533; AN-277619; AN-277675; AN-277681; AN-277767; AN-277805; AN-277810; AN-277818; AN-277875; AN-277933; AN-277988; AN-278105; AN-278115; AN-278122; AN-278192; AN-278407; AN-278437; AN-278559; AN-278604; AN-278610; AN-278709; AN-278835; AN-278849; AN-278881; AN-279067; AN-279103; AN-279111; AN-279219; AN-279237; AN-279312

## Avisos importantes para administradores do [!DNL Analytics] {#aa-notices}

| Aviso | Data de adição ou atualização | Descrição |
| ----------- | ---------- | ---------- |
| Expiração de lista de permissões de extensão EOL para integrações OAuth/JWT herdadas do Analytics | 14 de janeiro de 2022 | Em **25 de maio de 2022**, a [API do Analytics 1.3, a API SOAP 1.4 e a extensão de lista de permissões do Analytics OAuth/JWT EOL](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md) herdado irá expirar. Ela era fornecida para que os clientes que usavam credenciais herdadas do [!DNL Adobe Analytics] OAuth/JWT tivessem mais tempo para migrar suas integrações de clientes para as [credenciais do Adobe IMS](https://developer.adobe.com/console). Essa expiração afeta (mas não se limita a) [!DNL Adobe Analytics Livestream] e [!DNL Adobe Campaign] clientes que não concluíram as migrações de IMS necessárias. Atualmente, os clientes que estão usando as [!DNL Analytics] credenciais OAuth/JWT herdadas por meio da extensão da lista de permissões e que não concluírem a migração para credenciais do IMS até o dia 25 de maio de 2022, perderão o acesso aos serviços da Adobe. Os clientes do Livestream podem se referir a essas [instruções](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) ao migrar seus aplicativos de clientes para as credenciais IMS. [!DNL Campaign] os clientes podem entrar em contato com a equipe da conta da Adobe para saber como atualizar para a versão mais recente do [!DNL Campaign]. |
| Fim da vida útil do [!DNL Reports & Analytics] | 4 de janeiro de 2022 | A partir de **31 de dezembro de 2023**, a Adobe pretende descontinuar o , juntamente com os relatórios e recursos que o acompanham. [!DNL Reports & Analytics] Os relatórios, as visualizações e as tecnologias subjacentes que alimentam o [!DNL Reports & Analytics] não atendem mais aos padrões de tecnologia da Adobe. A maioria dos recursos do [!DNL Reports & Analytics] estão disponíveis no [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=pt-BR). Desde o lançamento do Analysis Workspace em 2015, a funcionalidade e os recursos do [!DNL Reports & Analytics] foram movidos para o Analysis Workspace e um limite de paridade de fluxo de trabalho foi atingido. [Este aviso explica o processo do fim da vida útil.](https://spark.adobe.com/page/6WnF8JK6IRDhf/) |
| Atualização de serviços do Protocolo de transferência segura de arquivo (SFTP) | 13 de janeiro de 2022 | Em **2 de maio de 2022**, o [!DNL Adobe Analytics] atualizará os seus serviços de Protocolo de transferência segura de arquivo (SFTP) para oferecer maior segurança às transferências de arquivos. Com essa alteração, não haverá mais suporte para algumas configurações de cliente SFTP. Também adicionaremos algumas opções de conexão que estarão disponíveis em **1 de março de 2022**. Isso afetará somente os dados enviados para ou recuperados do Adobe Analytics por meio do SFTP. O protocolo FTP não será afetado. Para evitar interrupções do serviço, verifique se os clientes SFTP (código, ferramentas, serviços) estarão de acordo com as alterações detalhadas [aqui](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=pt-BR). |
| Tipo de RDC _Global + China_ | 22 de novembro de 2021 | _Global + China_ é um novo tipo de Coleta de dados regional (RDC) que simplifica o roteamento de tráfego para clientes globais que usam o [!UICONTROL Pacote complementar para otimização de desempenho na China]. Anteriormente, era preciso determinar se os dados deveriam ser roteados para o endpoint de coleta da China ou para um dos endpoints de coleta globais. Agora é possível escolher esse *tipo* de RDC para permitir que a Adobe determine o endpoint de coleta ideal com base na geolocalização do usuário. |
| Fim da vida útil do processamento completo nas fontes de dados | 18 de outubro de 2021 | Em **31 de janeiro de 2022**, a Adobe encerrará a vida útil do processamento completo, que permite que os usuários assimilem dados de ocorrência offline no Analytics. Esse recurso está disponível por meio da [API de inserção de dados em massa](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md). [Saiba mais](https://experienceleague.adobe.com/docs/analytics/import/data-sources/data-types-and-categories/datasrc-fullproc-eol.html?lang=pt-BR ) |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement {#appm}

Para obter as atualizações mais recentes sobre as versões do AppMeasurement (versão 2.22.4), consulte as [notas de versão do AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=pt-BR).