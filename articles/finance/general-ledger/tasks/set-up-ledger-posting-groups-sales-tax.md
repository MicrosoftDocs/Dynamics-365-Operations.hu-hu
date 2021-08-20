---
title: Főkönyvi feladási csoportok beállítása az áfához
description: Az áfa számítása és postázása a Főkönyvi feladási csoportok lehetőségben megadott fő számlákra történik.
author: twheeloc
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxAccountGroup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e779887a650f4ca79ea4c9f0d69a5abb5533ac69abab38e1fae38e745e4157bd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6754170"
---
# <a name="set-up-ledger-posting-groups-for-sales-tax"></a>Főkönyvi feladási csoportok beállítása az áfához

[!include [banner](../../includes/banner.md)]

Az áfa számítása és postázása a Főkönyvi feladási csoportok lehetőségben megadott fő számlákra történik. Az egyes áfakódokhoz Főkönyvi postázási csoportok vannak csatolva. Beállíthat külön főkönyvi feladási csoportot mindegyik áfakódhoz, vagy használhat egyetlen főkönyvi feladási csoportot minden áfakódhoz, továbbá több főkönyvi feladási csoportot is hozzárendelhet az áfakódokhoz. Ez a felvétel az DEMF bemutatócéget használja. 

1. Ugorjon a **Navigációs ablakpanel > Modulok > Áfa > Főkönyvi feladási csoportok elemre**.
2. Kattintson az **Új** elemre.
3. Adjon meg egy értéket a **Főkönyvi feladási csoport** mezőbe.
4. Írjon egy értéket a **Leírás** mezőbe.
5. A **Fizetendő áfa** mezőben válassza ki a fő számlát ahhoz a kimenő áfákhoz, amelyeket az adóhatóságnak kell kifizetni. Az Áfát az Adóhatóság szedi be, amikor elad adóköteles termékeket és szolgáltatásokat.  
6. A **Visszaigényelhető áfa** mezőben válassza ki a fő számlát azokhoz a bejövő áfákhoz, amelyek az adóhatóságtól érkeznek. Az Áfát a szállítók szedik be az adóhatóság nevében, amikor adóköteles termékeket és szolgáltatásokat vesz. Ez a mező nem érhető el, csak ha a **Főkönyvi paraméterek** oldalon be van jelölve a Áfaadózási szabályok alkalmazása opció. Ehelyett a szállítóknak befizetett adók ugyanarra a beszerzési számlára terhelődnek.   
7. Az **Importadó költsége** mezőben válassza a fő számlát azoknak a leírható Importadóknak a feladásához, amelyek nem visszaigényeltek, vagy amelyeket jelentettek az adóhatóságnak a szállítók az EU fordított GST/HST részeként. Az **Importadó** lehetőséget ki kell választani az **Áfakódhoz** abból az **Áfacsoportból**, amelyet a tranzakcióban használnak. Ez a mező nem lesz elérhető, csak ha a **Főkönyvi paraméterek** oldalon be van jelölve a **Áfaadózási szabályok alkalmazása** opción.   
8. A **Fizetendő importadó** mezőben válassza ki a fő számlát azokhoz a bemenő Importadókhoz, amelyeket az adóhatóságoknak kell kifizetni. Az **Importadó** lehetőséget ki kell választani az **Áfakódban** abból az **Áfacsoportból**, amelyet az **Importadó** feladásához használnak. Ha az **Áfaadózási szabályok alkalmazása** lehetőséget választja a **Főkönyv paraméterei** oldalon, akkor az eltérés a tranzakció költségszámlájára kerül.   
9. A **Kiegyenlítési számla** mezőben válassza ki a fő számlát, így a **Fizetendő importadó** és **Visszaigényelhető áfa** mezőkben megadott főkönyvi számlák nettó egyenlegét adja fel a rendszer. Az egyenleg az áfák kiegyenlítése és a feladat feladása lett lefuttatva.  Ha a kiegyenlítés időszaknál az adóhatóság egy szállítói számlához van rendelve, akkor az egyenleg feladása ehelyett a szállítói számlára történik majd.
10. A **Szállítói készpénzfizetési engedmény** mezőben a főkönyvi feladási csoporthoz társított áfakód vonatkozásában válassza ki a fő számlát a készpénzfizetési engedmény feladásához. Ez nem kötelező, és ha nincs megadva számla, a **Készpénzfizetési engedmény kódjain** található fő számlát használja a rendszer. Érdemes az egyes **Főkönyvi feladási csoportoknál** különböző számlákat használni, amennyiben fordított áfát használ az Áfacsoportokban a készpénzfizetési engedmény lehetőségnél.  
11. A **Vevői eset engedmény** mezőben válassza ki a fő számlát a készpénzfizetési engedmény feladásához a **Főkönyvi feladási csoporthoz** társított **Áfakódok** esetében. Ez válaszható, és ha nincs megadva számla, a **Készpénzfizetési engedmény kódjain** található fő számlát használja a rendszer. Érdemes az egyes **Főkönyvi feladási csoportoknál** különböző számlákat használni, amennyiben fordított áfát használ az  **Áfacsoportokban** a készpénzfizetési engedmény lehetőségnél.  
12. Kattintson a **Mentés** gombra.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]