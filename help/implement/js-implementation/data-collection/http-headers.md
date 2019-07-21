---
description: A solicitação HTTP e os cabeçalhos de resposta são usados para coletar dados adicionais, além daqueles coletados pelo AppMeasurement. Esta seção descreve os cabeçalhos usados durante a coleta de dados.
keywords: Implementação do Analytics
seo-description: A solicitação HTTP e os cabeçalhos de resposta são usados para coletar dados adicionais, além daqueles coletados pelo AppMeasurement. Esta seção descreve os cabeçalhos usados durante a coleta de dados.
seo-title: Cabeçalhos HTTP da coleção de dados
solution: Analytics
title: Cabeçalhos HTTP da coleção de dados
topic: Desenvolvedor e implementação
uuid: 3325 e 13 c-b 300-46 e 4-a 592-3 a 83 ed 59718 b
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Cabeçalhos HTTP da coleção de dados

A solicitação HTTP e os cabeçalhos de resposta são usados para coletar dados adicionais, além daqueles coletados pelo AppMeasurement. Esta seção descreve os cabeçalhos usados durante a coleta de dados.

## Cabeçalhos de solicitação HTTP  {#section_C1DE3416CCC241A898155C915A01A0FC}

<table id="table_84D1F4B54ABE4423A2EBE840C49D3876"> 
 <tbody> 
  <tr> 
   <td> <b>Cabeçalho</b> </td> 
   <td> <b>Uso</b> </td> 
  </tr> 
  <tr> 
   <td> Cookie </td> 
   <td> <p>Leitura dos cookies criados anteriormente pelos servidores de coleta de dados. </p> <p> A partir de 2014, os servidores da Adobe descartarão todos os cookies que acompanham uma chamada de servidor, exceto os definidos pela Adobe. Consulte <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/" format="https" scope="external">Cookies usados na Experience Cloud</a> para obter uma lista completa dos cookies da Adobe. </p> </td> 
  </tr> 
  <tr> 
   <td> User-Agent </td> 
   <td> Usado para detecção de navegador, sistema operacional e dispositivo móvel. </td> 
  </tr> 
  <tr> 
   <td> X-Device-User-Agent </td> 
   <td> Usado como uma alternativa ao Agente de usuário para detecção correta do navegador, sistema operacional e dispositivo móvel para alguns navegadores, como OperaMini. </td> 
  </tr> 
  <tr> 
   <td> X-Original-User-Agent </td> 
   <td> Usado como uma alternativa ao Agente de usuário para detecção correta do navegador, sistema operacional e dispositivo móvel para alguns navegadores, como OperaMini. </td> 
  </tr> 
  <tr> 
   <td> Agente de usuário para telefone OperaMini X </td> 
   <td> Usado como uma alternativa ao Agente de usuário para detecção correta do navegador, sistema operacional e dispositivo móvel para alguns navegadores, como OperaMini. </td> 
  </tr> 
  <tr> 
   <td> X-Skyfire-Phone </td> 
   <td> Usado como uma alternativa ao Agente de usuário para detecção correta do navegador, sistema operacional e dispositivo móvel para alguns navegadores, como OperaMini. </td> 
  </tr> 
  <tr> 
   <td> X-Bolt-Phone-UA </td> 
   <td> Usado como uma alternativa ao Agente de usuário para detecção correta do navegador, sistema operacional e dispositivo móvel para alguns navegadores, como OperaMini. </td> 
  </tr> 
  <tr> 
   <td> UA-OS </td> 
   <td> Usado como uma alternativa para identificar o sistema operacional. </td> 
  </tr> 
  <tr> 
   <td> UA-Pixels </td> 
   <td> Usado como uma fonte alternativa de resolução na tela do cliente. </td> 
  </tr> 
  <tr> 
   <td> UA-Color </td> 
   <td> Usado como uma fonte alternativa de profundidade de cor na tela do cliente. </td> 
  </tr> 
  <tr> 
   <td> X-moz </td> 
   <td> Detecção de que a solicitação da coleta de dados foi feita como parte da busca prévia de uma página da Web. </td> 
  </tr> 
  <tr> 
   <td> X-Purpose </td> 
   <td> A detecção de que a solicitação da coleta de dados foi feita enquanto o navegador estava mostrando uma visualização de uma página da Web. </td> 
  </tr> 
  <tr> 
   <td> Accept </td> 
   <td> Usado para identificar os formatos de imagem suportados pelo navegador para que saibamos se precisamos enviar uma imagem GIF ou WBMP de volta. </td> 
  </tr> 
  <tr> 
   <td> Referenciador </td> 
   <td> Usado como um fallback para obter informações sobre a URL de página da qual a solicitação da coleta de dados foi feita quando não foi transmitida na string de consulta ou quando era diferente do valor na string da consulta. </td> 
  </tr> 
  <tr> 
   <td> X-Forwarded-For </td> 
   <td> Usado para localizar o endereço IP correto para o cliente que fez a solicitação da coleta de dados. O endereço IP é usado par gerar a região geográfica, a operadora de celular e outros relatórios. </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>As implementações que usam variáveis dinâmicas têm a opção de ler em outros cabeçalhos de solicitação HTTP não listados acima.

## Cabeçalhos de resposta HTTP {#section_A9C7035198C84037A21A8033CC408F0E}

| **Cabeçalho** | **Uso** |
|---|---|
| Origem de permissão do controle de acesso | Usado para permitir o suporte para recursos de origem cruzadas que compartilham as solicitações da coleta de dados de estilo com nossos servidores. |
| Expira | Controle de armazenamento em cache do navegador. |
| Última modificação | Controle de armazenamento em cache do navegador. |
| Controle de cache | Controle de armazenamento em cache do navegador. |
| Pragma | Controle de armazenamento em cache do navegador. |
| ETag | Controle de armazenamento em cache do navegador. |
| Vary | Controle de armazenamento em cache do navegador. |
| P3P | Oferece a política P3P padrão ou personalizada para a solicitação da coleta de dados. |
| Status | Contém status "SUCESSO" ou "FALHA" para uma solicitação sem conteúdo. Usado somente quando a solicitação especifica que nenhum conteúdo deve ser retornado. |
| Motivo | Contém o motivo para o status de falha de uma solicitação sem conteúdo. Usado somente quando a solicitação especifica que nenhum conteúdo deve ser retornado. |
| Local | Usado para redirecionar o cliente que faz a solicitação da coleta de dados para uma URL diferente. Um exemplo é nosso handshake de cookie para detectar a capacidade de definir o cookie da ID do visitante. |
| Tipo de conteúdo | Especifica o tipo de conteúdo enviado de volta ao cliente (GIF, texto, JavaScript etc). |
| Tamanho do conteúdo | Especifica o tamanho do conteúdo enviado de volta ao cliente. |

>[!NOTE]
>
>Outros cabeçalhos HTTP podem ser definidos em resposta ao monitoramento de status interno. Alguns desses cabeçalhos podem ser retornados para o navegador, mas eles não precisam recebê-los.
