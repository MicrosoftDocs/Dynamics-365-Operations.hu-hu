---
title: Veszélyes anyagokkal kapcsolatos lekérdezések és jelentések
description: Ez a témakör azt mutatja be, hogyan lehet a veszélyes anyagokhoz kapcsolódó különböző jelentésekkel dolgozni. Számos ilyen jelentés szükséges annak érdekében, hogy a szállítás és a tárolás során a különböző veszélyes anyagokra vonatkozó rendeletek követelményei teljesüljenek.
author: t-benebo
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: ca8c973d3322bd51bf519e83fb5a5c19d35c0bed
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7568543"
---
# <a name="hazardous-materials-inquiries-and-reports"></a>Veszélyes anyagokkal kapcsolatos lekérdezések és jelentések

[!include [banner](../includes/banner.md)]

A Microsoft Dynamics 365 Supply Chain Management különböző jelentéseket tartalmaz, amelyek a veszélyes anyagokhoz kapcsolódnak. Számos ilyen jelentés szükséges annak érdekében, hogy a szállítás és a tárolás során a különböző veszélyes anyagokra vonatkozó rendeletek követelményei teljesüljenek.

Mindezek a jelentések – a **Multimodális veszélyes áruk** jelentés kivételével – a szállítmányhoz megadott szállítási módot használják a cikkek szállítási szövegének kinyomtatásához használt előírás megtalálásához. A szállítási mód a szállítmányozóhoz és a szállítmányozói szolgáltatáshoz van társítva. Ezért be kell állítania egy szállítmányozót és egy szállítmányozói szolgáltatást, majd csatolni kell azokat a szállítási módhoz. A szállítási mód a veszélyes anyagok szabályozásához kapcsolódik.

A következő ábra azokat a tevékenységfolyamatokat jeleníti meg, amelyek akkor következnek be, amikor a rendszer a veszélyes anyagok jelentéseit hozza létre.

![A veszélyes anyagok jelentéseihez kapcsolódó tevékenységek sorozata.](media/hazmat-report-sequence.png "A veszélyes anyagok jelentéseihez kapcsolódó tevékenységek sorozata")

## <a name="set-up-hazardous-materials-reporting"></a><a name="set-up"></a>Veszélyes anyagok jelentéseinek beállítása

Általában a veszélyes anyagokat tartalmazó cikkek szállítása esetén a biztonság megőrzéséhez és a veszélyes anyagokra vonatkozó rendeletek teljesítéséhez specifikus jelentéseket kell létrehozni. A jelentések beállításához kövesse az alábbi lépéseket.

1. Lépjen a **Raktárkezelés \> Beállítás \> Raktárkezelési paraméterek** részre.
2. Nyissa meg a **Jelentések** lapot. A **Veszélyes anyagok jelentési paramétere** gyorslapon állítsa be a következő mezőket.

    | Szakasz | Mező | Leírás |
    |---|---|---|
    | Multimodális veszélyes áruk | Szabályozás kódja | Válassza ki a **Multimodális veszélyes áruk** jelentésének létrehozásakor használandó rendeletet. |
    | Veszélyes anyagok raktárkészletkorlátai | Szabályozás kódja | Válassza ki a készletkorlátok kiértékelése során használandó rendeletet. |
    | Áruk közúti szállítása | CMR-termékcsoport | A CMR jelentése „karcinogén, mutagén és reprotoxikus anyagok”. Ezt a beállítást **Igen** értékre állítva beállíthatja, hogy a rendszer kinyomtassa az ilyen anyagok kezelésével kapcsolatos konkrét figyelmeztetéseket és üzeneteket. |
    | Áruk közúti szállítása | Veszélyes anyag csoportjának leírása | Adja meg a CMR-rel és a közúti árufuvarozással kapcsolatos konkrét figyelmeztetések szövegét. Ez a szöveg fel lesz tűntetve a jelentésben. |
    | Szállítmányozói nyilatkozat | Figyelmeztetés | Írja be egy figyelmeztető üzenet szövegét, amelyet a szállítmányozói nyilatkozat űrlapjára kell nyomtatni (például „Figyelmeztetés: veszélyes áruk, gyúlékony”). |
    | Szállítmányozói nyilatkozat | Lábléc-nyilatkozat | Adja meg azt a szöveget, amelyet a szállítmánynyilatkozat dokumentumának aljára kell nyomtatni. |
    | Veszélyes áruk jelentési nyelve | Veszélyes áruk belföldi jelentési nyelve | Válassza ki a belföldi szállítmányokhoz társított veszélyes anyagokra vonatkozó jelentések alapértelmezett nyelvét. |
    | Veszélyes áruk jelentési nyelve | Veszélyes áruk exportálásának jelentési nyelve | Válassza ki a nemzetközi szállítmányokhoz társított veszélyes anyagokra vonatkozó jelentések alapértelmezett nyelvét. |

## <a name="hazardous-materials-report"></a>Veszélyes anyagok jelentése

A **Veszélyes anyagok** jelentés felsorolja azokat a cikkeket, amelyek úgy vannak beállítva és definiálva, hogy tartozik azokhoz veszélyesanyag-információ. Ezzel a jelentéssel nyomon követheti és megtekintheti a karbantartani szükséges adatokat. A jelentés lapja a veszélyes anyagok beállításaiból kiválasztott mezők egy részét jelenít meg. Azonban személyre szabhatja, hogy további mezőket vegyen fel igény szerint.

A jelentés megtekintéséhez válassza a **Termékinformáció-kezelés \> Lekérdezések és jelentések \> Veszélyes anyagok szállítási dokumentációja \> Veszélyes anyagok** lehetőséget.

## <a name="hazardous-material-stock-limit-report"></a><a name="stock-limit-report"></a>Veszélyes anyagok raktárkészletkorlát jelentése

A **Veszélyes anyagok készletkorlátozása** jelentéssel nyomon követheti a veszélyes anyagok készletének szintjét a raktári helyeken, hogy a meghatározott biztonsági korlátok között maradjon. Ezek a korlátozások a kiadott termékhez megadott korlátokból származnak.

A jelentés megtekintéséhez válassza a **Termékinformáció-kezelés \> Lekérdezések és jelentések \> Veszélyes anyagok szállítási dokumentációja \> Veszélyes anyagok raktárkészletkorlátai** lehetőséget.

Ha további tájékoztatást szeretne arról, hogyan lehet a kiadott termékre vonatkozó készlet-korlátozásokat megadni, akkor lásd: [Készletkorlátok a veszélyes termékekhez](hazmat-items.md#stock-limits).

A készletkorlátokhoz használt előírás a **Raktárkezelési paraméterek** oldalon definiálható. Nyissa meg a **Raktárkezelés \> Beállítások \> Raktárkezelési paraméterek** lehetőséget, majd a **Jelentések** lapon a **Veszélyes anyagok készletkorlátozása** lapon adja meg a rendeletkódot. További tudnivalókért tekintse meg a [Veszélyes anyagok jelentéseinek beállítása](#set-up) című részt, a témakör korábbi részében.

## <a name="verified-gross-mass-report"></a>Ellenőrzött bruttótömeg jelentés

Az **Ellenőrzött bruttó tömeg** jelentéssel információkat nyomtathat ki a szállítmány tömegéről.

A jelentés létrehozásához és kinyomtatásához nyissa meg a **Raktárkezelési \> Szállítmányok \> Összes szállítmány** lehetőséget, és nyissa meg a megfelelő szállítmányt. Ezután a műveleti ablaktábla **Szállítmányok** lapján a **Veszélyes anyagok dokumentumai** csoportban válassza az **Ellenőrzött bruttó tömeg** lehetőséget.

## <a name="multimodal-dangerous-goods-report"></a>Multimodális veszélyes áruk jelentése

A **Multimodális veszélyes áruk** jelentés olyan szállítmányokra vonatkozik, amelyeket a szállítási módok kombinációjának használatával kell mozgatni. Általában akkor használatos, ha a szállítást először a közúton, majd tengeren végzik.

A jelentés létrehozásához és kinyomtatásához nyissa meg a **Raktárkezelési \> Szállítmányok \> Összes szállítmány** lehetőséget, és nyissa meg a megfelelő szállítmányt. Ezután a műveleti ablaktábla **Szállítmányok** lapján a **Veszélyes anyagok dokumentumai** csoportban válassza az **Multimodális veszélyes áruk** lehetőséget.

Amikor létrehozza ezt a jelentést, a program menti az adatokat, így szerkesztheti és/vagy újranyomtathatja a jelentést, ha szükséges. Egy elkészített jelentés szerkesztéséhez nyissa meg a **Raktárkezelés \> Lekérdezések és jelentések \> Veszélyes anyagok szállítási dokumentációja \> Multimodális veszélyes áruk** menüpontot, és keresse meg a megfelelő jelentést a listában. Miután befejezte a tartalom szerkesztését a szükséges módon, válassza a **Nyomtatás** lehetőséget műveleti ablaktáblán a jelentés nyomtatásához.

## <a name="shippers-declaration-report"></a>Szállítmányozói nyilatkozat jelentése

A **Szállítmányozói nyilatkozat** jelentéssel kinyomtathatja a szállítmányban szereplő anyagok nyilatkozatával kapcsolatos adatokat.

A jelentés létrehozásához és kinyomtatásához nyissa meg a **Raktárkezelési \> Szállítmányok \> Összes szállítmány** lehetőséget, és nyissa meg a megfelelő szállítmányt. Ezután a műveleti ablaktábla **Szállítmányok** lapján a **Veszélyes anyagok dokumentumai** csoportban válassza az **Szállítmányozói nyilatkozat** lehetőséget.

## <a name="carriage-of-merchandise-by-road-report"></a>Áruk közúti szállítása jelentés

Az **Áruk közúti szállítása** jelentés egy fuvarlevélhez hasonlít, de általában a veszélyes áruk nemzetközi közúti (ADR) rendelkezéseivel kapcsolatos megállapodás alapján Európában a közúti fuvarozásban használatos. Ez a jelentés egy cikk szállítási nyomtatási szövegét használja, hacsak nem állítja be a **Veszélyesanyag-csoport leírása** mezőt a **Raktárkezelési paraméterek** lapon.

A jelentés létrehozásához és kinyomtatásához nyissa meg a **Raktárkezelési \> Szállítmányok \> Összes szállítmány** lehetőséget, és nyissa meg a megfelelő szállítmányt. Ezután a műveleti ablaktábla **Szállítmányok** lapján a **Veszélyes anyagok dokumentumai** csoportban válassza az **Áruk közúti szállítása** lehetőséget.

Amikor létrehozza ezt a jelentést, a program menti az adatokat, így szerkesztheti és/vagy újranyomtathatja a jelentést, ha szükséges. Egy elkészített jelentés szerkesztéséhez nyissa meg a **Raktárkezelés \> Lekérdezések és jelentések \> Veszélyes anyagok szállítási dokumentációja \> Áruk közúti szállítása** menüpontot, és keresse meg a megfelelő jelentést a listában. Miután befejezte a tartalom szerkesztését a szükséges módon, válassza a **Nyomtatás** lehetőséget műveleti ablaktáblán a jelentés nyomtatásához.

## <a name="shipment-summary-report"></a>Szállítmány összefoglaló jelentése

A **Szállítmányösszesítő** jelentés olyan információkat tartalmaz, amelyet a kiadott cikkekhez kapcsolódó szállítási kategóriák összesítenek.

A jelentés létrehozásához és kinyomtatásához nyissa meg a **Raktárkezelési \> Szállítmányok \> Összes szállítmány** lehetőséget, és nyissa meg a megfelelő szállítmányt. Ezután a műveleti ablaktábla **Szállítmányok** lapján a **Veszélyes anyagok dokumentumai** csoportban válassza az **Szállítmányösszesítő** lehetőséget.

## <a name="bill-of-lading-report"></a>fuvarlevél jelentése

Amikor a veszélyes anyagok funkció be van kapcsolva a rendszerben, a **fuvarlevél** jelentés tartalmaz egy **Veszélyes anyagok** oszlopot, amely azt jelzi, hogy a rakomány tartalmaz-e veszélyes anyagokat. Ez a jelentés a szokásos módon érhető el a **Minden rakomány** oldalon.

## <a name="packing-list-report"></a>Csomagolási lista jelentése

Amikor a veszélyes anyagok funkció be van kapcsolva a rendszerben, a csomagolási listák a cikkek szállítási nyomtatási szövegével kapcsolatos további információkat tartalmazzák. Ez a jelentés a szokásos módon érhető el a **Minden rakomány** oldalon.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]