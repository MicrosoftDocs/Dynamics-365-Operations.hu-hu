---
title: Projekt költségvetéseinek átvitele a pénzügyi év végén
description: Ez a cikk a fennmaradó költségvetési összegek későbbi évekre történő átvitelével és a költségvetési tételjegyzék létrehozásával kapcsolatosan tartalmaz információkat.
author: RadhikaRS
manager: AnnBe
ms.date: 03/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 41e985825a24de2d6510938cf3d61715c35f9939
ms.sourcegitcommit: 2ea5ff784500d5be9203e9a1560eabd4fea46f4e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172330"
---
# <a name="transfer-project-budgets-at-fiscal-year-end"></a>Projekt költségvetéseinek átvitele a pénzügyi év végén

[!include [banner](../includes/banner.md)]

Ha egy többéves projekten dolgozik, előfordulhat, hogy a pénzügyi év végén marad még a költségvetéséből. A fennmaradó költségvetést átviheti egy későbbi évre, és költségvetési tételjegyzéket hozhat létre az összegekhez a kapcsolódó főkönyvi számlákban. Mielőtt átviszi a fennmaradó összegeket, tekintse át és elemezze a fennmaradó költségvetési összegeket.

## <a name="review-and-analyze-remaining-budget-amounts"></a>Fennmaradó költségvetési összegek áttekintése és elemzése

Végezze el az alábbi lépéseket a projektek év végi költségvetési összegeinek áttekintéséhez az összegek átvitele nélkül.

1. Válassza a **Projektvezetés és könyvelés** > **Időszakos** > **Költéségvetések** > **Költségvetések átvitele** lehetőséget. 
2. A **Projektköltségvetés átviteli folyamata** oldalon az **Év végi lehetőségek** lapon győződjön meg arról, hogy **A projekt költségvetéséből fennmaradó összegek áthozatala** ne legyen engedélyezve.
3. A **Paraméterek** lapon a **Projektköltségvetés éve** mezőben válassza ki annak a pénzügyi évnek a kezdetét, amelyre vonatkozóan meg szeretné tekinteni a projektek fennmaradó költségvetési összegét. 
4. A **Nyitó pénzügyi év** mezőben válassza ki annak a pénzügyi évnek a kezdetét, amelyre vonatkozóan meg szeretné tekinteni a fennmaradó költségvetési összeget. 
5. A **Kezdő előrejelzési modell** mezőben válassza a **Fennmaradó költségvetés** elemet. 
6. Ha szerepeltetni szeretné a kiválasztott feltételeknek megfelelő és nincs fennmaradó költségvetése, válassza ki a **Nulla értékű fennmaradó összegek megjelenítése** lehetőséget.  
7. A **Költségvetések kiválasztása** lapon jelölje be az **Összes költségvetés beolvasása** lehetőséget a kiválasztott feltételeknek megfelelő összes költségvetés betöltéséhez, majd válassza a **Feldolgozás** elemet. 
8. Egy adatbázis-lekérdezés tervezéséhez, amely betölti a projektköltségvetések meghatározott készletét az ablaktáblába, válassza a **Kijelölt költségvetések** beolvasása lehetőséget.

Ha további tájékoztatást szeretne az ablaktábla egy adott soráról, válassza ki a sort, majd válassza a **Költségvetés részleteinek megtekintése** vagy a **Számlák megtekintése** parancsot.

## <a name="carry-forward-remaining-budget-amounts"></a>A költségvetésből fennmaradó összegek áthozatala 

A fennmaradó költségvetési összegek feldolgozásakor létrehozhat főkönyvi tranzakciókat az átvitt összegekhez. Főkönyvi tranzakciók létrehozásához hajtsa végre a következő szakasz lépéseit: [Költségvetési összegek átvitele és főkönyvi tranzakciók létrehozása](#carry-forward). 

> [!NOTE]
> Az átvitt költségvetési összegeket a program átviszi abba az előrejelzési modellbe, amelyet kiválasztottak átviteli előrejelzési modellként az **Előrejelzési modellek** lapon.  

## <a name="carry-forward-budget-amounts-and-create-general-ledger-transactions"></a><a name="carry-forward"></a>Költségvetési összegek átvitele és főkönyvi tranzakciók létrehozása

1.  Menjen a **Projektvezetés és könyvelés** > **Időszakos** > **Költéségvetések** > **Költségvetések átvitele** menüpontba. 
2. A **Projektköltségvetés átviteli folyamata lap** lapon válassza az **Év végi** lehetőséget majd engedélyezze a **Projekt költségvetéséből fennmaradó összegek áthozatala** és a **Költésgvetésijegyzék-bejegyzések létrehozása a főkönyvben** lehetőségeket. 
3. A **Paraméterek** lapon a **Projekt paraméterei** mezőcsoportban válassza a következőt:

   - **Projektköltségvetés éve**: Válassza ki annak a pénzügyi évnek a kezdetét, amelyre vonatkozóan meg szeretné tekinteni a fennmaradó költségvetési összegeket. 
   - **Eredmény**: Eredménytranzakciókat hozhat létre a főkönyvben. 
   -  **Befejezetlen termelés**: Befejezetlen termelés (WIP) tranzakciók létrehozása a főkönyvben.
   -  **Bérlista**: Bérfoglalási tranzakciók létrehozása a főkönyvben. 

5. A **Főkönyv** mezőcsoportban adja meg a következő adatokat: 

   - A **Nyitó pénzügyi év** mezőben válassza ki annak a pénzügyi évnek a kezdetét, amelyre át szeretné vinni a projektek fennmaradó költségvetési összegét. Az alapértelmezett érték a **Projekt költségvetési éve** mezőben megadott évet követő év.
   -  Az **Átviteli időszak** mezőben jelölje ki azt az időszakot, amelyben létre kívánja hozni a költségvetési tételjegyzékbeli részletes adatokat a főkönyvben. Ez általában a nyitó pénzügyi év első időszaka.

6. A **Másolása innen/ide** mezőcsoportban adja meg a következő adatokat:

   - A **Kezdő előrejelzési modell** mezőben válassza ki a projektek átvinni kívánt fennmaradó költségvetési összegeihez társított projekt-költségvetési előrejelzési modellt. 
   - A **Cél főkönyvi költségvetésmodell** mezőben válassza ki a főkönyvbe átvinni kívánt költségvetési összegekhez társított főkönyvi költségvetési modellt. 
   -  Ha a projekt értékesítési pénznemét kívánja használni a projektek költségvetési összegének átvitelekor létrehozott főkönyvi tranzakciókhoz, válassza ki az **Értékesítési pénznem átvitele** lehetőséget. Ha nincs bejelölve ez a beállítás, akkor a tranzakciók a könyvelési pénznemben jelennek meg. 
   -  Ha a képernyő alján levő ablaktáblában megjelenített projektek között fel szeretné tüntetni azokat a projekteket is, amelyekhez nem tartozik fennmaradó költségvetési összeg, de amelyek megfelelnek egyéb kiválasztott feltételeknek, válassza ki a **Nulla értékű fennmaradó összegek megjelenítése** lehetőséget.

7. A **Költségvetések kiválasztása** lapon jelölje be az **Összes költségvetés beolvasása** lehetőséget a kiválasztott feltételeknek megfelelő összes költségvetés betöltéséhez. Inkább egy olyan adatbázis-lekérdezés tervezéséhez, amely betölti a projektköltségvetések meghatározott készletét az ablaktáblába, válassza a **Kijelölt költségvetések** beolvasása lehetőséget.
8. Mindegyik feldolgozni kívánt projektnél jelölje be a projekt sorának elején levő lehetőséget.

    > [!TIP]
    > A projektek egészének vagy többségének kiválasztásához jelölje be a jelölőnégyzetet a bal felső sarokban. A projektek feldolgozásának kizárásához törölje a jelet az adott projekthez tartozó jelölőnégyzetből.

9. A kiválasztott projektekhez tartozó fennmaradó költségvetési összegeknek a kijelölt pénzügyi évre való átviteléhez, valamint költségvetési tételjegyzékbeli részletes adatok létrehozásához a főkönyvben válassza a **Feldolgozás** lehetőséget.

## <a name="carry-forward-budget-amounts-without-creating-general-ledger-transactions"></a>Költségvetési összegek átvitele főkönyvi tranzakciók létrehozása nélkül

1. Válassza a **Projektvezetés és könyvelés** > **Időszakos** > **Költéségvetések** > **Költségvetések átvitele** lehetőséget.
2. A **Projektköltségvetés átviteli folyamata** oldalon az **Év végi lehetőségek** lapon válassza ki **A projekt költségvetéséből fennmaradó összegek áthozatala** lehetőséget.
3. A **Paraméterek** csoportban a **Projektköltségvetés éve** mezőben válassza ki annak a pénzügyi évnek a kezdetét, amelyre vonatkozóan meg szeretné tekinteni a projektek fennmaradó költségvetési összegeit.
4. A **Másolása innen/ide** csoportban adja meg a következő adatokat:

   - A **Kezdő előrejelzési modell** mezőben válassza ki a projektek átvinni kívánt fennmaradó költségvetési összegeihez társított projekt-költségvetési előrejelzési modellt. 
   - Válassza ki a **Nulla értékű fennmaradó összegek megjelenítése** lehetőséget, ha szerepeltetni szeretné a kiválasztott feltételeknek megfelelő és nincs fennmaradó költségvetése.
   - A **Költségvetések kiválasztása** csoportban jelölje be az **Összes költségvetés beolvasása** lehetőséget a kiválasztott feltételeknek megfelelő összes költségvetés betöltéséhez. Egy adatbázis-lekérdezés tervezéséhez, amely betölti a projektköltségvetések meghatározott készletét az ablaktáblába, válassza a **Kijelölt költségvetések** beolvasása lehetőséget.

5. Mindegyik feldolgozni kívánt projektnél jelölje be a projekt sorának elején levő lehetőséget. 
6. Válassza a **Feldolgozás** lehetőséget a kiválasztott projektekhez tartozó fennmaradó költségvetési összegeknek a kijelölt pénzügyi évre való átviteléhez.

