---
title: Cookie-hozzájárulás modul
description: Ez a témakör a cookie-hozzájárulás modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 43f18a0963d84d486c8077bde1dad50fdd4fe85beb95dc8b22ae2f3ee724ba0f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6750738"
---
# <a name="cookie-consent-module"></a>Cookie-hozzájárulási modul

[!include [banner](includes/banner.md)]

Ez a témakör a cookie-hozzájárulás modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.

A cookie-hozzájárulás modul felkéri a webhely felhasználóit, hogy explicit módon egyezzenek a bele a cookie-k engedélyezéséve bármely funkcióhoz vagy modulhoz, amely nyomon követi a böngésző-cookie-kat. A hozzájárulás megadása szükséges az első alkalommal, amikor a webhely felhasználója egy új böngésző-munkamenetben böngészik a webhelyen. A jóváhagyás megkapását követően az nyomon lesz követve, és nem lesz újra beleegyezés kérve a webhely felhasználójától. További információ:- [Cookie-k megfelelősége](cookie-compliance.md).

Ha nem érkezik meg a webhely felhasználójának cookie-hozzájárulása, akkor a program nem jeleníti meg a cookie-hozzájárulást igénylő funkciókat és modulokat a lapon. Például a pénztár modul, a közösségi megosztás modul és az előnyben részesített áruház funkció megköveteli a cookie-hozzájárulást, és nem fog megjelenni, ha a webhely felhasználójának hozzájárulása nem érkezik meg. 

A cookie-hozzájárulási modul konfigurálható a lap fejléctöredékében, hogy az a lap betöltésekor érvényesíthető legyen. A cookie-hozzájárulási modulnak tartalmaznia kell egy olyan egyértelmű üzenetet, amely tájékoztatja a webhely felhasználóját a webhely cookie-használatáról, és tartalmaznia kell egy hivatkozást webhely adatvédelmi lapjára.

A következő ábra a webhely fejlécében megjelenő cookie-hozzájárulási üzenetet jelenít meg, egy hivatkozással az adatvédelmi tájékoztató oldalra.
![Példa egy cookie-hozzájárulási modulra.](./media/ecommerce-cookieconsent.png)

## <a name="cookie-consent-module-properties"></a>Cookie-hozzájárulási modul tulajdonságai

| Tulajdonság neve             | Érték                 | Leírás |
|---------------------------|-----------------------|-------------|
| Rich Text                  | Rich Text | Egy Rich Text értesítést határoz meg a webhely felhasználói számára arról, hogy a webhely böngésző cookie-kat használ, és a felhasználóknak el kell fogadniuk a cookie-k használatát a webhely teljes funkcionalitásához. |
| Hivatkozások | URL-cím | Egy vagy több hivatkozás hozzáadható a webhely adatvédelmi lapjára, amely leírja, hogy milyen típusú cookie-k vannak nyomon követve a webhelyen. |

## <a name="add-a-cookie-consent-module-to-site-pages"></a>Cookie-hozzájárulási modul hozzáadása a webhely oldalaihoz

A cookie-hozzájárulási modul több oldalra történő hatékony hozzáadásához hozzáadhatók egy megosztott lapfejléc-töredékhez is. Miután a fejléc-töredéket hozzáadta az összes webhelyoldalhoz, a program automatikusan megjeleníti a cookie-hozzájárulást, amikor a webhely felhasználója első alkalommal a webhely valamelyik lapjára navigál.

További tájékoztatás a fejléc-töredékekről és modulokról: [Fejléc modul](author-header-module.md).

## <a name="additional-resources"></a>További erőforrások

[Modulkönyvtár – áttekintés](starter-kit-overview.md)

[Fejlécmodul](author-header-module.md) 

[Cookie-k megfelelősége](cookie-compliance.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]