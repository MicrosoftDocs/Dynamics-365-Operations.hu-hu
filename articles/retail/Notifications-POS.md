---
title: "Rendelési értesítések megjelenítése a pénztárban"
description: "Ez a témakör ismerteti, hogyan lehet engedélyezni a rendelési értesítéseket a pénztárban és az értesítési keretrendszerben, amely egyéb műveletekhez is bővíthető."
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: 
ms.search.region: Global
ms.author: ShalabhjainMSFT
ms.search.validFrom: 2017-10-30
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: ec6cb212766dd90fa9db7719a2119419ecb935c7
ms.openlocfilehash: aea36591a81f727059e37a958efa62a9ebde9d9d
ms.contentlocale: hu-hu
ms.lasthandoff: 12/20/2017

---

# <a name="display-notifications-in-point-of-sale"></a>Értesítések megjelenítése a pénztárban

A mai modern kiskereskedelmi környezetben az üzlet munkatársai különböző feladatokat látnak el, például segítenek a vevőknek, beviszik a tranzakciókat, leltáraznak és rendeléseket fogadnak az üzletben. A pénztár (POS) ügyfél lehetővé teszi a munkatársak számára, hogy elvégezzék ezeket a feladatokat és még sok minden mást is, egyetlen alkalmazásban. A nap folyamán végrehajtandó különböző feladatok miatt szükség lehet a munkatársak értesítésére, amikor valami figyelmet igényel. A pénztár értesítési keretrendszere megoldja ezt a problémát azáltal, hogy a kiskereskedőknek szerepköralapú értesítések beállítását teszi lehetővé. A Dynamics 365 for Retail 5. alkalmazásfrissítésétől ezek az értesítések csak pénztárműveletekhez konfigurálhatók.

Jelenleg a rendszer a rendelésteljesítési művelet értesítéseinek megjelenítését teszi lehetővé, azonban a keretrendszert bővíthetőnek terveztük, vagyis a jövőben a fejlesztők elkészíthetnek egy értesítéskezelőt minden művelethez, és az értesítések megjeleníthetők lesznek a pénztáron.  

## <a name="enable-notifications-for-order-fulfillment-operations"></a>A rendelésteljesítési műveletek értesítéseinek engedélyezése

A rendelésteljesítési műveletek értesítéseinek engedélyezéséhez hajtsa végre a következő lépéseket:

 - Nyissa meg a **Műveletek** lapot (**Kiskereskedelem** > **Csatorna beállítása** > **POS beállítása** > **POS** > **Műveletek**).
 - Keresse meg a Rendelésteljesítés műveletet, és válassza ki az **Értesítések engedélyezése** jelölőnégyzetet ehhez a művelethez. Ez jelzi az értesítési keretrendszernek, hogy figyelje a kezelőt a rendelésteljesítési műveletre nézve. Ha a kezelő telepítve van, az értesítés megjelenik a pénztáron, ellenkező esetben az értesítés nem fog megjelenni a művelethez.
- Menjen a dolgozókhoz kapcsolódó POS-engedélyekhez, és az **Értesítések** gyorslapon adja meg a rendelés teljesítése műveletet 1-es értékű „Megjelenítési sorrenddel”. Ha egynél több értesítés van konfigurálva, a megjelenítési sorrend rendezi el az értesítéseket felülről lefelé, ahol az 1 van legfelül. Csak azok a műveletek adhatók hozzá, amelyhez az **Értesítések engedélyezése** jelölőnégyzet be van jelölve. Emellett az értesítések csak az itt hozzáadott műveletekhez jelennek meg, és csak azoknak a munkatársaknak, akikél a műveletek hozzá lettek adva a megfelelő POS-engedélyekhez. 

> [!NOTE]
> Az értesítések felülbírálhatók a felhasználó szintjén: ehhez nyissa meg a dolgozói rekordot, majd válassza ki a **POS-engedélyek** elemet, majd szerkessze az adott felhasználói értesítés-előfizetést.

 - Ugorjon a **Funkcióprofil** lapra (**Kiskereskedelem** > **Csatorna beállítása** > **POS beállítása** > **POS profilok** > **Funkcióprofilok**). Frissítse az **Értesítési időköz** tulajdonságot annak az intervallumnak a beállításához (percben), amennyi időnként le kell kérni az értesítéseket. Azt ajánljuk, hogy azért, hogy elkerülje a szükségtelen kapcsolatba lépést a központtal, 10 perces értéket állítson be. Az értesítéseket kikapcsolja, ha az értesítési intervallum beállítása „0”.  

 - Lépjen a **Kiskereskedelem** > **Kiskereskedelem IT** > **Elosztási ütemezés** pontra. Válassza az „1060-Staff” lehetőséget az értesítési előfizetési beállítások szinkronizálásához, és kattintson a **Futtatás most** elemre. Ezután szinkronizálja az engedélyintervallumot az „1070-Channel configuration” kiválasztásával, és kattintson a **Futtatás most** elemre. 

## <a name="view-notifications-in-pos"></a>Értesítések megtekintése a pénztárban

A fenti lépések befejezése után a dolgozók, akiknek az értesítések be vannak állítva, megtekinthetik az értesítéseket a pénztárban. Az értesítés megtekintéséhez kattintson a pénztár üzenetsorán található értesítés ikonra. Megjelenik az értesítési központ a rendelésteljesítési művelethez tartozó értesítésekkel. Az értesítési központnak a rendelésteljesítési műveletben a következő csoportokat kell megjelenítenie: 

- **Függő rendelések** – Ez a csoport jeleníti meg a függő állapotban levő rendelések számát, például azokat a rendeléseket, amelyeket el kell fogadnia a POS-dolgozónak, és rendelkeznek a megfelelő engedélyekkel a üzletben való teljesítéshez. A csoportban a számra kattintva megnyílik a **Rendelésteljesítés** oldal, a szűrés miatt csak a függőben lévő rendelések jelennek meg, amelyek az üzlethez való teljesítésre vannak kijelölve. Ha az üzlet automatikusan elfogadja a rendeléseket, ennek a csoportnak a számlálója nulla lesz.

- **Átvétel az üzletben** – Ebben a csoportban azoknak a megrendeléseknek a száma jelenik meg, amelyeknél a szállítási mód az **Átvétel**, és az átvétel az aktuális üzlethez van ütemezve. A csoportban a számra kattintva megnyílik a **Rendelésteljesítés** oldal, a szűrés miatt csak az aktív rendelések jelennek meg, amelyek az üzletben való átvételre vannak kijelölve.

- **Szállítás az üzletből** – Ebben a csoportban azoknak a megrendeléseknek a száma jelenik meg, amelyeknél a szállítási mód a **Szállítás**, és a szállítás az aktuális üzletből van ütemezve. A csoportban a számra kattintva megnyílik a **Rendelésteljesítés** oldal, a szűrés miatt csak az aktív rendelések jelennek meg, amelyek az üzletből való szállításra vannak kijelölve.

Amikor új rendelések vannak teljesítésre az üzlethez társítva, az értesítési ikon megváltozik, hogy jelezze az új értesítéseket, és a megfelelő csoportok száma frissülni fog. A felhasználó a művelet neve melletti frissítési ikonra is kattinthat, és így azonnal frissítheti a csoportok számát. A számlálót a rendszer az előre meghatározott időközönként is frissíti. Bármely csoport, amely rendelkezik egy új elemmel, amelyet az aktuális dolgozó még nem látott, égő ikont jelenít meg azt jelezve, hogy a csoport rendelkezik egy új elemmel. Az értesítéseken belül a csempékre kattintva megnyílik az a művelet, amelyhez az értesítést konfigurálták. A fenti esetekben az értesítésekre kattintva megnyílik a **Rendelésteljesítés** lap a megfelelő paraméterekkel: függő rendelések, átvétel az üzletben és szállítás az üzletből. 

> [!NOTE]
> A függő rendelésekre vonatkozó értesítések funkció a Dynamics 365 for Retail egyik későbbi frissítésével válik elérhetővé. 


