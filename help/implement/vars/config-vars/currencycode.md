---
title: O que é a variável currencyCode e como usá-la?
description: Para sites de comércio eletrônico, define a moeda em que a página negocia.
feature: Appmeasurement Implementation
exl-id: 3332c366-c472-4778-96c8-ef0aa756cca8
role: Admin, Developer
TQID: https://experienceleague.adobe.com/DKHPWh0KRGKXW6QOspE5K0FGBFCrzLYSrTufIt3Xf4g
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 952
ht-degree: 96%

---

# currencyCode

Em sites que usam comércio, receita e moeda, é uma parte importante do Analytics. Muitos sites, especialmente aqueles que abrangem vários países, usam moedas diferentes. Use a variável `currencyCode` para verificar se os atributos de receita estão na moeda correta.

A conversão de moeda usa a seguinte lógica em cada ocorrência. Essas etapas se aplicam aos valores de receita definidos pela variável [`products`](../page-vars/products.md) e a todos os eventos listados como “Moeda” na seção [Eventos bem-sucedidos](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/c-success-events/success-event.md) das configurações do conjunto de relatórios.

* Se `currencyCode` não estiver definido, a Adobe presume que todos os valores de moeda são a moeda do conjunto de relatórios. Consulte [Configurações gerais da conta](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md) nas configurações do conjunto de relatórios para ver a moeda do conjunto de relatórios.
* Se `currencyCode` for definida e corresponder à moeda do conjunto de relatórios, nenhuma conversão de moeda será aplicada.
* Se `currencyCode` estiver definida e for diferente da moeda do conjunto de relatórios, a Adobe aplicará uma conversão de moeda com base na taxa de câmbio do dia. A Adobe tem uma parceria com o [XE](https://xe.com) para converter moeda a cada dia. Todos os valores armazenados no conjunto de relatórios estão na moeda do conjunto de relatórios.
* Se `currencyCode` estiver definido com um valor inválido, **a ocorrência inteira será descartada, causando perda de dados.** Verifique se essa variável está definida corretamente sempre que for usada.

Essa variável não é mantida entre ocorrências. Verifique se essa variável está definida em todas as páginas que envolvam eventos de receita ou moeda que não correspondam à moeda padrão do conjunto de relatórios.

>[!NOTE]
>
>Embora os códigos de moeda possam mudar entre páginas, todas as métricas de moeda em uma única ocorrência devem usar a mesma moeda.

Um ponto **deve** ser usado como separador para todas as moedas ao implementar essa variável. Por exemplo, a coroa sueca, que normalmente exibe um separador de vírgula, deve ser modificada para usar um ponto na variável `products` e em todos os eventos de moeda. A Adobe exibe o separador de moeda correto no relatório.

## Código de moeda usando o SDK da Web

O código de moeda é mapeado para as seguintes variáveis:

* [objeto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.commerce.order.currencyCode`
* [Objeto de dados](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.currencyCode` ou `data.__adobe.analytics.cc`

## Código de moeda usando a extensão do Adobe Analytics

O Código de moeda é um campo da opção [!UICONTROL Geral] ao configurar a extensão do Adobe Analytics.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade de tag desejada.
1. Vá até a guia [!UICONTROL Extensões] e clique no botão **[!UICONTROL Configurar]**, no Adobe Analytics.
1. Expanda a opção [!UICONTROL Geral], que revela o campo [!UICONTROL Código monetário].

É possível usar um código monetário predefinido ou personalizado. Se estiver usando um código monetário personalizado, verifique se ele é válido.

## Código monetário no SDK móvel da Adobe Experience Platform

O código monetário é passado para os SDKs do Adobe Experience Platform Mobile por meio de variáveis de dados de contexto na extensão do Adobe Analytics.

1. Defina o código monetário em uma variável de dados de contexto durante `trackState` ou `trackAction`.
1. Crie uma regra de processamento nas Ferramentas administrativas do Adobe Analytics para o conjunto de relatórios. Defina a regra para substituir a variável Código monetário.
1. Transmita o código monetário para a variável `products` na sua chamada para `trackState` ou `trackAction`.

É possível usar um código monetário predefinido ou personalizado. Se estiver usando um código monetário personalizado, verifique se ele é válido.

## s.currencyCode no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `s.currencyCode` é uma cadeia de caracteres que contém um código de 3 letras maiúsculas representando a moeda na página. Os valores diferenciam maiúsculas de minúsculas.

```js
s.currencyCode = "USD";
```

Os seguintes códigos monetários são válidos:

| Código de moeda | Rótulo |
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
