---
title: Parancsfájl hozzáadása a webhely oldalaihoz a telemetria támogatásához
description: Ez a témakör azt ismerteti, hogyan lehet ügyféloldali parancsfájlkódot hozzáadni a webhelyoldalakhoz, hogy támogassák az ügyféloldali parancsfájlok gyűjteményét.
author: bicyclingfool
ms.date: 09/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: a0a5103d239c7f93ad6888a2eaf56d1cac32bd58
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282272"
---
# <a name="add-script-code-to-site-pages-to-support-telemetry"></a>Parancsfájl hozzáadása a webhely oldalaihoz a telemetria támogatásához

[!include [banner](includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet ügyféloldali parancsfájlkódot hozzáadni a webhelyoldalakhoz, hogy támogassák az ügyféloldali parancsfájlok gyűjteményét.

A webanalitika fontos eszköz, ha meg szeretné tudni, hogyan lépnek interakcióba a vevők a webhellyel, és amelyek alapján a felhasználói élmény maximális konverzió érdekében történő optimalizálására szolgáló döntéseket hozhat. Számos webes elemzési csomag érhető el, amely segít elérni ezeket a célokat, például a Google Analytics, a Clicky, a Moz Analytics és a KISSMetrics. A legtöbb webanalitikai csomag megköveteli, hogy ügyféloldali parancsfájlt adjon meg a HTML **\<head\>**  elemében a weboldala minden oldalán.

> [!NOTE]
> Az ebben a cikkben található útmutatás olyan egyéni ügyféloldali Microsoft Dynamics 365 Commerce funkciókra is vonatkozik, amelyek nem natív módon szolgáltatásokat nyújtanak.

## <a name="create-a-reusable-fragment-for-your-script-code"></a>Újra felhasználható töredék létrehozása a parancsfájl kódjához

A töredékek lehetővé teszik a belső és a külső parancsfájlkódok használatát a webhely összes lapján, függetlenül attól, hogy milyen sablont használnak.

### <a name="create-a-reusable-fragment-for-your-inline-script-code"></a>Újra felhasználható töredék létrehozása a szövegközi parancsfájl kódjához

A webhelykészítőben a szövegközi parancsfájlkódhoz tartozó újrahasználható töredék létrehozásához kövesse az alábbi lépéseket.

1. Lépjen a **Töredékek** pontra, majd válassza az **Új** lehetőséget.
1. Az **Új töredék** párbeszédpanelen válassza ki a **Szövegközi parancsfájl** lehetőséget.
1. A **Töredék neve** pontban adja meg a töredék nevét, majd válassza ki az **OK** lehetőséget.
1. Válassza ki az **alapértelmezett szövegközi parancsfájl** modult a létrehozott töredék alatt.
1. A jobb oldali ablaktáblában a **Szövegközi parancsfájl** területen adja meg a kliensoldali parancsfájlt. Ezt követően konfigurálja a szükséges egyéb beállításokat.
1. Válassza a **Mentés** parancsot, majd válassza a **Szerkesztés befejezése** elemet.
1. Válassza a **Közzététel** lehetőséget.

### <a name="create-a-reusable-fragment-for-your-external-script-code"></a>Újra felhasználható töredék létrehozása a külső parancsfájl kódjához

A webhelykészítőben a külső parancsfájlkódhoz tartozó újrahasználható töredék létrehozásához kövesse az alábbi lépéseket.

1. Lépjen a **Töredékek** pontra, majd válassza az **Új** lehetőséget.
1. Az **Új töredék** párbeszédpanelen válassza ki a **Külső parancsfájl** lehetőséget.
1. A **Töredék neve** pontban adja meg a töredék nevét, majd válassza ki az **OK** lehetőséget.
1. Válassza ki az **alapértelmezett külső parancsfájl** modult a létrehozott töredék alatt.
1. A jobb oldali ablaktáblában a **Parancsfájl forrása** területen adja meg a külső parancsfájlhoz tartozó külső vagy kapcsolódó URL-címet. Ezt követően konfigurálja a szükséges egyéb beállításokat.
1. Válassza a **Mentés** parancsot, majd válassza a **Szerkesztés befejezése** elemet.
1. Válassza a **Közzététel** lehetőséget.

> [!NOTE]
> Ha a webhelyhez engedélyezve van a tartalmi biztonsági irányelv (CSP), győződjön meg arról, hogy a Commerce webhelykészítőben a **script-src** CSP direktívához minden külső URL-cím hozzá van-e rendelve. További információ: [Tartalomra vonatkozó biztonsági irányelv (CSP) kezelése](manage-csp.md).

## <a name="add-a-fragment-that-includes-script-code-to-a-template"></a>Parancsfájlkódot tartalmazó töredék hozzáadása sablonhoz

A webhelykészítőben egy sablonhoz egy parancsfájlkódot tartalmazó töredék hozzáadásához kövesse az alábbi lépéseket.

1. Nyissa mega **Sablonok** pontot, majd nyissa meg azon oldalakhoz tartozó sablont, amelyhez hozzá szeretné adni a parancsfájlkódot.
1. A bal oldali panelen bontsa ki a sablon hierarchiáját a **HTML-fejléc** helyének megjelenítéséhez.
1. A **HTML-fejléc** helyben válassza a három pont (**…**) gombot, majd válassza a **Töredék hozzáadása** elemet.
1. Válassza ki a parancsfájl kódjához létrehozott töredéket.
1. Válassza a **Mentés** parancsot, majd válassza a **Szerkesztés befejezése** elemet.
1. Válassza a **Közzététel** lehetőséget.

## <a name="add-an-external-script-or-inline-script-directly-to-a-template"></a>Külső parancsfájl vagy szövegközi parancsfájl hozzáadása sablonhoz közvetlenül

Ha azt szeretné, hogy egy szövegközi vagy külső parancsfájlt közvetlenül egyetlen sablon által vezérelt oldalak csoportjába szúrjunk be, akkor előbb nem kell létrehoznia a töredéket.

### <a name="add-an-inline-script-directly-to-a-template"></a>Szövegközi parancsfájl hozzáadása sablonhoz közvetlenül

Ha egy szövegközi parancsfájlt közvetlenül egy sablonhoz szeretne hozzáadni a webhelykészítőben, hajtsa végre az alábbi lépéseket.

1. Nyissa mega **Sablonok** pontot, majd nyissa meg azon oldalakhoz tartozó sablont, amelyhez hozzá szeretné adni a parancsfájlkódot.
1. A bal oldali panelen bontsa ki a sablon hierarchiáját a **HTML-fejléc** helyének megjelenítéséhez.
1. A **HTML-fejléc** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédablakban válassza a **Szövegközi parancsfájl** lehetőséget.
1. A jobb oldali ablaktáblában a **Szövegközi parancsfájl** területen adja meg a kliensoldali parancsfájlt. Ezt követően konfigurálja a szükséges egyéb beállításokat.
1. Válassza a **Mentés** parancsot, majd válassza a **Szerkesztés befejezése** elemet.
1. Válassza a **Közzététel** lehetőséget.

### <a name="add-an-external-script-directly-to-a-template"></a>Külső parancsfájl hozzáadása sablonhoz közvetlenül

Ha egy külső parancsfájlt közvetlenül egy sablonhoz szeretne hozzáadni a webhelykészítőben, hajtsa végre az alábbi lépéseket.

1. Nyissa mega **Sablonok** pontot, majd nyissa meg azon oldalakhoz tartozó sablont, amelyhez hozzá szeretné adni a parancsfájlkódot.
1. A bal oldali panelen bontsa ki a sablon hierarchiáját a **HTML-fejléc** helyének megjelenítéséhez.
1. A **HTML-fejléc** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédablakban válassza a **Külső parancsfájl** lehetőséget.
1. A jobb oldali ablaktáblában a **Parancsfájl forrása** területen adja meg a külső parancsfájlhoz tartozó külső vagy kapcsolódó URL-címet. Ezt követően konfigurálja a szükséges egyéb beállításokat.
1. Válassza a **Mentés** parancsot, majd válassza a **Szerkesztés befejezése** elemet.
1. Válassza a **Közzététel** lehetőséget.

## <a name="additional-resources"></a>További erőforrások

[Embléma hozzáadása](add-logo.md)

[Webhely témájának kiválasztása](select-site-theme.md)

[A CSS felülíró fájljainak használata](css-override-files.md)

[Kedvencek ikon hozzáadása](add-favicon.md)

[Szerzői jogi értesítés hozzáadása](add-copyright-notice.md)

[Nyelvek hozzáadása a webhelyhez](add-languages-to-site.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
