---
title: Szállítók másolása megosztott számsorozatok használatával
description: Ez a témakör ismerteti, hogyan használhatók a megosztott számsorozatok a szállítók másik jogi személyhez való átmásolásához úgy, hogy a szállítók megőrzik ugyanazt a szállítóazonosítót.
author: mikefalkner
manager: aolson
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 33338c331a53586b325def398267ab10db23f78a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4459156"
---
# <a name="copy-vendors-by-using-shared-number-sequences"></a>Szállítók másolása megosztott számsorozatok használatával

[!include [banner](../includes/banner.md)]

A megosztott számsorozatok használatával szállítóazonosítókat rendelhet hozzá. A megosztott számsorozatok egyúttal lehetővé teszik szállítók másolását egy jogi személyből egy másik jogi személybe úgy, hogy mindkét jogi személyben ugyanazzal a szállítóazonosítóval rendelkeznek.

## <a name="setup"></a>Beállítás

A funkció akkor aktiválódik, amikor egy megosztott számsort használ a szállítóazonosítók hozzárendeléséhez. Ugyanazt a számsorozatot kell használnia minden jogi személyben, amelybe a szállítót másolni kívánja. A szállító számsorozata az egyes jogi személyek **Kötelezettségek paraméterei** oldalán módosítható. Válassza a **Kötelezettségek** \> **Beállítás** \> **Kötelezettségek paraméterei** menüpontot, majd válassza a **Számsorozatok** lapot.

Emellett beállíthat szállítói számsorozatokat az egyes szállítócsoportok számára. Ezeket a számsorozatokat meg is kell osztani. Először a szállítócsoporthoz tartozó számsorozat kerül használatra. Ha egy szállítócsoport számára nincs megadva számsorozat, akkor a rendszer a **Kötelezettségek paraméterei** oldalon megadott számsorozatot használja.

A manuális szállítóazonosító használatakor átmásolhatja továbbá a szállítókat a jogi személyek között. Ha azonban olyan jogi személybe próbálja másolni a szállítót, ahol a szállítóazonosító már létezik, a rendszer nem indítja el a másolási folyamatot.

## <a name="copy-a-vendor"></a>Szállító másolása

Szállító másolásához válassza a **Minden szállító** listaoldalon az **Új** lehetőséget, amely megnyitja a **Minden szállító, új rekord** oldalt. Figyelje meg, hogy az új szállítóazonosító nincs azonnal hozzárendelve. Ez a viselkedés eltér a korábbi verziókban megszokott viselkedéstől. Mivel nem választotta ki a szállítócsoportot, a rendszer nem tudja megállapítani a megfelelő, felhasználni kívánt számsorozatot. Nem tudja továbbá megállapítani, hogy új szállítót próbál létrehozni, vagy másolni szeretne egy szállítót. A rendszer ezért a szállítóazonosítót csak azután rendeli hozzá, miután az oldal alsó részén található **Mentés** gombra kattint.

Ha új szállítót hoz létre, folytathatja a szokásos módon a mezők értékeinek megadásával. Amikor végzett, és kiválasztja a **Mentés** lehetőséget, láthatja, hogy a rendszer automatikusan hozzárendelte a szállítóazonosítót. A másik esetben, a manuális számsorozatok esetén láthatja, hogy a manuális szállítóazonosítót használja a rendszer.

Egy szállító másolásához adjon meg a **Név** mezőben legalább egy, a keresett szállítónak megfelelő karaktert. A keresőmező megjeleníti a felek listáját, akik megfelelhetnek a keresett szállítónak. A felek egyikének kiválasztásakor a párbeszédpanel jobb oldalán további információk jelennek meg:

- Az **Általános** lap a fél telefonszámát és címét jeleníti meg.
- A **Szerepkörök** lap megjeleníti a szerepköröket, amelyekkel a kiválasztott fél rendelkezhet, valamint a jogi személyeket, amelyekben az egyes szerepkörökkel rendelkezik.
- Az **Adóregisztrációs azonosító** lap megjeleníti a félhez rendelt adóregisztrációs azonosítót.

Csak akkor másolhat egy felet, ha rendelkezik szállítói szerepkörrel, és ez a szerepkör az aktuális jogi személytől eltérő jogi személyben található. Ha talál ezeket a követelményeket teljesítő felet, kövesse az alábbi lépéseket.

1. Megjelenik a **Szállító másolása** lehetőség. Alapértelmezés szerint ez a beállítás **Nem** értékre van beállítva. A szállító másolásához az aktuális jogi személybe, adja meg a beállítás esetében az **Igen** értéket. 
2. Megjelenik a **Jogi személy** mező. Válassza ki a jogi személyt, amelyből a szállítót másolni kívánja. Ha a szállító csak egy jogi személyben létezik, akkor a mező alapértelmezésben arra a jogi személyre van beállítva.
3. Válassza ki a **Kiválasztás** lehetőséget. Létrejön az új szállító.

## <a name="validation"></a>Ellenőrzés

A szállító másolásakor a rendszer megpróbálja menteni az új szállító adatait. A másolt adatok megfelelőségének biztosításához a rendszer ellenőrzéseket futtat. Minden meghiúsult ellenőrzésről hibaüzenetet kap. A hibaüzenetek elmagyarázzák, hogy mely adatokat kell frissíteni. A szállító másolata addig nem menthető, amíg nem javította az összes ellenőrzési hibát.

## <a name="copy-a-vendor-by-using-the-tax-exempt-number-search-feature"></a>Szállító másolása Adómentességi szám keresés funkció használatával

Szállítókat is másolhat az Adómentességi szám keresés funkció használatával, amely a **Regisztráció** csoportban található a **Minden szállító** oldal Művelet panelének **Szállító** lapján. A megjelenő **Adómentességi szám keresés** párbeszédpanel megjeleníti az adómentességi számot, a szállítóazonosítót, a szállító nevét, valamint a jogi személyt, ahol az adómentességi azonosító használatban van. Csak akkor másolhatja a szállítót, ha az olyan jogi személyben van, ami nem az aktuális jogi személy. Miután kiválasztott egy, a követelménynek megfelelő szállítót, kövesse az alábbi lépéseket.

1. Megjelenik a **Szállító másolása** lehetőség. Alapértelmezés szerint ez a beállítás **Nem** értékre van beállítva. A szállító másolásához az aktuális jogi személybe, adja meg a beállítás esetében az **Igen** értéket.
2. Válassza ki a **Kiválasztás** lehetőséget. Létrejön az új szállító.
