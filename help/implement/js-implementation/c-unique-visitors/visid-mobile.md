---
description: A maioria dos dispositivos móveis aceita os cookies do navegador. Porém, em casos nos quais os dispositivos não aceitam cookies, um outro método é usado para identificar os dispositivos sem fio.
keywords: Implementação do Analytics
seo-description: A maioria dos dispositivos móveis aceita os cookies do navegador. Porém, em casos nos quais os dispositivos não aceitam cookies, um outro método é usado para identificar os dispositivos sem fio.
seo-title: Identificar dispositivos móveis
solution: Analytics
title: Identificar dispositivos móveis
topic: Desenvolvedor e implementação
uuid: 22587 dd 1-cead -485 b-a 4 d 8-94 dfb 7 cd 9662
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# Identificar dispositivos móveis

A maioria dos dispositivos móveis aceita os cookies do navegador. Porém, em casos nos quais os dispositivos não aceitam cookies, um outro método é usado para identificar os dispositivos sem fio.

A Adobe identificou diversos cabeçalhos HTTP de [assinantes de ID](../../../implement/js-implementation/c-unique-visitors/visid-mobile.md#section_60D6EAC0D16945A89DD5A7ADF3B8298D) que identificam exclusivamente a maioria dos dispositivos móveis. Esses cabeçalhos com frequência incluem o número do telefone (ou uma versão com hash do número) ou outros identificadores. A maioria dos dispositivos tem um ou mais cabeçalhos que identificam exclusivamente o dispositivo, e todos os centros de dados da Adobe usam esses cabeçalhos no lugar de uma ID do visitante.

In a typical image request, a '1' in the path ( `/b/ss/rsid/1`) causes Adobe servers to return a gif image and to attempt to set a persistent [!UICONTROL visitor ID] cookie ( `AMCV_` or `s_vi`). Porém, caso o dispositivo seja reconhecido como móvel com base nos cabeçalhos HTTP, um "5" será aprovado em lugar do "1" - o que indica que um formato de imagem wbmp deverá ser devolvido e que a lista de cabeçalhos sem fio reconhecidos (ou seja, que não são cookies) deverá ser usado para identificar o dispositivo.

A tabela a seguir exibe a ordem que os métodos de ID são utilizados, com base no valor do tipo da imagem devolvida ("1" ou "5") no caminho:

<table id="table_07B0E55D5DAA4552A5CBC6937D47A857"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Configuração </th> 
   <th colname="col2" class="entry"> Ordem do método de ID </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> /1/</code> </td> 
   <td colname="col2"> <p>Padrão: </p> 
    <ul id="ul_E37E9919658A492C92187BAA18D33AB6"> 
     <li id="li_1A9E39C7CFB24C68AA07C8E85D33A858">ID personalizada do visitante </li> 
     <li id="li_0DC8D17828C848BEB614C6E47C090064">Cookie </li> 
     <li id="li_52706792FAD14F459266E3A672F92EA1">Cabeçalho da ID do assinante </li> 
     <li id="li_ECAD713D22314338BB5C92167DC0BB02"> Endereço IP-Agente do usuário-Endereço IP do Gateway </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> /5/ /5.1/ /5.5/</code> </td> 
   <td colname="col2"> <p>O dispositivo foi identificado como móvel, ou <code>/5/</code> foi enviado manualmente na solicitação de imagem: </p> 
    <ul id="ul_624BEDFA3E1243CF9B42081D8B8EFFFB"> 
     <li id="li_D65761D23B684DB59BC23E92C9098122">ID personalizada do visitante </li> 
     <li id="li_ADBA806B74CA43EFA8612301E06106C6">Cabeçalho da ID do assinante </li> 
     <li id="li_79DFD0DEAA1242C09A03E8134A40F799">Cookie </li> 
     <li id="li_A462B9120FC6443480D62F37D456747E">Endereço IP-Agente do usuário-Endereço IP do Gateway </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

Também é possível aprovar "1" ou "5" em solicitações manuais de imagem, mas veja se esses códigos são mutualmente exclusivos já que aprovar um "5" não faz com que o cookie seja aproveitado (mesmo que seja suportado). Você pode incorporar seu próprio mecanismo para determinar se um dispositivo suporta cookies e, em caso positivo, transmitem um '1' para a imagem, em vez de um '5'. O aprimoramento da precisão nessa situação é limitado ao número de dispositivos móveis que suportam cookies.

## Cabeçalhos da ID de assinante {#section_60D6EAC0D16945A89DD5A7ADF3B8298D}

Em geral, o método de ID do assinante é mais confiável do que um cookie para identificação do usuário devido à exclusão do cookie, a problemas de aceitação de cookie e gerenciamento de cookie de gateway.

Você pode melhorar a probabilidade de identificar um visitante ao ser incluído na lista branca da operadora que seus visitantes móveis usam. Para obter acesso à ID de visitante da operadora, entre em contato com a operadora para adicionar seu domínio à lista branca. Se você está na lista branca da operadora, é possível acessar os cabeçalhos de ID de assinante que, do contrário, não estão acessíveis.

A lista de cabeçalhos a seguir é usada para identificar dispositivos sem fio. O algoritmo usado para processar os cabeçalhos serve para

1. extrair a chave do cabeçalho HTTP (nome do cabeçalho, como "X-Up-Calling-Line-ID")
1. arrumar todos os caracteres não-alfabéticos (A-Z e a-z)
1. converter a chave do cabeçalho para minúsculas
1. comparar o final da chave àqueles presentes na seguinte tabela (e encontrar uma correspondência):

| Cabeçalho | Tipo | Exemplo |
|---|---|---|
| callinglineid | ID | X-Up-Calling-Line-ID: 8613802423312 |
| subno | ID | x-up-subno: swm_10448371100_vmag.mycingular.net |
| clientid | ID | ClientID: eGtUpsqEO19zVHmbOkgaPVI-@sprintpcs.com |
| uid | ID | x-jphone-uid: a2V4Uh21XQH9ECNN |
| clid | ID | X-Hts_clid: 595961714786 |
| deviceid | ID | rim-device-id: 200522ae |
| forwardedfor | ID ou endereço IP | X-Forwarded-For: 127.0.0.1 |
| msisdn | ID ou endereço IP | X-Wap-msisdn: 8032618185 |
| clientip | Endereço IP | Client-ip: 10.9.41.2 |
| wapipaddr | Endereço IP | X-WAPIPADDR: 10.48.213.162 |
| huaweinasip | Endereço IP | x-huawei-NASIP: 211.139.172.70 |
| userip | Endereço IP | UserIP: 70.214.81.241 |
| ipaddress | Endereço IP | X-Nokia-ipaddress: 212.97.227.125 |
| subscriberinfo | Endereço IP | X-SUBSCRIBER-INFO: IP=10.103.132.128 |

Por exemplo, "callinglineid" corresponderia a "X-Up-Calling-Line-ID" e "nokia-callinglineid". O tipo de cabeçalho informa o que esperar do cabeçalho. A ordem de prioridade do cabeçalho é listada aqui (se um cabeçalho "callinglineid" estiver presente, ele é usado no lugar de "subno").

Você pode utilizar [Variáveis dinâmicas](../../../implement/js-implementation/c-variables/dynvars-overview.md#concept_B016789733A94070A9EAB209EEC05262) para extrair valores específicos de um cabeçalho.
