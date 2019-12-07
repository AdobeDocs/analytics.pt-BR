---
description: O plug-in getTimeParting preenche as variáveis personalizadas com a hora, o dia da semana e os valores de fim de semana e de dias da semana. A Analysis Workspace oferece dimensões de hora do visitante prontas para uso. O plug-in deve ser usado se as dimensões de hora do visitante forem necessárias em outras soluções do Analytics, fora do Analysis Workspace.
keywords: Analytics Implementation
subtopic: Plug-ins
title: getTimeParting
topic: Developer and implementation
uuid: 74f696a3-7169-4560-89b2-478b3d8385e1
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# getTimeParting

O plug-in getTimeParting preenche as variáveis personalizadas com a hora, o dia da semana e os valores de fim de semana e de dias da semana. [!UICONTROL A Analysis Workspace] oferece dimensões de hora do visitante prontas para uso. O plug-in deve ser usado se as dimensões de hora do visitante forem necessárias em outras soluções do Analytics, fora do [!UICONTROL Analysis Workspace].

Esse plug-in captura as informações de data e hora disponíveis no navegador Web do usuário. Ele obtém a hora do dia e o dia da semana com base nessas informações. Em seguida converte esses dados para o fuso horário de sua escolha. Ele também considera o horário de verão.

> [!NOTE] Observação: as instruções a seguir exigem que você altere o código da coleta de dados do seu site. Isso pode afetar a coleta de dados no site e só deve ser feito por um desenvolvedor com experiência de uso e implementação do [!DNL Analytics].

## Código do plug-in {#section_1390D6FA53BE4C40B748B0C0AE09C4FA}

**Seção de configuração**

Coloque o seguinte código na área do arquivo [!DNL s_code.js] rotulada como [!UICONTROL SEÇÃO DE CONFIGURAÇÃO] e faça as atualizações necessárias como descrito abaixo.

`s._tpDST` - uma matriz de valores DST. A matriz está estruturada no seguinte formato: `YYYY:'MM/DD,MM/DD'`

```js
//time parting configuration 
//Australia 
s._tpDST = { 
2012:'4/1,10/7', 
2013:'4/7,10/6', 
2014:'4/6,10/5', 
2015:'4/5,10/4', 
2016:'4/3,10/2', 
2017:'4/2,10/1', 
2018:'4/1,10/7', 
2019:'4/7,10/6',
2020:'4/5,10/4',
2021:'4/4,10/3'} 
  
//US 
s._tpDST = { 
2012:'3/11,11/4', 
2013:'3/10,11/3', 
2014:'3/9,11/2', 
2015:'3/8,11/1', 
2016:'3/13,11/6', 
2017:'3/12,11/5', 
2018:'3/11,11/4', 
2019:'3/10,11/3',
2020:'3/8,11/1',
2021:'3/14,11/7'} 
  
//Europe 
s._tpDST = { 
2012:'3/25,10/28', 
2013:'3/31,10/27', 
2014:'3/30,10/26', 
2015:'3/29,10/25', 
2016:'3/27,10/30', 
2017:'3/26,10/29', 
2018:'3/25,10/28', 
2019:'3/31,10/27',
2020:'3/29,10/25',
2021:'3/28,10/31'}
```

Observação para clientes do Hemisfério norte: na matriz de valores DST são DST de início, DST de fim.

Observação para clientes do Hemisfério sul: na matriz de valores DST são DST de fim, DST de início.

**Parâmetros**

```js
var tp = s.getTimeParting(h,z);
```

* Hemisfério h = (obrigatório) - Especifique para qual hemisfério você está convertendo o horário. Este é um valor de "n" ou "s". Ele é usado para determinar como a matriz aprovada de DST será utilizada. Se "n" for aprovado, o plugin utilizará as datas quando DST estiver ativo. Se "s" for aprovado, o plugin utilizará as datas quando DST estiver inativo.
* z = (opcional) Fuso horário - Caso queira que os dados sejam baseados em um período de tempo específico, será necessário informar essa decisão; as horas, aqui, são diferentes do GMT. Observe que o GMT deve ser executado durante um período que não pertencente ao DST. Se nenhum valor for especificado, o valor GMT será selecionado (por exemplo, "-5" para a Hora do Leste dos EUA)

**Devoluções**

Devolve um valor concatenado do horário em minutos e dia da semana. Por exemplo:

```
8:03 AM|Monday
```

Você pode, então, usar [Classificações](https://marketing.adobe.com/resources/help/en_US/reference/classifications.html) para agrupar visitas em períodos de tempo. É possível, por exemplo, configurar uma regra no Construtor de regra de classificação que agrupe visitas entre 9h00 e 9h59 AM e no grupo "9h00 - 10h00 AM". Uma outra alternativa é oferecer lógica adicional do lado do cliente e agrupar visitas no JavaScript.

**Exemplo de chamada**

```js
var tp = s.getTimeParting('n','-7'); 
s.prop1 = tp;
```

**SEÇÃO DE PLUG-INS**

Adicione o seguinte código à [!UICONTROL SEÇÃO DE PLUG-INS] no arquivo [!DNL s_code.js].

```js
/* 
 * Plugin: getTimeParting 3.4 
 */ 
s.getTimeParting=new Function("h","z","" 
+"var s=this,od;od=new Date('1/1/2000');if(od.getDay()!=6||od.getMont" 
+"h()!=0){return'Data Not Available';}else{var H,M,D,U,ds,de,tm,da=['" 
+"Sunday','Monday','Tuesday','Wednesday','Thursday','Friday','Saturda" 
+"y'],d=new Date();z=z?z:0;z=parseFloat(z);if(s._tpDST){var dso=s._tp" 
+"DST[d.getFullYear()].split(/,/);ds=new Date(dso[0]+'/'+d.getFullYea" 
+"r());de=new Date(dso[1]+'/'+d.getFullYear());if(h=='n'&&d>ds&&d<de)" 
+"{z=z+1;}else if(h=='s'&&(d>de||d<ds)){z=z+1;}}d=d.getTime()+(d.getT" 
+"imezoneOffset()*60000);d=new Date(d+(3600000*z));H=d.getHours();M=d" 
+".getMinutes();M=(M<10)?'0'+M:M;D=d.getDay();U=' AM';if(H>=12){U=' P" 
+"M';H=H-12;}if(H==0){H=12;}D=da[D];tm=H+':'+M+U;return(tm+'|'+D);}");
```

**Notas**

* Sempre teste as instalações de plug-ins para garantir que a coleta de dados ocorra como esperado antes de implantar na produção.
* Para funcionarem corretamente, as variáveis de configuração devem ser definidas para plug-ins.

