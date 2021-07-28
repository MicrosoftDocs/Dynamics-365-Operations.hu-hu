---
title: Ürítési elvek
description: Ez a témakör azt a négy ürítési elvet mutatja be, amelyeket a nyersanyag-fogyasztásnál használ a rendszer.
author: johanhoffmann
ms.date: 04/04/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgShopSupervisorReleaseOrders
audience: Application User
ms.reviewer: kamaybac
ms.custom: 221264
ms.assetid: dde49743-1541-4353-a030-63ca3069cd7d
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 360172b8029faf128e9ab7e4eb34dfbed3cb3e21
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2021
ms.locfileid: "6354036"
---
# <a name="flushing-principles"></a>Ürítési elvek

[!include [banner](../includes/banner.md)]

Az ürítési elvek a termelési folyamatokban használt nyersanyagok különböző fogyasztási stratégiáit tükrözik. A fogyasztás az a folyamat, amely levonja az anyagot a készletből és az elhasznált anyagok értékét a gyártási rendelések és kötegelt rendelések esetében **Folyamatban lévő** (WIP) értékre állítja. A nyersanyagokat általában olyan helyről fogyasztják el, amely az anyagot elhasználó folyamat számára készült. Ezt a helyet a termelési bemeneti helynek is nevezik.

Az anyagfelhasználás előtt az anyagokat áthelyezik a beviteli helyre. Az alábbi ábra bemutatja a folyamatot.

[![scenario4a.](./media/scenario4a.png)](./media/scenario4a.png)

1. Nyersanyagraktár
2. Nyersanyag kitárolása
3. Termelések beérkezési helye
4. Nyersanyagfelhasználás
5. Termelési folyamat

A nyersanyagfogyasztás kezelése az alábbi ürítési elvek használatával történik:

- Manuális
- Eleje
- Elvégzés
- Rendelkezésre áll a helyen

Az ürítési elvek az alapértelmezett értékek hierarchiájában vannak beállítva. A hierarchia a kiadott terméknél kezdődik, ahol az ürítési elv értéke **Start**. Az anyagjegyzéken (BOM) vagy receptúrasoron a termék ürítési elve felülbírálható. Az alapértelmezett ürítési elv a termelési BOM sorokon vagy a kötegelt sorrendű sorokon a termék vagy a felülbírált érték a BOM-ban vagy képletekből származik.

## <a name="description-of-the-flushing-principles"></a>Az ürítési elvek leírása

### <a name="manual"></a>Manuális
A manuális ürítési alapelv azt jelzi, hogy a nyersanyag-felhasználásának regisztrálása kézi művelet. Ezt az elvet jelentősége, ha például szeretné lehet nyomon követni az idő, és a felhasznált köteg- vagy sorozatszámok mennyiségét figyelembe kell venni, nyomon követési célokkal. A kézi fogyasztás regisztrálva van egy termelési kitárolási listán. A speciális raktárkezelési folyamatok számára engedélyezett cikkek esetében a kézi folyamat alkalmazhatók.

### <a name="start"></a>Eleje
Ürítési alapelv kezdő azt jelzi, hogy anyag fog kell felhasználása automatikusan a termelési rendelés indításakor. A felhasznált anyag mérete arányos a megkezdett mennyiség. Ürítési alapelv kezdő és a Gyártásvégrehajtás használatakor a rendszer, is használható, amikor egy művelet anyagok ürítése, vagy egy feldolgozási feladat elindítva. Ezt az elvet jelentősége, ha, például az eltérés felhasználási hamarosan lemerül, az anyagok alacsony értékű anyagok, nincsenek nyomon követési követelmények, vagy nincs rövid futási idő műveletek. 

### <a name="finish"></a>Elvégzés
A Befejezés ürítési alapelv azt jelzi, hogy anyag fog kell felhasználása automatikusan a termelési rendelés készként való jelentése, vagy egy olyan művelet, amely be van állítva az anyagok felhasználása legfeljebb regisztrálja befejezettként. A felhasznált anyag mérete arányos az elkészült mennyiséggel. Ürítési alapelv befejező és a gyártásvégrehajtás használatakor a rendszer, is használható, amikor egy művelet anyagok ürítése, vagy egy feldolgozási feladat befejezve. Ez az elv ugyanazoknál a szituációknál lényeges, mint az Indítási elv. A Befejezés elv viszont a műveletek, amelyekhez már futási idő, ahol anyagok nem kell beállítani folyamatban lévő munka a művelet befejezése előtt. 

### <a name="available-at-location"></a>Rendelkezésre áll a helyen
Rendelkezésre álló hely kiürítési elvét, azt jelzi, hogy az anyag lesz automatikusan felhasználandó regisztrálásakor, valamint a termelés. Az anyag regisztrálva van, valamint a helyről munka a nyersanyag kitárolása befejeződött, vagy ha anyag érhető el a termelési bemeneti hely és az anyagjegyzéksorban ki van adva a raktárba. A kitárolási lista, amely a folyamat során létrejön egy kötegelt feladatban feladása. Ezt az elvet jelentősége, ha például egy termelési rendeléssel szembeni több kitárolási tevékenységek vannak beállítva. Ebben az esetben nem kell manuálisan a kitárolási lista frissítése, és letöltheti a folyamatban lévő munka egyenlegű aktuális nézetét.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]