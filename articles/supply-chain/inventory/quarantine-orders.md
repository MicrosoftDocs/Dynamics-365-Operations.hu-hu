---
title: "Karanténutasítások"
description: "Ez a témakör bemutatja, hogy a karanténutasításokat hogyan lehet a készlet blokkolására használni."
author: perlynne
manager: AnnBe
ms.date: 11/02/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventLocation, InventModelGroup, InventQuarantineOrder, InventQuarantineParmEnd, InventQuarantineParmReportFinished, InventQuarantineParmStartUp, InventTrans
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 30021
ms.assetid: d5047727-653c-49da-b489-6fd3fe50445e
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 515f14e72137f7299093cc6e75cb8e6eec2893fb
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="quarantine-orders"></a>Karanténutasítások

[!INCLUDE [banner](../includes/banner.md)]

Ez a témakör bemutatja, hogy a karanténutasításokat hogyan lehet a készlet blokkolására használni.

A karantén-utasítások használhatóak a készlet blokkolására. Például lehet, hogy minőség-ellenőrzési okok miatt szeretne karanténba tenni cikkeket. A karanténba helyezett készlet át lesz szállítva egy karantén raktárba. **Megjegyzés:** Ha speciális raktárkezelési folyamatokat használ (a Raktárkezelésben), a karantén utasítás feldolgozása csak értékesítési visszáru-rendeléseknél lesz használva.

## <a name="quarantine-on-hand-inventory-items"></a>Aktuálisan készleten lévő cikkek karanténba helyezése
Cikkek karanténba helyezésekor létrehozhatja a karanténutasításokat manuálisan, vagy beállíthatja a rendszert, hogy automatikusan hozza létre a karantén utasításokat a bejövő feldolgozás során. Karantén-utasítások automatikus létrehozásához válassza ki a **Karantén kezelése** lehetőséget a **Készletre vonatkozó irányelvek** fülön a **Cikkmodellcsoportok** lapon. Az alapértelmezett karantén raktárt is meg kell adnia a **Karantén raktár** mezőben, a fogadó raktár esetén. Amikor az aktuális készlet rögzítve lesz egy beszerzési rendelésben vagy termelési rendelésben, a karanténba helyezett cikkek automatikus egy karanténraktárba kerülnek a Microsoft Dynamics 365 for Finance and Operations rendszerben. Ez a mozgás akkor következik be, a karantén rendelés állapota felveszi a következő értéket: **Elindítva**. Amikor manuálisan hoz létre karanténutasításokat, akkor nincs rá szükség, hogy az aktuális cikkhez be legyen állítva a karantén kezelés a társított cikkmodellcsoportban. Ehhez a folyamathoz meg kell határoznia a karanténozásra váró aktuális készletet, valamint a használni kívánt karantén raktárt. A folyamat megtervezéséhez használhatja a karanténutasítás állapotokat.

## <a name="quarantine-order-statuses"></a>Karanténutasítás-állapotok
A karanténutasítások a következő állapotúak lehetnek:

-   Létrehozva
-   Elkezdve
-   Készként jelentve
-   Befejezve

### <a name="created"></a>Létrehozva

Ha egy karanténutasítást manuálisan hoztak létre, de a cikk még nincs a karantén raktárban, akkor a karanténutasítás állapota **Létrehozott**. Két készlettranzakció jön létre. Az egyik tranzakció egy kiadási tranzakció, amelynek az állapota lehet **Megrendelt**, **Foglalt tényleges**, vagy **Kitárolt**. A második pedig egy bevételezési tranzakció, amely a **Megrendelt** vagy **Regisztrált** állapotokkal rendelkezhet a karantén raktárban. A szokásos folyamatokkal végezheti a lefoglalását, a kitárolást és a készlet frissítésének regisztrálást.

### <a name="started"></a>Elkezdve

Ha egy karanténutasítás állapota **Elindítva** a készlet átkerül a szokásos raktárból a karanténraktárba, és létrejön két készlettranzakció. Az egyik tranzakció állapota **Levonva**, a másik tranzakció állapota pedig **Bevételezett**. Ugyanakkor két olyan készlettranzakció is létrejön, amelyek a visszáru-átvezetés kezelését szolgálják. Ezek a tranzakciók nem dátumhoz kötöttek. Az egyik tranzakció állapota **Foglalt tényleges**, a másik tranzakció állapota pedig **Megrendelt**.

### <a name="reported-as-finished"></a>Készként jelentve

A **Jelentés készként** parancsra kattintva jelentheti, hogy egy elindított karanténutasítás befejeződött. A cikk felszabadul a karanténból, de még nem kerül vissza a szokásos raktárba. A visszamozgatást az eredeti raktárba egy cikkbeérkezési naplón keresztül lehet feldolgozni, amelyet a Jelentés során lehet befejezett folyamatként inicializálni.

### <a name="ended"></a>Befejezve

Egy karanténutasítás befejezésekor, a cikk a karantén raktárból visszakerül a rendes raktárba. A cikktranzakció állapota **Eladva** a karanténraktárban és **Beszerezve** a rendes raktárban.

## <a name="quarantine-order-scrap"></a>Karanténutasítás-selejt
A karanténutasítási folyamat részeként lehetséges a készlet selejtezése. A selejt feldolgozásakor a készlet állapota **Értékesítve** lesz, a karantén raktárból származó kiadási tranzakció által.

<a name="see-also"></a>Lásd még
--------

[Készletzárolás](inventory-blocking.md)

