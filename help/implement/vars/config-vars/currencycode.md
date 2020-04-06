---
title: currencyCode
desciption: For eCommerce sites, set the currency the page deals in.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# currencyCode

Em sites que usam comércio, receita e moeda, é uma parte importante do Analytics. Muitos sites, especialmente aqueles que abrangem vários países, usam moedas diferentes. Use a variável `currencyCode` para verificar se os atributos de receita estão na moeda correta.

Se `currencyCode` não estiver definido, os valores monetários definidos para a variável [`products`](../page-vars/products.md) e os eventos monetários serão tratados como se fossem a mesma moeda do conjunto de relatórios. Consulte [Configurações gerais de conta](/help/admin/admin/general-acct-settings-admin.md) no guia do usuário Admin para ver a moeda do conjunto de relatórios.

Se `currencyCode` for definida e corresponder à moeda do conjunto de relatórios, nenhuma conversão de moeda será aplicada.

Se `currencyCode` estiver definida e for diferente da moeda do conjunto de relatórios, a Adobe aplicará uma conversão de moeda com base na taxa de câmbio do dia. A Adobe tem uma parceria com o [XE](https://xe.com) para converter moeda a cada dia. Todos os valores armazenados nos servidores de coleta de dados são armazenados na moeda do conjunto de relatórios.

>[!IMPORTANT] Se `currencyCode` contiver um valor inválido, a ocorrência inteira será descartada, causando perda de dados. Certifique-se de que essa variável esteja definida corretamente se usá-la na implementação.

Essa variável não é mantida entre ocorrências. Certifique-se de que essa variável esteja definida em cada página que envolva eventos de receita ou moeda.

## Código monetário no Adobe Experience Platform Launch

Currency Code is a field under the [!UICONTROL General] accordion when configuring the Adobe Analytics extension.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. Amplie o [!UICONTROL General] acordeão, que revela o [!UICONTROL Currency Code] campo.

É possível usar um código monetário predefinido ou personalizado. Se estiver usando um código monetário personalizado, verifique se ele é válido.

## s.currencyCode no AppMeasurement e no editor de código personalizado do Launch

A variável `s.currencyCode` é uma cadeia de caracteres, que contém um código de 3 letras maiúsculas representando a moeda na página.

```js
s.currencyCode = "USD";
```

Os seguintes códigos monetários são válidos:

| Código de moeda | Descrição da moeda |
| --- | --- |
| `AED` | Emirados Árabes Unidos - Dirrãs |
| `AFA` | Afeganistão - Afeganis |
| `ALL` | Albânia - Leks |
| `AMD` | Armênia - Drams |
| `ANG` | Atilles Guilder - Países Baixos |
| `AOA` | Angola - Kwanza |
| `ARS` | Argentina - Pesos argentinos |
| `AUD` | Austrália - Dólares australianos |
| `AWG` | Aruba - Florins |
| `AZM` | Azerbaijão - Manats |
| `BAM` | Marco Conversível da Bósnia e Herzegovina |
| `BBD` | Barbados - Dólares barbadianos |
| `BDT` | Bangladesh - Taka |
| `BGN` | Bulgária - Leva |
| `BHD` | Bahrein - Dinar do Bahrein |
| `BIF` | Burundi - Francos |
| `BMD` | Bermudas - Dólares das Bermudas |
| `BND` | Brunei - Dólares de Brunei |
| `BOB` | Bolívia - Bolivianos |
| `BRL` | Brasil - Reais |
| `BSD` | Bahamas - Dólares das Bahamas |
| `BTN` | Butão - Ngultrum |
| `BWP` | Botsuana - Pulas |
| `BYR` | Bielorrússia - Rublos |
| `BZD` | Belize - Dólares de Belize |
| `CAD` | Canadá - Dólares canadenses |
| `CDF` | Congo/Kinshasa - Francos |
| `CHF` | Suíça - Francos suíços |
| `CLP` | Chile - Pesos chilenos |
| `CNY` | China - Yuan Renminbi |
| `COP` | Colômbia - Pesos colombianos |
| `CRC` | Costa Rica - Colones costarriquenhos |
| `CSD` | Sérvia - Dinares |
| `CUP` | Cuba - Pesos cubanos |
| `CVE` | Cabo Verde - Escudos |
| `CYP` | Chipre - Libras chipriotas |
| `CZK` | República Tcheca - Coroa tcheca |
| `DJF` | Djibuti - Francos |
| `DKK` | Dinamarca - Coroa dinamarquesa |
| `DOP` | República Dominicana - Pesos |
| `DZD` | Argélia - Dinares |
| `EEK` | Estônia - Coroa |
| `EGP` | Egito - Libras egípcias |
| `ERN` | Eritreia - Nakfa |
| `ETB` | Etiópia - Birr |
| `EUR` | Euro |
| `FJD` | Fiji - Dólares de Fiji |
| `FKP` | Ilhas Falkland - Libras |
| `GBP` | Reino Unido - Libras |
| `GEL` | Geórgia - Lari |
| `GGP` | Guernsey - Libras |
| `GHC` | Gana - Cedis |
| `GIP` | Gibraltar - Libras |
| `GMD` | Gâmbia - Dalasi |
| `GNF` | Guiné - Francos guineanos |
| `GTQ` | Guatemala - Quetzales |
| `GYD` | Guiana - Dólares guianenses |
| `HKD` | Hong Kong - Dólares de Hong Kong |
| `HNL` | Honduras - Lempiras |
| `HRK` | Croácia - Kuna |
| `HTG` | Haiti - Gourdes |
| `HUF` | Hungria - Florim húngaro |
| `IDR` | Indonésia - Rúpias |
| `ILS` | Israel - Novos Shekels |
| `IMP` | Ilha de Man - Libras |
| `INR` | Índia - Rúpias indianas |
| `IQD` | Iraque - Dinares iraquianos |
| `IRR` | Irã - Rials |
| `ISK` | Islândia - Coroa |
| `JEP` | Jersey - Libras |
| `JMD` | Jamaica - Dólares jamaicanos |
| `JOD` | Jordânia - Dinares jordanianos |
| `JPY` | Japão - Iene |
| `KES` | Quênia - Xelins |
| `KGS` | Quirguistão - Soms |
| `KHR` | Camboja - Riels |
| `KMF` | Comoros - Francos |
| `KPW` | Coreia do Norte - Won norte-coreano |
| `KRW` | Coreia do Sul - Won sul-coreano |
| `KWD` | Kuwait - Dinares kuwaitianos |
| `KYD` | Ilhas Cayman - Dólares das Caimans |
| `KZT` | Cazaquistão - Tenge |
| `LAK` | Laos - Kips |
| `LBP` | Líbano - Libras |
| `LKR` | Sri Lanka - Rúpias cingalesas |
| `LRD` | Libéria - Dólares liberianos |
| `LSL` | Lesoto - Maloti |
| `LTL` | Lituânia - Litai |
| `LVL` | Letônia - Lati |
| `LYD` | Líbia - Dinares líbios |
| `MAD` | Marrocos - Dirrãs marroquinos |
| `MDL` | Moldávia - Leu |
| `MGA` | Madagascar - Ariary |
| `MKD` | Macedônia - Dinares |
| `MMK` | Mianmar - Quiates |
| `MNT` | Mongólia - Tugriks |
| `MOP` | Macau - Patacas |
| `MRO` | Mauritânia - Ouguiyas |
| `MTL` | Malta - Liri |
| `MUR` | Maurício - Rúpias mauricianas |
| `MVR` | Maldivas - Rúpias maldívias |
| `MWK` | Malauí - Cuachas malauianas |
| `MXN` | México - Pesos mexicanos |
| `MYR` | Malásia - Ringgits malaios |
| `MZM` | Moçambique - Meticais |
| `NAD` | Namíbia - Dólares namibianos |
| `NGN` | Nigéria - Nairas |
| `NIO` | Córdoba Ouro da Nicarágua |
| `NOK` | Noruega - Coroa norueguesa |
| `NPR` | Nepal - Rúpias nepalesas |
| `NZD` | Nova Zelândia - Dólares da Nova Zelândia |
| `OMR` | Omã - Rials omanenses |
| `PAB` | Panamá - Balboas |
| `PEN` | Peru - Sóis Novos |
| `PGK` | Papua Nova Guiné - Kina |
| `PHP` | Filipinas - Pesos filipinos |
| `PKR` | Paquistão - Rúpias paquistanesas |
| `PLN` | Polônia - Zlotych |
| `PYG` | Paraguai - Guarani |
| `QAR` | Catar - Rials |
| `ROL` | Romênia - Leu |
| `RUR` | Rússia - Rublos |
| `RWF` | Ruanda - Francos |
| `SAR` | Arábia Saudita - Rials sauditas |
| `SBD` | Ilhas Salomão - Dólares das Ilhas Salomão |
| `SCR` | Seychelles - Rúpias de Seychelles |
| `SDD` | Sudão - Dinares sudaneses |
| `SEK` | Suécia - Coroa sueca |
| `SGD` | Singapura - Dólares de Singapura |
| `SHP` | Santa Helena - Libras |
| `SIT` | Eslovênia - Tolares |
| `SKK` | Eslováquia - Coroa eslovaca |
| `SLL` | Serra Leoa - Leones |
| `SOS` | Somália - Xelins somalianos |
| `SPL` | Seborga - Luigino |
| `SRD` | Dólares do Suriname |
| `SRG` | Suriname - Florins do Suriname |
| `STD` | Dobra são-tomense |
| `SVC` | El Salvador - Colones salvadorenhos |
| `SYP` | Libras Sírias |
| `SZL` | Emalangeni da Suazilândia |
| `THB` | Baht tailandês |
| `TJS` | Somani tadjique |
| `TMM` | Manats turcomenos |
| `TND` | Dinares tunisianos |
| `TOP` | Tonga - Pa&#39;anga |
| `TRL` | Liras turcas |
| `TTD` | Dólares de Trinidad e Tobago |
| `TVD` | Dólares de Tuvalu |
| `TWD` | Novo Dólar de Taiwan |
| `TZS` | Xelins Tanzanianos |
| `UAH` | Ucrânia - Hrvyna |
| `UGX` | Xelins de Uganda |
| `USD` | Dólar americano |
| `UYU` | Pesos uruguaios |
| `UZS` | Som uzbeque |
| `VEB` | Bolívares venezuelanos |
| `VND` | Dong vietnamita |
| `VUV` | Vanuatu - Vatu |
| `WST` | Tala de Samoa |
| `XAF` | Communauté Financière Africaine Francs B |
| `XAG` | Onças de prata |
| `XAU` | Onças de ouro |
| `XCD` | Dólares do leste caribenho |
| `XDR` | Saque Especial do Fundo Monetário Internacional |
| `XOF` | Communauté Financière Africaine Francs B |
| `XPD` | Onças de paládio |
| `XPF` | Comptoirs Français du Pacifique Francs |
| `XPT` | Onças de platina |
| `YER` | Rial do Iêmen |
| `ZAR` | Rand da África do Sul |
| `ZMK` | Cuacha zambiana |
| `ZWD` | Dólar de Zimbábue |
