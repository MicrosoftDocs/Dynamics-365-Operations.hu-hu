--- 
title: "Bizományosi készlet tulajdonosának módosítása gyártási igény alapján"
description: "Ez az eljárás bemutatja, hogyan módosítható a bizományosi készlet tulajdonosa a szállítóról a jogi személyére, amikor a készletre gyártási igény van."
author: perlynne
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventJournalOwnershipChange, InventJournalCreate
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 5925f5423d596adc4326dfff4734de2afd80b5a8
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="change-the-ownership-of-consignment-inventory-based-on-production-demand"></a>Bizományosi készlet tulajdonosának módosítása gyártási igény alapján

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogyan módosítható a bizományosi készlet tulajdonosa a szállítóról a jogi személyére, amikor a készletre gyártási igény van. A tulajdonjog-változás készlettulajdonos-változási napló létrehozásával és feladásával történik. A tulajdonosváltozási napló sorai létrehozhatók manuálisan, illetve, ahogy az a felvételen látható, meglévő gyártási igény alapján is. Ezt a feladatot általában egy üzemirányítási felügyelő végzi el. Ezt a folyamatot az USMF bemutatócégnél vagy a saját adataiban is használhatja. Saját adatok használatakor győződjön meg arról, hogy teljesíti a következő előfeltételeket: be van állítva egy készletnaplónév, amely be van állítva a készlet tulajdonjog-változásához, vannak fizikailag rögzített szállító tulajdonában lévő aktuális készletelemek, és egy vagy több gyártási rendelés sor az anyaghoz. Ez az eljárás egy olyan funkcióra vonatkozik, amely a Dynamics 365 for Operations 1611-es verziójába került be.


## <a name="create-an-inventory-ownership-journal"></a>Készlettulajdonosi napló létrehozása
1. Lépjen a Készletgazdálkodás > Naplóbejegyzések > Cikkek > Készlet tulajdonosváltozása elemre.
2. Kattintson az Új lehetőségre.
    * A készlettulajdonos-változási naplót a bizományosi készlet tulajdonosának módosítására használjuk a szállítóról az aktuális jogi személyre. A tulajdonjog-változás úgy történik, hogy feloldjuk a szállító tulajdonában álló aktuális készletet, majd bevételezzük a készletet az aktuális jogi személy számára.  
3. A Név mezőben adjon meg vagy válasszon ki egy értéket.
    * Csak az olyan készletnaplónevek választhatók ki, amelyeknek a naplótípusa Tulajdonosváltozás.  
4. Kattintson az OK gombra.
5. Kattintson a Funkciók elemre.
6. Kattintson a Naplósorok létrehozása termelési rendelésekből elemre.
    * A tulajdonjog módosítása folyamat az összes olyan gyártósor lekérdezésével indítható, amelyeknek nyersanyag-felhasználás iránti igénye van.  
7. A Befoglalandó készletkiadási állapotok mezőben válasszon egy beállítást.
    * Ez a beállítás lehetővé teszi a szűrést a készlettranzakciók kiadási állapota alapján. Létrehozhatók például naplósorok olyan készlethez, amelynek a fizikai állapota Kitárolva és Lefoglalva.  
8. Bontsa ki a Szerepeltetni kívánt rekordok szakaszt.
    * Ez a rész további szűrést tesz lehetővé. Kiválasztható például egy bizonyos nyersanyag dátuma.  
9. Kattintson az OK gombra.

## <a name="post-the-inventory-ownership-change-journal"></a>Készlettulajdonos-változási napló feladása
1. Kattintson a Feladás lehetőségre.
    * A napló feladásakor megtörténik a szállító tulajdonában lévő készlet felszabadítása egy „Tulajdonosváltozás” hivatkozás segítségével. Ezután megtörténik a készlet érkeztetése aktuális készletként egy készlettranzakcióval, amely egy beszerzési rendelés termékbevételezéssel frissül. Vegye figyelembe, hogy csak a feladott naplóval kapcsolatos tranzakciók jönnek létre. Nem jönnek létre várt készlettranzakciók.  
2. Kattintson az OK gombra.
3. Zárja be a lapot.


