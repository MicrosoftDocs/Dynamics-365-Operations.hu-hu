---
title: Statikus fájlok feltöltése és kiszolgálása
description: Ez a témakör bemutatja, hogyan lehet feltölteni egy statikus fájlt a Microsoft Dynamics 365 Commerce webhelyszerkesztőbe, és hogyan lehet létrehozni egy egyéni URL-címet és fájlnevet, amely a fájl kérésére használható.
author: bicyclingfool
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 8b30150d4187bbb0195bcb23960afe7389d56a5c
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9281939"
---
# <a name="upload-and-serve-static-files"></a>Statikus fájlok feltöltése és kiszolgálása

[!include [banner](includes/banner.md)]

Ez a témakör bemutatja, hogyan lehet feltölteni egy statikus fájlt a Microsoft Dynamics 365 Commerce webhelyszerkesztőbe, és hogyan lehet létrehozni egy egyéni URL-címet és fájlnevet, amely a fájl kérésére használható.

Egyes külső összekötők megkövetelik, hogy egy fájlt az e-kereskedelmi webhelyről tárolják és szolgálják ki. Ezek az összekötők arra számítanak, hogy a fájlt egy adott visszahívási URL elérési útvonalra és fájlnévre irányuló kérelmek adják vissza. Ebből következően ez a cikk bemutatja egy olyan statikus fájl feltöltését és kiszolgálását, amely felhasználó által definiálható URL-címet és fájlnevet tartalmaz egy Dynamics 365 Commerce e-commerce webhelyen.

## <a name="create-a-site-url-that-returns-a-static-file"></a>Statikus fájlt visszaadó webhely URL-címének létrehozása

Ha olyan webhely URL-címet szeretne létrehozni, amely statikus fájlt ad vissza a Commerce webhelyszerkesztőben, kövesse az alábbi lépéseket.

1. Nyissa meg a webhely médiatárát, és töltse fel azt a fájlt, amelyet a megadott URL-címre érkező kéréseknek kell kézbesíteni. Ha már feltöltötte a fájlt, kihagyhatja ezt a lépést.
1. Nyissa meg a webhely **URL-címeit**.
1. Válassza az **Új \> Új URL-cím** lehetőséget.
1. Az **Új URL-cím** párbeszédpanelen válassza a **Médiatár-eszköz** lehetőséget.
1. Az **URL elérési út** mezőbe írja be az URL elérési utat. Adja meg a fájlnevet az elérési útban.
1. Válassza ki **Következő** lehetőséget. Megnyílik a Médiatár, és megjeleníti a feltöltött **dokumentum** típusú összes médiaelemet.
1. Válassza ki azt a fájlt, amelyet az 5. lépésben meghatározott URL-címre vonatkozó kérések esetén kell megjeleníteni.
1. Válassza a **Mentés** lehetőséget.

Ezen a ponton a létrehozott URL piszkozat állapotban van. Az URL-cím által mutatott fájl csak akkor lesz visszaadva, ha közzéteszi az URL-címet. Az URL közzététele előtt ellenőrizheti, hogy a megfelelő adatokat adja-e vissza.

## <a name="validate-and-publish-a-url"></a>URL ellenőrzése és közzététele

Az URL közzététel előtti ellenőrzéséhez kövesse az alábbi lépéseket.

1. Lépjen az **URL-címek** részhez a webhelynél, és válassza ki az URL címet az előnézethez.
2. A jobb oldali Tulajdonságok ablaktáblán, a **Szerkesztés** gomb alatt válassza ki a megfelelő URL-hivatkozást. Egy új böngészőablak nyílik meg, és 404-es hibaüzenetet kell kapnia.
3. Fűzze a **?preview=inprogress** lekérdezési sztringet az URL-címhez (például `https://yoursite.com/callback.html?preview=inprogress`), és töltse be újra az oldalt. A válaszban a rendszernek a médiatárba feltöltött fájlt kell visszaadnia.

Miután ellenőrizte az URL-címet, közzéteheti azt.

1. Lépjen az **URL-címek** részhez a webhelynél, és válassza ki az URL címet.
2. Válassza a parancssáv **Közzététel** elemét.

## <a name="update-the-file-that-a-url-points-to"></a>A fájl frissítése, amelyre egy URL-cím mutat

Az URL-cím közzététele után frissítheti azt, hogy az egy másik fájlra mutatjon. Azt is megteheti, hogy frissíti az URL-címet, hogy egy másik erőforrástípusra mutasson a következő szakaszban leírtak szerint. Az URL-címet például egy belső oldalra vagy egy átirányításra irányíthatja.

Az URL-címmel megcélzott fájl frissítéséhez kövesse az alábbi lépéseket.

1. Lépjen az **URL-címek** részhez a webhelynél, és válassza ki az URL címet a frissítéshez.
1. A jobb oldali tulajdonságok panelen válassza a **Szerkesztés** lehetőséget.
1. Az **URL-hozzárendelés** szakaszban válassza a **2. lépés** mezőt, majd válasszon egy új dokumentumot a médiatárból.
1. Válassza az **Alkalmazás** lehetőséget.

## <a name="update-the-asset-type-that-a-url-points-to"></a>Az eszköztípus frissítése, amelyre egy URL-cím mutat

Az URL-címeket is frissítheti úgy, hogy az más típusú eszközre (erőforrásra), például belső oldalra vagy átirányításra mutasson.

Az URL-címmel megcélzott eszköztípus frissítéséhez kövesse az alábbi lépéseket.

1. Lépjen az **URL-címek** részhez a webhelynél, és válassza ki az URL címet a frissítéshez.
1. A jobb oldali tulajdonságok panelen válassza a **Szerkesztés** lehetőséget.
1. Az **URL-hozzárendelés** szakaszban az **1. lépés** részben válasszon egy másik eszköztípust.
1. Válassza a **2. lépés** mezőt, és válasszon új eszközt.
1. Válassza az **Alkalmazás** lehetőséget.

## <a name="change-the-url-path"></a>Az URL elérési útjának módosítása

Az URL-cím létrehozása után az elérési út nem módosítható. Ha módosítania kell a fájlra vagy más típusú erőforrásra mutató URL-címet, új URL-címet kell létrehoznia, hozzá kell rendelnie a meglévő fájlhoz vagy más erőforráshoz, majd vissza kell vonnia a közzétételt, és törölnie kell a régi URL-címet.

Az URL-cím elérési útjának módosításához kövesse az alábbi lépéseket.

1. Új URL-cím [létrehozásához és meglévő fájlhoz vagy más erőforráshoz való leképezéséhez kövesse a Webhely létrehozása URL-címben található útmutatást, amely statikus fájlszakaszt ad vissza a](#create-a-site-url-that-returns-a-static-file) cikk korábbi részében.
1. Jelölje ki az új URL-címet, és válassza a **Közzététel** lehetőséget a parancssávon. Az új URL-cím közzé lesz téve.
1. A régi URL közzétételének visszavonásához jelölje ki, majd válassza a **Közzététel visszavonás** elemet a parancssávon. Most már törölheti a régi URL-t, ha akarja.

## <a name="additional-resources"></a>További erőforrások

[Digitális eszközkezelés – áttekintés](dam-overview.md)

[Képek feltöltése](dam-upload-images.md)

[Videók feltöltése](dam-upload-video.md)

[Fájlok feltöltése képek és videók kivételével](dam-upload-files.md)

[Képek körülvágása](dam-crop-images.md)

[Képfókuszpontok testreszabása](dam-custom-focal-point.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
