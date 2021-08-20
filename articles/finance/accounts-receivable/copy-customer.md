---
title: Vevők másolása megosztott számsorozatok használatával
description: Ez a témakör ismerteti, hogyan használhatók a megosztott számsorozatok a vevők másik jogi személyhez való átmásolásához úgy, hogy a vevő megőrzik ugyanazt a vevőazonosítót.
author: mikefalkner
ms.date: 08/31/2018
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: CustTable
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: d906ed3cb7af0af9e0137f878c39d5ad47616a783688ad70b1465bd0b2d470aa
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6763334"
---
# <a name="copy-customers-by-using-shared-number-sequences"></a>Vevők másolása megosztott számsorozatok használatával

[!include [banner](../includes/banner.md)]

A megosztott számsorozatok használatával vevőazonosítókat rendelhet hozzá. A megosztott számsorozatok egyúttal lehetővé teszik vevők másolását egy jogi személyből egy másik jogi személybe úgy, hogy mindkét jogi személyben ugyanazzal a vevőazonosítóval rendelkeznek.

## <a name="setup"></a>Beállítás

A funkció akkor aktiválódik, amikor egy megosztott számsort használ a vevőazonosítók hozzárendeléséhez. Ugyanazt a számsorozatot kell használnia minden jogi személyben, amelybe a vevőt másolni kívánja. A vevő számsorozata az egyes jogi személyek **Kinnlevőségek paraméterei** oldalán módosítható. Válassza a **Kinnlevőségek** \> **Paraméterek** menüpontot, majd válassza a **Számsorozatok** lapot.

Emellett beállíthat vevői számsorozatokat az egyes vevőcsoportok számára. Ezeket a számsorozatokat meg is kell osztani. Először a vevőcsoporthoz tartozó számsorozat kerül használatra. Ha egy vevőcsoport számára nincs megadva számsorozat, akkor a rendszer a **Kinnlevőségek paraméterei** oldalon megadott számsorozatot használja.

A manuális vevőazonosító használatakor átmásolhatja továbbá a vevőket a jogi személyek között. Ha azonban olyan jogi személybe próbálja másolni a vevőt, ahol a vevőazonosító már létezik, a rendszer nem indítja el a másolási folyamatot.

## <a name="copy-a-customer"></a>Vevő másolása

A vevő másolásához válassza az **Új** lehetőséget a **Minden vevő** listaoldalon, amely megnyitja a **Vevő létrehozása** párbeszédpanelt. Figyelje meg, hogy az új vevőkód nincs azonnal hozzárendelve. Ez a viselkedés eltér a korábbi verziókban megszokott viselkedéstől. Mivel még nem választotta ki a vevőcsoportot, a rendszer nem tudja megállapítani a felhasználni kívánt megfelelő számsorozatot. Nem tudja továbbá megállapítani, hogy új vevőt próbál létrehozni, vagy másolni szeretne egy vevőt. A rendszer ezért a vevőazonosítót csak azután rendeli hozzá, miután a párbeszédpanel alsó részén található **Mentés** gombra kattint.

Ha új vevőt hoz létre, folytathatja a szokásos módon a mezők értékeinek megadásával. Amikor végzett, és kiválasztja a **Mentés** lehetőséget, láthatja, hogy a rendszer automatikusan hozzárendelte a vevőazonosítót. A másik esetben, a manuális számsorozatok esetén láthatja, hogy a manuális vevőazonosítót használja a rendszer.

Egy vevő másolásához adjon meg a **Név** mezőben legalább egy, a keresett vevőnek megfelelő karaktert. A keresőmező megjeleníti a felek listáját, akik megfelelhetnek a keresett vevőnek. A felek egyikének kiválasztásakor a párbeszédpanel jobb oldalán további információk jelennek meg:

- Az **Általános** lap a fél telefonszámát és címét jeleníti meg.
- A **Szerepkörök** lap megjeleníti a szerepköröket, amelyekkel a kiválasztott fél rendelkezhet, valamint a jogi személyeket, amelyekben az egyes szerepkörökkel rendelkezik.
- Az **Adóregisztrációs azonosító** lap megjeleníti a félhez rendelt adóregisztrációs azonosítót.

Csak akkor másolhat egy felet, ha rendelkezik vevői szerepkörrel, és ez a szerepkör az aktuális jogi személytől eltérő jogi személyben található. Ha talál ezeket a követelményeket teljesítő felet, kövesse az alábbi lépéseket.

1. Megjelenik a **Vevő másolása** lehetőség. Alapértelmezés szerint ez a beállítás **Nem** értékre van beállítva. A vevő másolásához az aktuális jogi személybe, adja meg a beállítás esetében az **Igen** értéket. 
2. Megjelenik a **Jogi személy** mező. Válassza ki a jogi személyt, amelyből a vevőt másolni kívánja. Ha a vevő csak egy jogi személyben létezik, akkor a mező alapértelmezésben arra a jogi személyre van beállítva.
3. Válassza ki a **Kiválasztás** lehetőséget. Létrejön az új vevő.

## <a name="validation"></a>Ellenőrzés

A vevő másolásakor a rendszer megpróbálja menteni az új vevő adatait. A másolt adatok megfelelőségének biztosításához a rendszer ellenőrzéseket futtat. Minden meghiúsult ellenőrzésről hibaüzenetet kap. A hibaüzenetek elmagyarázzák, hogy mely adatokat kell frissíteni. A vevő másolata addig nem menthető, amíg nem javította az összes ellenőrzési hibát.

## <a name="copy-a-customer-by-using-tax-exempt-number-search-feature"></a>Vevő másolása az adómentességi szám keresés funkció használatával

Vevőket is másolhat az Adómentességi szám keresés funkció használatával, amely a **Regisztráció** csoportban található a **Minden vevő** oldal Művelet panelének **Vevő** oldalán. A megjelenő **Adómentességi szám keresés** párbeszédpanel megjeleníti az adómentességi számot, a vevőazonosítót, a vevő nevét, valamint a jogi személyt, ahol az adómentességi azonosító használatban van. Csak akkor másolhatja a vevőt, ha az olyan jogi személyben van, ami nem az aktuális jogi személy. Miután kiválasztott egy, a követelménynek megfelelő vevőt, kövesse az alábbi lépéseket.

1. Megjelenik a **Vevő másolása** lehetőség. Alapértelmezés szerint ez a beállítás **Nem** értékre van beállítva. A vevő másolásához az aktuális jogi személybe, adja meg a beállítás esetében az **Igen** értéket. 
2. Válassza ki a **Kiválasztás** lehetőséget. Létrejön az új vevő.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]