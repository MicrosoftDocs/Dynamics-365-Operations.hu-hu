---
title: "Kereskedelmi termékek beállítása"
description: "A cikk ismerteti, hogyan állítható be a Microsoft Dynamics 365 műveletek - kiskereskedelmi termékek kiskereskedelmi."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16181
ms.assetid: b1b57734-1406-4ed6-8e28-21c705ee17e2
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 116c49174989ff14982027cc235640c2ad7322f2
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-retail-products"></a>Kereskedelmi termékek beállítása

A cikk ismerteti, hogyan állítható be a Microsoft Dynamics 365 műveletek - kiskereskedelmi termékek kiskereskedelmi.

Viszonteladásra szánt termékek is kínálnak a kiskereskedelmi csatornák, mielőtt létrehozása és konfigurálnia kell a termékek 365 Dynamics műveletek AX - Kiskereskedelmi. Kiskereskedelmi Dynamics 365 műveletekhez a termékjellemzők segítségével hozza létre a szervezeti szintű termékek a termék mester. Létrehozhat termékeket, meghatározhatja a terméktulajdonságokat és -attribútumokat és a termékeket hozzárendelheti kiskereskedelmi hierarchiákhoz. Ahhoz, hogy elérhetővé tehesse a termékeket a kiskereskedelmi csatornák számára és hozzáadhassa őket egy aktív szortimenthez, fel kell szabadítania a termékeket a jogi személyek számára, amelyeknél azok rendelkezésre állnak. A kiskereskedelmi csatornák használatával értékesített termékek beállításához hajtsa végre a következő feladatokat.

1.  Határozzon meg egy kiskereskedelmi termékhierarchiát. Szolgáltatásaival a kategória hierarchia 365 Dynamics műveletekhez, csoportosítására és kategorizálhatja a termékeket a kiskereskedelmi csatornák olyan kiskereskedelmi hierarchiák adhatja meg. A felhasználó által definiált és rendszerattribútumokat a kategória szintjén lehet megadni. Ezt követően a kategóriához rendelt összes termék örökli azokat az attribútumokat. Több kategóriahierarchiát is meg lehet adni, és az egyes termékeket több hierarchiához is hozzárendelheti. Azonban egy hierarchiában az egyes termékek csak egy kategóriához rendelhetők hozzá.
2.  Termékek és termékvariációk hozzáadása az alaptermékhez. A termékek, amelyek alaptermékhez vannak hozzáadva, a globális termékek listáját képviselik. Termékeket manuálisan is hozzá lehet adni, egyesével, vagy importálhatja a termékadatokat a szállítóktól.
3.  Termékek kiadása jogi személynek Csak a jogi személynek számára kiadott termékek bocsáthatók rendelkezésre a kiskereskedelmi csatornák számára. Amikor először határoz meg egy terméket, azt a szervezeti szinten teszi. Ezután kiválaszthat egy vagy több jogi személyt, akiknek kiadja a terméket. A termék ekkor elérhetővé válik több kiskereskedelmi csatorna számára a szervezeten belül. A funkció segítségével lehetséges a termék egyszeri létrehozása, termékattribútumok és tulajdonságok hozzáadása és frissítése egy helyen, a termék szervezeten belüli elosztása a kiskereskedelmi csatornákban, ahol az nem áll rendelkezésre.
4.  Termékek hozzáadása szortimentekhez. Egy szortiment felel egy kiskereskedelmi csatornákban kínált termékkollekciónak. Megadhat egy vagy több szortimentet, és minden termék egy vagy több szortimenthez rendelhető hozzá. Termékek kiskereskedelmi csatornákhoz való hozzárendeléséhez a szortimenteket hozzá kell rendelni a kiskereskedelmi csatornákhoz. Ha létrehoz egy szortimentet, hozzáadhat termékeket, ha azokat még nem adták ki jogi személynek. Mielőtt azonban a termékeket a kiskereskedelmi csatornák számára elérhetővé teheti, ki kell adnia őket egy jogi személy számára.
5.  Termékek hozzáadása a navigációs hierarchiaként. Termékek online vagy a in point of (POS) értékesítés böngészhetnek, mielőtt azokat a navigációs kiskereskedelmi hierarchia kell kategorizált.
6.  Termékek hozzáadása a katalógusokhoz. Bár ez a lépés nem kötelező a POS, online áruházak van szükség, hogy legalább egy katalógus termékeket kell venni.



