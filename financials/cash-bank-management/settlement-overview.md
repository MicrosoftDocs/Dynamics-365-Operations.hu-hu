---
title: "Kiegyenlítés – áttekintés"
description: "Ez a cikk a rendezési folyamat általános ismertetését tartalmazza. Leírja a rendezhető tranzakciókat, azt, hogy mikor és hogyan egyenlíthetők ki ezek és a kiegyenlítési folyamat eredményeit."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym, LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 14551
ms.assetid: 0968fa71-5984-415b-8689-759a0136d5d1
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 298ac47e2253f8add1aa3938dda15afe186afbeb
ms.openlocfilehash: ab12ef4127daf57fb0816ae1585876b50d1e81ed
ms.contentlocale: hu-hu
ms.lasthandoff: 06/20/2017


---

# <a name="settlement-overview"></a>Kiegyenlítés – áttekintés

[!include[banner](../includes/banner.md)]


Ez a cikk a rendezési folyamat általános ismertetését tartalmazza. Leírja a rendezhető tranzakciókat, azt, hogy mikor és hogyan egyenlíthetők ki ezek és a kiegyenlítési folyamat eredményeit.

Kiegyenlítés során az egy bizonylaton található tranzakciók alkalmazásra kerülnek egy másik bizonylaton található tranzakciókhoz, hogy az egyes bizonylatok egyenlegét növeljék vagy csökkentsék. Például egy kifizetés alkalmazható egy számlához. Számos tranzakció-típus egyenlíthető ki különböző időkben és különböző módokon. A kiegyenlítés járhat továbbá új tranzakciók létrehozásával.

## <a name="what-transactions-can-be-settled"></a>Mely tranzakciók egyenlíthetőek ki
A kötelezettségeken vagy kinnlevőségeken belüli tranzakciók létrejöhetnek bármely tranzakció-típus között, amely hatással van a szállítói egyenlegre vagy vevői egyenlegre, úgy mint számlák, kifizetések, jóváírások és díjak. Bármely tranzakció-típus kiegyenlíthető bármely egyéb tranzakció-típussal Például kiegyenlíthet egy kifizetést egy számlával, egy jóváírást egy számlával, egy számlát egy számlával vagy egy kifizetést egy kifizetéssel. Kiegyenlíthet kifizetést egy tranzakcióval ugyanazon jogi személyben vagy más jogi személyben. A szervezetekben, amelyek központosított kifizetési modellt használnak a [központosított kifizetések](set-up-centralized-payments.md) elem segíthet a kifizetési folyamat hatékonyabbá tételében.

## <a name="when-to-settle-transactions"></a>Mikor történik a tranzakciók kiegyenlítése
A tranzakciók a fizetési tétel idejében egyenlíthetőek ki. Például, amikor létrehoz egy kifizetést egy szállítónak, akkor általában kiválasztja a kifizetendő számlákat. A számlák kijelölésével megjelöli őket kiegyenlítésre a kifizetés számára. Amikor egy kinnlevőség-kifizetés ügyintéző rögzít egy vevői kifizetés, akkor megjelölik a megfelelő számlákat kiegyenlítésre, a vevői kifizetésben szereplő adatok alapján. A **Tranzakciók kiegyenlítése** lap használatos a tranzakciók megjelöléséhez kiegyenlítéshez. Ez a lap megnyitható bármely feladatlan számlából vagy kifizetésből. Amikor a tranzakció feladásra kerül, akkor a kiegyenlítés is feladásra kerül. A tranzakciók kiegyenlíthetőek továbbá a feladásuk után. Megadhat és feladhat egy vevői kifizetést anélkül, hogy kiegyenlítene vele bármilyen számlát. Előfordulhat azonban, hogy utána kell járnia a dolgoknak, hogy meggyőződjön, hogy a kifizetés a megfelelő számlát egyenlíti ki. A **Tranzakciók kiegyenlítése** lap megnyitható az **Összes vevő** vagy **Összes szállító** lapról, vagy a **Tranzakciók** lapról bármely vevőhöz, vagy szállítóhoz. Lefoglalhat továbbá feladott előlegeket egy számlához a megjelölve a kifizetést a beszerzési rendelés vagy értékesítési rendelés kiegyenlítéséhez. Ebben az esetben a kifizetés továbbra is nyílt egyenleggel fog rendelkezni, de nem lehet majd vele más számlát kiegyenlíteni. A kifizetés automatikusan a beszerzési rendelésből vagy értékesítési rendelésből létrejött számla kiegyenlítéséhez lesz felhasználva.

## <a name="how-to-settle-transactions"></a>Hogyan történik a tranzakciók kiegyenlítése
A tranzakciók kiegyenlíthetőek manuálisan, automatikusan, vagy a két módszer kombinálásával. A kifizetési mód kiválasztása az üzleti folyamatoktól függ, amely ezután megvalósítható a kiegyenlítés beállításai alapján, amely a kötelezettségek paraméterekben és a kinnlevőségek paraméterekben található. Létrehozhat szállítói kifizetéseket és vevői közvetlen levonás kifizetéseket egy kifizetési ajánlat használatával, amely a kifizetendő számlák kiválasztásánál használatos. A kifizetési ajánlat manuálisan van elindítva, azonban azután a Microsoft Dynamics 365 for Finance and Operations automatikusan megjelöli a kijelölt számlákat kiegyenlítésre, amikor a kifizetések létrejönnek. Ha a kifizetéseket manuálisan hozza létre, akkor használhatja a **Tranzakciók kiegyenlítése** lapot, hogy kiválassza a kiegyenlítendő számlákat. Manuálisan kiválaszthatja a számlákat vagy használhatja a **Megjelölés prioritás szerint** opciót, hogy a számlákat automatikusan megjelölje kiegyenlítéshez. A **Megjelölés prioritás szerint** beállítás csak a kinnlevőségek számára érhető el. Hogy engedélyezze ezt a beállítást használja a **Kiegyenlítési rangsor** lapot a kinnlevőségi paraméterekben. Ha egy kifizetési ügynök rögzít egy kifizetés, de nem egyenlíti ki a kifizetést mielőtt feladja, akkor a kifizetés kiegyenlíthető automatikusan. Engedélyezheti az automatikus kiegyenlítést a kinnlevőségi paraméterekben és kötelezettség paraméterekben. Amikor az automatikus kiegyenlítést használja, akkor használhatja az előre meghatározott kiegyenlítési sorrendet, vagy meghatározhatja a saját kiegyenlítési rangsorát a kinnlevőségi paraméterekben. Ez a funkció csak a kinnlevőségek számára érhető el.

## <a name="results-of-settlement"></a>A kifizetés eredménye
Ahogy a tranzakciók kifizetésre kerülnek az egyes tranzakciók hátralékos egyenlege növekszik vagy csökken a megfelelő mértékben. Egy jellemző esetben, ahol egy számla és kifizetés kerül kiegyenlítésre az egyes tranzakciók állapota és egyenlege a következő szabályoknak megfelelően frissül:

-   Ha a kifizetés összege több mint a számla összege, akkor a számla egyenlege 0,00-ra csökken és a számla lezárul. A kifizetés nyitva marad és az egyenlege az az összeg lesz, amellyel a kifizetés meghaladja a számla összegét.
-   Ha a kifizetés összege kevesebb mint a számla összege, akkor a kifizetés egyenlege 0,00-ra csökken és a kifizetés lezárul. A számla nyitva marad és az egyenlege azzal az összeggel lesz egyenlő, amennyivel a kifizetés alulfizette a számlát.
-   Ha a kifizetés összege egyenlő a számla egyenlegével, akkor a számla és a kifizetés is lezárul és mindkettő egyenlege 0,00 lesz.

Ha a [kifizetés kevesebb mint a számla összege](../accounts-payable/vendor-payments-partial-amount.md) egy készpénzfizetési engedmény, leírás vagy alulfizetés miatt, akkor a számla és a kifizetés még mindig lezárható, a kiegyenlítés beállításaitól függően a kötelezettség paraméterek és a kinnlevőségi paraméterek szerint. Egy kiegyenlítés létre is hozhat tranzakciókat. Például egy számla és kifizetés kiegyenlítése termelhet készpénzfizetés engedményt, realizált nyereséget vagy veszteséget, áfakorrekciókat, leírásokat vagy fillérkülönbözeteket.




