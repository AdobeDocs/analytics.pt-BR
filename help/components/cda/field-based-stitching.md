---
title: Compilação em campo
description: Entenda os pré-requisitos e as limitações da compilação de dados usando a compilação em campo.
exl-id: 81f2768c-53c2-40b4-8d3b-8d3b94cd7318
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '499'
ht-degree: 100%

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
* Embora props e eVars tenham regras para como caracteres em maiúsculas e minúsculas são tratados para fins de relatório, a compilação em campo não transforma a prop ou eVar usada para compilação de maneira alguma. A compilação em campo usa o valor no campo especificado, pois ele existe após as regras VISTA e as regras de pós-processamento. O processo de compilação diferencia maiúsculas de minúsculas. Por exemplo, se às vezes aparecer a palavra &quot;Bob&quot; na prop/eVar e, às vezes, a palavra &quot;BOB&quot;, elas serão tratadas como duas pessoas separadas pelo processo de compilação.
* Como a compilação em campo diferencia maiúsculas de minúsculas, a Adobe recomenda revisar quaisquer regras VISTA ou regras de processamento que se aplicam à prop ou eVar usada para a compilação em campo. Elas precisam ser revistas para garantir que nenhuma dessas regras introduza novas formas da mesma ID. Por exemplo, você deve garantir que nenhuma regra VISTA ou de processamento introduza letras minúsculas na prop ou eVar em apenas uma parte das ocorrências.
* A compilação em campo não aceita o uso de mais de uma prop ou eVar para fins de compilação. Por exemplo, se a eVar 12 contiver ID de logon e a eVar 20 contiver ID de email, você deverá escolher uma delas.
* A compilação em campo não combina nem concatena campos (por exemplo, eVar10 + prop5).
* A prop ou eVar deve conter um único tipo de ID. Por exemplo, a prop ou eVar não deve conter uma combinação de IDs de logon e IDs de email.
* Se houver várias ocorrências com o mesmo carimbo de data e hora para o mesmo visitante, mas com valores diferentes na prop ou eVar de compilação, o CDA escolherá por ordem alfabética. Portanto, se o visitante A tiver duas ocorrências com o mesmo carimbo de data e hora e uma das ocorrências especificar Bob e a outra especificar Ann, o CDA escolherá Ann.


## Próximas etapas

Assim que a sua organização atender a todos os requisitos e compreender as limitações, você poderá começar a [Configurar o Cross-Device Analytics](setup.md).
