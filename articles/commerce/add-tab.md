---
title: Lapmodul
description: Ez a témakör a lapmodulokat tartalmazza, és bemutatja, hogyan lehet hozzáadni azokat a webhelyoldalakhoz Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.openlocfilehash: 91c79ca1b70a776352ef99d854397ada34c548e3
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276973"
---
# <a name="tab-module"></a>Lapmodul

[!include [banner](includes/banner.md)]

Ez a témakör a lapmodulokat tartalmazza, és bemutatja, hogyan lehet hozzáadni azokat a webhelyoldalakhoz Microsoft Dynamics 365 Commerce.

A lapmodulok olyan tárolószerű modulok, amelyek az oldalak adatainak lapokra rendszerezésére szolgálnak. Ezeket bármilyen oldalon fel lehet használni, ahol az információt a lapokon kell megjeleníteni.

Minden lapmodulon belül egy vagy több lapelem-modul is hozzáadható. Minden lapelem-modul egyetlen lapot jelent. Minden lapelem-modulhoz vagy több modul hozzáadható. Nincsenek korlátozások a lapelem-modulhoz adható modulok típusaira vonatkozóan.

A következő kép egy webhelyoldalon használt lapmodul egy példáját jeleníti meg. Ebben a példában a **Szállítás** lap van kiválasztva.

![Példa egy lapmodulra.](./media/ecommerce-tab.PNG)

## <a name="tab-module-properties"></a>Lapmodul tulajdonságai

| Tulajdonság neve | Értékek | Leírás |
|---------------|--------|-------------|
| Fejléc | Szöveg | Ez a tulajdonság a lapmodul opcionális szöveges fejlécét határozza meg. |
| Aktív lap indexe | Szám | Ez a tulajdonság azt a lapot határozza meg, amely az oldal betöltésekor alapértelmezés szerint aktív. Ha nincs megadva érték, akkor az első lapelem lesz alapértelmezés szerint aktív. |

## <a name="tab-item-module-properties"></a>Lapelem-modul tulajdonságai

| Tulajdonság neve | Értékek | Leírás |
|---------------|--------|-------------|
| Megszólítás | Szöveg | Ez a tulajdonság a lapmodul címszövegét határozza meg. |

## <a name="add-a-tab-module-to-a-page"></a>Lapmodul felvétele egy oldalra

A lapmodul felvételéhez egy oldalra, és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.

1. Használja a Fabrikam marketingsablont, (vagy bármilyen olyan sablont amelyen nincs korlátozás), egy új oldal létrehozásához amelynek neve **Üzletszabályzatok lap**.
1. Az Alapértelmezett **lap** főbejáratában **válassza** ki a három pontból (**...**), **majd válassza a Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **a** Tároló modult, majd válassza az **OK gombra.**
1. A tárolóhelyen **válassza** ki a három pontból (**...**), majd válassza a **Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **a Lap** modult, majd kattintson az **OK gombra**.
1. A lapmodul tulajdonságlapján válassza a ceruza szimbólum melletti **Címsor** elemet.
1. Adja meg a címsorszöveget (például **Irányelvek**) a **Címsor szövege** területen látható **Címsor** párbeszédpanelen. Majd kattintson az **OK** lehetőségre.
1. A tabulátorban **válassza** ki a három pontból (**...**), majd válassza a **Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki a Lap **cikkmodult**, majd válassza az **OK elemet**.
1. A lapelem modul elemének tulajdonságlapján, a **Cím** területen írja be a cím szövegét (például a **Kiszállítás**).
1. A Lap cikk-pontnál **válassza** ki a három pontból (**...**), majd válassza a **Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **a** Szövegblokk modult, majd válassza az **OK gombra.**
1. A szövegblokkmodul tulajdonságlapján adja meg a **Rich Text** alatt a szöveg bekezdését.
1. A **Lap** helyen adjon hozzá néhány további lapot, amelyeknek vannak címei. Minden egyes lapelem-modulban adja hozzá a tartalmat tartalmazó szövegblokk-modult.
1. Válassza a **Mentés** lehetőséget, majd az oldal előnézetének megtekintéséhez az **Előnézet** elemet. Az oldal egy lap modult jelenít meg, amelyben lapelem-modulok találhatók, amelyek tartalmazzák a hozzáadott tartalmat.
1. Válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

## <a name="additional-resources"></a>További erőforrások

[Modulkönyvtár – áttekintés](starter-kit-overview.md)

[Tárolómodul](add-container-module.md)

[Harmonikamodul](add-accordion.md)

[Szövegterület-modul](add-content-rich-block.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
