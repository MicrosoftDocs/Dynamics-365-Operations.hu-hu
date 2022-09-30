---
title: Szállítói minősítés karbantartása
description: Ez a cikk azokat a lépéseket ismerteti, amelyek segítségével a szállítók a szállítói együttműködési munkaterületen karbantartják a tanúsítványukat.
author: TaylorVH
ms.date: 04/27/2021
ms.topic: article
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: TaylorVH
ms.search.validFrom: 2021-02-09
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: c66952d19cddd9d4a9a102ba59e8d6d97b75ed4d
ms.sourcegitcommit: adadbc6e355e2ad68a1f6af26a1be1f89dc8eec6
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/22/2022
ms.locfileid: "9583230"
---
# <a name="maintain-vendor-certification"></a>Szállítói minősítés karbantartása

[!include [banner](../includes/banner.md)]

Ez a cikk azokat a lépéseket ismerteti, amelyek segítségével a **szállítók a szállítói együttműködési munkaterületen karbantartsák a tanúsítványukat**. A minősítési példák között lehet Női üzleti vállalkozás (WBE) vagy Energia- és környezettervezésben vezető (LEED) vállalat. A szállítóknak meg kell adniuk a minősítési információkat a **Szállítói adatok** munkaterületen. Ezután a szállítók kiválasztják a **További részleteket**, majd a **Minősítéseket**.

## <a name="turn-on-the-vendor-certification-feature"></a>Kapcsolja be a szállítóminősítési funkciót

A funkció használata előtt be kell azt kapcsolnia saját rendszerében. A rendszergazdák használhatják a [Funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) oldalt a funkció állapotának ellenőrzéséhez, és szükség esetén engedélyezéséhez. A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:

- **Modul** - *Kötelezettségek*
- **Funkció neve** - *A szállítói együttműködés tanúsítványkezelésének engedélyezése*

## <a name="add-a-new-certification"></a>Új tanúsítvány hozzáadása

Új minősítés hozzáadásához válassza a **Hozzáadás** gombot, amely a **Szállítói adatok** munkaterület **Minősítés** rácsa felett található. Adja meg a következő adatokat:

- Tanúsítvány száma
- Tanúsítvány típusa
- Tanúsító szervezet
- Tanúsítvány dátuma
- Kötelezettség összege, ha szükséges
- Érvényesség dátuma
- Lejárati dátum
- Megjegyzések, választható

Ha az adott minősítéshez dokumentumok kapcsolódnak, akkor a **Dokumentum** gombbal csatolhatja őket.

Az ezen a lapon a szállítók által megadott minősítésekhez a „Szállító” forrást rendeli hozzá a rendszer. A szállító nevében minősítésadatokat lehet megadni a szállító bankszámlái alatt. Az adatok itt jelennek meg, a forrás pedig **Vevőként**.

A szállítók szükség szerint szerkeszthetik vagy törölhetik a minősítésüket.

## <a name="vendor-collaboration-generated-certification-records"></a>Szállítói együttműködéssel generált tanúsítványrekordok

Miután a szállító hozzáadta a tanúsítási információkat, az információk a **Szállítói együttműködéssel generált tanúsítványrekordok** lapon lesznek láthatók. Az oldal megnyitásához lépjen a **Kintlévőségek > Lekérdezések > Szállítói jelentések > Szállítói együttműködés által generált tanúsítványok** menübe. Alapértelmezés szerint minden új vagy módosított tanúsítási rekord látható. A kötelezettségekért felelős ügyintéző megtekintheti a változásokat, és érvényesítheti az információkat a megerősítési folyamaton keresztül. Az információ megerősítésekor az oldalon szereplő tanúsítási rekord kiválasztható és felülvizsgáltként megjelölhető. A rekord ellenőrzöttként való megjelölése eltávolítja azt az alapértelmezett listáról.

Az összes tanúsítási módosítás látható a **Szállítói együttműködés által generált tanúsítványok** lapon. Ha egy módosítás nem jelenik meg az oldalon, megtekintheti szűrők módosításával, a szállítói számla, tényleges dátumtartomány értékre vagy annak kiválasztásával, hogy a felülvizsgált tanúsítási módosítások információi szerepeljenek.

