---
description: É possível capturar os valores de elementos de formulários, como botões de opção e itens de caixa de seleção, em relatórios. Esse recurso ajuda você a analisar as escolhas mais comuns em seus formulários online.
keywords: Implementação do Analytics
seo-description: É possível capturar os valores de elementos de formulários, como botões de opção e itens de caixa de seleção, em relatórios. Esse recurso ajuda você a analisar as escolhas mais comuns em seus formulários online.
seo-title: Coletar dados de elementos de formulário
solution: Analytics
title: Coletar dados de elementos de formulário
topic: Desenvolvedor e implementação
uuid: e 0 c 13 b 96-e 1 ca -4744-a 912-60 ca 2 b 8 f 25 c 3
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Coletar dados de elementos de formulário

É possível capturar os valores de elementos de formulários, como botões de opção e itens de caixa de seleção, em relatórios. Esse recurso ajuda você a analisar as escolhas mais comuns em seus formulários online.

Por exemplo, se você tiver um botão de opção que permita ao usuário especificar um gênero de música favorito (como rock, rap, clássica ou jazz), poderá capturar essa resposta em uma variável para determinar as preferências gerais de música da sua base de usuários.

O melhor método para capturar esses dados depende de como seus formulários são processados. Ele depende também se as seleções de formulário que você deseja capturar estão disponíveis na string de consulta na página seguinte ao envio do formulário. Os exemplos neste tópico estão em PHP. No entanto, é possível adaptar esses conceitos para outra linguagem, dependendo do ambiente do servidor.

Essas informações são para usuários avançados que conhecem bem os relatórios e a implementação. Não tente editar sua implementação sem conhecer totalmente as consequências. Se for necessário efetuar alterações na implementação, entre em contato com o Gerente de conta da sua organização.

## Método GET {#section_7A2B35822BFF4F6EB57940B31AE6303A}

Se o seu formulário usa um método [!UICONTROL GET] para enviar dados, é possível acessar os dados desejados na string de consulta do URL na página seguinte ao envio do formulário. Você pode usar o plug-in [!UICONTROL getQueryParam] para capturar automaticamente esses dados na string de consulta e colocá-los na variável de sua escolha.

## Método POST {#section_56715C30EF374BA7AA12B946B50E4A9A}

Se o seu formulário usa um método [!UICONTROL POST] para enviar dados (que é a situação mais comum), os resultados de cada elemento de formulário específico estarão disponíveis para você em [!UICONTROL $_POST superglobal]. Para capturar isso em uma variável, determine o nome do elemento de formulário em questão. Utilizando o exemplo de gênero musical mencionado acima, parte do elemento de formulário em questão é semelhante a:

```
<input type="radio" name="music_genre" value="rock">
```

Este botão de opção pertence ao elemento de formulário "music_genre". You then have access to the user's selected value by using $_POST['music_genre']. Ele pode ser gravado em uma variável na página seguinte ao envio do formulário:

```js
s.eVar1="<?=$_POST['music_genre'];?>"
```

A variável [!UICONTROL eVar1] recebe uma cópia do valor enviado para seu servidor pelo formulário, como especificado na propriedade value=.

Se você precisar de informações adicionais relacionadas a esse método de implementação personalizado, entre em contato com o Gerente de conta de sua organização. Ele pode organizar um encontro com consultores de implementação para ajudá-lo com suas necessidades.
