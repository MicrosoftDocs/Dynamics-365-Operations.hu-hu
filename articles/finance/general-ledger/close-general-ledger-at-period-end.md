---
title: A főkönyv lezárása időszak végén
description: Ez a témakör azokat a feladatokat írja le, amelyek általában a főkönyv időszaki zárása során hajtódnak végre.
author: aprilolson
ms.date: 08/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerPeriodCloseWorkspace
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14111
ms.assetid: cec9e039-c1a2-482c-bea6-e11d896eea9d
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 42a5df1cd1a73462c93012b26f9b9b5c1631f2ce
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8878041"
---
# <a name="close-the-general-ledger-at-period-end"></a>A főkönyv lezárása időszak végén

[!include [banner](../includes/banner.md)]

Ez a témakör azokat a feladatokat írja le, amelyek általában a főkönyv időszaki zárása során hajtódnak végre. 

A Főkönyvben, záró eljárásokat az időszak vagy az év végén hajthatja végre. A záró folyamatok előkészítik a rendszert egy új időszakra. Az új év előkészítéséhez futtatni kell az év végi zárási folyamatot. Minden szervezetnek különböző folyamatai és lépései vannak, amelyek az időszakok végén futnak le. Néhány a lehetséges időszakvégi lépések közül:

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

A **pénzügyi időszak zárási** munkaterülete a különböző időszakvégi folyamatokhoz szükséges feladatok rendszerezésére és nyomon követésére használható. 


A képernyővel kapcsolatos további információkat lásd a következő témakörökben:
- [Pénzügyi időszak lezárása munkaterület](financial-period-close-workspace.md) 
- [Év végi zárás](Year-end-close.md)  
- [Pénzügyi időszakok tömeges lezárása](tasks/mass-financial-period-close.md)






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
