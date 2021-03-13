---
title: Szállítási költség egyeztetése a szállításkezelésben
description: A témakör a szállítási költség egyeztetési folyamatot ismerteti.
author: MarkusFogelberg
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSAuditMaster, TMSFreightBillInvoiceReconcile, TMSFreightBillSummary, TMSFreightBillType, TMSFreightMatchReason, TMSFBDetailReconcile, TMSInvoiceTable,TMSInvoiceLineReconcile,TMSReconcileInvoice, TMSFreightBillDetail, TMSFreightBillTypeAssignment, TMSRejectInvoiceLine, TMSMiscellaneousCharge
audience: Application User
ms.reviewer: kamaybac
ms.custom: 89983
ms.assetid: bc34a9b1-0c11-4797-b463-25409cf98ca8
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ac07155e4dde77689b1994abfb8b30f45d5a5a30
ms.sourcegitcommit: b6686265314499056690538eaa95ca51cff7c720
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5014508"
---
# <a name="reconcile-freight-in-transportation-management"></a>Szállítási költség egyeztetése a szállításkezelésben

[!include [banner](../includes/banner.md)]

A témakör a szállítási költség egyeztetési folyamatot ismerteti.

Szállítási költség egyeztetés elvégezhető manuálisan vagy beállítható automatikusra. Automatikus szállítási egyeztetés használatához vizsgálati alapadatok beállítása szükséges, ahol megadhatja a feltételeket, amelyek meghatározzák, hogy mely fuvarszámla egyeztetése legyen automatikus.

## <a name="the-freight-reconciliation-process"></a>A fuvaregyeztetési folyamat

A szállítási díjakat a megfelelő szállítási fuvarozóval társított díjkalkulátor számítja ki. Rakomány megerősítése esetén a fuvarlevélszámla létrejön, és a szállítási díjak átvitele a fuvarlevélszámlára megtörténik. A fuvardíjak vegyes költségek szerint vannak arányosítva a vonatkozó forrásbizonylat (beszerzési rendelés, értékesítési rendelés és/vagy átmozgatási rendelés) alapján, a rendszeres számlázási folyamat beállításaitól függően. A szállítási költség egyeztetési folyamata elindítható, amint a fuvarszámla megérkezik a szállítmányozótól. A számla elektronikus úton vagy nyomtatott papíron érkezhet. Ha papíralapú számla érkezik, elektronikus számlát hozhat létre a fuvarlevelet használva sablonként.

[![Fuvaregyeztetési folyamat](./media/freight-reconcilation-process.jpg)](./media/freight-reconcilation-process.jpg)

## <a name="manual-reconciliation"></a>Manuális egyeztetés

Ha az egyeztetést manuálisan végzi, minden számlázási sorral minden fuvarlevélsort vagy a számlázandó rakománysort egyeztetnie kell. Ezt a **Fuvarlevél és számlaegyeztetés** oldalon végezheti el. Ha a számlasor összege nem egyezik meg a fuvardíj összegével, az eltérés egyeztetés okát kell kiválasztania. Ha több egyeztetési ok fordul elő, a nem egyeztetett összeget feloszthatja. Az egyeztetés oka határozza meg, hogyan kerülnek a különbözet összegei feladásra a főkönyvbe. Amikor a teljes számlaösszeg egyeztetése számba lett véve, jóváhagyás céljából elküldik és a napló feladásra kerül. Az alábbi ábra bemutatja, hogyan készíthető szállítási számla és hajtható végre a fuvarlevél-egyeztetés.

[![Fuvaregyeztetési feladatok](./media/processflowforfreightreconciliation.jpg)](./media/processflowforfreightreconciliation.jpg)

## <a name="automatic-reconciliation"></a>Automatikus egyeztetés

Automatikus egyeztetéshez meg kell adnia a használni kívánt egyeztetés, számlák, és szállítmányozók ütemezését. A számlasorok és fuvarlevelek ellenőrzése alapvizsgálat beállításainak és a fuvarlevél típusának megfelelően történik. Az automatikus egyeztetés futtatása után kezelnie kell azokat a számlákat, melyeket a rendszer nem tudott. Manuálisan kell feldolgoznia ezeket a számlákat a kifizetés előtt.

## <a name="match-freight-bills-with-freight-invoices-using-automatic-or-manual-reconciliation"></a>Fuvarlevelek egyeztetése a fuvarszámlákkal automatikus vagy manuális módon

Az *egyeztetés* az egyes fuvarleveleknek megfelelő fuvarszámlák megkeresésének folyamatát jelenti. Ez a számlasorok egyenként történő (kézi egyeztetés) vagy az összes rendelkezésre álló számla egyszerre történő egyeztetésével (automatikus egyeztetés) hajtható végre.

### <a name="auto-matching"></a>Automatikus egyeztetés

Ha több fuvarszámlát egyeztet ugyanahhoz a fuvarlevélhez, az automatikus egyeztetés folyamata a következőképpen működik:

1. A nem egyeztetett fuvarszámlák összeg szerint vannak rendezve, kezdve a legnagyobb összeggel.
1. A fuvarszámlák egyeztetése egyenként történik, amíg a fuvarlevél fennmaradó összege nem lesz pozitív.
1. Az alapvizsgálat beállításaitól és a fuvarszámlák fennmaradó összegétől függően a fennmaradó összeg be van állítva.

### <a name="manual-matching"></a>Manuális egyeztetés

A pozitív összeget tartalmazó fuvarlevelek egyeztetésre elérhetők. Az automatikus egyeztetéshez hasonlóan a felhasználó csak a negatív összegű fuvarszámlákat tudja egyezteti a nem teljesen egyező fuvarlevelekkel.

### <a name="example"></a>Példa

Tegyük fel, hogy van egy 1500 összegű fuvarlevél (FB), és Ön létrehozott három fuvarszámlát a fuvarlevélhez, mindegyik számlához egy számlasorral, a következő beállításokkal:

- Eredeti fuvarlevél (FB): 1500 összeg
- 1. számla (Inv1): 1000 összeg
- 2. számla (Inv2): 600 összeg
- 3. számla (Inv3): -100 összeg

#### <a name="automatic-matching-result"></a>Automatikus egyeztetés eredménye

Az automatikus egyeztetés a következő sorrendben lesz végrehajtva:

1. Az összes fuvarszámla rendezése összeg szerint csökkenő sorrendben: Inv1 -> Inv2 -> Inv3.
1. Egyeztesse az Inv1-et az FB-vel. Az Inv1 1000 értékű összegének egyeztetése megtörtént, és az FB-n 500 fennmaradó összeg szerepel, így az állapot *Részben egyező* lesz.
1. Egyeztesse az Inv2-t az FB-vel. Az Inv2 500 értékű összegének egyeztetése megtörtént, és az FB-n 0 fennmaradó összeg szerepel, így az állapot *Teljesen egyező* lesz.
1. Mivel az FB már teljesen egyeztetve van, az Inv3 nem lesz feldolgozva.

#### <a name="manual-matching-result"></a>Kézi egyeztetés eredménye

A kézi egyeztetésnél az eredmények az egyeztetés sorrendjétől függenek, mint azt az alábbi példák mutatják.

##### <a name="manual-matching-case-1"></a>1. manuális egyeztetési eset

A manuális egyeztetés egyik módja például a következő:

1. Egyeztesse az FB-t az Inv1-gyel. Az FB-n 500 fennmaradó összeg szerepel, így az állapot *Részben egyező* lesz.
1. Egyeztesse az Inv2-t az FB-vel. Az Inv2 500 értékű összegének egyeztetése megtörtént, és az FB-n 0 fennmaradó összeg szerepel, így az állapot *Teljesen egyező* lesz.
1. Ha manuálisan egyezteti az Inv3-at, nem fog találni nem egyező fuvarleveleket.

Ez az eset alapvetően megegyezik az automatikus egyeztetéssel

##### <a name="manual-matching-case-2"></a>2. manuális egyeztetési eset

A manuális egyeztetés egy másik módja például a következő:

1. Egyeztesse az Inv3-at az FB-vel. Az FB fennmaradó összege most 1600, ami megegyezik az 1500-as értékkel, ha 1600-ból kivonunk 100-at. Az FB és az Inv3 is -100 mennyiséggel rendelkezik.
1. Egyeztesse az Inv1-et és a Inv 2-t az FB-vel egymás után. Az FB teljesen egyezik.

Mint a példa mutatja, a fuvarszámlák negatív összegekkel való egyeztetését csak manuálisan szabad elvégezni. Így mindig lehet egyeztetni a negatív összegű fuvarszámlákat egy nem teljesen egyező fuvarszámlával, mert így lehetősége van szabályozni az egyeztetési sorrendet.
