---
title: Változatok létrehozása tervezési termékekhez
description: Ez a témakör azt ismerteti, hogyan lehet változatokat létrehozni mérnöki termékekhez.
author: t-benebo
ms.date: 06/08/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-06-08
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 08feb66dedfa79f5a21a7723a22f3bef883431e6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8870753"
---
# <a name="generate-variants-for-engineering-products"></a>Változatok létrehozása tervezési termékekhez

[!include [banner](../includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet változatokat létrehozni a mérnöki termékekhez.

## <a name="turn-variant-generation-for-engineering-products-on-or-off"></a>Változatok generálása mérnöki termékeknél be- és kikapcsolása

Az ebben a cikkben *leírt* *funkciókhoz* a mérnöki termékekhez szükséges, hogy mind a Mérnöki változáskezelés, mind a Változatok generálása be legyen kapcsolva a rendszerben. A funkciók be- és kikapcsolása a [Műszaki változáskezelés témakörében található](product-engineering-overview.md).

## <a name="generate-one-or-more-new-variants-of-an-engineering-product"></a>Tervezési termék egy vagy több új változatának létrehozása

A termékből létrehozható egy vagy több új változat, az adatok a meglévő termékből való másolása nélkül. Ez olyankor hasznos, amikor egyszerre több termékváltozatot kell létrehoznia.

Az alábbi eljárás bemutatja, hogyan lehet több változatot létrehozni, amelyek tartalmazzák a színdimenziót.

1. Nyissa meg a **Kiadott termékek** lapot (például **Tervezési változáskezelés \> Közös \> Kiadott termékek**).
1. A műveleti ablaktáblán nyissa meg a **Termék** lapot, és az **Új** csoportban válassza a **Mérnöki termék** lehetőséget.
1. Megjelenik az **Új termék** párbeszédpanel. Válassza ki a megfelelő **Tervezési kategóriát**.
1. Ha a kiválasztott tervezési kategória változatdimenziókat is tartalmaz, akkor most már be lehet állítani a hozzájuk tartozó értékeket. Ebben a példában a kategória rendelkezik a **Szín** dimenzióval *Kék* értékre állíthatja.
1. Szükség szerint adjon meg további beállításokat. Az termék létrehozásához kattintson az **OK** lehetőségre.
1. Létrejön a termék és a kék V-1 változat, és megnyílik az új termék.
1. Szükség szerint adjon hozzá egy anyagjegyzéket (BOM) és egy útvonalat a változathoz.
1. Nyissa meg a műveleti ablaktáblán a **Termék** lapját, és az **Alaptermék** csoportban válassza a **Termékdimenziók** lehetőséget.
1. Megnyílik a **Termékdimenziók** lap. Ez a lap tartalmaz egy lapot az egyes elérhető dimenziókhoz. Minden egyes lapon adjon meg egy sort mindegyik értékhez, amely az egyes dimenziókhoz támogatottak lesznek. (Ebben a példában sorokat adhat hozzá a **Szín** lapon a *Fehér*, a *Sárga* és a *Zöld* színekhez).
1. Zárja be a lapot, majd válassza a **Kiadott termékváltozatok** lehetőséget. Figyelje meg, hogy az első létrehozott változat (kék V-1) megjelenik.
1. A Művelet panel **Termékváltozat** lapján válassza az **Változatjavaslatok** menüpontot.
1. A **Változatjavaslatok** párbeszédpanelen hajtsa végre a következő lépések valamelyikét:

    - A párbeszédpanel tetején minden egyes elérhető dimenzióhoz van egy szakasz. Mindegyik dimenziónál jelölje be mindegyik érték jelölőnégyzetét, amelyekhez változatjavaslatot szeretne létrehozni, majd válassza a **Javaslat** lehetőséget az eszköztáron. A rendszer hozzáadta a megfelelő javaslatokat a **Javasolt változatok** szakaszhoz.
    - Válassza az eszköztárban az **Javaslat mindenhez** lehetőséget a dimenzióértékek összes elérhető kombinációjához használható változatjavaslatok létrehozásához. A rendszer hozzáadta a javaslatokat a **Javasolt változatok** szakaszhoz.

1. A **Javasolt változatok** szakaszban jelölje be mindegyik létrehozni kívánt változat jelölőnégyzetét. Ezután nyomja meg a **Létrehozás** elemet a kiválasztott változatok létrehozásához és kibocsátásához a tervezővállalat számára. A következő feltételeket kell figyelembe venni:

    - A létrehozott változatok közül egyiknek sem lesz anyagjegyzéke vagy útvonala.
    - Ezeknek a változatoknak az attribútumai alapértelmezésben a tervezési kategóriából lesznek átmásolva, és nem másolhatók át az előző változatból.

## <a name="generate-a-variant-as-a-copy-of-another-product-variant"></a>Változat létrehozása másik termékváltozat másolataként

A termékből egy másik termékváltozat alapján is létrehozható változat. A forrástermékváltozat anyagjegyzékét (BOM) és útvonalát a program az új változatba másolja. Ez olyan elkülönített gyártási termékeknél lehet hasznos, amelyeknél hasznos lehet az anyagjegyzék létrehozása egy kezdő anyagjegyzék alapján, és az előző változat változásainak nyomon követése. A nyomonkövethetőség fenntartása érdekében a rendszer rögzíti, hogy melyik másolat lett másolva az új másolat létrehozásához.

Az alábbi művelet bemutatja hogyan lehet létrehozni a szín dimenziót tartalmazó új változatot egy meglévő változat másolatának létrehozásával

1. Nyissa meg a **Kiadott termékek** lapot (például **Tervezési változáskezelés \> Közös \> Kiadott termékek**).
1. A műveleti ablaktáblán nyissa meg a **Termék** lapot, és az **Új** csoportban válassza a **Mérnöki termék** lehetőséget.
1. Megjelenik az **Új termék** párbeszédpanel. Válassza ki a megfelelő **Tervezési kategóriát**.
1. Ha a kiválasztott tervezési kategória változatdimenziókat is tartalmaz, akkor most már be lehet állítani a hozzájuk tartozó értékeket. Ebben a példában a kategória rendelkezik a **Szín** dimenzióval *Kék* értékre állíthatja.
1. Szükség szerint adjon meg további beállításokat. Az termék létrehozásához kattintson az **OK** lehetőségre.
1. Létrejön a termék és a kék V-1 változat, és megnyílik az új termék.
1. Szükség szerint adjon hozzá egy anyagjegyzéket és egy útvonalat a változathoz.
1. Szükség szerint adjon hozzá attribútumokat a termékváltozathoz.
1. A kék V-1 termékváltozatot adja hozzá egy tervezési módosítási utasítához.
1. A **Hatás** beállítása legyen *Új változat*.
1. Az új színértéket válassza ki (például *Fehér*). Figyeljen arra, hogy a következő feltételek érvényesek: 
    - Az új változathoz tartozik anyagjegyzék és útvonal amely az előző változatból van másolva.
    - Az új változat az előző változatból átmásolt attribútumokkal rendelkezik.
1. Hagyja jóvá a módosítási rendelést.
1. Dolgozza fel a módosítási rendelést. A rendelés feldolgozása után az új V-1 változat létrejön és ki lesz adva a tervezővállalatnak.
