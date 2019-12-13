---
title: Forgótármodul
description: Ez a témakör a forgótármodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
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
ms.dyn365.ops.version: ''
ms.openlocfilehash: c2c5adc8ab2e0330f7b07e5153fd8332ab0203e5
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785237"
---
# <a name="carousel-module"></a>Forgótármodul

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Ez a témakör a forgótármodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A forgótármodul több, a felhasználók által böngészhető promóciós elem forgótárban való elhelyezésére használható. Ez egy speciális tárolómodul, amely a többi modult tárolja. Például egy kiskereskedő a kezdőlapon a forgótármodul segítségével több új terméket vagy promóciót mutathat be.

A forgótármodulon belül főkép- és funkciómodulokat adhat hozzá. A forgótármodul tulajdonságai határozzák meg a modulok megjelenítésének módját.

## <a name="examples-of-carousel-modules-in-e-commerce"></a>Példák az e-Commerce forgótármoduljaira

- A több promóciós modult tartalmazó forgótár használható a kezdőlapon.
- A több promóciós modult tartalmazó forgótár használható a termék részletes lapján.
- A körhinta bármilyen marketinglapon több promóció vagy termék népszerűsítésére.

## <a name="carousel-module-properties"></a>Forgótármodul tulajdonságai

| Tulajdonság neve             | Érték                                | Leírás |
|---------------------------|--------------------------------------|-------------|
| Automatikus lejátszás                  | **Igaz** vagy **Hamis**                | Ha az érték **Igaz**, akkor a forgótár elemei közötti váltás automatikus. Ha az érték **Hamis**, csak akkor történik váltás, ha a vevő a billentyűzet vagy az egér segítségével az egyik elemről a másikra vált. |
| Áttűnési időköz | Egy érték másodpercben                   | Az elemek közötti váltások intervalluma. |
| Áttűnési animáció      | **Csúszás** vagy **Elhalványulás**                | Az áttűnési effektus. |
| Szélesség                     | **Tárolóhoz igazított** vagy **Képernyő kitöltése** | Ha az érték **Tárolóhoz igazított**, akkor a forgótárban lévő elemek a forgótár szélességére korlátozódnak. Ha **Képernyő kitöltése** értékre van beállítva, akkor az elemek mérete nem korlátozódik a forgótár szélességére, hanem teljes képernyős üzemmódban jelenhetnek meg. A kívánt elrendezés elérése érdekében módosíthatja az értéket. |

## <a name="add-a-carousel-module-to-a-page"></a>Forgótármodul felvétele egy oldalra

A forgótármodul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.

1. Hozzon létre egy **forgótársablon** nevű oldalsablont.
1. Az alapértelmezett lap **Fő** helyén adjon hozzá egy forgótármodult.
1. Vegyen fel egy főképmodult a forgótármodulba.
1. Vegyen fel egy funkciómodult a forgótármodulba.
1. Adja be a sablont és tegye közzé. 
1. A most létrehozott forgótársablon használatával hozzon létre egy **forgótárlap** nevű lapot.
1. Az új lap **Fő** helyén adjon hozzá egy forgótármodult.
1. Állítsa be a forgótármodul **Szélesség** tulajdonságát **Képernyő kitöltése** értékre. 
1. Állítsa be az **Áttűnési animáció** tulajdonságot **Csúszás** értékre.
1. Vegyen fel egy főképmodult a forgótármodulba.
1. A főképmodulban adjon hozzá egy képet és egy címsort, majd válassza a **Mentés** parancsot.
1. Vegyen fel egy funkciómodult a forgótármodulba.
1. A funkciómodulban adjon hozzá egy képet, egy címsort és egy szövegbekezdést.
1. Mentse a lapot, és tekintse meg az előnézetét. A lapnak egy olyan forgótárat kell megjelenítenie, amely két modult tartalmaz (egy főképmodul és egy funkciómodul). A kívánt hatás elérése érdekében módosíthatja a forgótár-, a főkép- és a funkciómodulok további tulajdonságait.
1. Adja be a lapot, és tegye közzé.

## <a name="additional-resources"></a>További erőforrások

[Kezdő csomag áttekintése](starter-kit-overview.md)

[Figyelmeztetési modul](add-alert.md)

[Tartalomgazdag blokkmodul](add-content-rich-block.md)

[Tartalomelhelyezési modul](add-content-placement-modules.md)

[Funkciómodul](add-feature-module.md)

[Főképmodul](add-hero-module.md)

[Videólejátszó modul](add-video-player.md)
