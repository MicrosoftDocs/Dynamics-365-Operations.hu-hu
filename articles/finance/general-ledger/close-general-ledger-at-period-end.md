---
title: A főkönyv lezárása időszak végén
description: A témakör a főkönyvi időszak zárásának végrehajtásakor általában elvégzett feladatokat ismerteti.
author: aprilolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerPeriodCloseWorkspace
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14111
ms.assetid: cec9e039-c1a2-482c-bea6-e11d896eea9d
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7eca533ed1621ec3507d8510f75842c0f0165275
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186739"
---
# <a name="close-the-general-ledger-at-period-end"></a>A főkönyv lezárása időszak végén

[!include [banner](../includes/banner.md)]

A témakör a főkönyvi időszak zárásának végrehajtásakor általában elvégzett feladatokat ismerteti. 

A Főkönyvben, záró eljárásokat az időszak vagy az év végén hajthatja végre. A záró folyamatok előkészítik a rendszert egy új időszakra. A rendszer új évre történő felkészítéséhez futtatni kell az év végi zárás folyamatot. Minden szervezetnek különböző folyamatai és lépései vannak, amelyek az időszakok végén futnak le. Néhány a lehetséges időszakvégi lépések közül:

-   Fejezzen be minden feladatot minden más modulhoz, például Kinnlevőségek, Kötelezettségek, és Készlet.
-   Győződjön meg róla, hogy az összes napló feladása került.
-   Futtasson devizaátértékelést, hogy létrehozzon minden nem realizált nyereséget vagy elvesztett összeget.
-   Kiegyenlítési tranzakciók a főkönyvi számlák között.
-   Felosztási kérések feldolgozása.
-   Manuális helyesbítések időszak végén.
-   Tranzakciók naplózása, és a **Főkönyvi napló** jelentés felülvizsgálata.
-   Egy konszolidációs vállalat vagy Pénzügyi jelentések segítségével konszolidáció végrehajtása.
-   Időszak végi pénzügyi kimutatások létrehozása a Pénzügyi jelentések segítségével.
-   Főkönyvi időszak átállítása **Várakoztatott** állapotra, így további feladás nem történik. Időszakot korlátozhat egy megadott felhasználócsoportnak, amikor az időszakvégi tevékenységek megjelennek, a jobb ellenőrzés érdekében. Nem tanácsos időszakokat **Véglegesen lezárva** állapotba helyezni, mert egy lezárt időszakot nem lehet újranyitni.

A Pénzügyi időszak lezárása munkaterület használható a különböző időszakzáró folyamatok megszervezéséhez és nyomon követéséhez. 


A képernyővel kapcsolatos további információkat lásd a következő témakörökben:
- [Pénzügyi időszak lezárása munkaterület](financial-period-close-workspace.md) 
- [Év végi zárás](Year-end-close.md)  
- [Pénzügyi időszakok tömeges lezárása](tasks/mass-financial-period-close.md)




