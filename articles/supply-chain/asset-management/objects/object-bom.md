---
title: Eszköz DBJ-k
description: Ez a témakör az Eszközkezelésben használt eszközök darabjegyzékét mutatja be (DBJ-j)
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 32bb95445a31c1de949c6aa1821bf84d42198acb
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3214803"
---
# <a name="asset-boms"></a>Eszköz DBJ-k

[!include [banner](../../includes/banner.md)]

 

Ez a témakör az Eszközkezelésben használt eszközök darabjegyzékét mutatja be (DBJ-j) Az **Eszköz DBJ** oldalon látható az eszköz által a teljes élettartama alatt használt összes cikk listája (pótalkatrészek és más cikkek egyaránt). Új eszköz létrehozásakor javasoljuk az eszköz DBJ létrehozását a beállítási eljárás részeként. Így nyomon követheti az eszköz cikkelőzményeit a létrehozás dátumától.

Miután befejezett egy karbantartási feladatot, és a cikkfelhasználást rögzítik a munkarendelésen, nyomon követheti a pótalkatrészek és más cikkek felhasználását, amelyeket az eszközhöz használtak. Ez a funkció lehetővé teszi, hogy teljes cikkfelhasználási rekordot tartson nyilván az összes eszköz számára. A rekorddal például megfigyelheti, hogy egy adott pótalkatrészt gyakran cserélnek-e, vagy nyomon követheti a pótalkatrészeket és más cikkeket, amelyeket jelenleg az eszközön használnak.

> [!NOTE]
> A munkarendelésen a cikkfelhasználásba beletartozhatnak a pótalkatrészek, és más kiegészítő cikkek, például kenőanyagok, csavarok és tömítések.

Az eszköz DBJ-t automatikusan frissíthető az Eszközkezelés beállításainak megfelelően. Ha a munkarendelés életciklus-állapotát azért hozták létre, hogy elkészült vagy befejezett munkarendeléseket kezeljen, és ha az adott munkarendelési életciklus-állapot **Eszköz DBJ frissítése** beállítása **Igen** a **Munkarendelés életciklus-állapotai** oldalon, akkor a munkarendelésen használt összes cikk automatikusan frissül az **Eszköz DBJ** oldalon, amikor a munkarendelést az adott életciklus-állapotra frissítik. 


Az Eszköz DBJ-t manuálisan is frissítheti az új cikksorok létrehozásával az **Eszköz DBJ** oldalon.

Az **Eszköz DBJ** oldalon nyomon követheti az eszközökhöz tartozó pótalkatrész-előzményeket, miután a cikkfelhasználást rögzítették a munkarendelésen. A funkció használatához ki kell választania a pótalkatrészek nyilvántartásához használatos cikkcsoportot a **Pótalkatrészek cikkcsoportjai** odlalon.

Az Eszköz DBJ funkció használatához először be kell állítania a szükséges pótalkatrész-cikkcsoportokat. Ezt követően, ha azt szeretné, hogy az Eszköz DBJ automatikusan frissüljön egy munkarendelés befejezésekor, akkor egy beállíthat egy munkarendelési életciklus-állapotot az adott frissítés kezelésére. 


## <a name="set-up-spare-parts-item-groups"></a>Pótalkatrész-cikkcsoportok beállítása

A pótalkatrészekkel kapcsolatos előzmények beállítása a **Készlet- és raktárkezelés** modulban létrehozott cikkcsoportokon alapul. Az Eszközkezelés modulban beállíthat cikkcsoportokat, így nyomon követheti a pótalkatrészek előzményeit a kiválasztott cikkcsoportokban szerepelő cikkeknél.

1. Válassza ki az **Eszközkezelés** \> **Beállítás** \> **Eszköz** \> **Pótalkatrészek cikkcsoportjai** lehetőséget.
2. Válassza az **Új** lehetőséget a Cikkcsoport beállításához.
3. A **Cikkcsoport** mezőben válassza ki a csoportot. A csoport nevét a program automatikusan beírja a **Név** mezőbe.

## <a name="view-and-update-asset-boms"></a>Eszköz DBJ megtekintése és frissítése

Miután bejegyezte a cikkfelhasználást egy munkarendelésen, megtekintheti a rögzített cikkfelhasználást az **Eszköz DBJ** oldalon.

1. Válassza ki az **Eszközkezelés** \> **Általános** \> **Eszközök** \> **Aktív eszközök** lehetőséget. Válassza ki az eszközt a listában, majd válassza az **Eszköz DBJ** értéket.

    > [!NOTE]
    > Ha az összes eszközre vonatkozó összes cikkfelhasználási nyilvántartást meg szeretné tekinteni,válassza az **Eszközkezelés** \> **Lekérdezések** \> **Eszközök** \> **Eszköz DBJ** elemet.

2. Válassza az **Eszköz DBJ frissítése** lehetőséget. Igény szerint hozzáadhat eszközöket, eszköztípusokat és erőforrásokat a frissítéshez a **Kiválasztás** elemmel. A frissítés az **OK** gombot választva indítható el. A Frissítés funkciót kötegelt feladatként is beállíthatja.
3. Ha a cikkekhez kapcsolódó további információkat szeretne látni, készletdimenziókat is hozzáadhat. Válassza a **Készlet** \> **Dimenziók megjelenítése** elemet, majd jelölje be a látni kívánt dimenziók melletti jelölőnégyzeteket. Ha ezt a beállítást meg szeretné őrizni az **Eszköz DBJ** lapon lévő összes eszközre vonatkozóan, állítsa a **Beállítás mentése** beállítást **Igen** értékre.
4. Ha szeretne áttekintést kapni arról, hogy az Eszközkezelésben hol használják a kiválasztott sorban található cikk az eszközökkel, alapértelmezett feladattípusokkal, pótalkatrészekkel és munkarendelésekkel kapcsolatban, válassza a **Cikket hol használják** elemet. 
5. Ha csak az aktív cikksorokat szeretné látni, válassza a **Megtekintés** \> **Aktuális** elemet. Az összes cikksor megtekintéséhez, beleértve azokat a sorokat is, amelyeknél a lejárat dátuma korábbi az aktuális dátumnál, válassza a **Megtekintés** \> **Összes** elemet.

> [!NOTE]
> Amikor befejezett egy unkarendelést, és a kapcsolódó eszközhöz kapcsolódó cikkek vagy pótalkatrészek egy része lejárt vagy lecserélték már cikkekre vagy pótalkatrészekre, javasoljuk, hogy ennek megfelelően frissítse az Eszköz DBJ-t.

## <a name="create-a-new-item-line-in-an-asset-bom"></a>Új cikksor létrehozása egy eszköz DBJ-ben

Az eszközök cikksorait manuálisan is létrehozhatja.

1. Az **Eszköz DBJ** oldalon válassza az **Új** lehetőséget.
2. Az **Eszköz** mezőben válassza ki azt az eszközt, amelyhez cikksort szeretne hozzáadni.
3. A **Sor száma** mezőben adjon meg egy sorrendben következő sorszámot.
4. A **Hatályos** mezőben válassza ki az cikk kezdő dátumát.
5. Ha a cikknek van lejárata, a **Lejárat** mezőben adjon meg egy befejezési dátumot.
6. Válasszon egy cikket a **Cikkszám** mezőben. A nevet a program automatikusan beírja a **Terméknév** mezőbe.
7. A **Mennyiség** mezőbe írja be a használt mennyiséget. A **Kiszerelés** mező frissítése automatikusan történik.
