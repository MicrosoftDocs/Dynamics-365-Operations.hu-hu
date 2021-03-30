---
title: Alárendelt jogi személy beállítása konszolidációhoz
description: Ez a témakör bemutatja, hogyan dolgozhat a konszolidációs vállalatok számlatükreivel.
author: jinniew
manager: AnnBe
ms.date: 10/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2020-10-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 44bd184514b24a816cc83f6b0070a5e08163921b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5204809"
---
# <a name="set-up-a-subsidiary-legal-entity-for-consolidation"></a>Alárendelt jogi személy beállítása konszolidációhoz

[!include [banner](../includes/banner.md)]

A leányvállalati számlák konszolidációra való előkészítésének módja részben attól függ, hogy az alárendelt jogi személy számlatükre milyen mértékben felel meg a konszolidált jogi személy számlatükrének.

Mielőtt konszolidációt indít egy időszak zárásának részeként, végezze el az időszak végi zárás előkészítő tevékenységeit, de addig ne zárja le a leányvállalati számlákat, amíg be nem fejeződött a konszolidáció. Az időszak végén történő lezárással kapcsolatos további tudnivalókat lásd: [A főkönyv lezárása időszak végén](close-general-ledger-at-period-end.md) és [A pénzügyi év lezárása](tasks/close-fiscal-year.md).

> [!NOTE]
>  Javasoljuk, hogy a Management Reporter for Microsoft Dynamics 365 Finance szoftverrel egyesítse több jogi személy pénzügyi eredményeit konszolidált formátumban. A Management Reporter segítségével konszolidált pénzügyi jelentéseket készíthet több jogi személyre vonatkozóan, az Excel segítségével importálhatja a konszolidációs adatokat más forrásokból, és összegeket fordíthat le bármely jelentési pénznemre anélkül, hogy a konszolidációs folyamatot kellene futtatnia a Dynamics 365 Finance rendszerben.

## <a name="map-subsidiary-main-accounts-to-consolidated-main-accounts"></a>Leányvállalati fő számlák leképezése konszolidált fő számlákra

Ha az alárendelt jogi személy számlatükre nem felel meg a konszolidált jogi személy számlatükrének, az alárendelt jogi személy fő számláit leképezheti a konszolidált jogi személy fő számláira.

1. A *leányvállalati jogi személyben* kattintson a **Főkönyv \> Beállítás** \> **Számlatükrök \> Számlatükrök** lehetőségre.
2. Válasszon ki egy számlatükröt. A **Fő számlák** gyorslapon válasszon ki egy fő számlát, majd válassza a **Szerkesztés** lehetőséget.
3. Jelöljön ki minden leányvállalati fő számlát, amelyeket le kell képezni a konszolidált jogi személyhez. Az **Általános** gyorslap **Konszolidációs számla** mezőjében adja meg a konszolidált jogi személynek azt a számláját, amelyre átkerül a kijelölt leányvállalati fő számla egyenlege vagy tranzakciói. Ugyanaz a konszolidált fő számla több leányvállalati számlához is megadható.

    > [!NOTE]
    > Ha a leképezett leányvállalati számlák főszámla-típusa eltér a konszolidált jogi személy számláinak főszámla-típusától, az **Összesen** főszámla-típusú számlák értékei a konszolidáció során felülíródnak.

4. Készítsen jelentéseket és pénzügyi kimutatásokat a konszolidált jogi személy számára pénzügyi dimenziók alapján. A következő lépéseket követve leképezheti a leányvállalati számlákban használt pénzügyi dimenziókat a konszolidált jogi személy pénzügyi dimenzióihoz:

    1. A *leányvállalati jogi személyben* lépjen a **Főkönyv \> Beállítás \> Pénzügyi dimenziók \> Pénzügyi dimenziók** részre, válasszon ki egy pénzügyi dimenziót, majd válassza a **Pénzügyi dimenzióértékek** lehetőséget.
    2. Válassza ki a konszolidált jogi személy eltérő pénzügyi dimenzióértékére leképezendő pénzügyi dimenzióértéket.
    3. Az **Általános** gyorslap **Csoportdimenzió** mezőjébe írja be a konszolidált jogi személy pénzügyi dimenzióját. A konszolidáció során ez a pénzügyi dimenzió lesz hozzárendelve azokhoz a tranzakciókoz és egyenlegekhez, melyek a kiválasztott pénzügyi dimenziót használják az alárendelt jogi személynél. Az itt megadott pénzügyi dimenziókat kell használni a konszolidált jogi személynél. A csoport pénzügyi dimenziójaként használt pénzügyi dimenziót több leányvállalati pénzügyi dimenzióhoz is hozzárendelheti.

5. Online konszolidáció esetén kövesse a következő lépéseket annak érdekében, hogy az átvitelek a várt módon történjenek meg.

    1. A *konszolidált jogi személy* esetében lépjen a **Főkönyv \> Időszakos \> Konszolidálás \> Konszolidálás \[Exportálás ide:\]** lehetőséget a **Konszolidálás \[Online\]** oldal megnyitásához.
    2. A **Kritériumok** lapon jelölje be **Konszolidációs számla használata** jelölőnégyzetet.
    3. A **Pénzügyi dimenziók** lapon válassza ki a megfelelő pénzügyi dimenziókat.
    4. Minden egyes kiválasztott pénzügyi dimenziónál adjon meg egy számot a **Szegmenssorrend** mezőben, amely jelzi a dimenziók megjelenítési sorrendjét.

## <a name="maintain-the-same-chart-of-accounts-in-the-subsidiary-and-consolidated-legal-entities"></a>Azonos számlatükör megőrzése a leányvállalatnál és a konszolidált jogi személynél

Az alárendelt jogi személy és a konszolidált jogi személy fő számlái ugyanazokkal a számlaszámokkal és ugyanazzal a számlatükör-szerkezettel rendelkezhetnek. Ebben az esetben nem kell kézzel hozzárendelnie a leányvállalat fő számláit a konszolidált jogi személy fő számláival.

A konszolidáció előtt kövesse az alábbi lépéseket.

1. A *konszolidált jogi személy* esetében lépjen a **Főkönyv \> Időszakos \> Konszolidálás \> Konszolidálás \[Exportálás ide:\]** lehetőséget a **Konszolidálás \[Online\]** oldal megnyitásához.
2. Jelölje be a **Konszolidációs számla használata** jelölőnégyzetet. A konszolidálás során a tranzakciókat és egyenlegeket automatikusan átviszi a rendszer a megfelelő számlára.

> [!NOTE]
> Ha a számlák nem feleltethetők meg egymásnak, a konszolidálás leáll, és hibaüzenet jelenik meg.

## <a name="create-a-chart-of-accounts-for-the-consolidated-legal-entity-based-on-an-existing-chart-of-accounts"></a>Konszolidált jogi személy számlatükrének létrehozása egy meglévő számlatükör alapján

Konszolidálást anélkül is végrehajthat, hogy előzetesen létrehozná a konszolidált jogi személy számlatükrét.

- Ha megtervezte a használandó számlastruktúrát a konszolidált jogi személynél, akkor leképezheti a leányvállalati számlákat erre a struktúrára.
- Ha nem képez le egyetlen leányvállalati számlát sem, a konszolidált jogi személyben automatikusan létrejönnek a számlák, amikor a leányvállalati adatokat átviszi a konszolidált jogi személybe. Ezek a számlák a fő számlán alapulnak. A további adatok a konszolidált jogi személy leányvállalatival megegyező számlaszámú számláin halmozódnak.

Attól függetlenül, hogy leképezte-e a számlákat, az ilyen típusú konszolidálás futtatása előtt törölje a jelet a **Konszolidációs számla használata** jelölőnégyzetetben a konszolidált jogi személynél a **Konszolidálás** oldalon.

> [!NOTE]
> Ezzel a módszerrel a konszolidált jogi személynél az egyik alárendelt jogi személy számlatükréből hozhat létre számlatükröt. (További tudnivalókért lásd: [Konszolidációs csoportok és további konszolidációs számlák](../budgeting/consolidation-account-groups-consolidation-accounts.md).) Ezután rendeljen hozzá egy megfelelő konszolidációs átváltási elvet minden egyes konszolidált fő számlához, és futtassa a konszolidációt az összes leányvállalati jogi személyre vonatkozóan.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]