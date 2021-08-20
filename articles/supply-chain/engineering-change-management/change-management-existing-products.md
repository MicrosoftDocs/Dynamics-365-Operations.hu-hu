---
title: Változáskezelés engedélyezése meglévő termékek esetében
description: Ez a témakör azt mutatja be, hogyan lehet engedélyezni a változáskezelést a meglévő termékeknél. Azokat az eseteket is leírja, amelyekben a változáskezelés engedélyezése korlátozott.
author: t-benebo
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-05-02
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 2fd3d2e4f4c3e53913bd811728b0950c63b38bc5afe6fe5282b4cfb05f414619
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6744178"
---
# <a name="enable-change-management-on-existing-products"></a>Változáskezelés engedélyezése meglévő termékek esetében

[!include [banner](../../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet engedélyezni a változáskezelést a meglévő termékeknél. Azokat az eseteket is leírja, amelyekben a változáskezelés engedélyezése korlátozott.

Ha engedélyezi egy meglévő termék változáskezelését, létrehozhatja az adott termék verzióit, és nyomon követheti az egész élettartamán keresztül végrehajtott módosításokat. Ebből következően a módosítási utasítások segítségével nyomon követheti a változásokat. A változáskezelés engedélyezéséhez a megfelelő termékeket *tervezési cikkekké* (más néven tervezési termékekké) kell alakítania. A tervezési termékek olyan termékek, amelyek verziószámozva vannak, és változáskezeléssel kezelik őket. A varázsló végigvezeti az átalakítási folyamaton.

## <a name="turn-on-the-feature-in-your-system"></a>A funkció bekapcsolása a rendszerben

A képesség használatához az alábbi feladatokat kell elvégeznie:

1. Engedélyezze a Tervezési változáskezelés funkciót és a konfigurációs kulcsát a [Tervezési változáskezelés áttekintése](product-engineering-overview.md) részben leírtak szerint.
1. Kapcsolja be a *Változáskezelés engedélyezése meglévő termékek esetében* funkciót a funkciókezelésben. További tájékoztatás: [Funkciókezelés – áttekintés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="restrictions-and-limitations"></a>Korlátozások és korlátok

Nem minden terméktípus konvertálható az összes többi típusra. A következő korlátozások és korlátok érvényesek:

- Amikor egy terméket tervezési termékké alakít át, az *termék* marad. Nem válik *alaptermékké*.
- Ha olyan alapterméket alakít át, amely meghatározott dimenziókészlettelrendelkezik, a program a módosítás után megtartja ezeket a dimenziókat. Ha például olyan alapterméket konvertál, amely méretdimenzióval rendelkezik, akkor megtartja a méretdimenziót.

Ezért ha egyedi terméke van, akkor csak olyan mérnöki termékre lehet módosítani, amely nem követi nyomon a termékdimenziót a tranzakciókban (vagyis a verziódimenzió nincs használva). Ezekkel a problémákkal kapcsolatos további információkért tekintse meg a jelen témakör hátralevő szakaszait.

## <a name="prepare-for-conversion-by-creating-all-required-engineering-product-categories"></a>Felkészülés az átalakításra az összes szükséges tervezési termékkategória létrehozásával

Minden tervezési termékhez hozzá kell rendelni egy *tervezési termékkategóriát*. Ezt a hozzárendelést akkor végezheti el, amikor futtatja az **Átalakítás tervezési termékké** varázslót futtatja. Létezniük kell tervezési termékkategóriáknak az összes releváns standard termékhez, *mielőtt* átalakíthatná azokat a termékeket.

A tervezési termékkategória alapot biztosít a tervezési termékek létrehozásához, és az alapértelmezett értékek és irányelvek halmazát hozza létre. A tervezési kategóriának meg kell felelnie a terméknek, amelyhez hozzárendeli. Például a terméktípusnak és a dimenziócsoportnak meg kell egyeznie a termékkel és a termék tervezési termékkategóriájával is. A további tudnivalókat lásd: [Mérnöki verziók és a mérnöki termékkategóriák](engineering-versions-product-category.md).

> [!IMPORTANT]
> Az **Átalakítás mérnöki termékké** varázsló a terméket csak olyan tervezési termékké képes alakítani, ahol a verziót nem követik nyomon a tranzakciókban. Ezért a meglévő termékek átalakítása céljából létrehozott tervezési termékkategóriák esetén a **Verziókövetés a tranzakciókban** beállítást *Nem* értékre kell állítani.

A tervezési termékkategóriák létrehozásával kapcsolatos további tudnivalókat lásd: [Mérnöki verziók és a mérnöki termékkategóriák](engineering-versions-product-category.md).

## <a name="run-the-convert-to-engineering-product-wizard"></a>Az Átalakítás tervezési termékké varázsló futtatása

Az **Átalakítás tervezési termékké** varázsló segítségével egy vagy több meglévő terméket tervezési termékké alakíthat át. A termékeket tervezési termékekké (verziószámozott termékekké) alakítja át, ahol a verzió nincs nyomon követve tranzakciókban (ez azt jelenti, hogy a verziódimenzió nincs használatban). Az átalakítás befejezése után a termékek a Tervezési változáskezelés segítségével kezelhetők.

Az átalakítás végleges. Így később nem fogja tudni visszafordítani. 

Minden átalakított tervezési termék továbbra is ki lesz adva ugyanazokban a vállalatokban, amelyekben az eredeti termék ki lett adva. A tervezési anyagjegyzékek és útvonalak azonban nem lesznek automatikusan kiadva ezeknek a vállalatoknak.

Az alábbi lépések szerint futtassa az **Átalakítás tervezési termékké** varázslót, és alakítson át egy terméket tervezési termékké.

1. Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.
1. A rácsban jelölje be az egyes átalakítani kívánt termékek jelölőnégyzetét.
1. A művelet ablaktáblán, a **Mérnök** lapon, a **Tervezési változáskezelés** csoportban válassza a **Átalakítás tervezési termékké** elemet a varázsló megnyitásához.
1. A varázsló első oldala az **Üdvözlő** oldal. Ha még nem ismeri az átalakítási folyamatot, olvassa el alaposan az ezen a lapon található információkat. Ha készen áll a folytatásra, válassza a **Következő** lehetőséget.
1. Az **Átalakítani kívánt termékek részleteinek kiválasztása** oldalon megjelenik minden egyes termék, amelyet a varázsló megnyitása előtt kiválasztott. Vizsgálja meg a listát. Az **Új** és a **Törlés** gombokkal az eszköztáron igény szerint hozzáadhat és eltávolíthat termékeket.
1. A következő, a rács tetején található mezők használatával rendeljen alapértelmezett értékeket minden felsorolt termékhez. (Az átalakítás befejezése után az egyes termékekre vonatkozó értékeket módosíthatja.) Nem rendelhetők alapértelmezett értékek olyan termékekhez, amelyekhez már hozzá van rendelve megfelelő érték.

    - **Alapértelmezett tervezési kategória** – válasszon egy kezdő tervezési termékkategóriát, amely minden felsorolt termékhez hozzá lesz rendelve. A kiválasztott kategória csak az azzal kompatibilis termékekre lesz alkalmazva.
    - **Alapértelmezett verzió** – Adja meg az összes felsorolt termékhez rendelendő kezdeti termékverziót. Minden tervezési terméknek legalább egy tervezési verziója van.
    - **Alapértelmezett életciklus-állapot** – válassza ki a termék életciklusának kezdeti állapotát, amely minden felsorolt termékhez hozzá lesz rendelve.
    - **Az aktuális anyagjegyzék a tervezési termék része lesz** – akkor jelölje be ezt a jelölőnégyzetet, ha az egyes felsorolt termékek aktuális anyagjegyzékét a tervezési termék anyagjegyzékeként kell használni.

    Termékbeállításokkal kapcsolatos további információkért tekintse meg a következő lépést.

1. Tekintse át a rácsban felsorolt összes terméket, és értékelje ki, milyen jól vonatkoznak rá a hozzárendelt alapértelmezett értékek. Minden sorban tekintse át az alábbi adatokat, és állítsa be a megfelelő mezőket:

    - **Termékszám** – A termékszám.
    - **Terméknév** – A termék neve.
    - **Tervezési kategória** – válassza ki azt a tervezési termékkategóriát, amelyhez a terméknek az átalakítás után tartoznia kell. Az egyes termékekhez már léteznie kell egy megfelelő kategóriának, mint azt a témakör előző részében leírtuk. Kategóriát kell rendelni minden termékhez.
    - **Verzió** – Adja meg a termékhez az átalakítás után rendelendő termékverziót. Kiválaszthat például egy számot, amely megfelel a kategória által már használt számsorozatnak. Minden egyes mérnöki verzió tárolja a mérnöki szempontból releváns adatokat, amelyek az adott verzióra jellemzők. A további tudnivalókat lásd: [Mérnöki verziók és a mérnöki termékkategóriák](engineering-versions-product-category.md).
    - **Termék életciklus-állapota** – Itt kiválaszthatja azt a termékéletciklus-állapotot, amelyben a terméknek az átalakítás után rendelkeznie kell. A termékéletciklus-állapot segítségével lehet szabályozni, hogy egy adott tervezési verzióhoz mely tranzakciók engedélyezettek. További információ: [Termékéletciklus-állapotok és tranzakciók](product-lifecycle-state-transactions.md).
    - **Anyagjegyzékkel rendelkezik** – Ha be van jelölve a jelölőnégyzet, az azt jelzi, hogy a termékhez anyagjegyzék is van. A jelölőnégyzet beállítása segít eldönteni, hogy hogyan állítsa be **Az aktuális anyagjegyzék a tervezési termék része lesz** jelölőnégyzetet.
    - **Az aktuális anyagjegyzék a tervezési termék része lesz** – akkor jelölje be ezt a jelölőnégyzetet, ha a termék aktuális anyagjegyzékét a tervezési termék anyagjegyzékeként kell használni. Ezt követően az anyagjegyzéket a Tervezési változáskezelés kezeli. Ha a terméknek nincs anyagjegyzéke, vagy ha később inkább manuálisan szeretne anyagjegyzéket létrehozni az átalakított termékhez, törölje a jelölést ebből a jelölőnégyzetből.
    - **Hibákat tartalmaz** – Ha be van jelölve a jelölőnégyzet, az azt jelzi, hogy a termékbeállításban egy vagy több hiba van. Például előfordulhat, hogy a terméktípus vagy a dimenziócsoport nem felel meg a kategóriában. A program kihagyja a hibás termékeket, és nem alakítja át őket.

1. Ha végzett, az eszköztár **Ellenőrzés** gombjára kattintva ellenőrizze a termékbeállításokat. A program minden sor esetén frissíti a **Hibákat tartalmaz** jelölőnégyzetet, jelezve a termék állapotát. Módosítsa az értékeket addig, amíg az összes termék beállítása nem hibamentes.
1. Ha minden termék helyesen van beállítva, a folytatáshoz kattintson a **Következő** gombra.
1. A **Kiválasztás megerősítése** oldalon azon termékek száma látható, amelyek beállításai nem tartalmaznak hibát, így készen állnak az átalakításra. A hibák miatt kihagyott termékek számát is megjeleníti. Az átalakítás kötegelt feladatként való futtatásához állítsa *Igen* értékre a **Kötegelt futtatás** beállítást.
1. A beállítások alkalmazásához válassza a **Befejezés** lehetőséget, és indítsa el a termékek tervezési termékekké való átalakítását.

> [!NOTE]
> Ha a rendszer úgy van beállítva, hogy a termékek kiadása előtt manuálisan el kell fogadnia a termékeket, akkor minden átalakított terméket el kell fogadnia a megfelelő vállalatok **Termékkiadások megnyitása** lapján. További információért lásd: [A termék áttekintése és elfogadása a helyi vállalatban történő kiadás előtt](engineering-scenarios.md#accept).
