---
title: Számlastruktúrák konfigurálása
description: Ez a témakör a számlastruktúrákról és a pénzügyi dimenziókról nyújt tájékoztatást.
author: aprilolson
ms.date: 06/03/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerEliminationRule
audience: Application User
ms.reviewer: roschlom
ms.custom: 13131
ms.assetid: 08fd46ef-2eb8-4942-985d-40fd757b74a8
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3632f115b1ef4cd3a41a483270fb5f6bb6c73526ce9322f16a6533265302937c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6719716"
---
# <a name="configure-account-structures"></a>Számlastruktúrák konfigurálása

[!include[banner](../includes/banner.md)]

A számlastruktúrák a fő számla és a pénzügyi dimenziók segítségével létrehoznak egy sor szabályt, amely meghatározza a használt rendelést és értékeket a számlaszám megadásakor. Tetszőleges számú számlastruktúrákát beállíthat a vállalat igényeitől függően. A számlastruktúrák társítva vannak a vállalat főkönyvének beállításához, így meg lehet őket osztani.

Számlastruktúra létrehozása esetén a szegmensek maximális száma 11 lehet. Ha ennél több szegmensre van szüksége, alaposan értékelje ki a beállítást és a követelményeket, mivel ez befolyásolja majd a felhasználói élményt. Gondolja végig, hogy egy szegmens az adatbevitel során történő származtatás helyett származtatható-e jelentéskészítéskor egy hierarchia használatával vagy egy felhasználó által megadott mezővel. Például ha szeretne jelenteni a helyről, és ki tudja kalkulálni a helyet a részleg vagy a költséghely alapján, akkor nem kell pénzügyi dimenzióként megadnia a helyet. Ha a kiértékelés után úgy tűnik, hogy több, mint 11 szegmensre van szükség, a speciális szabályok segítségével hozzáadhat további szegmenseket.

A számlastruktúrákhoz szükség van a fő számlára. A fő számla nem kell az első szegmens legyen a szerkezetben, de azonosítania kell, hogy a számlaszámbejegyzés során melyik számlastruktúrát használja a rendszer. Ennek következtében egy fő számla érték csak egy struktúrában létezhet, hozzárendelve a főkönyvhöz, hogy ne legyenek átfedésben. A számlastruktúra azonosítása után, a megengedett értékek szűrővel ellátott listája végigvezeti a felhasználót, hogy csak érvényes dimenzióértékeket válasszon ki, csökkentve a helytelen naplóbejegyzés lehetőségét.

> [!NOTE] 
> Ha egy pénzügyi dimenzióhoz képest tervez költségvetést, a számlastruktúra részének kell lennie. Költségvetés-készítés jelenleg nem használja fel a speciális szabályokat.

## <a name="example"></a>Példa
Ahhoz, hogy illusztráljuk a legjobb gyakorlatot a számlastruktúra beállításához, tegyük fel, hogy egy vállalat szeretné nyomon követni a mérlegszámlákat (100000..399999) a számla és üzleti egység pénzügyi dimenzió szintjén. Ami a bevételi és kiadási számlákat illeti (400000..999999), az üzleti egység, részlet és költséghely pénzügyi dimenziókat követik nyomon. Ha értékesítési megállapodást kötnek, általában a vevő pénzügyi dimenziót is nyomon követik. Ebben az esetben javasolt lenne, hogy a vállalat főkönyvéhez két számlastrukta legyen hozzárendelve – egy a mérlegszámlákhoz és egy az eredményszámlákhoz. A felhasználói élmény és az ellenőrzési optimalizálása érdekében a vevőnek speciális szabálynak kell lennie, amelyet csak értékesítési számla használata esetén használnak.

**Mérlegszámla-struktúra**

|Fő számla          | Üzleti egység    |
|----------------------|-----------|
|100000..399999 | *;” “|

**Eredményszámla struktúra**

|Fő számla          | Üzleti egység    |Részleg           | Költséghely    | &nbsp; |
|----------------------|------------------|--------------------|-----------|---|
|400000..999999 | \*;” “| \*;” “| \*;” “| \*;” “|

**Speciális szabály vevő hozzáadásához**

Feltétel: Ha a fő számla 400000 és 499999 között van, akkor adjon hozzá vevőt. Nem lehet üresen hagyni.

|Vevő         |
|-----------------|
|* |

Ebben az egyszerűsített példában minden érték és üres mező engedélyezett, így * és " " jeleket használunk.

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

## <a name="more-than-7-criteria-needed"></a>Több, mint 7 feltételek szükséges

Ha több, mint 7 feltétel szükséges, folytathatja és hozzáadhatja őket a következő sorban. Miközben a **Megengedett értékek részletei** . szakaszon dolgozik, megfigyelheti, hogy az **+Új hozzáadása** feltétel már nem aktív, miután a hetedik kritériát is megadta. Ez számos tényezőnek köszönhető, például: 
 - Oszlopszélesség 
 - Hogyan történik az adatok tárolása 
 - A **Megengedett értékek részletei** vezérlő teljesítménye
 - Használhatóság  
 
A további feltételek hozzáadásának folytatásához kattintson **Duplikálás a szegmensben** és a **Megengedett értékek szakasz** lehetőségekre. Ezzel átmásolja a feltételt egy új sorba. Ezután átírhatja vagy módosíthatja a **Megengedett értékek részletei** szakaszt.

## <a name="best-practices"></a>Gyakorlati tanácsok
A számlastruktúra beállításakor van néhány ajánlott eljárás, melyet követhet. Ez azonban csak útmutatás, így vegye fontolóra, hogy a megbeszélés során sort kerítsen az üzleti kérdések, növekedési és karbantartási terv átfogó megbeszélésére is.

- Legyen a fő számla az első vagy legyen olyan közel a számlastruktúra elejéhez, amennyire csak lehetséges, így a felhasználóknak a lehető legjobb irányított tapasztalatban lesz részük a számlabejegyzés során.

- Használja fel újra a számlastruktúrát, ahányszor csak lehetséges, hogy csökkentse a jogi személyekre fordított karbantartást.

- Ami a jogi személyek közötti eltéréseket illeti, vegye fontolóra a speciális szabályok használatát, hogy a számlastruktúrát újra felhasználhassa.

- A megengedett értékek meghatározásakor használjon minél több tartományt és helyettesítő karaktert. Ez nemcsak a karbantartási nélküli növekedést és módosítást teszi lehetővé, de a rendszer jobban is teljesít ezzel a konfigurációval.

- Nem javasoljuk, hogy a számlastruktúra minden szegmensét megcsillagozza, majd ezután kizárólag a speciális szabályokra támaszkodjon. Ezt nehéz lehet kezelni, és gyakran vezet felhasználói hibához a karbantartás alatt, amelynek következtében előfordulhat, hogy a rendszer nem lesz képes a feladásra.

## <a name="account-structure-activation"></a>Számlastruktúra aktiválása
Ha elégedett az új beállítással vagy a számlastruktúra módosításával, aktiválnia kell. Ha egy számlastruktúra hozzá van rendelve egy főkönyvhöz, az aktiválási folyamat hosszú ideig is eltarthat, mivel a rendszerben szereplő összes fel nem adott tranzakciót szinkronizálni kell az új struktúrával. A feladott tranzakciókat nem befolyásolja a számlastruktúra módosítása.

További tudnivalókért lásd: [Számlatükör tervezése](plan-chart-of-accounts.md), [Pénzügyi dimenziók](financial-dimensions.md) és [A számla és dimenzió kombinációk megadása (szegmentált bejegyzés ellenőrzés)](enter-account-dimension-combinations-segmented-entry-control.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]