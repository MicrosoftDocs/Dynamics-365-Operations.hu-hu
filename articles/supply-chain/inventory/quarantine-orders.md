---
title: Karanténutasítások
description: Ez a témakör a karanténutasítások készletzárlatokkal való használatát ismerteti.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventLocation, InventModelGroup, InventQuarantineOrder, InventQuarantineParmEnd, InventQuarantineParmReportFinished, InventQuarantineParmStartUp, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 30021
ms.assetid: d5047727-653c-49da-b489-6fd3fe50445e
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7e18735117d1f671e0efc0947248bbe266fa0ca6
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/29/2022
ms.locfileid: "9065585"
---
# <a name="quarantine-orders"></a>Karanténutasítások

[!include [banner](../includes/banner.md)]

Ez a témakör a karanténutasítások készletzárlatokkal való használatát ismerteti.

A karanténutasításokkal blokkolhatja a készletet. Például lehet, hogy minőség-ellenőrzési okok miatt szeretne karanténba tenni cikkeket. A karanténba helyezett készlet át lesz szállítva egy karantén raktárba.

> [!NOTE]
> Ha raktárkezelési folyamatokat használ (a Raktárkezelés modulban), a karanténutasítás feldolgozása csak visszárurendelések esetén használatos.

## <a name="quarantine-on-hand-inventory-items"></a>Aktuálisan készleten lévő cikkek karanténba helyezése

Cikkek karanténba helyezésekor létrehozhatja a karanténutasításokat manuálisan, vagy beállíthatja a rendszert, hogy automatikusan hozza létre azokat a bejövő feldolgozás során.

A következő lépések szerint állítsa be a rendszert a karanténutasítások automatikus előállítására.

1. Ugorjon a **Készletkezelés \> Beállítás \> Készlet \> Cikkmodellcsoportok** pontra.
1. Válasszon ki egy kapcsolódó modellcsoportot a listapanelen, vagy hozzon létre egy új modellcsoportot.
1. A **Készletszabályok** gyorslapon jelölje be a **Karantén kezelése** jelölőnégyzetet.
1. Zárja be a lapot.
1. Az alapértelmezett karantén raktárt is meg kell adnia a **Karantén raktár** mezőben, a fogadó raktár esetén.

Ha egy, a raktárban bevételként regisztrált cikk olyan modellcsoportba tartozik, amelyben be van jelölve a **Karanténkezelés** jelölőnégyzet, akkor a rendszer létrehoz hozzá egy karanténutasítást. A karanténutasítás arra utasítja a dolgozókat, hogy helyezzék át a cikket a karanténraktárba.

Amikor manuálisan hoz létre karanténutasításokat a **Karanténutasítások** oldalon, akkor nincs rá szükség, hogy az aktuális cikkhez be legyen állítva a karantén kezelés a társított cikkmodellcsoportban. Ehhez a folyamathoz meg kell határoznia a karanténozásra váró aktuális készletet, valamint a használni kívánt karantén raktárt. A folyamat megtervezéséhez használhatja a karanténutasítás állapotokat.

## <a name="quarantine-order-statuses"></a>Karanténutasítás-állapotok

A karanténutasítások a következő állapotúak lehetnek:

- Létrehozva
- Elkezdve
- Készként jelentve
- Befejezve

### <a name="created"></a>Létrehozva

Ha egy karanténutasítást manuálisan hoztak létre, de a cikk még nincs a karantén raktárban, akkor a karanténutasítás állapota **Létrehozott**. Két készlettranzakció jön létre. Az egyik tranzakció egy kiadási tranzakció, amelynek az állapota lehet **Megrendelt**, **Foglalt tényleges**, vagy **Kitárolt**. A második pedig egy bevételezési tranzakció, amely a **Megrendelt** vagy **Regisztrált** állapotokkal rendelkezhet a karantén raktárban. A szokásos folyamatokkal végezheti a lefoglalását, a kitárolást és a készlet frissítésének regisztrálást.

### <a name="started"></a>Elkezdve

Ha egy karanténutasítás állapota **Elindítva** a készlet átkerül a szokásos raktárból a karanténraktárba, és létrejön két készlettranzakció. Az egyik tranzakció állapota **Levonva**, a másik tranzakció állapota pedig **Bevételezett**. Ugyanakkor két olyan készlettranzakció is létrejön, amelyek a visszáru-átvezetés kezelését szolgálják. Ezek a tranzakciók nem dátumhoz kötöttek. Az egyik tranzakció állapota **Foglalt tényleges**, a másik tranzakció állapota pedig **Megrendelt**.

### <a name="reported-as-finished"></a>Készként jelentve

Ha egy elindított karanténutasítást készként szeretne jelenteni, nyissa meg a rendelést, és válassza a műveletpanel **Készként jelentés** elemét. A cikk felszabadul a karanténból, de még nem kerül vissza a szokásos raktárba. A visszamozgatást az eredeti raktárba egy cikkbeérkezési naplón keresztül lehet feldolgozni, amelyet a jelentés során lehet befejezett folyamatként inicializálni.

### <a name="ended"></a>Befejezve

Egy karanténutasítás befejezésekor, a cikk a karantén raktárból visszakerül a rendes raktárba. A cikktranzakció állapota *Eladva* a karanténraktárban és *Beszerezve* a rendes raktárban.

## <a name="quarantine-order-scrap"></a>Karanténutasítás-selejt

A karanténutasítási folyamat részeként lehetséges a készlet selejtezése. A selejt feldolgozásakor a készlet állapota *Értékesítve* lesz, a karantén raktárból származó kiadási tranzakció által.

## <a name="additional-resources"></a>További erőforrások

- [Készletzárolás](inventory-blocking.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
