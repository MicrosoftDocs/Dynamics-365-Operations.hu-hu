---
title: Számlastruktúrák konfigurálása
description: Ez a cikk a számlastruktúrákkal és a pénzügyi dimenziókkal kapcsolatban tartalmaz tájékoztatást.
author: aprilolson
ms.date: 10/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerEliminationRule
audience: Application User
ms.reviewer: twheeloc
ms.custom: 13131
ms.assetid: 08fd46ef-2eb8-4942-985d-40fd757b74a8
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b3fbdd6e2cac61c358848a21e1126bea900e86b2
ms.sourcegitcommit: c6c2486be2359bd30106f7f52bda788239147d8c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/22/2022
ms.locfileid: "9713943"
---
# <a name="configure-account-structures"></a>Számlastruktúrák konfigurálása

[!include[banner](../includes/banner.md)]

A számlastruktúrák a fő számla és a pénzügyi dimenziók segítségével létrehoznak egy sor szabályt, amely meghatározza a használt rendelést és értékeket a számlaszám megadásakor. Tetszőleges számú számlastruktúrákát beállíthat a vállalat igényeitől függően. A számlastruktúrák hozzá vannak rendelve a vállalat főkönyvi beállításaihoz, így azok megoszthatóak.

Számlastruktúra létrehozása esetén a szegmensek maximális száma 11 lehet. Ha 11-től több szegmensre van szüksége, gondosan vizsgálja meg a beállításokat és a követelményeket, mivel ez hatással van a felhasználói felületre. Gondolja végig, hogy egy szegmens az adatbevitel során történő származtatás helyett származtatható-e jelentéskészítéskor egy hierarchia használatával vagy egy felhasználó által megadott mezővel. Ha például a helyről szeretne jelentést készít, de a helyet részleg vagy költséghely szerint is meg tudja találni, akkor nincs szüksége helyre pénzügyi dimenzióként. Ha a kiértékelés után úgy tűnik, hogy több, mint 11 szegmensre van szükség, a speciális szabályok segítségével hozzáadhat további szegmenseket.

A számlastruktúrákhoz szükség van a fő számlára. A fő számlának nem kell a szerkezet első szegmensének lennie, de meghatározza, hogy a számlaszám bejegyzése során milyen számlastruktúra használatos. Emiatt a fő számla értéke csak egy, a főkönyvhöz rendelt struktúrában létezhet, így azok nem fedik át egymást. A számlastruktúra azonosítása után, a megengedett értékek szűrővel ellátott listája végigvezeti a felhasználót, hogy csak érvényes dimenzióértékeket válasszon ki, csökkentve a helytelen naplóbejegyzés lehetőségét.

> [!NOTE] 
> Ha egy pénzügyi dimenzióhoz képest tervez költségvetést, a számlastruktúra részének kell lennie. Költségvetés-készítés jelenleg nem használja fel a speciális szabályokat.

## <a name="example"></a>Példa
Ahhoz, hogy illusztráljuk a legjobb gyakorlatot a számlastruktúra beállításához, tegyük fel, hogy egy vállalat szeretné nyomon követni a mérlegszámlákat (100000..399999) a számla és üzleti egység pénzügyi dimenzió szintjén. Ami a bevételi és kiadási számlákat illeti (400000..999999), az üzleti egység, részlet és költséghely pénzügyi dimenziókat követik nyomon. Ha értékesítési megállapodást kötnek, általában a vevő pénzügyi dimenziót is nyomon követik. Ebben az esetben javasolt két számlastruktúrát hozzárendelni a vállalat főkönyvéhez – egyet a mérlegszámlákhoz, egyet az eredményszámlákhoz. A felhasználói élmény és az ellenőrzési optimalizálása érdekében a vevőnek speciális szabálynak kell lennie, amelyet csak értékesítési számla használata esetén használnak.

**Mérlegszámla-struktúra**

|Fő számla          | Üzleti egység    |
|----------------------|-----------|
|100000..399999 | *;"&nbsp;"|

**Eredményszámla struktúra**

|Fő számla          | Üzleti egység    |Részleg          | Költséghely    | &nbsp; |
|----------------------|------------------|--------------------|-----------|---|
|400000..999999 | \*;"&nbsp;"| \*;"&nbsp;"| \*;"&nbsp;"| \*;"&nbsp;"|

**Speciális szabály vevő hozzáadásához**

Feltétel: Ha a fő számla 400000 és 499999 között van, akkor adjon hozzá vevőt. Nem hagyható üresen.

|Vevő         |
|-----------------|
|\* |

Ebben az egyszerűsített példában minden érték és üres engedélyezve van, \* és a "&nbsp;" értéket használja a rendszer.

## <a name="segments-and-allowed-values"></a>Szegmensek és megengedett értékek
A **Szegmensek** és **Megengedett értékek részletei** szakaszok rácsszerű élményt biztosítanak a szabályok megadásához, amelyet az ellenőrzés követ a feladás során. Beírhatja az adatokat közvetlenül a rácsban szereplő cellákba, importálhatja az Excelből, vagy használja az **Megengedett értékek részletei** szakaszt, amely végigvezeti a folyamaton.

A **Megengedett értékek részletei** szakasz végigvezeti a feltételek létrehozásán az **Operátorok** (például ezzel kezdődik, a következők között van, tartalmazza, és sok más) segítségével.

[![Értékek engedélyezése.](./media/account.png)](./media/account.png) 

Az engedélyezett értékek az alapértelmezett érték lesz egy napló- vagy könyvelési felosztási bejegyzés oldalán, ha nincsen már lehetséges, kiválasztható érték a számlastruktúra-beállítás alapján.

Itt egy példa az **Eredményszámla struktúrájára**.

|Fő számla          | Üzleti egység    |Részleg           | Költséghely    |
|----------------------|-----------|----------------------|-----------|
|400000..999999 | 002 | 022 | 014 |

Egy napló bevitelekor és egy számla kiválasztásakor az eredménytartományban a „002”-es üzleti egység választásával a 022 és 014 értékek válnak alapértelmezetté a számlavezérlőben. Ez a viselkedés a könyvelési felosztás lapon is megjelenik. 

## <a name="more-than-seven-criteria-needed"></a>Több mint hét feltétel szükséges.

Ha több mint hét feltétel szükséges, a következő sorban folytathatja a hozzáadást. Az Engedélyezett **értékek** **részletei szakaszban való munka során észreveszi, hogy a +Új** feltétel hozzáadása már nem aktív a 7. feltétel bevitele után. Ez számos tényezőnek köszönhető, például: 
 - Oszlopszélesség 
 - Hogyan történik az adatok tárolása 
 - A **Megengedett értékek részletei** vezérlő teljesítménye
 - Használhatóság  

> [!NOTE]
> Microsoft Dynamics AX 2012-től való frissítés, amelyben több mint hét feltétel van megadva, nem támogatott. A pénzügyi és műveleti alkalmazásokra való frissítés befejezése előtt ki kell javítani. 

A további feltételek hozzáadásának folytatásához kattintson **Duplikálás a szegmensben** és a **Megengedett értékek szakasz** lehetőségekre. Ezzel átmásolja a feltételt egy új sorba. Ezután átírhatja vagy módosíthatja a **Megengedett értékek részletei** szakaszt.

## <a name="best-practices"></a>Bevált gyakorlatok
A számlastruktúrák beállításakor van néhány gyakorlati tanácsok, amelyek követhetők. Ez azonban csak útmutatás, így vegye fontolóra, hogy a megbeszélés során sort kerítsen az üzleti kérdések, növekedési és karbantartási terv átfogó megbeszélésére is.

- A fő számla létrehozása először vagy a számlastruktúra elejéhez a lehető legnagyobb mértékben, hogy a felhasználók a legmegfelelőbbek legyenek a számlabejegyzés során.
  
  - Győződjön meg róla, hogy az első pozícióban található olyan külső megoldások, amelyek a fő számlát támogatják.

- Használja fel újra a számlastruktúrát, ahányszor csak lehetséges, hogy csökkentse a jogi személyekre fordított karbantartást.

- Ami a jogi személyek közötti eltéréseket illeti, vegye fontolóra a speciális szabályok használatát, hogy a számlastruktúrát újra felhasználhassa.

- A megengedett értékek meghatározásakor használjon minél több tartományt és helyettesítő karaktert. Ez nemcsak a karbantartási nélküli növekedést és módosítást teszi lehetővé, de a rendszer jobban is teljesít ezzel a konfigurációval.

- Nem javasoljuk, hogy a számlastruktúra minden szegmensét megcsillagozza, majd ezután kizárólag a speciális szabályokra támaszkodjon. Ezt nehéz lehet kezelni, és gyakran vezet felhasználói hibához a karbantartás alatt, amelynek következtében előfordulhat, hogy a rendszer nem lesz képes a feladásra.

## <a name="account-structure-activation"></a>Számlastruktúra aktiválása
Ha meg van elégedve az új beállítással vagy egy számlastruktúra változtatásával, aktiválnia kell. Ha egy számlastruktúra hozzá van rendelve egy főkönyvhöz, az aktiválási folyamat hosszú ideig is eltarthat, mivel a rendszerben szereplő összes fel nem adott tranzakciót szinkronizálni kell az új struktúrával. A számlastruktúra változásai nem befolyásolják a feladott tranzakciókat. A 10.0.31-es alkalmazásverziótól a funkciókezelésben elérhető egy új funkció, amely a **Számlastruktúra** aktiválása teljesítményjavító funkció. A számlastruktúra aktiválására vonatkozó új funkcióval kapcsolatos további [tudnivalókat lásd a Számlastruktúra aktiválása teljesítményjavításában](account-structure-improvement.md). 

A további tudnivalókat lásd [: Számlatükre](plan-chart-of-accounts.md), Pénzügyi dimenziók [megterve](financial-dimensions.md), számla [- és dimenziókombinációk beírása (szegmentált bejegyzésvezérlő)](enter-account-dimension-combinations-segmented-entry-control.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
