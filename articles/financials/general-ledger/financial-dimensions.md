---
title: "Pénzügyi dimenziók"
description: "Ez a témakör leírja a pénzügyi dimenziók különféle típusait és azok beállításának módját."
author: aprilolson
manager: AnnBe
ms.date: 08/24/2018
ms.topic: article
ems.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DimensionDetails, DimensionValueDetails, SysTranslationDetail
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 25871
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.1
ms.translationtype: HT
ms.sourcegitcommit: d6b7b1219974cb5de1a625d87c3bce2a4439470b
ms.openlocfilehash: 9973d03de031ad2fa5647bb167c12b9231633a22
ms.contentlocale: hu-hu
ms.lasthandoff: 10/01/2018

---

# <a name="financial-dimensions"></a>Pénzügyi dimenziók

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja a pénzügyi dimenziók különféle típusait és azok beállításának módját.

Használja a **Pénzügyi dimenziók** oldalt pénzügyi dimenziók létrehozásához, melyeket számlaszegmensként használhat számlatükrökhöz. Kétféle pénzügyi dimenzió van: egyéni és entitás által támogatott dimenzió. Az egyéni dimenziók jogi entitások között oszlanak meg, és az értékeket a felhasználók adják meg és tartják karban. Az entitás által támogatott dimenziók értéke a rendszerben máshol van meghatározva, például a Vevők vagy Üzletek entitásoknál. Néhány entitás által támogatott dimenzió megoszlik a jogi személyek között, míg néhány más entitás által támogatott dimenzió vállalatspecifikus.

A pénzügyi dimenziók létrehozása után használja a **Pénzügyi dimenzióértékek** oldalt, és rendeljen hozzá további tulajdonságokat az egyes pénzügyi dimenziókhoz.

A pénzügyi dimenziók segítségével jogi személyek képezhetők le. A jogi személyeket nem kell létrehozni a Microsoft Dynamics 365 for Finance and Operations alkalmazásban. Ugyanakkor a pénzügyi dimenziókat nem a jogi személyek üzemi vagy üzleti követelményeinek teljesítésére tervezték. A Microsoft Dynamics 365 for Finance and Operations rendszerben a Egységközi könyvelés funkció csak az egyes tranzakciók által létrehozott könyvelési tételek kezelését szolgálja.

Jogi személyiséggel rendelkező pénzügyi dimenziók beállítása előtt a következő területeken értékelje ki az üzleti folyamatait annak meghatározására, hogy ez a beállítás működik-e a szervezete esetében:

- Készlet
- Értékesítések és beszerzések üzleti dimenziók és jogi személyek között
- Áfa számítás és jelentés
- Üzemi jelentés

Az alábbiakban a limitációk közül sorolunk fel néhányat:

- Az áfa funkciók csak jogi személyekhez használhatók, a pénzügyi dimenziókhoz pedig nem.
- Egyes jelentésekben nem szerepelnek a pénzügyi dimenziók. Ezért pénzügyi dimenziók szerinti jelentéskészítésnél előfordulhat, hogy módosítani kell a jelentéseket.

## <a name="custom-dimensions"></a>Egyéni dimenziók

A felhasználó által definiált pénzügyi dimenziók létrehozásához az **Értékek használata innen** mezőben jelölje be az **&lt;&nbsp;Egyéni dimenzió&nbsp;&gt;**  lehetőséget.

A formátummaszk megadásával továbbá korlátozhatja a dimenzióértékekhez megadható adatok mennyiségét és típusát. Megadhat olyan karaktereket, például betűket vagy kötőjelet (-), amelyek minden egyes dimenzióértéknél változatlanok maradnak. Emellett megadhat kettős kereszt (\#) vagy és-jelet (&) olyan karakterek helyőrzőjeként, amelyek változni fognak a dimenzióértékek minden létrehozásakor. A kettős kereszt (\#) a számok, míg az és-jel (&) a betűk helyőrzője. Ez a mező a formátummaszkhoz csak akkor érhető el, ha az **&lt;&nbsp;Egyéni dimenzió&nbsp;&gt;** opciót választja ki az **Értékek használata innen** mezőből.

**Példa**

Ha például a dimenzióértéket két „C” betűre és három számra szeretné korlátozni, formátummaszkként a **CC-\#\#\#** értéket adja meg.

## <a name="entity-backed-dimensions"></a>Entitás által támogatott dimenziók

Entitás által támogatott pénzügyi dimenzió létrehozásához az **Értékek használata innen** mezőben válasszon ki egy a pénzügyi dimenzió alapjául szolgáló rendszer által definiált entitást. A kijelölés alapján létrejönnek a pénzügyi dimenzióértékek az érintett entitásból. Például projektek dimenzióértékeinek létrehozásához jelölje ki a **Projekteket**. A rendszer ekkor minden projektnévhez létrehozza a dimenzióértéket. A **Pénzügyi dimenzióértékek** lap jeleníti meg az entitás értékeit. Ha ezek az értékek vállalatspecifikusak, a lapon a vállalat is szerepel.

## <a name="activating-dimensions"></a>Dimenziók aktiválása

Amikor aktivál egy pénzügyi dimenziót, a tábla frissül, hogy a pénzügyi dimenzió nevét is tartalmazza. A törölt dimenziók törlődnek. A pénzügyi dimenzió aktiválása előtt dimenzióértékeket adhat meg. Azonban a pénzügyi dimenzió sehol sem használható fel, amíg nincs aktiválva. Például nem adhat hozzá pénzügyi dimenziót számlastruktúrához, amíg nem aktiválódik a pénzügyi dimenzió. Amikor kiválasztja az **Aktiválás** lehetőséget, az összes dimenzió frissül, és megjelennek az állapotváltozások.

## <a name="translations"></a>Fordítások

A **Szöveg fordítása** lapon a kijelölt pénzügyi dimenzióhoz különböző nyelveken lehet szöveget beírni. A **Fő számla** lapon a fő számlához különböző nyelveken lehet szöveget beírni. 

## <a name="legal-entity-overrides"></a>Jogi személy felülbírálásai

Nem minden dimenzió érvényes minden jogi személyhez. Ezenkívül néhány dimenzió csak egy adott időszakra vonatkozhat. Ezekben az esetekben a **Jogi személy felülbírálása** szakasz használható annak a megadására, hogy mely vállalatok számára kell felfüggeszteni a dimenziót, ki a tulajdonos, és mely időszakban aktív a dimenzió.

## <a name="deleting-financial-dimensions"></a>Pénzügyi dimenziók törlése

Az adatok hivatkozási integritásának fenntartása érdekében a pénzügyi dimenziók ritkán törölhetők. Ha megpróbálja törölni a pénzügyi dimenziót, a következő feltételek értékelése történik meg:

- Használták a pénzügyi dimenziót bármely feladatlan vagy feladott tranzakcióban, vagy bármilyen típusú dimenzióérték-kombinációban?
- Használták a pénzügyi dimenziót bármilyen aktív számlastruktúrában, speciális szabálystruktúrában vagy pénzügyidimenzió-készletben?
- Része a pénzügyi dimenzió az alapértelmezett pénzügyidimenzió-integrációs formátumnak?
- A pénzügyi dimenzió be van állítva alapértelmezés szerinti dimenzióként?

Ha a feltételek bármelyike teljesül, a pénzügyi dimenzió nem törölhető.

## <a name="default-dimension-values"></a>Alapértelmezett dimenzióértékek

Az új dimenziók alapértelmezett értékeiként használhatja a törzsrekordok értékeit, például az ügyfelek és a szállítók értékeit. Az új dimenziók létrehozásakor a törzsrekordazonosító szerepel a dimenzióértékekben a törzsrekordoknál. Amikor például új ügyfelet hoz létre, az ügyfél-azonosító beírása az ügyféldimenzióba történik. Értékesítési rendelések, számlák vagy más olyan dokumentumok létrehozásakor, amelyek vevői azonosítót igényelnek, a meglévő alapértelmezési szabályok érvényesek, és a vevői azonosító hozzáadódik a dokumentumhoz.

Ezt a funkciót a dimenzió egyik beállítása szabályozza. A beállítás neve **Értékek másolása ehhez a dimenzióhoz minden egy létrehozott új DimensionName esetén**, ahol **DimensionName** a dimenzió neve. Alapértelmezés szerint a funkció ki van kapcsolva. Azonban bármikor bekapcsolható.

Ha már léteznek rekordok a dimenziónál, a törszrekordok a funkció bekapcsolásakor frissülnek. A meglévő bizonylatok és tranzakciók azonban nem frissülnek.

## <a name="derived-dimensions"></a>Származtatott dimenziók

Beállítható egy dimenzió úgy, hogy a többi dimenzió információi automatikusan bekerüljenek olyankor, amikor Ön megadja az adott dimenziót egy dokumentumban. Ha például a költséghely értékeként a 10-et adja meg, akkor a rendszer a **20** értéket automatikusan beírhatja a részleg dimenzióhoz.

A származtatott értékeket a dimenziók lapon állíthatja be.

1. Válasszon ki egy dimenziót, majd válassza a **Származtatott dimenziók** lehetőséget.

    A **Származtatott dimenziók** lap tartalmaz egy rácsot. A kiválasztott dimenziószegmens a rács első oszlopa.

2. Adja meg a származtatni kívánt szegmenseket. Minden szegmens oszlopként jelenik meg.

Adja meg azokat a dimenziókombinációkat, amelyeket az első oszlopban lévő dimenzióból kell származtatni. Ha például a költséghelyet szeretné használni, mint a dimenziót, amelyből a részleget és a helyet származtatni kívánja, adja meg a 10 értéket költséghelyként, a 20-at részlegként és a 30-at helyként. Ha ezt követően megadja a 10-es költséghelyet egy tözsrekordban vagy egy tranzakciólapon, akkor a rendszer automatikusan beviszi a 20-as részleget és a 30-as helyet alapértelmezés szerint.

A származtatott dimenzió folyamata nem bírálja felül a meglévő értékeket a származtatott dimenzióknál. Ha például a 10-es költséghelyet ír be, és nincs megadva másik dimenzió, akkor a rendszer automatikusan beviszi a 20-as részleget és a 30-as helyet alapértelmezés szerint. Ha azonban módosítja a költséghelyet, a korábban beállított értékek nem változnak. Így megadhatja az alapértelmezett dimenziókat a törzsrekordokon, de ezeket a dimenziókat nem módosítják a származtatott dimenziók.

### <a name="derived-dimensions-and-entities"></a>Származtatott dimenziók és entitások

Entitások használatával beállíthatja a származtatott dimenziók szegmenseit és értékeit.

- A Származtatott dimenziók entitás beállítja az irányadó dimenziókat és az adott dimenzióknál használt szegmenseket.
- A DerivedDimensionValue entitással importálhatja azokat az értékeket, amelyeket az egyes irányadó dimenzióknál származtatni kell.

Ha egy adott entitás révén importálja az adatokat, akkor amennyiben az adott entitás dimenziókat importál, akkor a származtatott dimenziószabályokat alkalmazza a rendszer az importálás során, kivéve, ha az entitás kifejezetten felülbírálja az adott dimenziókat.

További információ a következő témakörökben olvasható:

- [Pénzügyi dimenziók meghatározása](tasks/define-financial-dimensions.md)
- [Pénzügyi dimenzió alapértelmezett sablonjainak karbantartása](tasks/maintain-financial-dimension-default-templates.md)

