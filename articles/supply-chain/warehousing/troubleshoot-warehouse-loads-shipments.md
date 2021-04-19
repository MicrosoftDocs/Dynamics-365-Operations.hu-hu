---
title: Rakományok összeállítása és szállítása – hibaelhárítás
description: Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben a rakományok összeállítását és szállítását végzi a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: e9964376a794661058da78152879d2142dd7ec51
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828202"
---
# <a name="troubleshoot-load-building-and-shipments"></a>Rakományok összeállítása és szállítása – hibaelhárítás

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben a rakományok összeállítását és szállítását végzi a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban.

## <a name="i-receive-the-following-error-message-you-cant-create-a-load-line-for-this-order-line-because-it-contains-inventory-dimensions-that-are-invalid"></a>A következő hibaüzenet jelenik meg: „Nem hozhat létre terheléssort ehhez a rendelési sorhoz, mert érvénytelen készletdimenziókat tartalmaz...”

### <a name="issue-description"></a>Probléma leírása

A következő hibaüzenet jelenik meg, amikor visszáruértékesítési rendelést próbál kiadni a raktárba:

> Nem hozhat létre terheléssort ehhez a rendelési sorhoz, mert érvénytelen készletdimenziókat tartalmaz. Nem hivatkozhat olyan készletdimenziókra, amelyek a helydimenzió alatt találhatók a foglalási hierarchiában. Távolítsa el az érvénytelen dimenziókat a rendelési sorból.

### <a name="issue-resolution"></a>Probléma megoldása

Sajnos a termék nem támogatja a terhelés feldolgozását az értékesítési visszárufolyamatnál. Ezért a visszáruértékesítési rendelést nem adhatja ki a raktárba.

A rendeléstranzakciókon nem hivatkozhat olyan készletdimenziókra, amelyek a **Helydimenzió** alatt találhatók a foglalási hierarchiában. Az a megoldás, hogy távolítsa el az érvénytelen dimenziókat a rendelési sorból.

## <a name="i-receive-the-following-error-message-one-of-the-lines-is-already-on-a-load-unable-to-release-to-warehouse"></a>A következő hibaüzenet jelenik meg: „Az egyik sor már be van töltve. Nem lehet kiadni a raktárba.”

### <a name="issue-description"></a>Probléma leírása

Ha manuálisan hoz létre rakományokat, vagy úgy állítja be a folyamatot, hogy a rakományok már az értékesítésrendelési sor bevitele előtt létrejönnek, akkor azt feltételezi a rendszer, hogy a későbbi kiadás manuálisan történik, és a rakományból származó útvonal és minősítés lesz használva.

Egy másik lehetséges forgatókönyv, hogy automatikus kiadást próbál végezni a raktárba, de a hullámfolyamat nem tud munkát létrehozni. Ezért egy nyitott szállítmány vagy rakomány továbbra is létrejön. Ez a nyitott szállítmány vagy betöltés letiltja a rendelés automatikus kiadására irányuló későbbi kísérleteket, amíg nem törli a nyitott szállítmányt vagy betöltést, vagy manuálisan fel nem dolgozza a hullámot.

### <a name="issue-resolution"></a>Probléma megoldása

Az értékesítési rendelés lapról kiadhatja, vagy az automatikus kiadást eszközölhet a kiadás értékesítési rendelés lapról, csakis akkor, ha nincs rakomány a raktárba történő kiadás előtt. A rakomány automatikusan létrejön a hullám feldolgozása után.

## <a name="i-receive-the-following-error-message-the-delivery-note-correction-cant-be-processed-the-delivery-note-only-contains-items-that-are-subject-to-warehouse-management-processes-as-these-are-not-supported-by-delivery-note-correction"></a>A következő hibaüzenet jelenik meg: „A szállítólevél helyesbítése nem dolgozható fel. A szállítólevél csak olyan cikkeket tartalmaz, amelyekre raktárkezelési folyamatok vonatkoznak, mivel ezeket a Szállítólevél helyesbítése nem támogatja."

### <a name="issue-description"></a>Probléma leírása

A szállítólevél kiadása után nem vonhatja vissza, mert a **Mégse** gomb nem érhető el. A szállítólevél nem helyesbíthető. Ha megpróbálja, ez a hibaüzenet jelenik meg.

### <a name="issue-resolution"></a>Probléma megoldása

A speciális raktárkezeléshez (WMS) engedélyezett cikkek könyvelt szállítólevélének helyesbítéséhez a könyvelést a rakományból kell kiadnia, nem pedig közvetlenül a rendelésből.

## <a name="how-can-i-create-work-from-outbound-loads-instead-of-waves"></a>Hogyan hozhatok létre munkát a kimenő rakományokból és nem a hullámokból?

### <a name="issue-description"></a>Probléma leírása

Itt van egy módja, hogyan reprodukálja ezt a problémát.

1. Hozzon létre értékesítési vagy átmozgatási rendelést kimenő rakomány létrehozásához.
2. A rakomány kiadása a raktárba
3. Figyelje meg, hogy még nem jött létre kitárolási munka.

### <a name="issue-resolution"></a>Probléma megoldása

Ha a munkát azonnal létre kell hozni a rakomány kiadásakor, ennek megfelelően kell konfigurálnia a hullámsablont. A hullámsablonon állítsa a következő beállításokat *Igen* értékre:

- Hullámlétrehozás automatizálása
- Hullám feldolgozása a raktárba történő kiadáskor
- Hullámkiadás automatizálása

## <a name="i-cant-re-release-a-partially-shipped-load"></a>Nem tudok újra kiadni egy részlegesen szállított rakományt.

### <a name="issue-description"></a>Probléma leírása

Nem adhat ki részlegesen szállított rakomány a raktárba. Amikor elvégzi a kiadást a raktárba, megjelenik egy „Művelet befejezve” üzenet, de nem történik semmi, és nem jön létre munka a fennmaradó mennyiséghez. Ez a probléma akkor fordul elő, ha a szállítási rakomány funkciót használja, és hiányos a foglalás.

### <a name="issue-resolution"></a>Probléma megoldása

A [KB 470069 számú probléma](https://fix.lcs.dynamics.com/Issue/Details?kb=4574490&bugId=470069&dbType=3&qc=84ce1e09d7032d8b8ef86f5a0c68b86badf3dfaf29686c5ebbe97c53c0957b5f) („A részlegesen szállított rakományok újrahullámosíthatók és újra feldolgozhatók”) [a 10.0.15 kiadásban](../get-started/whats-new-scm-10-0-15.md) lett kijavítva.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]