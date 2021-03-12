---
title: Compilação em campo
description: Entenda os pré-requisitos e as limitações da compilação de dados usando a compilação em campo.
translation-type: tm+mt
source-git-commit: beed7ffcc39b9b2628b1487b5e2eac42fa3a94d0
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 35%

---


# Compilação em campo

O Cross-Device Analytics fornece dois métodos distintos para compilar dados. Esse método depende de uma variável do Analytics, como uma [prop](/help/implement/vars/page-vars/prop.md) ou [eVar](/help/implement/vars/page-vars/evar.md), para conter um identificador de pessoa. Ele usa essa variável como base para vincular dispositivos.

## Pré-requisitos específicos da compilação em campo

Se você pretende implementar o Cross-Device Analytics usando a compilação em campo, as seguintes etapas são obrigatórias. Trabalhe com as equipes em sua organização e com seu Gerente de conta da Adobe para atender a todos os itens a seguir.

>[!IMPORTANT]
>
>O não cumprimento de todos os pré-requisitos pode gerar a incapacidade de ativar o Cross-Device Analytics ou resultados inadequados ao compilar os dados.

* Todos os pré-requisitos estão listados na [página de visão geral](overview.md).
* Sua implementação deve definir uma prop ou eVar que identifique exclusivamente um indivíduo sempre que possível, como quando um usuário faz logon ou abre um email. Esse requisito se aplica a todas as plataformas, incluindo aplicativos móveis, se usados. Comunique a variável de identificação desejada ao seu Gerente de conta quando provisionado para a compilação em campo.

## Limitações específicas da compilação em campo

* A compilação em campo funciona melhor em conjuntos de relatórios que têm uma alta taxa de identificação/autenticação do usuário.
* Embora props e eVars tenham regras para como caracteres em maiúsculas e minúsculas são tratados para fins de relatório, a compilação em campo não transforma a prop ou o eVar usado para compilação de qualquer maneira. A compilação em campo usa o valor no campo especificado, pois ele existe após as regras VISTA e as regras de pós-processamento. O processo de compilação diferencia maiúsculas de minúsculas. Por exemplo, se às vezes a palavra &quot;Bob&quot; aparecer na propriedade/eVar e, às vezes, a palavra &quot;BOB&quot; aparecer, eles serão tratados como duas pessoas separadas pelo processo de compilação.
* Como a compilação em campo diferencia maiúsculas de minúsculas, o Adobe recomenda revisar quaisquer regras VISTA ou regras de processamento que se aplicam à propriedade ou ao eVar usado para a compilação em campo. Eles precisam ser revistos para garantir que nenhuma dessas regras esteja introduzindo novas formas da mesma ID. Por exemplo, você deve garantir que nenhuma VISTA ou regra de processamento esteja introduzindo letras minúsculas na propriedade ou no eVar em apenas uma parte das ocorrências.
* A compilação em campo não suporta o uso de mais de uma prop ou eVar para fins de compilação. Por exemplo, se o eVar 12 contiver ID de login e o eVar 20 contiver ID de email, você deverá escolher uma delas.
* A compilação em campo não combina nem concatena campos (por exemplo, eVar10 + prop5).
* A prop ou eVar deve conter um único tipo de ID. Por exemplo, o prop ou eVar não deve conter uma combinação de IDs de logon e IDs de email.
* Se várias ocorrências ocorrerem com o mesmo carimbo de data e hora para o mesmo visitante, mas com valores diferentes na prop de identificação ou eVar, o CDA escolherá com base na ordem alfabética. Portanto, se o visitante A tiver duas ocorrências com o mesmo carimbo de data e hora e uma das ocorrências especificar Bob e a outra especificar Ann, o CDA escolherá Ann.


## Próximas etapas

Assim que sua organização atender a todos os requisitos e entender as limitações, você poderá iniciar a [Configuração do Cross-Device Analytics](setup.md).
