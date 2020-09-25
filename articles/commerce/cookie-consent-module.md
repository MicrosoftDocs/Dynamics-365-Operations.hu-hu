---
title: Cookie-hozzájárulás modul
description: Ez a témakör a cookie-hozzájárulás modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 842096c6e3045e434aced9642c86690e2ff7483a
ms.sourcegitcommit: 420b9e538f706178f8e1f2786e02f4f400bf2336
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/02/2020
ms.locfileid: "3761396"
---
# <a name="cookie-consent-module"></a>Cookie-hozzájárulás modul

[!include [banner](includes/banner.md)]

Ez a témakör a cookie-hozzájárulás modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A cookie-hozzájárulás modul felkéri a webhely felhasználóit, hogy explicit módon egyezzenek a bele a cookie-k engedélyezéséve bármely funkcióhoz vagy modulhoz, amely nyomon követi a böngésző-cookie-kat. A hozzájárulás megadása szükséges az első alkalommal, amikor a webhely felhasználója egy új böngésző-munkamenetben böngészik a webhelyen. A jóváhagyás megkapását követően az nyomon lesz követve, és nem lesz újra beleegyezés kérve a webhely felhasználójától. További információ:- [Cookie-k megfelelősége](cookie-compliance.md).

Ha nem érkezik meg a webhely felhasználójának cookie-hozzájárulása, akkor a program nem jeleníti meg a cookie-hozzájárulást igénylő funkciókat és modulokat a lapon. Például a pénztár modul, a közösségi megosztás modul és az előnyben részesített áruház funkció megköveteli a cookie-hozzájárulást, és nem fog megjelenni, ha a webhely felhasználójának hozzájárulása nem érkezik meg. 

A cookie-hozzájárulási modul konfigurálható a lap fejléctöredékében, hogy az a lap betöltésekor érvényesíthető legyen. A cookie-hozzájárulási modulnak tartalmaznia kell egy olyan egyértelmű üzenetet, amely tájékoztatja a webhely felhasználóját a webhely cookie-használatáról, és tartalmaznia kell egy hivatkozást webhely adatvédelmi lapjára.

A következő ábra a webhely fejlécében megjelenő cookie-hozzájárulási üzenetet jelenít meg, egy hivatkozással az adatvédelmi tájékoztató oldalra.
![Példa egy cookie-hozzájárulási modulra](./media/ecommerce-cookieconsent.png)

## <a name="cookie-consent-module-properties"></a>Cookie-hozzájárulási modul tulajdonságai

| Tulajdonság neve             | Érték                 | Leírás |
|---------------------------|-----------------------|-------------|
| Rich Text                  | Rich Text | Egy Rich Text értesítést határoz meg a webhely felhasználói számára arról, hogy a webhely böngésző cookie-kat használ, és a felhasználóknak el kell fogadniuk a cookie-k használatát a webhely teljes funkcionalitásához. |
| Hivatkozások | URL-cím | Egy vagy több hivatkozás hozzáadható a webhely adatvédelmi lapjára, amely leírja, hogy milyen típusú cookie-k vannak nyomon követve a webhelyen. |

## <a name="add-a-cookie-consent-module-to-site-pages"></a>Cookie-hozzájárulási modul hozzáadása a webhely oldalaihoz

A cookie-hozzájárulási modul több oldalra történő hatékony hozzáadásához hozzáadhatók egy megosztott lapfejléc-töredékhez is. Miután a fejléc-töredéket hozzáadta az összes webhelyoldalhoz, a program automatikusan megjeleníti a cookie-hozzájárulást, amikor a webhely felhasználója első alkalommal a webhely valamelyik lapjára navigál.

További tájékoztatás a fejléc-töredékekről és modulokról: [Fejléc modul](author-header-module.md).

## <a name="additional-resources"></a>További erőforrások

[Kezdőcsomag áttekintése](starter-kit-overview.md)

[Fejlécmodul](author-header-module.md) 

[Cookie-k megfelelősége](cookie-compliance.md)
