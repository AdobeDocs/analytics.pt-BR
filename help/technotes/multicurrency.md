---
description: Descreve como definir códigos monetários de destino para que o suporte multimoeda funcione.
title: Suporte multimoeda
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 63a6ca92ae5fe103648c74bd16bcdf90858c71f3

---


# Suporte multimoeda

Este documento descreve como definir códigos de moeda de destino para suporte a várias moedas.

Os códigos monetários de destino são definidos em três níveis:

## Nível da página

É possível definir uma variável JavaScript para a moeda de destino no nível da página. O proprietário do site define essa variável com o código monetário ISO 4217 de três letras (conforme listado abaixo neste documento). Se a variável [currencyCode](https://docs.adobe.com/content/help/en/analytics/implementation/vars/config-vars/currencycode.html) não estiver definida nesse nível, a moeda padrão será a mesma especificada no conjunto de relatórios. Se a variável no nível da página estiver em conflito com a variável especificada no conjunto de relatórios, a variável no conjunto de relatórios terá prioridade.


## Nível do conjunto de relatórios

A moeda **** base é especificada ao [criar conjuntos](https://docs.adobe.com/content/help/en/analytics/admin/manage-report-suites/new-report-suite/new-report-suite.html)de relatórios. Essa é a configuração padrão para moeda e tem prioridade sobre os códigos monetários definidos no nível da página. Assim, se um conjunto de relatórios tiver pedidos que aceitam Dólares Americanos, Euro e Libras Esterlinas e o conjunto de relatórios tiver um código monetário padrão definido como &quot;Dólares Americanos&quot;, o banco de dados back-end do relatório converterá todas as transações em Dólares Americanos.

Os relatórios de marketing usam a taxa de câmbio no momento em que a solicitação de imagem ocorre para traduzir os valores monetários no nível da página para os valores monetários padrão do conjunto de relatórios. Os conjuntos de relatórios usam &quot;Dólares Americanos&quot; como moeda padrão.


## Nível do relatório

Os usuários podem definir a moeda padrão reportada para a sessão de logon do usuário. Essa informação pode ser acessada por meio do link **Opções de exibição** em qualquer Relatório de Conversão. Os relatórios de marketing usam a taxa de câmbio no momento em que o relatório é executado para converter valores monetários do conjunto de relatórios em valores monetários especificados pelo relatório.

## Códigos monetários suportados (ISO 4217)

O Analytics suporta atualmente os seguintes formatos de moeda para transações de conversão:


&quot;AFA&quot; Afegãos do Afeganistão (AFA)

&quot;AFN&quot; Afegãos do Afeganistão (AFN)

&#39;ALL&#39; Albânia Leke (ALL)

Dinar Argélia &#39;DZD&#39; (DZD)

&quot;AOA&quot; Angola Kwanza (AOA)

Pesos argentinos &#39;ARS&#39; (ARS)

&#39;AMD&#39; Armenia Drams (AMD)

Guildas de Aruba (AWG)

Dólares australianos &#39;AUD&#39; (AUD)

&quot;AZM&quot; Azerbaijão Manats (AZM)

&quot;AZN&quot; Azerbaijão - Novos Manats (AZN)

Dólares das Bahamas (BSD)

Dinar &#39;BHD&#39; do Bahrein (BHD)

&#39;BDT&#39; Bangladesh Taka (BDT)

Dólares de Barbados (BBD)

Rublos &#39;BYR&#39; Belarus (BYR)

Dólares de Belize &#39;BZD&#39;

Dólares das Bermudas &quot;BMD&quot; (BMD)

BTN - Ngultrum do Butão (BTN)

&#39;BOB&#39; Bolivia Bolivianos (BOB)

Marco Conversível da Bósnia e Herzegovina (BAM)

&#39;BWP&#39; Pulas do Botswana (BWP)

Brasil Reais &#39;BRL&#39;

Dólares de Brunei &#39;BND&#39; (BND)

&quot;BGN&quot; Bulgária Leva (BGN)

Franco &#39;BIF&#39; Burundi (BIF)

&#39;KHR&#39; Camboja Riels (KHR)

Dólares canadenses &#39;CAD&#39; (CAD)

Escudos de Cabo Verde (CVE)

Dólares das Ilhas Caimão &quot;KYD&quot; (KYD)

&#39;CLP&#39; Chile Pesos (CLP)

&#39;CNY&#39; China Yuan Renminbi (CNY)

Pesos colombianos (COP)

&#39;XOF&#39; Communauté Financière Africaine Francs BCEAO (XOF)

&#39;XAF&#39; Communauté Financière Africaine Francs BEAC (XAF)

&#39;KMF&#39; Comoros Francs (KMF)

Comptoirs Français du Pacifique Francs (XPF)

&#39;CDF&#39; Congo/Franco de Kinshasa (CDF)

&#39;CRC&#39; Colones da Costa Rica (CRC)

&quot;HRK&quot; Croácia Kuna (HRK)

Pesos Conversíveis &quot;CUC&quot; Cuba (CUC)

&#39;CUP&#39; Pesos cubanos (CUP)

Libras cipriotas &#39;CYP&#39;

&quot;CZK&quot; Coroa da República Checa (CZK)

&quot;DKK&quot; Coroa dinamarquesa (DKK)

&#39;DJF&#39; Djibouti Francs (DJF)

&quot;DOP&quot; Pesos da República Dominicana (DOP)

&#39;XCD&#39; Dólares do Caribe Oriental (XCD)

Libras Egípcias &#39;EGP&#39;

&#39;SVC&#39; Colones de El Salvador (SVC)

&#39;ERN&#39; Eritrea Nakfa (ERN)

ERR &#39;XBT&#39; (XBT)

&quot;EEK&quot; Estônia - Krooni (EEK)

&#39;ETB&#39; Etiópia Birr (ETB)

&quot;EUR&quot; Euro (EUR)

Libras das Ilhas Falkland &#39;FKP&#39; (FKP)

Dólares Fiji &#39;FJD&#39; (FJD)

&quot;GMD&quot; - Dalasi da Gâmbia (GMD)

&quot;GEL&quot; Georgia Lari (GEL)

&quot;GHC&quot; Ghana Cedis (GHC)

&quot;GHS&quot; Ghana Cedis (GHS)

&#39;GIP&#39; - Libras de Gibraltar (GIP)

Onças de ouro &#39;XAU&#39; (XAU)

&#39;GTQ&#39; Guatemala Quetzales (GTQ)

Libras Guernsey &#39;GGP&#39; (GGP)

Francos da Guiné &#39;GNF&#39; (GNF)

Dólares da Guiana &#39;GYD&#39; (GYD)

&#39;HTG&#39; Haiti Gourdes (HTG)

&quot;HNL&quot; Honduras Lempiras (HNL)

&#39;HKD&#39; Dólares de Hong Kong (HKD)

&quot;HUF&quot; Hungria Forint (HUF)

&quot;ISK&quot; Coroa islandesa (ISK)

Rúpias indianas &#39;INR&#39;

&#39;IDR.&#39; Rúpias Indonésia (IDR)

Direitos de Saque Especiais do Fundo Monetário Internacional (XDR)

Rials do Irã (IRR)

Dinar &#39;IQD&#39; Iraque (IQD)

&#39;IMP&#39; Isle of Man Pounds (IMP)

Novos Shekels &quot;ILS&quot; Israel (ILS)

Dólares jamaicanos &#39;JMD&#39;

&#39;JPY&#39; Iene japonês (JPY)

&#39;JEP&#39; Jersey Pounds (JEP)

JOD&#39;Jordan Dinars (JOD)

&quot;KZT&quot; Cazaquistão Tenge (KZT)

Xelins do Quénia &quot;KES&quot; (KES)

Dinar &#39;KWD&#39; Kuwait (KWD)

Soms do Quirguistão &#39;KGS&#39; (KGS)

LAK (LAK) Laos Kips (LAK)

&quot;LVL&quot; Lati (LVL)

Libras Libanesas &quot;LBP&quot; (LBP)

&#39;LSL&#39; Lesotho Maloti (LSL)

Dólares Libéria LRD (LRD)

Dinar líbio &#39;LYD&#39; (LYD)

LTL Lituânia Litai (LTL)

Patacas de Macau &#39;MOP&#39; (MOP)

Denars da Macedônia &#39;MKD&#39; (MKD)

Ariary de Madagáscar (MGA)

&#39;MWK&#39; Malawi Kwachas (MWK)

Ringgits da Malásia &#39;MYR&#39;

&#39;MVR&#39; Maldives Rufiyaa (MVR)

&quot;MTL&quot; Liri (MTL)

&quot;MRO&quot; Ouguiyas mauritano (OPR)

Rúpias Maurícias &quot;MUR&quot; (MUR)

Pesos mexicanos &#39;MXN&#39; (MXN)

Lei da Moldávia &#39;MDL&#39; (MDL)

Tugriks da Mongólia &#39;MNT&#39;

&#39;MAD&#39; Morocco Dirhams (MAD)

&#39;MZN&#39; Moçambique Meticais (MZN)

&#39;MZM&#39; Moçambique Meticais (MZM)

&#39;MMK&#39; Myanmar Kyats (MMK)

Dólares da Namíbia &#39;NAD&#39;

Rúpias Nepal &#39;NPR&#39;

&quot;ANG&quot; Florins das Antilhas Holandesas (ANG)

Dólares &quot;NZD&quot; da Nova Zelândia (NZD)

&#39;NIO&#39; Nicarágua Cordobas (NIO)

Nairas da Nigéria (NGN)

Won &quot;KPW&quot; da Coreia do Norte (KPW)

&quot;NOK&quot; Noruega - Coroa (NOK)

&#39;OMR.&#39; Oman Rials (OMR)

Rúpias PKR do Paquistão

Onças de Paládio &#39;XPD&#39; (XPD)

&#39;PAB&#39; Panama Balboas (PAB)

PGK Papua Nova Guiné Kina (PGK)

&#39;PYG&#39; Guarani Paraguai (PYG)

&quot;PEN&quot; Peru Nuevos Soles (PEN)

&#39;PHP&#39; Filipinas Pesos (PHP)

Onças Platinum &#39;XPT&#39; (XPT)

Zlotych polonês &quot;PLN&quot; (PLN)

Riyal do QAR (QAR)

&quot;ROL&quot; Romênia Lei (ROL)

&quot;RON&quot; Nova Lei da Romênia (RON)

Rublos Rússia &#39;RUB&#39; (RUB)

Rublos &#39;RUR&#39; Rússia (RUR)

Franco Ruanda &#39;RWF&#39; (RWF)

&#39;SHP&#39; - Libras de Saint Helena (SHP)

Tala Samoa &#39;WST&#39; (WST)

Dobras de São Tomé e Príncipe (STD)

Rials da Arábia Saudita &#39;SAR&#39; (SAR)

&quot;SPL&quot; Seborga Luigini (SPL)

Dinares &#39;RSD&#39; da Sérvia (RSD)

&quot;CSD&quot; Sérvia Dinar (CSD)

RCS — Rúpias Seicheles (SCR)

&quot;SLL&quot; Serra Leoa Leones (SLL)

Onças de prata &#39;XAG&#39; (XAG)

Dólares de Singapura &quot;SGD&quot; (SGD)

&quot;SKK&quot; Eslováquia Koruny (SKK)

&#39;SIT&#39; Tolares eslovenos (SIT)

Dólares das Ilhas Salomão (SBD)

&quot;SOS&quot; Xelins da Somália (SOS)

ZAR (South Africa Rand)

Won da Coreia do Sul (KRW)

&quot;LKR&quot; Rúpias do Sri Lanka (LKR)

Dinares Sudan &#39;SDD&#39; (SDD)

Libras Sudanesas &#39;SDG&#39; (SDG)

Dólares do Suriname (SRD)

&quot;SRG&quot; Suriname Guilders (SRG)

&quot;SZL&quot; Suazilândia Emalangeni (SZL)

&quot;SEK&quot; Coroa sueca (SEK)

Francos suíços &quot;CHF&quot; (CHF)

&#39;SYP&#39; - Libras sírias (SYP)

&quot;TWD&quot; Novo Dólar de Taiwan (TWD)

&quot;TJS&quot; Tajiquistão Somoni (TJS)

Xelins da Tanzânia &#39;TZS&#39;

&#39;THB&#39; Tailândia Baht (THB)

&#39;TOP&#39; Tonga Pa&#39;anga (TOP)

Dólares de Trinidade e Tobago (TTD)

Dinar Tunísia &#39;TND&#39; (TND)

&#39;TRY&#39; Lira turca (TRY)

&quot;TRL&quot; Liras turcas (TRL)

&#39;TMM&#39; Manats do Turquemenistão (TMM)

&#39;TMT&#39; Novos Manats do Turcomenistão (TMT)

Dólares Tuvalu &#39;TVD&#39; (TVD)

Xelins &quot;UGX&quot; de Uganda (UGX)

&quot;UAH&quot; Ucrânia Hryvnia (UAH)

Dirrãs dos Emirados Árabes Unidos (AED)

&#39;GBP&#39; Libras do Reino Unido (GBP)

&#39;USD&#39; selecionado Dólares dos Estados Unidos (USD)

&#39;UYU&#39; Pesos uruguaios (UYU)

Sums &quot;UZS&quot; Usbequistão (UZS)

&#39;VUV&#39; Vanuatu Vatu (VUV)

&quot;VEB&quot; Bolivares Venezuela (VEB)

&quot;VEF&quot; Venezuela Bolivares Fuertes (VEF)

&#39;VND&#39; Vietnam Dong (VND)

Rials do Iêmen &#39;YER&#39; (YER)

ZMK Zâmbia Kwacha (ZMK)

&quot;ZMW&quot; Zambia Kwacha (ZMW)

Dólares do Zimbábue &#39;ZWD&#39; (ZWD)


## Exemplo de AppMeasurement.js

A `currencyCode` variável pode ser definida globalmente no arquivo AppMeasurement.js. A definição da variável currencyCode neste arquivo garante que todas as transações monetárias usem um código monetário uniforme. O exemplo abaixo especifica Euros como a `currencyCode` variável no arquivo AppMeasurement.js `CONFIG SECTION` . Todos os eventos de compra serão interpretados mediante o reporte de informação como transações em &quot;euros&quot;.

```
/************************** CONFIG SECTION **************************/ 
/* You may add or alter any code config here. */ 
s.account="devnow"
s.currencyCode="EUR"
s.trackInlineStats=true 
s.linkLeaveQueryString=false 
s.linkTrackVars="None" 
s.linkTrackEvents="None" 
***
    
```

Para obter mais informações sobre como editar o arquivo AppMeasurement.js, consulte [Inserir código no arquivo](https://docs.adobe.com/content/help/en/analytics/implementation/implement-analytics-with-dtm/analytics-tool/t-appmeasurement-code.html)AppMeasurement.js.

## Outras notas de implementação

* Lembre-se de que, embora os códigos monetários possam mudar entre as páginas, todos os itens de linha de conversão definidos em uma determinada solicitação de página devem usar a mesma moeda (por exemplo, você não pode ter Euro, Libras Esterlinas e Dólares Americanos definidos na mesma exibição de página). Se você não quiser fazer nenhuma conversão monetária, deixe o valor currencyCode em branco. Isso faz com que os valores enviados sejam transmitidos diretamente para relatórios sem conversão.

* Definir um currencyCode inválido (qualquer valor que não esteja na lista de códigos de moeda suportados) faz com que toda a ocorrência seja excluída e os dados não sejam coletados para essa transação. Antes de configurar `currencyCode` em produção, use um conjunto de relatórios de teste para verificar se os dados foram coletados e se a conversão monetária está correta.

* Moedas que não usam ponto (.) como separador devem ser modificadas para usar ponto em vez do separador comum.  Por exemplo, a Coroa sueca, que utiliza vírgula (,), deve ser modificada para usar ponto em vez de vírgula. O Analytics usa a vírgula para separar valores, e os dados não serão transmitidos corretamente. O período passará corretamente o valor para os relatórios.
