---
title: Kiskereskedelmi termékek beállítása
description: Ez a cikk ismerteti kiskereskedelmi termékek beállítását a Dynamics 365 Retail rendszerben.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailProductAndCategoryWorkspace, EcoResProductDetails
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
ms.openlocfilehash: 74fa3a87ac2993adca3edf003bbc39371ce8e289
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/24/2019
ms.locfileid: "2024775"
---
# <a name="set-up-retail-products"></a>Kiskereskedelmi termékek beállítása

[!include [banner](includes/banner.md)]

Ez a cikk ismerteti kiskereskedelmi termékek beállítását a Dynamics 365 Retail rendszerben.

Mielőtt újraértékesítésre kínálna termékeket kiskereskedelmi csatornái révén, létre kell hoznia és konfigurálnia kell azokat a Dynamics 365 Retail rendszerben. A Retail egész szervezetre érvényes termékeket hoz létre az alaptermékben. Létrehozhat termékeket, meghatározhatja a terméktulajdonságokat és -attribútumokat, valamint hozzárendelheti a termékeket különböző kiskereskedelmi hierarchiákhoz. Ahhoz, hogy elérhetővé tehesse a termékeket a kiskereskedelmi csatornák számára és hozzáadhassa őket egy aktív szortimenthez, fel kell szabadítania a termékeket a jogi személyek számára, amelyeknél azok rendelkezésre állnak. A kiskereskedelmi csatornák használatával értékesített termékek beállításához hajtsa végre a következő feladatokat.

1. Határozzon meg egy kiskereskedelmi termékhierarchiát. A Retail rendszerben a kategóriahierarchia funkciók segítségével meghatározhatja a kiskereskedelmi hierarchiákat a termékek csoportosításához és kategorizálásához amelyeket a kiskereskedelmi csatornáin keresztül forgalmaz. A felhasználó által definiált és rendszerattribútumokat a kategória szintjén lehet megadni. Ezt követően a kategóriához rendelt összes termék örökli azokat az attribútumokat. Több kategóriahierarchiát is meg lehet adni, és az egyes termékeket több hierarchiához is hozzárendelheti. Azonban egy hierarchiában az egyes termékek csak egy kategóriához rendelhetők hozzá.
2. Termékek és termékvariációk hozzáadása az alaptermékhez. A termékek, amelyek alaptermékhez vannak hozzáadva, a globális termékek listáját képviselik. Termékeket manuálisan is hozzá lehet adni, egyesével, vagy importálhatja a termékadatokat a szállítóktól.
3. Termékek kiadása jogi személynek Csak a jogi személynek számára kiadott termékek bocsáthatók rendelkezésre a kiskereskedelmi csatornák számára. Amikor először határoz meg egy terméket, azt a szervezeti szinten teszi. Ezután kiválaszthat egy vagy több jogi személyt, akiknek kiadja a terméket. A termék ekkor elérhetővé válik több kiskereskedelmi csatorna számára a szervezeten belül. A funkció segítségével lehetséges a termék egyszeri létrehozása, termékattribútumok és tulajdonságok hozzáadása és frissítése egy helyen, a termék szervezeten belüli elosztása a kiskereskedelmi csatornákban, ahol az nem áll rendelkezésre.
4. Termékek hozzáadása szortimentekhez. Egy szortiment felel egy kiskereskedelmi csatornákban kínált termékkollekciónak. Megadhat egy vagy több szortimentet, és minden termék egy vagy több szortimenthez rendelhető hozzá. Termékek kiskereskedelmi csatornákhoz való hozzárendeléséhez a szortimenteket hozzá kell rendelni a kiskereskedelmi csatornákhoz. Ha létrehoz egy szortimentet, hozzáadhat termékeket, ha azokat még nem adták ki jogi személynek. Mielőtt azonban a termékeket a kiskereskedelmi csatornák számára elérhetővé teheti, ki kell adnia őket egy jogi személy számára.
5. Termékek hozzáadása a navigációs hierarchiákhoz. Termékeket a Kiskereskedelmi navigációs hierarchiájában kategorizálni kell, hogy azok tallózhatók legyenek online vagy egy pénztárnál (POS).
6. Termékek hozzáadása a katalógusokhoz. Annak ellenére, hogy ez a lépés nem kötelező a POS-hez, az online áruház esetében szükséges, hogy a termékek szerepeljenek legalább egy katalógusban.
