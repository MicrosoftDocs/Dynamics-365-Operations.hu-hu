---
title: Teljesítményértékelések létrehozása
description: Ez a témakör ismerteti, hogyan hozható létre teljesítmény-áttekintés, és ismerteti az áttekintés egyes szakaszainak célját.
author: andreabichsel
ms.date: 05/05/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EssWorkspace, HcmDiscussionNewDialog, HcmDiscussion, HcmDiscussionChangeSettings, HcmDiscussionAddGoalDialog, HcmTopicCreate, HcmMeasurementDetailDialog, HcmPerfJournalAdd, HcmEmployeeDevelopmentWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: acbfcadb32d3bfb66d290b89e3c90124f80a1be8
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5805586"
---
# <a name="create-performance-reviews"></a>Teljesítményértékelések létrehozása

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]


Ez a témakör ismerteti, hogyan hozható létre teljesítmény-áttekintés, és ismerteti az áttekintés egyes szakaszainak célját. Az eljárás a USMF bemutatócég segítségével lett létrehozva.

1. Válassza ki az **Alkalmazotti önkiszolgáló rendszer** munkaterületet a kezdőlapon.
2. Válassza az **Új ellenőrzés** lehetőséget új ellenőrzés létrehozásához.
3. Az **Ellenőrzési típus** mezőben adjon meg vagy válasszon ki egy értéket.
4. A **Teljesítmény-időszak** mezőben adjon meg vagy válasszon ki egy értéket.
5. Adja meg a dátumot a **Záró dátum** mezőben.
6. Válassza ki az **OK** lehetőséget. Sablonból is létre lehet hozni ellenőrzést. Ez az a legjobb módja az ellenőrzés létrehozásának, mert minden egyes szakasz tartalmazni fogja az ellenőrzés elindításához szükséges információkat.  
7. Megjelenítheti és elrejtheti a lapokat, például a mellékletek lapot:

    1. A Művelet ablaktáblán válassza a **Szakaszok megjelenítése** parancsot a párbeszédmenü megnyitásához.
    1. Válassza az **Igen** vagy a **Nem** lehetőséget a **Mellékletek megjelenítése** mezőben a mellékletek lap megjelenítéséhez vagy elrejtéséhez.
    1. Válassza a **Mentés** lehetőséget.

8. Válassza a **Cél hozzáadása ellenőrzéshez** elemet cél hozzáadásához. Amikor elkészült, válassza az **OK** elemet.
9. A **Kompetencia hozzáadása** gombra kattintva nyissa meg a legördülő párbeszédpanelt.
10. Érték beírása a **Cím** mezőbe.
11. A **Leírás** mezőben adja meg: `Increase customer skills by working with the support team`.
12. Válassza ki az **OK** lehetőséget.
13. Válassza **Az összes összecsukása** lehetőséget.
14. Válassza az **Összes kibontása** elemet.
15. Válassza a **Megjegyzés hozzáadása** lehetőséget.
16. Válassza a **Feladás** parancsot.
17. Válassza ki a **Mértékek** lapot.
18. A **Mérték hozzáadása** gombra kattintva nyissa meg a párbeszédmenüt.
19. A **Mérték** mezőben adjon meg vagy válasszon ki egy értéket.
26. A **Kitűzött összeg** mezőben adjon meg egy számot.
20. Válassza ki az **OK** lehetőséget.
21. Válassza ki a **Tevékenységek** lapot.
22. Válassza a **Hozzáadás** lehetőséget.
23. Érték beírása a **Cím** mezőbe.
24. Írjon egy értéket a **Leírás** mezőbe.
25. Adja meg a dátumot a **Kezdő dátum** mezőben.
26. Adja meg a dátumot a **Befejezés dátuma** mezőben.
27. A **Fejlesztési terv** mezőben válassza az **Igen** lehetőséget.
28. A **Kulcsszavak** mezőben adjon meg egy értéket.
29. Válassza a **Mentés** lehetőséget.
30. Válassza a **Minősítések** lapot.  

    - A **Minősítés részletei** gyorslapon az alkalmazottak saját maguk értékelhetik magukat, és a vezető értékelheti az alkalmazottat. Súlyok használata esetén a pontszámok súlyozásának értékét a program automatikusan kiszámítja.  
    - Ennek a szakasznak a megtekintéséhez engedélyezze az alkalmazotti minősítések megjelenítésének paraméterbeállításait.  

31. Válassza a **Láttamozások** lapot. Ha az ellenőrzés munkafolyamatot alkalmaz, a láttamozások csak a munkafolyamat befejeződése után jelennek meg. Nincs munkafolyamat használva, úgy mind a munkavállaló, mind a vezető egyaránt szerepelnek itt. A szükséges jelölőnégyzet be van jelölve az ellenőrzési típus beállításainak alapján.  
32. Válassza ki az **Általános** fület.

    - A teljesítési időszak létrehozza az alapértelmezett kezdési és befejezési dátumot. E dátumok szerkeszthetők.  
    - Az állapotok szabályozzák az ellenőrzés elérhetőségét. A **Még el nem kezdett** állapotnál mindenki szerkesztheti az ellenőrzést. A **Folyamatban** állapotnál csak az alkalmazott tekintheti meg és szerkesztheti az ellenőrzést. Az **Ellenőrzésre kész** állapotnál csak a vezető tekintheti meg és szerkesztheti az ellenőrzést. A **Végleges ellenőrzés** állapotnál az alkalmazott és a vezető egyaránt megtekinthetik az ellenőrzést, és szerkeszthetik is, ha ez be van állítva az ellenőrzés típusában. A **Kész** és **Visszavonva** állapotok csak olvashatóvá teszik az ellenőrzést. Ha egy felülvizsgálat **Elutasított** és vissza lesz küldve az alkalmazottnak, akkor az alkalmazott és a vezető is módosíthatja a szükséges módosításokat, hogy az alkalmazott újra beküldhesse.

33. Az **Áttekintés** mezőben adjon meg egy értéket.
34. Válasza a **Felülvizsgálat** lapot. Ahogy az ellenőrzés végighalad az állapotokon, mind az alkalmazott, mind a vezető adhat hozzá megjegyzéseket az egyes célokhoz és kompetenciákhoz.  
35. Válassza ki a **Láttamozások** lapot. A dolgozó és a vezető láttamozhatja a felülvizsgálatot. Ha minden szükséges láttamozás kész, az állapot átáll **Befejezett** értékre, és többé nem végezhető módosítás.  



[!INCLUDE[footer-include](../includes/footer-banner.md)]