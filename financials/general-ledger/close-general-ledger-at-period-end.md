---
title: "A főkönyv lezárása időszak végén"
description: "Ez a témakör ismerteti a főkönyvi időszak záró végrehajtásakor általában befejezett feladatok."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14111
ms.assetid: cec9e039-c1a2-482c-bea6-e11d896eea9d
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ef99caf4570969d2b920cec8b53669ce2094965
ms.openlocfilehash: a7b72dfa98758b14d303d09890bd46729b1cdbe9
ms.lasthandoff: 03/31/2017


---

# <a name="close-the-general-ledger-at-period-end"></a>A főkönyv lezárása időszak végén

Ez a témakör ismerteti a főkönyvi időszak záró végrehajtásakor általában befejezett feladatok. 

A Főkönyvben, záró eljárásokat az időszak vagy az év végén hajthatja végre. A záró folyamatok előkészítik a rendszert egy új időszakra. A rendszer előkészítése az új év, az év végi szoros feldolgozása kell futtatnia. Minden egyes szervezet rendelkezik a különböző folyamatok és az időszak végén végrehajtott lépéseket. Az alábbiakban néhány választható lépést az időszak vége:

-   Fejezzen be minden feladatot minden más modulhoz, például Kinnlevőségek, Kötelezettségek, és Készlet.
-   Győződjön meg róla, hogy az összes napló feladása került.
-   Futtasson devizaátértékelést, hogy létrehozzon minden nem realizált nyereséget vagy elvesztett összeget.
-   Kiegyenlítési tranzakciók a főkönyvi számlák között.
-   Felosztási kérések feldolgozása.
-   Manuális helyesbítések időszak végén.
-   Tranzakciók naplózása, és a **Főkönyvi napló** jelentés felülvizsgálata.
-   Egy konszolidációs vállalat vagy Pénzügyi jelentések segítségével konszolidáció végrehajtása.
-   Időszak végi pénzügyi kimutatások létrehozása a Pénzügyi jelentések segítségével.
-   Főkönyvi időszak átállítása **Várakoztatott** állapotra, így további feladás nem történik. Időszakot korlátozhat egy megadott felhasználócsoportnak, amikor az időszakvégi tevékenységek megjelennek, a jobb ellenőrzés érdekében. Nincs időszakot, érdemes **véglegesen lezárt**, mert egy lezárt időszakot nem lehet újranyitni.

A pénzügyi időszak lezárása munkaterület megszervezéséhez és nyomon követéséhez szükséges különböző időszak záró folyamatok feladatokat is használható. Olvassa el a [pénzügyi időszak lezárása munkaterület](financial-period-close-workspace.md) és [év végén közel](Year-end-close.md) kaphat tájékoztatást. 




