---
description: Descreve como definir códigos monetários de destino para que o suporte a várias moedas funcione.
title: Suporte a várias moedas
topic: null
uuid: null
translation-type: ht
source-git-commit: 63a6ca92ae5fe103648c74bd16bcdf90858c71f3

---


# Suporte a várias moedas

Este documento descreve como definir códigos de moeda de destino para suporte a várias moedas.

Os códigos monetários de destino são definidos em três níveis:

## Nível da página

É possível definir uma variável JavaScript para a moeda de destino no nível da página. O proprietário do site define essa variável com o código monetário ISO 4217 de três letras (conforme listado abaixo neste documento). Se a variável [currencyCode](https://docs.adobe.com/content/help/pt-BR/analytics/implementation/vars/config-vars/currencycode.html) não estiver definida nesse nível, a moeda padrão será a mesma especificada no conjunto de relatórios. Se a variável no nível da página estiver em conflito com a variável especificada no conjunto de relatórios, a variável no conjunto de relatórios terá prioridade.


## Nível do conjunto de relatórios

A **moeda base** é especificada ao [criar conjuntos de relatórios](https://docs.adobe.com/content/help/pt-BR/analytics/admin/manage-report-suites/new-report-suite/new-report-suite.html). Essa é a configuração padrão para moeda e tem prioridade sobre os códigos monetários definidos no nível da página. Assim, se um conjunto de relatórios tem pedidos que aceitam Dólar americano, Euro e Libra esterlina, e se o conjunto de relatórios tem um código monetário padrão definido como &quot;Dólar americano&quot;, então o banco de dados de relatórios do back-end converte todas as transações para dólares americanos.

Relatórios de marketing usam a taxa de câmbio do momento da solicitação de imagem para converter os valores monetários no nível da página para os valores monetários padrão do conjunto de relatórios. Todos os conjuntos de relatórios usarão &quot;Dólar americano&quot; como moeda padrão.


## Nível do relatório

Os usuários podem definir a moeda padrão registrada para uma sessão de login do usuário. Essa informação pode ser acessada por meio do link **Opções de exibição** em qualquer Relatório de conversão. Relatórios de marketing usam a taxa de câmbio no momento em que o relatório é executado para converter os valores monetários do conjunto de relatórios em valores monetários específicos do relatório.

## Códigos monetários compatíveis (ISO 4217)

O Analytics é compatível atualmente com os seguintes formatos de moeda para transações de conversão:


“AFA” Afegane, Afeganistão (AFA)

“AFN” Afegane, Afeganistão (AFN)

“ALL” Lek, Albânia (ALL)

“DZD” Dinar, Argélia (DZD)

“AOA” Kwanza, Angola (AOA)

“ARS” Peso, Argentina (ARS)

“AMD” Dram, Armênia (AMD)

“AWG” Florim, Aruba (AWG)

“AUD” Dólares australianos (AUD)

“AZM” Manat, Azerbaijão (AZM)

“AZN” Novo Manat, Azerbaijão (AZN)

“BSD” Dólar das Bahamas (BSD)

“BHD” Dinar, Bahrein (BHD)

“BDT” Taka, Bangladesh (BDT)

“BBD” Dólar de Barbados (BBD)

“BYR” Rublo, Bielorrússia (BYR)

“BZD” Dólar de Belize (BZD)

“BMD” Dólar das Bermudas (BMD)

“BTN” Ngultrum, Butão (BTN)

“BOB” Boliviano, Bolívia (BOB)

“BAM” Marco conversível, Bósnia e Herzegovina ( BAM)

“BWP” Pula, Botswana (BWP)

“BRL” Real, Brasil (BRL)

“BND” Dólar de Brunei (BND)

“BGN” Lev, Bulgária (BGN)

“BIF” Franco do Burundi (BIF)

“KHR” Riel, Camboja (KHR)

“CAD” Dólar canadense (CAD)

“CVE” Escudo, Cabo Verde (CVE)

“KYD” Dólar das Ilhas Caimã ( KYD)

“CLP” Peso chileno (CLP)

“CNY” Yuan-renminbi, China ( CNY)

“COP” Peso colombiano (COP)

“XOF” Franco CFA ocidental, BCEAO (XOF)

“XAF” Franco CFA central, BEAC (XAF)

“KMF” Franco comoriano (KMF)

“XPF” Franco CFP, Polinésia Francesa, Nova Caledônia, Wallis e Fortuna ( XPF)

“CDF” Franco congoles (CDF)

“CRC” Colon da Costa Rica (CRC)

“HRK” Kuna, Croácia (HRK)

“CUC” Peso conversível, Cuba (CUC)

“CUP” Peso cubano (CUP)

“CYP” Libras cipriotas “CYP”

“CZK” Coroa, República Tcheca/Chéquia (CZK)

“DKK” Coroa dinamarquesa (DKK)

“DJF” Franco do Djibouti (DJF)

“DOP” Peso da República Dominicana (DOP)

“XCD” Dólar do Caribe Oriental (XCD)

“EGP” Libras egípcias (EGP)

“SVC” Colon de El Salvador (SVC)

“ERN” Nafka, Eritreia (ERN)

“XBT” ERR (XBT)

“EEK” Coroa estoniana (EEK)

“ETB” Birr, Etiópia (ETB)

“EUR” Euro (EUR)

“FKP” Libra das Ilhas Malvinas (FKP)

“FJD” Dólar de Fiji (FJD)

“GMD” - Dalasi, Gâmbia (GMD)

“GEL” Lari, Georgia (GEL)

“GHC” Cedi, Ghana (GHC)

“GHS” Cedi, Ghana (GHS)

“GIP” Libra de Gibraltar (GIP)

“XAU” Onças de ouro (XAU)

“GTQ” Quetzal, Guatemala (GTQ)

“GGP” Libra de Guernsey (GGP)

“GNF” Francos da Guiné (GNF)

“GYD” Dólar da Guiana (GYD)

“HTG” Gourde, Haiti (HTG)

“HNL” Lempira, Honduras (HNL)

“HKD” Dólar de Hong Kong (HKD)

“HUF” Forint, Hungria (HUF)

“ISK” Coroa islandesa (ISK)

“INR” Rúpia indianas (INR)

“IDR” Rúpia indonésia (IDR)

“XDR” Direitos de especiais de saque do Fundo Monetário Internacional (XDR)

“IRR” Rial, Irã (IRR)

“IQD” Dinar iraquiano (IQD)

“IMP” Libra da Ilha de Man (IMP)

“ILS” Shekel, Israel (ILS)

“JMD” Dólares jamaicanos (JMD)

“JPY” Iene, Japão (JPY)

“JEP” Libra de Jersey (JEP)

“JOD” Dinar da Jordânia (JOD)

“KZT” Tenge, Cazaquistão (KZT)

“KES” Xelim, Quênia (KES)

“KWD” Dinar do Kuwait (KWD)

“KGS” Som, Quirguistão (KGS)

“LAK” Kip, Laos (LAK)

“LVL” Latis, Letônia (LVL)

“LBP” Libras libanesas (LBP)

“LSL” Loti, Lesoto (LSL)

“LRD” Dólar da Libéria (LRD)

“LYD” Dinar líbio (LYD)

“LTL” Litai, Lituânia (LTL)

“MOP” Pataca, Macau (MOP)

“MKD” Denar, Macedônia (MKD)

“MGA” Ariary, Madagáscar (MGA)

“MWK” Kwacha, Malawi (MWK)

“MYR” Ringgit, Malásia (MYR)

“MVR” Rufiyaa, Maldivas (MVR)

“MTL” Liri, Malta (MTL)

“MRO” Ouguiya, Mauritânia (MRO)

“MUR” Rúpia mauriciana (MUR)

“MXN” Pesos mexicanos (MXN)

“MDL” Leu da Moldávia (MDL)

“MNT” Tugriks, Mongólia (MNT)

“MAD” Dirham, Marrocos (MAD)

“MZN” Metical, Moçambique (MZN)

“MZM” Metical, Moçambique (MZM)

“MMK” Kyat, Myanmar (MMK)

“NAD” Dólar da Namíbia (NAD)

“NPR” Rúpia nepalesa (NPR)

“ANG” Florim das Antilhas Holandesas (ANG)

“NZD” Dólar da Nova Zelândia (NZD)

“NIO” Cordoba oro, Nicarágua (NIO)

“NGN” Naira, Nigéria (NGN)

“KPW” Won norte-coreano (KPW)

“NOK” Coroa norueguesa (NOK)

“OMR” Rial do Oman (OMR)

“PKR” Rúpia paquistanesa (PKR)

“XPD” Onças de Paládio (XPD)

“PAB” Balboa, Panamá (PAB)

“PGK” Kina de Papua Nova Guiné (PGK)

“PYG” Guarani, Paraguai (PYG)

“PEN” Novo Sol, Peru (PEN)

“PHP” Peso filipino (PHP)

“XPT” Onças de platina (XPT)

“PLN” Zlotych, Polônia (PLN)

“QAR” Riyal do Qatar (QAR)

“ROL” Leu da Romênia (ROL)

“RON” Novo Leu da Romênia (RON)

“RUB” Rublo, Rússia (RUB)

“RUR” Rublo, Rússia (RUR)

“RWF” Franco Ruanda (RWF)

“SHP” Libra de Saint Helena (SHP)

“WST” Tala, Samoa (WST)

“STD” Dobra de São Tomé e Príncipe (STD)

“SAR” Riyal da Arábia Saudita (SAR)

“SPL” Luigini, Seborga (SPL)

“RSD” Dinar da Sérvia (RSD)

“CSD” Dinar da Sérvia (CSD)

“SCR” Rúpia de Seicheles (SCR)

“SLL” Leone, Serra Leoa ( SLL)

“XAG” Onça de prata (XAG)

“SGD” Dólar de Singapura (SGD)

“SKK” Koruny, Eslováquia (SKK)

“SIT” Tolar, Eslovênia (SIT)

“SBD” Dólar das Ilhas Salomão (SBD)

“SOS” Xelim da Somália (SOS)

“ZAR” - Rand sul-africano (ZAR)

“KRW” Won sul-coreano (KRW)

“LKR” Rúpia do Sri Lanka (LKR)

“SDD” Dinar sudanês (SDD)

“SDG” Libra sudanesa (SDG)

“SRD” Dólar do Suriname (SRD)

“SRG” Florim do Suriname (SRG)

“SZL” Emalangeni, Suazilândia (SZL)

“SEK” Coroa sueca (SEK)

“CHF” Franco suíço (CHF)

“SYP” Libra síria (SYP)

“TWD” Novo Dólar de Taiwan (TWD)

“TJS” Somoni, Tajiquistão (TJS)

“TZS” Xelim da Tanzânia (TZS)

“THB” Baht, Tailândia (THB)

“TOP” Pa&#39;anga, Tonga (TOP)

“TTD” Dólar de Trinidad e Tobago (TTD)

“TND” Dinar da Tunísia (TND)

“TRY” Lira turca (TRY)

“TRL” Lira turca (TRL)

“TMM” Manat do Turquemenistão (TMM)

“TMT” Novo Manat do Turcomenistão (TMT)

“TVD” Dólar de Tuvalu (TVD)

“UGX” Xelim de Uganda (UGX)

“UAH” Hryvnia, Ucrânia (UAH)

“AED” Dirham dos Emirados Árabes Unidos (AED)

“GBP” Libra esterlina do Reino Unido (GBP)

“USD” Dólar americano (USD)

“UYU” Peso uruguaio (UYU)

“UZS” Som do Usbequistão (UZS)

“VUV” Vatu, Vanuatu (VUV)

“VEB” Bolivar, Venezuela (VEB)

“VEF” Bolivar Forte, Venezuela (VEF)

“VND” Dong, Vietnã (VND)

“YER” Rial do Iêmen (YER)

“ZMK” Kwacha, Zâmbia (ZMK)

“ZMW” Kwacha, Zâmbia (ZMW)

“ZWD” Dólar do Zimbábue (ZWD)


## Exemplo de AppMeasurement.js

A variável `currencyCode` pode ser definida globalmente no arquivo AppMeasurement.js. Definir a variável currencyCode nesse arquivo garante que todas as transações monetárias usem um mesmo código monetário. O exemplo abaixo especifica Euro como a variável `currencyCode` na `CONFIG SECTION` do arquivo AppMeasurement.js. Todos os eventos de compra serão interpretados pelos relatórios como transações em &quot;Euro&quot;.

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

Para obter mais informações sobre como editar o arquivo AppMeasurement.js, consulte [Inserir código no arquivo AppMeasurement.js](https://docs.adobe.com/content/help/pt-BR/analytics/implementation/other/dtm/analytics-tool/t-appmeasurement-code.translate.html).

## Outras notas de implementação

* Tenha em mente que, embora os códigos de moeda possam mudar entre as páginas, todos os itens da linha Conversão definidos em determinado pedido de página devem usar a mesma moeda (por exemplo, você não pode ter Euro, Libra Esterlina e Dólar americano definidos na mesma exibição de página). Se você não quiser fazer nenhuma conversão monetária, deixe o valor do currencyCode em branco. Isso faz com que os valores enviados sejam transmitidos diretamente para relatórios sem conversão.

* Definir um currencyCode inválido (qualquer valor que não esteja na lista de códigos de moeda compatíveis) faz com que toda a ocorrência seja excluída e os dados não sejam coletados para essa transação. Antes de configurar `currencyCode` em produção, use um conjunto de relatórios de teste para verificar se os dados foram coletados e se a conversão monetária está correta.

* Moedas que não usam ponto (.) como separador devem ser modificadas para usar ponto em vez do separador comum. Por exemplo, a Coroa sueca, que utiliza vírgula (,), deve ser modificada para usar ponto em vez de vírgula. O Analytics usa a vírgula para separar valores, e os dados não serão passados corretamente. O uso de ponto faz com que os valores sejam passados corretamente para relatórios.
