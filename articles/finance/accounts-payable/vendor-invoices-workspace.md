---
title: Szállítói számla bevitele munkaterület
description: Ez a témakör azt mutatja be, hogyan lehet beállítani a szállítói számlákkal kapcsolatos munkaterületet, valamint bemutatja a Microsoft Power BI szolgáltatáson keresztül elérhető adatokat.
author: abruer
manager: AnnBe
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.assetid: ''
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2020-09-21
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 04aca717c3f255799699d63fb74ee0b543f8c8ba
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993263"
---
# <a name="vendor-invoice-entry-workspace"></a>Szállítói számla bevitele munkaterület

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Ez a témakör azt mutatja be, hogyan lehet beállítani a szállítói számlákkal kapcsolatos munkaterületet, valamint bemutatja a Microsoft Power BI szolgáltatáson keresztül elérhető adatokat. A munkaterület szállítói számlájának adatait a program a meghatározott felhasználók számára szűri, és grafikus formában jeleníti meg.

## <a name="overview"></a>Áttekintés

A **Szállítói számla bevitele** munkaterület a szállítói számlák feldolgozásához kapcsolódó információkat jeleníti meg. Tartalmaz egy **Saját munka** és egy **Elemzés – az összes vállalat** nézetet. A **Saját munka** nézet összesítő lapokat, szállítói tranzakciórácsokat és a kapcsolódó szállítói adatokat jeleníti meg. Az **Elemzés - az összes vállalat** lap a Power BI lehetőségeit kihasználva a szállítói számlákkal kapcsolatos vizualizációkat jelenít meg.

## <a name="set-up-the-workspace-to-show-power-bi-content"></a>A munkaterület beállítása a Power BI-tartalom megjelenítésére

Ezt a beállítást végre kell hajtania, mielőtt a Power BI a **Szállítói számla bevitele** munkaterületen megjeleníthetné az adatokat.

1. A **Funkciókezelés** munkaterületen szűrje a listát, és keresse meg a **Szállítói számla automatizálása** funkciót.
3. Válassza az **Engedélyezés most** lehetőséget.
4. A szállítói számla munkafolyamatának beállításával biztosíthatja, hogy a számlák manuális beavatkozás nélkül is teljes egészükben feldolgozhatók legyenek. A munkafolyamat beállításához lépjen a **Kötelezettségek \> Beállítás \> Kötelezettségek munkafolyamatai** felületre.
5. Nyissa meg a **Kötelezettségek \> Beállítás \> Kötelezettségek paraméterei** lehetőséget, és válassza ki a **Szállítói számla automatizálása** lapot. További tájékoztatás a következő témakörben található: [A szállítói számla automatizálásának beállítási lehetőségei](vnd-invoice-set-up-options.md).
6. Állítsa az **Importált számlák automatikus elküldése a munkafolyamat-rendszerbe** értéket erre: **Igen**.
7. Ha a termékek számláit automatikusan kell egyeztetni, akkor a **Terméknyugták automatikus egyeztetése a számlasorokkal** beállítása legyen **Igen**.
8. Tekintse át a további, nem kötelező beállításokat, és konfigurálja azokat a szervezet igényei szerint.
9. Nyissa meg a **Rendszerfelügyelet \> Beállítás \> Rendszerparaméterek** pontot, és állítsa be a **Rendszerpénznem** és a **Rendszerváltási árfolyam** mezőket.
10. Lépjen a **Főkönyv \> Beállítás \> Főkönyv** részre, és állítsa be a **Könyvelési pénznem** és az **Árfolyamtípus** mezőket.
11. Lépjen a **Főkönyv \> Pénznemek \> Devizaárfolyamok** részre, és adja meg a tranzakció pénzneme és a könyvelési pénznem közötti átváltási árfolyamokat, valamint a könyvelési pénznem és a rendszer pénzneme közötti átváltási árfolyamokat.
12. Lépjen a **Rendszerfelügyelet \> Beállítás \> Entitástár** részre, és keresse meg a **Szállítói számla automatizálási eljárása** lehetőséget. Válassza a **Frissítés** lehetőséget.

Ha meg szeretné tekinteni a munkaterületen megjelenő adatokat, rendelkeznie kell a Kötelezettségek kezelője vagy a Kötelezettségek könyvelője biztonsági szerepkörrel.

## <a name="my-work-view"></a>Saját munka nézet

### <a name="company-selection"></a>Vállalat választása

Amikor a **Szállítói számlák automatizálása** funkciót bekapcsolta, a munkaterület felső részén megjelenik egy **Vállalat** mező. A **Vállalat** mezőben kiválasztott érték a munkaterületen megjelenített összes adatot érinti. Alapértelmezetten a nézet annak a vállalatnak az adatait jeleníti meg, amelyikbe bejelentkezett. Ha egy másik vállalatot választ ki a **Vállalat** mezőben, akkor a munkaterületen megjelenítheti a vállalat adatait. Ezután kiválaszthat egy csempét a munkaterületen, ha a kiválasztott vállalat kapcsolódó lapjára lépjen.

### <a name="summary-tiles"></a>Összesítő csempék

A **Saját munka** nézet **Függőben levő számlák összegzése** mozaikja áttekintést ad a szállítói számlák állapotáról. Láthatók a még fel nem adott naplók és a várakoztatott számlák. Ezenkívül az alábbi négy csempe tartozik a Szállítói számla automatizálása funkcióhoz:

- Manuális bevételezés egyeztetése szükséges
- Egyeztetés ellenőrzése sikertelen
- A munkafolyamatba nem beküldött számlák
- Nem importált számlák

(A négy csempe meglétéhez a Szállítói számla automatizálása funkciót be kell kapcsolni a Funkciókezelés részben.)

A **Szállítói számlák helyreállítása** lap használatához a funkciót be kell kapcsolni a Kötelezettségek paraméterei részben. Nyissa meg a **Kötelezettségek \> Kötelezettségek paraméterei** részt, majd a **Számla** lapon állítsa a **Szállítói számla helyreállításának engedélyezése** beállítást **Igen** értékre.

Amikor a funkció be van kapcsolva, a munkaterületen három csempe együtt szerepel a munkaterület **Naplók** nevű szakaszában. A csempék címei: **Naplók**, **Naplók – Hozzám rendelve** és **Számlagyűjtő**. 

A **Függőben levő számlák összegzése** szakaszá adatai arra a vállalatra szerepelnek, amely a bejelentkezéskori alapértelmezett vállalat.

### <a name="creating-new-records"></a>Új jelentések létrehozása

Új számlázási rekord létrehozásához válassza az **Új** lehetőséget, majd válassza ki a listából az alábbi rekordtípusok egyikét:

- Szállítói számla
- Számlanapló
- Globális számlanapló
- Számlajegyzék
- Számla jóváhagyása

Ne feledje, hogy a létrehozott rekord az illető vállalat szűrőjén alapul, és nem azén a vállalatén, amelyhez be van jelentkezve. Például be van jelentkezve az **UMSF** vállalatba, de a vállalat szűrőjének beállítása **GBSI**. Ebben az esetben az **Új** elem kiválasztása, majd a lista bejegyzéstípusának kiválasztása esetén a rekord a GBSI vállalatban jön létre.

### <a name="documents-not-invoiced-grids"></a>Nem számlázott dokumentumok rácsa

A **Nem számlázott dokumentumok** szakasz olyan rácsokat tartalmaz, amelyek a szállítói számlára várakozó dokumentumokat jelenítenek meg.

A **Nyitott beszerzési rendelések** rács azokat a beszerzési rendeléseket jeleníti meg, amelyek még nincsenek teljes mértékben számlázva. A **Számlázás most** gombbal létrehozhatja a beszerzési rendelés szállítói számláját. Az **Előlegszámlázás most** gombbal létrehozhatja a szállítási rendelés előlegszámláját.

A **Termékbevételezések** rács azokat a termékbevételezési tranzakciókat jeleníti meg, amelyek még nincsenek teljes mértékben számlázva. A **Számlázás most** gombbal létrehozhatja a beszerzési rendelés szállítói számláját.

A **Függőben levő szállítói számlák** rács a munkafolyamat-rendszerbe nem beküldött összes szállítói számlát jeleníti meg. A **Keresés** mező és/vagy a vállalat szűrője egy adott szállítói számla keresésére használható. A **Szerkesztés** gombbal szerkesztheti a rácsban megjelenő tranzakciókat.

A **Beszerzési rendelési keresése** rács **Keresés** mezőjével keresheti meg az adott beszerzési rendelést.

### <a name="related-information"></a>Kapcsolódó információ

A feladott számlákkal kapcsolatos információkat a munkaterület jobb oldalán található hivatkozásokkal tekintheti meg. Ilyen hivatkozások a **Nyitott szállítói számlák**, a **Számlázási napló** és a **Számlázási előzmények és egyeztetési részletek**. A **Szállítók** szakaszban hozzáférhet egy szűrt listához, amely megjeleníti az összes várakoztatott szállítót, vagy használhatja az **Összes szállító** hivatkozást is. Elérhetők ezenkívül az **Összes beszerzési rendelés** és az **Előlegek megnyitása** hivatkozások.

### <a name="analytics--all-companies-page"></a>Elemzés – az összes vállalat oldal

Amikor az **Importált számlák automatikus elküldése a munkafolyamat-rendszerbe** beállítás értéke a **Kötelezettségek paraméterei** lapon **Igen**, megtekintheti az automatizálási elemzéseket. Az **Elemzésel – az össze vállalat** lap fontos metrikákat tartalmaz, például a jóváhagyó és a vállalat által jóváhagyott szállítói számlákat. Ezen a lapon öt jelentéslap található. Egyik lapon egy áttekintés található, a többi lap a Kötelezettségek automatizálás metrikáival kapcsolatos részletes adatokat tartalmaz.

Az alábbi táblázat mutatja be az egyes jelentésoldalakon rendelkezésre álló megjelenítéseket.

| Jelentéslap                    | Vizualizációk |
|--------------------------------|----------------|
| Szállítói számla áttekintése        | <ul><li>Függőben levő, jelenleg automatizált szállítói számlák a rendszer pénznemében</li><li>Sikertelenül importált számlák</li><li>Számlák a munkafolyamatban</li><li>Érintés nélküli számlák az elmúlt 30 napban</li><li>Összesen automatizált számlák az elmúlt 30 napban</li><li>Nyitott számlák egyenlege a rendszer pénznemében</li><li>Meghibásodások okai, elmúlt 30 nap</li><li>Automatikusan feldolgozott feladott számlák (százalékban kifejezve)</li><li>A számla feldolgozásához szükséges napok száma</ul></li> |
| Automatizálási állapot              | <ul><li>Érintés nélküli számlák az elmúlt 30 napban</li><li>A vállalat által érintetlen számlák az elmúlt 30 napban</li><li>A szállítócsoport által érintetlen számlák az elmúlt 30 napban</li><li>Automatikusan feldolgozott feladott számlák (százalékban kifejezve)</li><li>A számla feldolgozásához szükséges napok száma</li></ul> |
| Sikertelenül importált számlák | <ul><li>Sikertelenül importált számlák</li><li>A vállalat által sikertelenül importált számlák</li></ul> |
| Az automaizálás meghibásodásának okai | <ul><li>Sikertelen számlázások</li><li>Vállalat sikertelen számlázásai</li><li>Szállítói csoport sikertelen számlázásai</li></ul> |
| Munkafolyamat állapota                | <ul><li>Számlák a munkafolyamatban</li><li>Szállítói számlázási munkafolyamat-példányok</li><li>Hozzárendelés jóváhagyónként</li><li>Szállítói számla-munkafolyamat vállalatonként</li><li>Átlagos napok a munkafolyamatban a jóváhagyó szerint</li></ul> |
