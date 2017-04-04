---
title: "Költségvetés-tervezési indoklás dokumentumok"
description: "Indoklás dokumentumok Kísérőszöveg biztosítanak annak megmagyarázására, miért szükség egy adott költségvetés költségvetés kérő azokat."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 259594
ms.assetid: 52576fad-32b9-48f2-8197-c11ec313fc29
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: c86d01fec3d8d7c210c7e73a034f4e9e384a0dcf
ms.lasthandoff: 03/31/2017


---

# <a name="budget-planning-justification-documents"></a>Költségvetés-tervezési indoklás dokumentumok

Indoklás dokumentumok Kísérőszöveg biztosítanak annak megmagyarázására, miért szükség egy adott költségvetés költségvetés kérő azokat. 

A költségvetés-kezelő a Microsoft Word által létrehozott és a jelenlegi költségvetés-tervezési folyamathoz rendelt költségvetési terv sablon. Költségvetési tulajdonosai majd nyissa meg a sablont, és rendelkezik a Word automatikusan kitöltött adatok alapján a költségvetési előirányzat. Majd adhat további szöveg vagy adat mentése és csatolása a saját személyre szabott igazoló bizonylat a költségvetési terv előtt.

##### <a name="set-up-microsoft-dynamics-office-add-in-for-microsoft-word"></a>Állítsa be a Microsoft Dynamics Office-bővítmény a Microsoft Word

1.  Nyisson meg egy új Microsoft Word dokumentum.
2.  Kattintson a **beszúrása** a szalag, majd kattintson a **tár**.
3.  Keresse meg a Microsoft Dynamics Office bővítményt, és kattintson a **hozzáadása**.
4.  A Word programban, a jobb oldali ablaktáblában kattintson a **server adatok felvétele**.
5.  Írja be vagy illessze be a kiszolgáló URL-CÍMÉT, majd kattintson a **OK**.

##### <a name="define-the-justification-template-in-microsoft-word"></a>Az indoklás a Microsoft Word sablon

1.  Kattintson a **Tervező** a Microsoft Dynamics Office a után már bejelentkezett.
2.  Fej-információk használata a **mezők hozzáadása** gombra.
3.  Kattintson az entitás adatforrás az BudgetPlanJustification, majd **tovább**. **Megjegyzés:** erre az entitásra szükség minden igazoló bizonylat. Más szervezetek is használható, de vissza a Microsoft Dynamics 365 műveletekhez a feltöltés sikertelen lesz, ha ez az entitás nem tartalmaz.
4.  A BudgetPlanName, BudgetPlanPreparer, ResponsibilityCenter és DocumentNumber feliratok és értékek hozzáadása a Word dokumentumban. **Megjegyzés:** szabványos címkék, hanem saját címkét is használhat, ha szükséges.
5.  Kattintson a **végzett** a csoportfej szakasz végrehajtásához.
6.  Kattintson a sor szintű részletes költségvetési terv összegek, **a tábla hozzáadása**.
7.  Újra, az BudgetPlanJustification entitás adatforrást, és kattintson **tovább**.
8.  Mezők hozzáadása a EffectiveDate, ScenarioName, AccountDisplayValue és AccountingCurrencyExpenseAmount. **Megjegyzés:** megjegyzések hozzáadása a költségvetési terv sorai belül érhetők el, ha azok lehet hozzáadni a táblázat itt.
9.  Adja hozzá a további utasításokat a végfelhasználó számára, és minden szükséges formázást vagy a dokumentum stílusokon végre.
10. Mentse a dokumentumot a helyi számítógépre, és a folytatás előtt zárja be a fájlt.

##### <a name="set-up-the-budget-planning-process-to-use-the-justification-template"></a>Állítsa be a költségvetés-tervezési folyamat az indoklási sablon használata

1.  A Microsoft Dynamics 365 műveletekhez, Ugrás **költségvetés**&gt;**telepítő**&gt;**költségvetés-tervezési**&gt;**indoklása Dokumentumsablonok**.
2.  Kattintson a **új**, és keresse meg az újonnan létrehozott Microsoft Word dokumentumba.
3.  Adja meg a sablon megjelenítendő nevet és leírást. Click **OK**.
4.  Ugrás a **költségvetés**&gt;**a telepítő**&gt;**költségvetési****tervezési**&gt;**költségvetés-tervezési folyamat**.
5.  Válassza ki a folyamat, ahol a Sorkizárás sablont kell használni, majd kattintson az **Szerkesztés**.
6.  A a **dokumentumsablont indoklás** mezőben válassza ki a megfelelő sablont, és mentse.

##### <a name="edit-and-save-personalized-justification-documents"></a>Szerkesztheti és mentheti a dokumentumok személyre szabott indoklása

1.  Műveletek 365 Dynamics hozzon létre egy új költségvetési terv, vagy nyisson meg egy meglévő költségvetési tervet.
2.  A a **indoklása** legördülő menü **hozzon létre új indoklás**.
3.  Miután kitöltötte az adatokat, jelölje ki a személyre szabott dokumentum feltöltése a **indoklása** legördülő menü.



