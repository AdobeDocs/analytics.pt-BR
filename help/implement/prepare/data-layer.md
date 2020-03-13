---
title: Criar uma camada de dados
description: Saiba o que é uma camada de dados na implementação do Analytics e como ela pode ser usada para mapear variáveis no Adobe Analytics.
translation-type: tm+mt
source-git-commit: 283fcd5832abe4c09caa332c2ebc3a22029e6707

---


# Criar uma camada de dados

Uma camada de dados é uma estrutura de objetos JavaScript no site que contém todos os valores variáveis usados na implementação. Permite maior controle e manutenção mais fácil na implementação.

## Pré-requisitos

[Criar um documento](solution-design.md) de design de solução - É importante que sua organização se alinhe aos requisitos de rastreamento. Certifique-se de estar preparado com um documento de design de solução antes de se aproximar das equipes de desenvolvimento em sua organização.

## Fluxo de trabalho

A implementação do Adobe Analytics usando uma camada de dados geralmente segue estas etapas:

1. **Trabalhe com a equipe de desenvolvimento do site para implementar uma camada** de dados: Sua equipe de desenvolvimento do site é responsável principalmente por garantir que o objeto da camada de dados seja preenchido com valores corretos. Revise esta página com a equipe de desenvolvimento do site para garantir que as expectativas estejam alinhadas entre as equipes.
   > [!NOTE] As especificações recomendadas da camada de dados da Adobe são opcionais. Se você já tiver uma camada de dados, ou optar por não seguir as especificações da Adobe, certifique-se de que sua organização se alinha em qual especificação seguir.
2. **Valide sua camada de dados usando um console** do navegador: Depois que uma camada de dados é criada, você pode validar se ela está funcionando usando qualquer console de desenvolvedor do navegador. Você pode abrir o console do desenvolvedor na maioria dos navegadores usando a `F12` tecla. Um exemplo de valor de variável seria `digitalData.page.pageInfo.pageID`.
3. **Use o Adobe Experience Platform Launch para mapear objetos de camada de dados para Iniciar elementos** de dados: Crie elementos de dados no Launch e mapeie-os para os atributos JavaScript descritos em sua camada de dados.
4. **Use a extensão do Adobe Analytics em Iniciar para mapear elementos de dados para variáveis** do Analytics: Após o documento de design da solução, atribua cada elemento de dados à variável adequada do Analytics.

## Especificações

A Adobe recomenda seguir a Camada [de Dados Digitais da Experiência do](https://www.w3.org/2013/12/ceddl-201312.pdf) Cliente descrita pelo Grupo [da Comunidade de Dados Digitais da Experiência do](https://www.w3.org/community/custexpdata/)Cliente. Use as seções a seguir para entender como os elementos da camada de dados interagem com o Adobe Analytics.

O objeto de camada de dados de abrangência recomendado é `digitalData`. O exemplo a seguir lista um objeto JSON de camada de dados um pouco abrangente com valores de exemplo:

```js
digitalData = {
    pageInstanceID: "Example page - production",
    page: {
        pageInfo: {
            pageID: "5093",
            pageName: "Example page",
            destinationURL: "https://example.com/index.html",
            referringURL: "https://example.com/referrer.html",
            sysEnv: "desktop",
            variant: "2",
            version: "1.14",
            breadCrumbs: ["Home","Example group","Example page"],
            author: "J Smith",
            issueDate: "Example date",
            effectiveDate: "Example date",
            expiryData: "Example date",
            language: "en-US",
            geoRegion: "US",
            industryCodes: "Example industry codes",
            publisher: "Example publisher"
        },
        category: {
            primaryCategory: "Example page category",
            subCategory1: "Sub-category example"
        },
        attributes: {
            country: "US",
            language: "en-US"
        }
    },
    product1: {
        productInfo: {
            productID: "4859",
            productName: "Example product",
            description: "Example description",
            productURL: "https://example.com/product.html",
            productImage: "https://example.com/product_image.png",
            productThumbnail: "https://example.com/product_thumbnail.png",
            manufacturer: "Example manufacturer",
            size: "Product size"
        },
        category: {
            primaryCategory: "Example product category",
            subCategory: "Example sub-category"
        }
    },
    cart: {
        cartID: "934856",
        price: {
            basePrice: 200.00,
            voucherCode: "EXAMPLEVOUCHER1",
            voucherDiscount: 0.50,
            currency: "USD",
            taxRate: 0.20,
            shipping: 5.00,
            shippingMethod: "UPS",
            priceWithTax: 120,
            cartTotal: 125
        }
    },
    transaction: {
        transactionID: "694025",
        profile: {
            profileInfo: {
                profileID: "exampleprofile",
                userName: "exampleusername",
                email: "user@example.com"
            },
            address: {
                line1: "123 Vague Street",
                line2: "Apt 1",
                city: "Austin",
                stateProvince: "TX",
                postalCode: "78610",
                country: "USA"
            },
            shippingAddress: {
                line1: "123 Vague Street",
                line2: "Apt 1",
                city: "Austin",
                stateProvince: "TX",
                postalCode: "78610",
                country: "USA"
            }
        }
    },
    event1: {
        category: {
            primaryCategory: "Example event category",
            subCategory: "Example sub-category"
        }
    },
    component1: {
        componentInfo: {
            componentID: "4921",
            componentName: "Example component"
        },
        category: {
            primaryCategory: "Example event category",
            subCategory: "Example sub-category"
        }
    },
    user1: {
        segment: "Premium membership",
        profile1: {
            profileInfo: {
                profileID: "exampleprofile",
                userName: "exampleusername",
                email: "user@example.com",
                language: "en-US",
                returningStatus: "New"
            },
            social: {
                facebook: "examplefacebookid",
                twitter: "exampletwitterhandle"
            }
        }
    },
    privacy: {
        accessCategories1: {
            categoryName: "Default",
            domains: "adobedtm.com"
        }
    },
    version: "1.0"
}
```

Use o relatório de Camada [de Dados Digitais da Experiência do](https://www.w3.org/2013/12/ceddl-201312.pdf) Cliente para obter detalhes sobre cada objeto e subobjeto. Nem todos os sites usam todos os objetos; por exemplo, se você hospeda um site de notícias, é improvável que tenha sido usado para o `digitalData.product` objeto.

As camadas de dados são extensíveis; se você tiver requisitos específicos da sua organização, poderá incluir objetos na camada de dados para acomodar essas necessidades.

## Configuração de valores da camada de dados

As camadas de dados normalmente geram no lado do servidor, referenciando os mesmos objetos usados para criar o conteúdo do site. Estabeleça a camada de dados do site com base nos requisitos de rastreamento definidos no documento [de design de](solution-design.md)solução da sua organização.

## Próximas etapas

[Mapear objetos de camada de dados para elementos](../launch/layer-to-elements.md)de dados: Use a camada de dados do site no Adobe Experience Platform Launch.
