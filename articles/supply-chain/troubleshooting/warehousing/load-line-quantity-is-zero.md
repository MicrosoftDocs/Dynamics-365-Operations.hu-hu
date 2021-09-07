---
title: Nem erősítheti meg a szállítmányt, mert a nulla mennyiséggel rendelkező rakománysora van
description: Nem erősítheti meg a szállítmányt, mert a nulla mennyiséggel rendelkező rakománysora van,
author: GalynaFedorova
ms.date: 07/30/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 15aa7f5e72ff8f2c027b5b020a23328978aa02b0
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/13/2021
ms.locfileid: "7344234"
---
# <a name="you-cant-confirm-a-shipment-because-load-lines-have-zero-quantity"></a>Nem erősítheti meg a szállítmányt, mert a nulla mennyiséggel rendelkező rakománysora van

Hibakód: WAX:LoadTableWarningAllLinesZero, WAX2543

## <a name="symptoms"></a>Tünetek

Szállítmány megerősítésekor a rendszer a következő hibaüzenetet jeleníti meg:

> A(z) %1 rakomány összes sorának mennyisége nulla.  
> Nem lehetett visszaigazolni a(z) %1 rakomány szállítmányát.

Ezért nem tudja megerősíteni a szállítmányt a betöltéshez.

## <a name="cause"></a>Ok

A rendszer kiértékeli, hogy a rakománysor szállításra visszaigazolható-e a létrehozott munkaazonosítók, a rakománysor mennyisége és az alulszállítás százalékos aránya alapján. Ha a rendszer úgy találja, hogy nincsenek munkaazonosítók, és az alulszállítás százalékos értéke 100 százalékra van állítva, akkor nem erősítheti meg a szállítmányt.

Ez a probléma például akkor fordulhat elő, ha a munkát visszavonták, és a rakománysor alulszállítási százaléka 100 százalék.

## <a name="resolution"></a>Megoldás

A rakomány vagy szállítmány jelenleg olyan állapotban van, amelyben a szállítmány megerősítése sikertelen. A probléma javításához végezze el a következő feladatok egyikét:

- Ellenőrizze a rakomány sorait, hogy meggyőződjön róla, hogy minden kapcsolódó munkát befejeztek a végleges kiszállítási helyen, és hogy a mennyiségek megegyeznek.
- Ellenőrizze a rakománysorokat, hogy az alulszállítás százalékos aránya és mennyiségei összhangban vannak-e a kitárolt munkával.

### <a name="review-your-load-lines-to-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a>Ellenőrizze a rakomány sorait, hogy meggyőződjön róla, hogy minden kapcsolódó munkát befejeztek a végleges kiszállítási helyen, és hogy a mennyiségek megegyeznek

Az alábbi módon ellenőrizze a rakomány sorait, hogy meggyőződjön róla, hogy minden kapcsolódó munkát befejeztek a végleges kiszállítási helyen, és hogy a mennyiségek megegyeznek.

1. Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.
1. Nyissa meg azt a rakományt, amelynél a szállítmányt nem lehet megerősíteni.
1. A **Rakománysorok** gyorslapon válassza ki a sor betöltése lehetőséget.
1. Jegyezze fel a **Munka létrehozott mennyisége** mező értékét.
1. A Művelet ablaktábla **Betöltések** lapjának **Kapcsolódó információk** csoportjában válassza a **Munka** elemet.
1. Ellenőrizze, hogy a munkát a végső kiszállítási helyen befejezték-e, és hogy a kitárolt munkamennyiség megegyezik-e a rakománysor létrehozott munkamennyiségével.
1. Ha eltérést talál, törölje a kapcsolódó munkát, konfigurálja újra a helyutasítást, és adja ki újra a rakományt. Az utasításokat lásd a [Nem erősítheti meg a szállítmányt, mert egyes cikkeket nem tároltak ki](picked-quantity-is-not-on-final.md) részben.
1. Ismételje meg ezt az eljárást minden rakománysorral annak érdekében, hogy minden feltétel teljesüljön.

### <a name="review-your-load-lines-to-make-sure-that-the-underdelivery-percentage-and-quantities-are-aligned-with-the-picked-work"></a>Ellenőrizze a rakománysorokat, hogy az alulszállítás százalékos aránya és mennyiségei összhangban vannak-e a kitárolt munkával

A következő eljárással ellenőrizze a rakománysorokat, hogy az alulszállítás százalékos aránya és mennyiségei összhangban vannak-e a kitárolt munkával.

1. Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.
1. Nyissa meg azt a rakományt, amelynél a szállítmányt nem lehet megerősíteni.
1. A **Rakománysorok** gyorslapon válassza ki annak a cikknek rakománysorát, amely meghaladja az alulszállítás százalékos arányát.
1. Szükség szerint módosítsa az **Alulszállítás** vagy a **Mennyiség mező** értékét.

> [!TIP]
> Ha a probléma továbbra sincs megoldva, akkor lehet, hogy a kapcsolódó értékesítési vagy átmozgatási rendeléseken további kitárolási munkát kell végrehajtania, amíg a rendelkezésre álló mennyiség nem igazodik a rakományhoz vagy szállítmányhoz.
