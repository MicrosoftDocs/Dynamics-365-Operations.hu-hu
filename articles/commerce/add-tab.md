---
title: Lapmodul
description: Ez a témakör a lapmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
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
ms.openlocfilehash: 42c3cd99897627dbcdbdec91cfdb03d5743f7388
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4980182"
---
# <a name="tab-module"></a>Lapmodul

[!include [banner](includes/banner.md)]

Ez a témakör a lapmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A lapmodulok olyan tárolószerű modulok, amelyek az oldalak adatainak lapokra rendszerezésére szolgálnak. Ezeket bármilyen oldalon fel lehet használni, ahol az információt a lapokon kell megjeleníteni.

Minden lapmodulon belül egy vagy több lapelem-modul is hozzáadható. Minden lapelem-modul egyetlen lapot jelent. Minden lapelem-modulhoz vagy több modul hozzáadható. Nincsenek korlátozások a lapelem-modulhoz adható modulok típusaira vonatkozóan.

A következő kép egy webhelyoldalon használt lapmodul egy példáját jeleníti meg. Ebben a példában a **Szállítás** lap van kiválasztva.

![Példa egy lapmodulra](./media/ecommerce-tab.PNG)

## <a name="tab-module-properties"></a>Lapmodul tulajdonságai

| Tulajdonság neve | Értékek | Leírás |
|---------------|--------|-------------|
| Címsor | Szöveg | Ez a tulajdonság a lapmodul opcionális szöveges fejlécét határozza meg. |
| Aktív lap indexe | Szám | Ez a tulajdonság azt a lapot határozza meg, amely az oldal betöltésekor alapértelmezés szerint aktív. Ha nincs megadva érték, akkor az első lapelem lesz alapértelmezés szerint aktív. |

## <a name="tab-item-module-properties"></a>Lapelem-modul tulajdonságai

| Tulajdonság neve | Értékek | Leírás |
|---------------|--------|-------------|
| Megszólítás | Szöveg | Ez a tulajdonság a lapmodul címszövegét határozza meg. |

## <a name="add-a-tab-module-to-a-page"></a>Lapmodul felvétele egy oldalra

A lapmodul felvételéhez egy oldalra, és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.

1. Használja a Fabrikam marketingsablont, (vagy bármilyen olyan sablont amelyen nincs korlátozás), egy új oldal létrehozásához amelynek neve **Üzletszabályzatok lap**.
1. Az **Alapértelmezett lap** **Fő** helyén válassza ki a három pont (**…**) gombot, majd válassza a **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki az **Tároló** modult, majd kattintson az **OK** gombra.
1. Az **Tároló** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki a **Lap** modult, majd kattintson az **OK** gombra.
1. A lapmodul tulajdonságlapján válassza a ceruza szimbólum melletti **Címsor** elemet.
1. Adja meg a címsorszöveget (például **Irányelvek**) a **Címsor szövege** területen látható **Címsor** párbeszédpanelen. Majd kattintson az **OK** lehetőségre.
1. A **Lap** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki a **Lapelem** modult, majd kattintson az **OK** gombra.
1. A lapelem modul elemének tulajdonságlapján, a **Cím** területen írja be a cím szövegét (például a **Kiszállítás**).
1. A **Lapelem** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki az **Szövegblokk** modult, majd kattintson az **OK** gombra.
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