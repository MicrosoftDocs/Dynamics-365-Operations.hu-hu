---
title: Dolgozói sérülések és megbetegedések adatainak karbantartása
description: Ez a feladat azt írja le, hogyan lehet létrehozni egy sérülés vagy betegség esetet.
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
ms.openlocfilehash: 7c351919616c8ab5cf15d14c6cc79a5097e248fc
ms.sourcegitcommit: 7e0e2a266d9a9473df72e207554d9bd150e17ce3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/05/2021
ms.locfileid: "7771255"
---
# <a name="maintain-employee-injury-and-illness-information"></a>Dolgozói sérülések és megbetegedések adatainak karbantartása

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Javasoljuk, hogy először a „Sérülés és betegség beállítása” feladat-útmutatót fejezze be, mivel annak néhány beállítási adatait itt használjuk. 



Ez a feladatrögzítés a sérülés vagy betegség esetének létrehozásának alapvető lépéseit írja le. A sérülés vagy betegség adatain kívül az eset állapotát nyomon követi a program. Alapértelmezés szerint az esetek állapota **Nyitott**. Az állapotot a lap tetején található Eset állapot menüeleme segítségével **·** lehet kezelni.

1. Ugrás az **Emberi erőforrások dolgozókhoz \> – Sérülés és betegség Sérülés vagy betegség \>\> események**
2. Válassza az **Új** lehetőséget.
3. Az Eset leírása mezőben adjon meg egy értéket **·** (például Súlyos **·** sérülés).
4. A Dolgozó mezőben adjon meg vagy válasszon ki egy **·** értéket (például **Mottán** Ana).
5. Az esemény dátuma és időpontja mezőbe írja be a dátumot és az időpontot **·** (például 2016. január 20., 10:00 óra).
6. A Sérülés vagy betegség típus mezőjében adjon meg vagy válasszon ki egy értéket **·** (például **Rossz.**).
7. A Testrész mezőben adjon meg vagy válasszon ki egy értéket **·** (például **Visszajelz).**
8. Az Eredménytípus mezőben adjon meg vagy válasszon ki egy értéket **·** (például: **·** Vita).
9. A Jelentett dátum és idő mezőbe **írja be a dátumot és az** időpontot.

    A jelentett dátumnak és időpontnak későbbinek kell lennie, mint az eseménynek.

10. Az esetmezőt bevivő személynél adjon meg vagy válasszon ki egy értéket **·** (például **Azna Mottán).**

    A megadott személy lehet az eset alkalmazottja vagy más személye.

11. Az Esemény terület Where esemény történt mezőjébe írjon be egy értéket **·** **·** (például **·** Raktár).
12. Válassza az Igen lehetőséget a Munkahelyi létesítményekben mezőben, ha az esemény a **·** **·** munkahelyen történt.
13. A Munka elkezdésének dátuma és időpontja mezőben adja meg azt a dátumot és időpontot, amikor az érintett személy elkezdte dolgozni az **·** eseményt megelőzően.
14. Az Alkalmazott – feladat vagy feladat mezőben adja meg azt a feladatot vagy feladatot, amit a dolgozó az esemény végrehajtásakor végzett (például doboz **·** **·** betöltése). 
15. Az Esemény oka mezőben adja meg az esemény okát **(például elszavadhat** a **·** padlón).
16. A **Súlyossági szint** mezőben adjon meg vagy válasszon ki egy értéket.
17. Adjon meg egy értéket a Szükséges művelet mezőben (például azonnal adja meg az értékek **·** **·** tisztítását).
18. A Munkától távol napjainak várható mezőjébe írja be, hogy várhatóan hány nap távol van **az adott személy a** munkahelytől.

    Miután az egyes adatok visszaértek a munkahelyre, frissítse a Munkától távol napok mezőben a napok tényleges számát, ami azt jelenti, hogy **az adott személy távol** volt.

19. A Sérülés **vagy betegség költségei szakaszban válassza a Hozzáadás** **·** lehetőséget.
20. Adja meg a dátumot a **Dátum** mezőben.
21. A Költségtípus mezőben adjon meg vagy válasszon ki egy értéket **·** (például: **Család.**).

    Meg lehet továbbá adnia egy összeget, és csatolhatja a költséghez az alátámasztó dokumentációt (például a számlákat vagy az összeghez tartozó jegyzeteket).

22. Válassza a **Hozzáadás** lehetőséget.
23. Adja meg a dátumot a **Dátum** mezőben.
24. A Költségtípus mezőben adjon meg vagy válasszon ki egy **·** értéket **(például, 2015).**
25. A Sérülés **vagy betegség kezelése területen válassza a Hozzáadás** **·** lehetőséget.
26. A Kezelés **dátuma** mezőben adja meg a dátumot és az időpontot.
27. A Kezelés típusa mezőben adjon meg vagy válasszon ki egy értéket **·** (például **Splint).**
28. Nem kötelező: Állítsa a sürgősségi **kórházi ellátás** szakaszt Igen **·** beállításra.
29. A Kezelés megjegyzései mezőbe írjon be egy értéket **·** (például **Splint 2** hétig).
30. Az Orvos neve mezőbe írjon be egy értéket **·** (például **D. D.**).
31. A Kezelés intézmény és hely mezőjébe írjon be egy értéket **·** (például **Elm St.** Emergency).
32. A Kezelés részletei mezőben adjon meg egy értéket **·** (például az X-megerősítés megerősíti a kezeléssel kapcsolatos **kezeléssel kapcsolatos** információkat).
33. Válassza a **Mentés** lehetőséget.

Az eset állapotát bármikor frissítheti. Ha a sérülés vagy betegség feldolgozása folyamatban van, az állapotot Folyamatban **állapotra kell** állítani. Az esemény bezárása után csak az esethez kapcsolódó költségeket, kezeléseket vagy iktatásokat lehet hozzáadni és eltávolítani. Egyéb adatok módosítása csak akkor nyitható meg, ha újra megnyitja az esetet.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
