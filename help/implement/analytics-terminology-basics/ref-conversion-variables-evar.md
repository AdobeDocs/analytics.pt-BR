---
description: A variável de conversão do Custom insight (ou eVar) é colocada no código da Adobe em páginas da Web selecionadas do site. Seu propósito principal é segmentar métricas de sucesso de conversão em relatórios de marketing personalizados.
keywords: Implementação do Analytics, eVar, variável de conversão, valor da eVar, conversão, evento bem-sucedido
seo-description: A variável de conversão do Custom insight (ou eVar) é colocada no código da Adobe em páginas da Web selecionadas do site. Seu propósito principal é segmentar métricas de sucesso de conversão em relatórios de marketing personalizados.
seo-title: Variáveis de conversão (eVars)
solution: Analytics
title: Variáveis de conversão (eVars)
topic: Desenvolvedor e implementação
uuid: 50071c1c-be00-4b3a-a7ee-5d129acf498b
translation-type: ht
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Variáveis de conversão (eVars)

A variável de conversão do Custom insight (ou eVar) é colocada no código da Adobe em páginas da Web selecionadas do site. Seu propósito principal é segmentar métricas de sucesso de conversão em relatórios de marketing personalizados.

O melhor uso das eVars é para medir causa e efeito, como:

* Quais campanhas internas influenciaram a receita
* Quais anúncios em banner resultam em um registro
* O número de vezes em que uma pesquisa interna foi usada antes de um pedido ser feito

>[!IMPORTANT]
>
>Ao implementar o Analytics, é importante saber quais e quantas eVars você usará. Você também deve saber como configurar as eVars no Admin Console. Para obter informações detalhadas sobre eVars, consulte [Variáveis de conversão (eVar)](https://marketing.adobe.com/resources/help/pt_BR/reference/conversion_var_admin.html) na documentação de Ajuda e referência do Analytics.

Uma eVar pode ter por base visitas e funcionar de forma semelhante aos cookies. Os valores passados para variáveis eVar seguem o usuário por um período predeterminado.

Quando uma eVar é definida como um valor para um visitante, a Adobe se lembra automaticamente desse valor até sua expiração. Quaisquer eventos bem-sucedidos que um visitante encontrar enquanto o valor da eVar está ativo são contados no valor da eVar.

>[!NOTE]
>
>Somente um valor único pode ser armazenado em uma eVar em uma solicitação de imagem. Se vários valores forem desejados no valor de uma eVar, recomendamos a implementação de [Listar variáveis](/help/implement/js-implementation/c-variables/page-variables.md) (list vars).

Para obter mais informações sobre variáveis, consulte:

* [Variáveis para implementação e relatórios do Analytics](../../implement/js-implementation/c-variables/sc-variables.md#concept_E10E43221A2740FAAF900B79CE1EC5FB) nesta ajuda
* [Variáveis - como são usadas nos relatórios](https://marketing.adobe.com/resources/help/pt_BR/reference/variable_definitions.html)
* [Variáveis de página](/help/implement/js-implementation/c-variables/page-variables.md)
* [Variável da campanha](/help/implement/js-implementation/c-variables/page-variables.md)
* [Variável products](/help/implement/js-implementation/c-variables/page-variables.md)
* [Variável de produtos](https://marketing.adobe.com/resources/help/pt_BR/mobile/android/products.html) na documentação do SDK móvel

