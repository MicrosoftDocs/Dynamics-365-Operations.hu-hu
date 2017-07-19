---
title: "Költségvetési tervezés igazoló dokumentumai"
description: "Az igazoló dokumentumok háttérmagyarázatokat biztosítanak arra az esetre, ha valaki egy költségvetést kikérve rákérdez, miért van szükség az adott költségvetésre."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 259594
ms.assetid: 52576fad-32b9-48f2-8197-c11ec313fc29
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-11-30T00:00:00.000Z
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 1d23c0e1725a39d25d2be8971f541b2c31bbe859
ms.contentlocale: hu-hu
ms.lasthandoff: 06/13/2017

---

# <a name="budget-planning-justification-documents"></a>Költségvetési tervezés igazoló dokumentumai

[!include[banner](../includes/banner.md)]


Az igazoló dokumentumok háttérmagyarázatokat biztosítanak arra az esetre, ha valaki egy költségvetést kikérve rákérdez, miért van szükség az adott költségvetésre. 

A költségvetés-kezelő Microsoft Wordben létrehoz egy költségvetésiterv-sablont, és azt hozzárendeli a jelenlegi költségvetés-tervezési folyamathoz. A költségvetés tulajdonosai ezt követően megnyithatják a sablont, és az adatokat automatikusan kitölthetik Wordben a költségvetési kérelmük alapján. Ezután további szöveget vagy adatokat adhatnak hozzá a személyre szabott igazló dokumentumok mentése és a költségvetési tervhez való csatolása előtt.

##### <a name="set-up-microsoft-dynamics-office-add-in-for-microsoft-word"></a>A Microsoft Dynamics Office Microsoft Word-bővítményének beállítása

1.  Nyisson meg egy új Microsoft Word-dokumentumot.
2.  Kattintson a **Beillesztés** elemre a szalagon, majd kattintson a **Tár** elemre.
3.  Keresse meg a Microsoft Dynamics Office bővítményt, és kattintson a **Hozzáadás** elemre.
4.  A Word programban a jobb oldali ablaktáblában kattintson a **Kiszolgáló adatainak hozzáadása** elemre.
5.  Írja be vagy illessze be a kiszolgáló URL-címét, majd kattintson a **OK** gombra.

##### <a name="define-the-justification-template-in-microsoft-word"></a>Az indoklás sablon megadása Microsoft Wordben

1.  Bejelentkezés után kattintson a **Tervezés** elemre a Microsoft Dynamics Office-bővítményben.
2.  A fejlécadatokhoz használja a **Mezők hozzáadása** gombot.
3.  Válassza ki a BudgetPlanJustification entitás-adatforrást, majd kattintson a **Tovább** gombra. **Megjegyzés:** erre az entitásra minden igazoló dokumentum esetén szükség van. Más entitások is használhatók, de a Microsoft Dynamics 365 for Finance and Operations, Enterprise editionbe való visszatöltés sikertelen lesz, ha ez az entitás nincs felvéve.
4.  Adja hozzá a BudgetPlanName, BudgetPlanPreparer, ResponsibilityCenter és DocumentNumber címkéket és értékeket a Word-dokumentumban. **Megjegyzés:** szükség esetén használhatja saját egyéni címkéit a szabványos címkék helyett.
5.  Kattintson a **Kész** elemre a fejléc befejezéséhez.
6.  A sorszintű részletes költségvetésiterv-összegekhez kattintson a **Tábla hozzáadása** elemre.
7.  Ismét válassza ki a BudgetPlanJustification entitás-adatforrást, majd kattintson a **Tovább** gombra.
8.  Adja hozzá az EffectiveDate, ScenarioName, AccountDisplayValue és AccountingCurrencyExpenseAmount elemekhez tartozó mezőket. **Megjegyzés:** ha megjegyzések elérhetők hozzáadásra az egyedi költségvetésiterv-sorokon belül, ezek itt adhatók hozzá a táblához.
9.  Adja hozzá a további utasításokat a végfelhasználó számára, és végezzen el minden szükséges formázást vagy stílusbeállítást a dokumentumon.
10. Mentse el a dokumentumot a helyi számítógépre, és a folytatás előtt zárja be a fájlt.

##### <a name="set-up-the-budget-planning-process-to-use-the-justification-template"></a>A költségvetés-tervezési folyamat beállítása az indoklási sablon használatára

1.  A Finance and Operationsben lépjen a **Költségvetés készítése** &gt; **Beállítás** &gt; **Költségvetés-tervezés** &gt; **Igazoló dokumentum sablonjai** elemre.
2.  Kattintson a **Új** lehetőségre, és keresse meg az újonnan létrehozott Microsoft Word-dokumentumot.
3.  Adja meg a sablon megjelenítendő nevét és leírását. Kattintson az **OK** gombra.
4.  Lépjen a következőhöz: **Költségvetés-készítés** &gt; **Beállítás** &gt; **Költségvetés****-tervezés** &gt; **Költségvetés-tervezési folyamat**.
5.  Válassza ki a folyamatot, ahol az indoklási sablont használni kívánja, majd kattintson a **Szerkesztés** elemre.
6.  Az **Igazoló dokumentum sablonja** mezőben válassza ki a megfelelő sablont, és mentse el.

##### <a name="edit-and-save-personalized-justification-documents"></a>Személyre szabott igazoló dokumentumok szerkesztése és mentése

1.  A Finance and Operationsben hozzon létre egy új költségvetési tervet, vagy nyisson meg egy meglévő költségvetési tervet.
2.  Az **Indoklás** legördülő menüben válassza az **Új igazolás létrehozása** elemet.
3.  Miután kitöltötte az adatokat, az **Indoklás** legördülő menüből töltse fel a személyre szabott dokumentumot.





