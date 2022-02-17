---
title: Dolgozói sérülések és megbetegedések adatainak karbantartása
description: Ez a feladat leírja, hogyan hozhat létre sérülést vagy betegséget.
author: twheeloc
ms.date: 11/03/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HRMInjuryIncident, HcmWorkerLookUp, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 06307331db4d420e99de21c0eb0b3cf1c233f0d5
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8066650"
---
# <a name="maintain-employee-injury-and-illness-information"></a>Dolgozói sérülések és megbetegedések adatainak karbantartása


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Javasoljuk, hogy először a „Sérülés és betegség beállítása” feladat-útmutatót fejezze be, mivel annak néhány beállítási adatait itt használjuk. 



Ez a feladatrögzítés leírja a sérülés- vagy betegségeset létrehozásának alapvető lépéseit. A sérülés vagy betegség részletein kívül az eset állapotát is nyomon követik. Alapértelmezés szerint az esetek állapota: **Nyisd ki**. Az állapotot a gombbal kezelheti **Az ügy állapota** menüpontot az oldal tetején.

1. Menj **Emberi Erőforrások \> Munkások \> Sérülés és betegség \> Sérülések vagy betegségek**.
2. Válassza az **Új** lehetőséget.
3. Ban,-ben **Esetleírás** mezőbe írjon be egy értéket (pl.**Csukló sérülés**).
4. Ban,-ben **Munkás** mezőbe írjon be vagy válasszon egy értéket (például **Ana Bowman**).
5. Ban,-ben **Az esemény dátuma és ideje** mezőben adjon meg egy dátumot és időt (például 2016. január 20. 10:00).
6. Ban,-ben **Sérülés vagy betegség típusa** mezőbe írjon be vagy válasszon egy értéket (például **Törés**).
7. Ban,-ben **Testrész** mezőbe írjon be vagy válasszon egy értéket (például **Csukló**).
8. Ban,-ben **Az eredmény típusa** mezőbe írjon be vagy válasszon egy értéket (például **Terápia**).
9. Ban,-ben **Jelentett dátum és idő** mezőbe írja be a dátumot és az időt.

    A jelentés dátumának és időpontjának későbbinek kell lennie, mint az esemény dátuma és időpontja.

10. Ban,-ben **Az esetet bejelentő személy** mezőbe írjon be vagy válasszon egy értéket (például **Ana Bowman**).

    A megadott személy lehet a munkavállaló vagy az esemény egy másik szemtanúja.

11. Ban,-ben **Incidens** részben, a **Ahol az incidens történt** mezőbe írjon be egy értéket (például **Raktár**).
12. Ban,-ben **Munkahelyiségben** mezőben válassza ki **Igen** ha az esemény a munkaterületen történt.
13. Ban,-ben **A munka megkezdésének dátuma és időpontja** mezőben adja meg azt a dátumot és időpontot, amikor az érintett személy az incidens bekövetkezte előtt dolgozni kezdett.
14. Ban,-ben **Alkalmazotti munkakör vagy feladat** mezőbe írja be azt a munkát vagy feladatot, amelyet a munkavállaló végzett az esemény bekövetkeztekor (például **Dobozok betöltése**). 
15. Ban,-ben **Az esemény oka** mezőbe írja be az incidens okát (például **Megcsúszott a nedves padlón**).
16. Ban,-ben **Súlyossági szint** mezőbe írja be vagy válasszon értéket.
17. Ban,-ben **Intézkedéseket kell hozni** mezőbe írjon be egy értéket (pl.**A kiömlött anyagot azonnal takarítsa fel**).
18. Ban,-ben **Várhatóan távoli napok a munkától** mezőbe írja be, hogy az egyénnek várhatóan hány napja van távol a munkától.

    Miután az egyén visszatért dolgozni, frissítse a **Napok távol a munkától** mezőbe, amelyen az adott személy távol töltött napjainak tényleges száma látható.

19. Ban,-ben **Sérülés vagy betegség költségei** szakaszban válassza ki **Hozzáadás**.
20. Adja meg a dátumot a **Dátum** mezőben.
21. Ban,-ben **Költségtípus** mezőbe írjon be vagy válasszon egy értéket (például **Terápia**).

    Ezenkívül megadhat egy összeget, és csatolhat bármilyen igazoló dokumentumot a költséghez (például számlák vagy orvosi feljegyzések).

22. Válassza a **Hozzáadás** lehetőséget.
23. Adja meg a dátumot a **Dátum** mezőben.
24. Ban,-ben **Költségtípus** mezőbe írjon be vagy válasszon egy értéket (például **Orvos**).
25. Ban,-ben **Sérülések vagy betegségek kezelése** szakaszban válassza ki **Hozzáadás**.
26. Ban,-ben **A kezelés dátuma** mezőbe írja be a dátumot és az időt.
27. Ban,-ben **A kezelés típusa** mezőbe írjon be vagy válasszon egy értéket (például **sín**).
28. Opcionális: Állítsa be a **Sürgősségi kórházi látogatás** szakaszhoz **Igen**.
29. Ban,-ben **Kezelési megjegyzések** mezőbe írjon be egy értéket (pl.**Sín 2 hétig**).
30. Ban,-ben **Orvos neve** mezőbe írjon be egy értéket (pl.**Dr. Anderson**).
31. A Kezelő létesítmény és **hely** mezőbe adjon meg egy értéket (például **Elm St. Emergency**).
32. **A Kezelés részletei** mezőben adjon meg egy értéket (például **a röntgen megerősíti a törést, sín kopását**).
33. Válassza a **Mentés** lehetőséget.

Az eset állapotát bármikor frissítheti. Ha a sérülés vagy betegség feldolgozása folyamatban van, állítsa az állapotot Folyamatban **állásra**. Az incidens lezárása után csak az incidenshez kapcsolódó költségeket, kezeléseket vagy beadványokat adhat hozzá vagy távolíthat el. Más információk módosításához újra meg kell nyitnia a tokot.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
