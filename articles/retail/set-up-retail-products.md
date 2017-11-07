---
title: "Kereskedelmi termékek beállítása"
description: "Ez a cikk a kiskereskedelmi termékek Microsoft Dynamics 365 for Retail rendszerben történő beállítását írja le."
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16181
ms.assetid: b1b57734-1406-4ed6-8e28-21c705ee17e2
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 85b794bb1a1a7a4e9b0e811d90408ed8872a6f0a
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="set-up-retail-products"></a>Kiskereskedelmi termékek beállítása

[!include[banner](includes/banner.md)]


Ez a cikk a kiskereskedelmi termékek Microsoft Dynamics 365 for Retail rendszerben történő beállítását írja le.

Mielőtt újraértékesítésre kínálna termékeket kiskereskedelmi csatornái révén, létre kell hoznia és konfigurálnia kell a termékeket a Dynamics 365 for Retail rendszerben. A kiskereskedelem a Microsoft Dynamics 365 for Retail rendszerben a termékfunkciók segítségével hozza létre a szervezeti szintű termékeket az alaptermékben. Létrehozhat termékeket, meghatározhatja a terméktulajdonságokat és -attribútumokat és a termékeket hozzárendelheti kiskereskedelmi hierarchiákhoz. Ahhoz, hogy elérhetővé tehesse a termékeket a kiskereskedelmi csatornák számára és hozzáadhassa őket egy aktív szortimenthez, fel kell szabadítania a termékeket a jogi személyek számára, amelyeknél azok rendelkezésre állnak. A kiskereskedelmi csatornák használatával értékesített termékek beállításához hajtsa végre a következő feladatokat.

1.  Határozzon meg egy kiskereskedelmi termékhierarchiát. A Dynamics 365 for Retail rendszerben a kategória-hierarchia funkciók segítségével meghatározhatja a kiskereskedelmi hierarchiákat a termékek csoportosításához és kategorizálásához amelyeket a kiskereskedelmi csatornáin keresztül forgalmaz. A felhasználó által definiált és rendszerattribútumokat a kategória szintjén lehet megadni. Ezt követően a kategóriához rendelt összes termék örökli azokat az attribútumokat. Több kategóriahierarchiát is meg lehet adni, és az egyes termékeket több hierarchiához is hozzárendelheti. Azonban egy hierarchiában az egyes termékek csak egy kategóriához rendelhetők hozzá.
2.  Termékek és termékvariációk hozzáadása az alaptermékhez. A termékek, amelyek alaptermékhez vannak hozzáadva, a globális termékek listáját képviselik. Termékeket manuálisan is hozzá lehet adni, egyesével, vagy importálhatja a termékadatokat a szállítóktól.
3.  Termékek kiadása jogi személynek Csak a jogi személynek számára kiadott termékek bocsáthatók rendelkezésre a kiskereskedelmi csatornák számára. Amikor először határoz meg egy terméket, azt a szervezeti szinten teszi. Ezután kiválaszthat egy vagy több jogi személyt, akiknek kiadja a terméket. A termék ekkor elérhetővé válik több kiskereskedelmi csatorna számára a szervezeten belül. A funkció segítségével lehetséges a termék egyszeri létrehozása, termékattribútumok és tulajdonságok hozzáadása és frissítése egy helyen, a termék szervezeten belüli elosztása a kiskereskedelmi csatornákban, ahol az nem áll rendelkezésre.
4.  Termékek hozzáadása szortimentekhez. Egy szortiment felel egy kiskereskedelmi csatornákban kínált termékkollekciónak. Megadhat egy vagy több szortimentet, és minden termék egy vagy több szortimenthez rendelhető hozzá. Termékek kiskereskedelmi csatornákhoz való hozzárendeléséhez a szortimenteket hozzá kell rendelni a kiskereskedelmi csatornákhoz. Ha létrehoz egy szortimentet, hozzáadhat termékeket, ha azokat még nem adták ki jogi személynek. Mielőtt azonban a termékeket a kiskereskedelmi csatornák számára elérhetővé teheti, ki kell adnia őket egy jogi személy számára.
5.  Termékek hozzáadása a navigációs hierarchiákhoz. Termékeket a Kiskereskedelmi navigációs hierarchiájában kategorizálni kell, hogy azok tallózhatók legyenek online vagy egy pénztárnál (POS).
6.  Termékek hozzáadása a katalógusokhoz. Annak ellenére, hogy ez a lépés nem kötelező a POS-hez, az online áruház esetében szükséges, hogy a termékek szerepeljenek legalább egy katalógusban.





