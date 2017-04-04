---
title: "Számlaegyeztetés és vállalatközi beszerzési rendelések"
description: "A vállalatközi kereskedelmi tranzakcióban érintett vásárló jogi személyt be kell állítani a kötelezettségek számlaegyeztetésének használatához. Ilyenkor a feladási követelményeknek a vállalatközi kereskedelemre és a kötelezettségek számlaegyeztetésre egyaránt teljesülnie kell a vállalatközi szállítói számlák feladása előtt."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: PurchLineMatchingPolicy
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3101
ms.assetid: 9c7c2e44-45f8-4325-b6de-a09fe790f9cf
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 45d0b24ed0a79176803a6efefc216f7e30fec86c
ms.lasthandoff: 03/31/2017


---

# <a name="invoice-matching-and-intercompany-purchase-orders"></a>Számlaegyeztetés és vállalatközi beszerzési rendelések

A vállalatközi kereskedelmi tranzakcióban érintett vásárló jogi személyt be kell állítani a kötelezettségek számlaegyeztetésének használatához. Ilyenkor a feladási követelményeknek a vállalatközi kereskedelemre és a kötelezettségek számlaegyeztetésre egyaránt teljesülnie kell a vállalatközi szállítói számlák feladása előtt.

A példák ebben a témában a vállalatközi kereskedelem következő beállításait használják:
-   A vásárló gyár a vásárló jogi személy.
-   A vásárló gyár az eladó jogi személy.
-   A 4020-as vevő az Értékesítő Gyár nyilvántartásában szerepel.
-   A 3024-es szállító a Vásárló Gyár nyilvántartásában szerepel.
-   A Fabrikam beszerzés vállalatközi adatainak szállító 3024 van megadva. A Fabrikam eladás a vevő vállalat van megadva, és a vevő 4020 van megadva a vevői számla, amely megfelel a Fabrikam beszerzési jogi személy.
-   Vállalatközi információk a Fabrikam eladás, vevő 4020 van megadva. A Fabrikam beszerzési a szállító vállalat van megadva, és a szállító 3024 van megadva a szállítói számlát, amely megfelel a Fabrikam értékesítési jogi személy.

A példák a kötelezettségek és számlaegyeztetés következő beállításait használják a vásárló gyárnak:
-   A kötelezettségek paraméteroldalon a számlaegyeztetés engedélyezése ellenőrzési opció ki van jelölve.
-   A kötelezettségek paraméteroldalon a számlafeladás eltérésekkel mezőben a Jóváhagyás szükséges van kijelölve.
-   A százalékos ártűréshatár a jogi személynek 2 százalék.

## <a name="example-price-matching-and-intercompany-trade"></a> Példa: áregyeztetés és vállalatközi kereskedelem
A vállalatközti szállító számláján és a vállalatközti vevő számláján szereplő nettó összegeknek egyenlőnek kell lenniük. Ez a követelmény felülbírál minden számlaegyeztetés jóváhagyást, vagy százalékos ártűréshatárt, ami érvényben van. Ha például ezeket a lépéseket követi.
1.  A Fabrikam beszerzési értékesítési rendelés SO888 vevő 4020. Vállalatközi beszerzési rendelés ICPO222 automatikusan létrejön a szállító 3024 a Fabrikam beszerzési és értékesítési rendelés ICSO888 automatikusan létrehozza a Fabrikam értékesítési.
2.  Az értékesítő gyárban jegyezze be, hogy a cikkek átvételre kerültek és adjon fel egy szállítólevelet. Az ICSO888 rendelés Leszállított állapotúvá válik. Az ICPO222 rendelés Beérkezett állapotúvá válik.
3.  Az értékesítő gyárban hajtson végre egy számlafrissítést az ICSO888 megrendeléshez. Az egységár 0,45, és 100 cikken történik a frissítés.
4.  A vásárló gyárban hozzon létre egy számlát az ICPO222 megrendeléshez. Véletlenül 45,00-ről 54,00-re módosítja a nettó összeget. Megjelenik egy ikon, hogy jelezze, hogy az ár meghaladja a megengedhető 2 százalékos ártűréshatárt.
5.  A számlaegyeztetés részletei lapon jelölje ki feladás engedélyezése egyeztetési eltérésekkel opciót. A szállítói számla lapon kattintson az OK gombra. Ha a szállítói számla nem egy vállalatközi szállító számlája lenne, akkor a feladás sikeres lenne. Azonban mivel vállalatközi szállítói számlával dolgozik a feladás sikertelen. A vállalatközi kereskedelemhez a vállalatközi értékesítési rendelés számlaösszegeinek egyenlőnek kell lennie a megfelelő vállalatközi beszerzési rendelés számlaösszegeivel. A probléma megoldásához a számla nettó árát vissza kell állítania a nettó ár alapértelmezett, 45,00 értékére.

## <a name="example-quantity-matching-with-intercompany-trade"></a> Példa: Mennyiségegyeztetés vállalatközi kereskedelemben
A vállalatközi beszerzési rendelésen és a vállalatközi értékesítési rendelésen szereplő mennyiségeknek egyenlőnek kell lenniük. Ez a követelmény minden számlaegyeztetési jóváhagyást felülbírál. Ez a példa a következő további vállalatközi kereskedelmi beállításokat használja:
-   A vásárló gyárban a beszerzési rendelés működési irányelve a 3024-es szállítóhoz úgy vagy beállítva, hogy automatikusan számlázza mind az eredetei vevői számlát és a vállalatközi szállítói számlát.

Ez a példa a következő további beállításokat használja a vásárló gyár kötelezettségeihez és számlaegyeztetéséhez:
-   A modellcsoport cikkmodellcsoportok oldalán, amelyet a B-R14 cikk használ a bevételezési követelmények opció ki van jelölve.
-   A B-R14 cikk aktuális készlete 0 (nulla).

Ha például ezeket a lépéseket követi.
1.  A Fabrikam beszerzési értékesítési rendelés SO999 vevő 4020. A rendelés egy tételt tartalmaz: az egyes 1,00 egység ára 100 akkumulátorok (B-r 14. cikk). Az ICPO333 vállalatközi beszerzési megrendelés automatikusan létrejön a 3024-es vevőhöz a vásárló gyárban és az ICSO999 értékesítési rendelés automatikusan létrejön az értékesítő gyárban.
2.  Az értékesítő gyárban hajtson végre egy számlafrissítést az ICSO999 megrendeléshez. A feladás sikertelen, mert a cikk nincs készleten és még nem érkezett meg. Emiatt a pénzügyi adatokat nem lehet frissíteni.
3.  Az értékesítő gyárban jegyezze be, hogy a cikkek megérkeztek és adjon fel egy szállítólevelet az ICSO999 megrendeléshez. Az ICPO333 megrendeléshez tartozó termékbevételezés automatikusan feladásra kerül a vásárló gyárban. A vásárló gyárban az átvett mennyiség a B-R14-e cikkhez 100-ra vált.
4.  Az értékesítő gyárban hajtson végre egy számlafrissítést az ICSO999 megrendeléshez. A feladás mindkét jogi személynél sikeres. A vásárló gyárban a vásárolt termékmennyiség a B-R14-es cikkhez 100-ra vált. 




