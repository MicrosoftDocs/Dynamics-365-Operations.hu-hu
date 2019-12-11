---
title: Tartalomelhelyezési modul
description: Ez a témakör a tartalomelhelyezési és tartalomelhelyezési elem modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 1b64e930628c969334ff6e643ba23b77445e6e4c
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785300"
---
# <a name="content-placement-module"></a>Tartalomelhelyezési modul

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Ez a témakör a tartalomelhelyezési és tartalomelhelyezési elem modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A tartalomelhelyezési modul egy speciális tároló, amelybe a többi modult egy konkrét elrendezésben helyezhető el. A tartalomelhelyezési modulok a következő típusú modulokat támogatják gyermekmodulként: tartalomelhelyezési elem, a fiók üdvözlőképernyő eleme, fiók megrendelési eleme, fiók kívánságlista eleme és fiók profileleme.

A tartalomelhelyezési modulok az általuk támogatott gyermekmodulokból származtatják adataikat. Ezért a tartalomelhelyezési modulok különböző módokon használhatók a hozzájuk adott moduloktól függően.

A tartalomelhelyezési elem moduljai képekkel és szöveggel mutatják be a promóciókat és termékjellemzőket. Például egy tartalomelhelyezési modul használható a kezdőlapon az üzletszabályzat és a szállítási információk megjelenítésére. A tartalomelhelyezési elem moduljait a tartalomkezelő rendszer (CMS) adatai vezérlik, és bármilyen lapra elhelyezhetők. Azonban csak a tartalomelhelyezési modulban használhatók.

## <a name="examples-of-content-placement-modules-in-e-commerce"></a>Példák az e-Commerce tartalomelhelyezési moduljaira

* A tartalomelhelyezési elem modulokat tartalmazó tartalomelhelyezési modulok a kezdőlapon vagy a marketinglapokon a termék jellemzőinek, a promócióknak, az üzletszabályzatoknak, a szállítási információknak és egyéb információknak a képekkel és szöveggel történő bemutatására használhatók.
* A tartalomelhelyezési elemeket tartalmazó tartalomelhelyezési modulok a termékek részletes lapjain a termékjellemzők megjelenítésére használhatók.
* A fiók üdvözlőképernyő elemét vagy fiók megrendelési elemét tartalmazó tartalomelhelyezési modulok a fiókkezelési lapokon használhatók.

## <a name="content-placement-module-properties"></a>Tartalomelhelyezési modul tulajdonságai

| Tulajdonság neve | Érték | Leírás |
|---------------|-------|-------------|
| Szélesség         | **Tárolóhoz igazított** vagy **Képernyő kitöltése** | Ha a **Tárolóhoz igazított** értékre van beállítva, akkor a tartalomelhelyezési modulon belüli elemek mérete a tartalomelhelyezési modul szélességére korlátozódik. Ha **Képernyő kitöltése** értékre van beállítva, akkor az elemek mérete nem korlátozódik a tartalomelhelyezési modul szélességére, hanem teljes képernyős üzemmódban jelenhetnek meg. |

## <a name="content-placement-item-module-properties"></a>Tartalomelhelyezési elem modul tulajdonságai

| Tulajdonság neve | Érték | Leírás |
|---------------|-------|-------------|
| Címsor       | Fejléc szövege és fejléc címkéi (**H1**, **H2**, **H3**, **H4**, **H5** vagy **H6**) | Minden a tartalomelhelyezési elem modul rendelkezhet fejléccel. A **Fejléc** tulajdonság támogatja a fejléccímkéket. Alapértelmezés szerint a **H2** fejléccímke van használatban, de a fejléccímke az akadálymentességi követelményeknek megfelelően módosítható. |
| Bekezdés     | Bekezdés szövege | A tartalomelhelyezési elem modulok támogatják a multimédiás szöveg formátumú bekezdésszövegeket. A program néhány alapvető multimédiás szöveg képességet támogat, mint például a félkövér, az aláhúzott és a dőlt szöveg, valamint a hiperhivatkozások. Ezeket a képességeket a modulra alkalmazott laptéma felülbírálhatja. |
| Kép         | Képfájl | A szöveghez kép társítható. |
| Hivatkozás          | Hivatkozás URL-címe és hivatkozás szövege | Hivatkozás adható a szöveghez, hogy a felhasználókat egy adott oldalra irányítsa át. |
| Csempeméret     | **1** és **12** közötti szám | Ez a tulajdonság minden tartalomelhelyezési elemhez meghatározza a helyek számát, amelyet az elemnek ki kell töltenie a tartalomelhelyezési modulban. A tartalomelhelyezési modul maximális mérete 12 hely. Ha a tartalomelhelyezési modul első *n* elemének mérete meghaladja a 12 helyet, akkor a program a következő sorba töri az elemeket. |

## <a name="add-a-content-placement-module-that-contains-a-content-placement-item-module-to-a-page"></a>Tartalomelhelyezési elem modult tartalmazó tartalomelhelyezési modul hozzáadása egy laphoz

Ha tartalomelhelyezési elem modult tartalmazó tartalomelhelyezési modult kíván hozzáadni egy új laphoz, és be szeretné állítani a szükséges tulajdonságokat, akkor kövesse az alábbi lépéseket.

1. Hozzon létre egy **tartalomelhelyezési sablon** nevű sablont.
1. Az alapértelmezett lap **Fő** helyén adjon hozzá egy tartalomelhelyezési modult.
1. A tartalomelhelyezési modulban adjon hozzá egy tartalomelhelyezési elem modult.
1. Adja be a sablont és tegye közzé.
1. A most létrehozott tartalomelhelyezési sablon használatával hozzon létre egy **Tartalomelhelyezési lap** nevű lapot.
1. Az új lap **Fő** helyén adjon hozzá egy tartalomelhelyezési modult.
1. A tartalomelhelyezési modulban adjon hozzá egy tartalomelhelyezési elem modult.
1. A tartalomelhelyezési elem modul tulajdonságlapján válasszon ki egy képet, adjon hozzá egy fejlécet, adjon hozzá egy bekezdést, adjon hozzá egy hivatkozást, állítsa be a hivatkozás URL-címét, és állítsa a csempeméretet **6**értékre.
1. Ismételje meg a 7–8. lépést egy olyan tartalomelhelyezési elem modul hozzáadásához, amely azonos csempemérettel rendelkezik.
1. Mentse a lapot, és tekintse meg az előnézetét. Két egymás mellett megjelenő tartalomelhelyezési elemet kell látnia. Minden egyes tartalomelhelyezési elem modulhoz beállíthatja a **Csempe mérete** tulajdonságát, vagy hozzáadhat további modulokat a kívánt elrendezés elérése érdekében.
1. Adja be a lapot, és tegye közzé.

## <a name="additional-resources"></a>További erőforrások

[Kezdő csomag áttekintése](starter-kit-overview.md)

[Figyelmeztetési modul](add-alert.md)

[Forgótármodul](add-carousel.md)

[Tartalomgazdag blokkmodul](add-content-rich-block.md)

[Funkciómodul](add-feature-module.md)

[Főképmodul](add-hero-module.md)

[Videólejátszó modul](add-video-player.md)
