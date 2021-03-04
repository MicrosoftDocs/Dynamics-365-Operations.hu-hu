---
title: Raktárkezelés készleten lévő bejegyzéseinek karbantartási feladata
description: Ez a témakör bemutatja az aktuális készlet bejegyzések karbantartási feladatát, amely a kapcsolódó, de szükségtelen rekordok azonosításával és törlésével segít a rendszer teljesítményének növelésében.
author: perlynne
manager: tfehr
ms.date: 04/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysOperationTemplateForm
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-04-03
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: 9d01c577fc33564d3517d242e9b01f73cc8e079c
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/16/2020
ms.locfileid: "4429903"
---
# <a name="warehouse-management-on-hand-entries-cleanup-job"></a>Raktárkezelés készleten lévő bejegyzéseinek karbantartási feladata

Az aktuális készlet kiszámításához használt lekérdezések teljesítményére hatással van az érintett táblák rekordjainak száma. A teljesítmény javítása érdekében az egyik mód az, hogy csökkentse azoknak a rekordoknak a számát, amelyeket az adatbázisnak figyelembe kell vennie.

Ez a témakör bemutatja az aktuális készlet bejegyzések karbantartási feladatát, amely törli a szükségtelen rekordokat az InventSum és a WHSInventReserve táblákban. Ezek a táblák a raktárkezelési feldolgozására engedélyezett cikkek aktuális adatait tárolják. (Ezeket a cikkeket WHS cikkeknek nevezzük.) A rekordok törlése jelentősen javíthatja az aktuáliskészlet-számítások teljesítményét.

## <a name="what-the-cleanup-job-does"></a>A karbantartási feladat tartalma

Az aktuális készlet bejegyzések karbantartási feladata törli a WHSInventReserve és az InventSum táblák azon rekordjait, amelyeknél az összes mező értéke *0* (nulla). Ezek a rekordok törölhetők, mivel nem járulnak hozzá az aktuális készlet adatokhoz. A feladat csak a **Hely** szintje alatt lévő rekordokat törli.

Ha a negatív tényleges készlet engedélyezve van, előfordulhat, hogy a karbantartási feladat nem tudja törölni az összes szükséges bejegyzést. Ennek a korlátozásnak az az oka, hogy a feladatnak lehetővé kell tennie egy speciális esetet, amikor az azonosítótábla több sorozatszámmal rendelkezik, és az egyik ilyen sorozatszám negatív lett. Például a rendszernek az azonosítótábla szintjén nulla értékkel rendelkezik aktuális készletként, amikor az azonosítótábla +1 darabbal rendelkezik az 1. sorozatszámból és – 1 darabbal a 2. sorozatszámból. Ennél a speciális esetnél a feladat ellőször egy szélességi törlést végez, ahol először az alsó szinteken próbál törölni.

## <a name="schedule-and-configure-the-cleanup-job"></a>A karbantartási feladat ütemezése és konfigurálása

Az aktuális készlet bejegyzések karbantartási feladata a **Készletkezelés \> Időszakos feladatok \> Karbantartás \> Raktárkezelés készleten lévő bejegyzéseinek karbantartása** alatt érhető el. A szokásos feladatok beállításával szabályozhatja a feladat futtatásának a hatókörét és ütemezését. Ezen túlmenően a következő beállítások állnak rendelkezésre:

- **Törlés, ha ennyi napig nem frissült** – Adja meg azt a minimális számú napot, ameddig a feladatnak várnia kell, mielőtt törli a nulla mennyiségere eső aktuális készlet bejegyzést. Ezzel a beállítással csökkentheti a még használatban lévő aktuális készlet bejegyzések törlésének kockázatát. Ha azt szeretné, hogy a karbantartás mielőbb történjen meg, adja meg a *0* (nulla) értéket, vagy hagyja üresen a mezőt.
- **Maximális végrehajtási idő (óra)** – Megadja a karbantartási feladat maximális végrehajtási idejét órában. Ha a feladat a megadott idő elteltével még nem fejeződött be, akkor az addig elvégzett munkát menti, majd lezárja magát. Ez a funkció különösen fontos a magas készlethasználatú megvalósításoknál. Ezekben az esetekben ütemeznie kell a feladatot, hogy időnként fusson, amikor a rendszer terhelése a lehető legkönnyebb. Ha azt szeretné, hogy a kötegelt feladat mindaddig fusson, amíg be nem fejeződik, írjon be *0* (nulla) értéket, vagy hagyja üresen a mezőt. Ez a beállítás csak akkor érhető el, ha a kapcsolódó funkció [be van kapcsolva a rendszerben](#max-execution-time).

Bár a feladat a szokásos munkaidő alatt is futtatható, javasoljuk, hogy a nyitvatartási időn kívül fusson. Ily módon megakadályozhatja az olyan ütközéseket, amelyek akkor merülhetnek fel, ha a felhasználó egy olyan rekordon dolgozik, amelyet a program még tisztít.

Ha a feladat egy elem rekordját próbálja törölni, miközben a rekordot egy másik felhasználó használja, akkor egy holtpont-hibát kap a karbantartási feladat vagy a felhasználó.

A feladat a futtatása esetén 100-as véglegesítési mérettel rendelkezik. Más szóval a program megpróbálkozik egy véglegesítéssel minden 100 törlést követően. Mivel azonban egyes törlések halmazalapúak, előfordulhatnak olyan helyzetek, hogy egy tranzakcióban több mint 100 rekordot lehet törölni. Ennek megfelelően zárolási eszkalációk néha továbbra is előfordulhatnak.

## <a name="possible-user-impact"></a>Lehetséges felhasználói hatás

Előfordulhat, hogy a felhasználók akkor is érintettek lehenek, ha az aktuális készlet bejegyzések karbantartási feladata egy adott szint összes rekordját törli (például az azonosítótábla szintje). Ebben az esetben előfordulhat, hogy a funkció, amely az azonosítótáblán korábban rendelkezésre álló készlet megtekintésére szolgál, nem az elvártaknak megfelelően működik, mivel a releváns aktuális készlet bejegyzések már nem állnak rendelkezésre. (Ez a funkció ellenőrzi a **Mennyiség \<\> 0** feltételt a **Dimenzió megjelenítése** beállításban, amikor a felhasználók aktuális készletre vonatkozó adatokat tekintenek meg.) A karbantartási feladat által biztosított teljesítményjavulás azonban ellensúlyozza ezt a kis funkcióvesztést.

## <a name="make-the-maximum-execution-time-setting-available"></a><a name="max-execution-time"></a>A Maximális végrehajtási idő beállítás elérhetővé tétele

Alapértelmezésben a **Maximális végrehajtási idő** beállítás nem érhető el. Ha használni szeretné, akkor a [funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) használatával be kell kapcsolnia a kapcsolódó funkciót a rendszerében. A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:

- **Modul:** *Raktárkezelés*
- **Funkció neve:** *Raktárkezelés készleten lévő bejegyzései karbantartási feladatának maximális végrehajtási ideje*


[!INCLUDE[footer-include](../../includes/footer-banner.md)]