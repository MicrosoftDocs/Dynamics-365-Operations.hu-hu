---
title: Harmonikamodul
description: Ez a témakör a harmonikamodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
ms.date: 05/18/2022
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
ms.dyn365.ops.version: ''
ms.openlocfilehash: e17476d745da6f498b4f3ed90d55b0d13a0264b6
ms.sourcegitcommit: ccb39767bd3430c24f4653c26560bba2cd66553c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/19/2022
ms.locfileid: "8780689"
---
# <a name="accordion-module"></a>Harmonikamodul

[!include [banner](includes/banner.md)]

Ez a témakör a harmonikamodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.

A harmonikamodulok olyan tárolószerű modulok, amelyek a lapon szereplő információk vagy modulok rendszerezésére szolgálnak egy összecsukható fiókszerű képesség biztosításával. Egy harmonikamodul használható bármilyen oldalon.

Minden harmonikamodulon belül egy vagy több harmonika cikkmodul is hozzáadható. Minden harmonika elemmodul egy összecsukható fiókot képvisel. Minden harmonika elemmodulon belül egy vagy több modul is hozzáadható. Nincsenek korlátozások a harmonika modulhoz adható modulok típusaira vonatkozóan.

A következő kép egy olyan harmonika modult mutat be, amely az üzlet gyakran feltett kérdéseket tartalmazó lapja adatainak rendszerezéséhez használatos.

![Példa egy harmonikamodulra.](./media/ecommerce-accordion.PNG)

## <a name="accordion-module-properties"></a>Harmonikamodul tulajdonságai

| Tulajdonság neve | Értékek | Leírás |
|---------------|--------|-------------|
| Címsor | Szöveg | Ez a tulajdonság a harmonikamodul opcionális szöveges fejlécét határozza meg. |
| Az összes kibontása | **Igaz** vagy **Hamis** | Ha az érték **Igaz** értékre van állítva, akkor a kibontás/összecsukás funkció be van kapcsolva, így a harmonikamodul minden eleme kibontható és összecsukható lehet. |
| Interakció stílusa | **Független** vagy **Csak egy elem kibontása** | Ez a tulajdonság határozza meg a harmonikaelemek interakciójának stílusát. Ha az érték **Független**, akkor minden egyes harmonika kibontható és összecsukható egymástól függetlenül. Ha az érték **Csak egy elem kibontása** értékre van állítva , akkor egyszerre csak egy elem bontható ki. Az elemek kibontása esetén a program összecsukja a korábban kibontott elemeket. |

## <a name="accordion-item-module-properties"></a>Harmonikamodul elemtulajdonságai

| Tulajdonság neve | Értékek | Leírás |
|----------------|--------|-------------|
| Megszólítás | Szöveg | Ez a tulajdonság a harmonikamodul címszövegét határozza meg. A cím területének kiválasztásával a felhasználók kibonthatják vagy összecsukhatják az adott részt. |
| Kibontás alapértelmezetten | **Igaz** vagy **Hamis** | Ha az érték **Igaz** értékre van állítva, akkor a rendszer alapértelmezés szerint kibontja a harmonika elemet a lap betöltésekor. |

## <a name="add-an-accordion-module-to-a-faq-page"></a>Harmonikamodul felvétele egy GYIK oldalra

Harmonikamodul felvételéhez egy GYIK oldalra és a tulajdonságainak beállításához az webhelykészítőben hajtsa végre az alábbi lépéseket.

1. Nyissa meg a **Lapok**, és használja a Fabrikam marketingsablont, (vagy bármilyen olyan sablont amelyen nincs korlátozás), egy új oldal létrehozásához amelynek neve **Üzlet GYIK**.
1. Az Alapértelmezett **lap** főbejáratában **válassza** ki a három pontból (**...**), **majd válassza a Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **a** Tároló modult, majd válassza az **OK gombra.**
1. A tárolóhelyen **válassza** ki a három pontból (**...**), majd válassza a **Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **a Modulmodult**, majd válassza az **OK gombra.**
1. A harmonikamodul tulajdonságlapján válassza a ceruza szimbólum melletti **Címsor** elemet.
1. A **Címsor** párbeszédpaneleben **Címsor szöveg** alatt írja be, hogy **Gyakran ismételt kérdések**. Majd kattintson az **OK** lehetőségre.
1. A harmonika modul tulajdonságlapján jelölje be az **Összes kibontása** jelölőnégyzetet, majd az **Interakció stílusa** mezőben válassza a **Független** lehetőséget.
1. Válassza ki **a rekedt** három pontból (**...**), majd válassza a **Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **a Elemelem** modult, majd válassza **az OK elemet**.
1. A harmonika modul elemének tulajdonságlapján, a **Cím** területen írja be a cím szövegét (például a **Hogyan működik a visszaküldés?**).
1. A Modulelem-pont **pontnál** válassza ki a három pontból (**...**), majd válassza a **Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **a** Szövegblokk modult, majd válassza az **OK gombra.**
1. A szövegblokk modul tulajdonság panelén írja be a szöveg bekezdését (például **A visszaküldéseket az ügyfélszolgálaton keresztül lehet intézni. A visszaküldéshez hívja az 1-800-FABRIKAM telefonszámot. A termékre 30 napos visszaküldési irányelv tartozik. A visszaküldést ebben az időkereten belül kell kezdeményezni.**).
1. A **Harmonika** bővítőhelyen adjon hozzá néhány harmonikaelem modult. Minden egyes harmonika elemmodulban adja hozzá a tartalmat tartalmazó szövegblokk-modult.
1. Válassza a **Mentés** lehetőséget, majd az oldal előnézetének megtekintéséhez az **Előnézet** elemet. A lap egy harmonikamodult jelenít meg, amely a hozzáadott tartalmát tartalmazta.
1. Válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

## <a name="additional-resources"></a>További erőforrások

[Modulkönyvtár – áttekintés](starter-kit-overview.md)

[Tárolómodul](add-container-module.md)

[Lapmodul](add-tab.md)

[Szövegterület-modul](add-content-rich-block.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
