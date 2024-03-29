---
title: Retail termékek beállítása
description: Ez a cikk ismerteti a termékek beállítását a Dynamics 365 Commerce rendszerben.
author: josaw1
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.custom: 16181
ms.assetid: b1b57734-1406-4ed6-8e28-21c705ee17e2
ms.search.industry: Retail
ms.search.form: RetailProductAndCategoryWorkspace, EcoResProductDetails
ms.openlocfilehash: 22a3ecb235b21e239b23e5450ca4a2f12f9a41ac
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276074"
---
# <a name="set-up-retail-products"></a>Retail termékek beállítása

[!include [banner](includes/banner.md)]

Ez a cikk ismerteti a termékek beállítását a Dynamics 365 Commerce rendszerben.

Mielőtt kiskereskedelmi értékesítésre kínálna termékeket kereskedelmi csatornái révén, létre kell hoznia és konfigurálnia kell azokat a rendszerben. A Commerce egész szervezetre érvényes termékeket hoz létre az alaptermékben. Létrehozhat termékeket, meghatározhatja a terméktulajdonságokat és -attribútumokat, valamint hozzárendelheti a termékeket különböző kereskedelmi hierarchiákhoz. Ahhoz, hogy a termék elérhetővé váljon a csatornák számára, valamint hogy felvehesse azokat az aktív szortimentbe, ki kell adnia a termékeket azoknak a jogi személyeknek, amelyekben azok rendelkezésre állnak. A csatornák használatával értékesített termékek beállításához hajtsa végre a következő feladatokat.

1. **Határozzon meg termékhierarchiát.** A Commerce rendszerben a kategóriahierarchia funkciók segítségével meghatározhatja a hierarchiákat a termékek csoportosításához és kategorizálásához, amelyeket a kiskereskedelmi csatornáin keresztül forgalmaz. A felhasználó által definiált és rendszerattribútumokat a kategória szintjén lehet megadni. Ezt követően a kategóriához rendelt összes termék örökli azokat az attribútumokat. Több kategóriahierarchiát is meg lehet adni, és az egyes termékeket több hierarchiához is hozzárendelheti. Azonban egy hierarchiában az egyes termékek csak egy kategóriához rendelhetők hozzá.
2. **Termékek és termékvariációk hozzáadása az alaptermékhez.** A termékek, amelyek alaptermékhez vannak hozzáadva, a globális termékek listáját képviselik. Termékeket manuálisan is hozzá lehet adni, egyesével, vagy importálhatja a termékadatokat a szállítóktól.
3. **Termékek kiadása jogi személynek** Csak a jogi személyek számára kiadott termékek bocsáthatók rendelkezésre az Ön csatornái számára. Amikor először határoz meg egy terméket, azt a szervezeti szinten teszi. Ezután kiválaszthat egy vagy több jogi személyt, akiknek kiadja a terméket. A termék ekkor elérhetővé válik több csatorna számára a szervezeten belül. A funkció segítségével lehetséges a termék egyszeri létrehozása, termékattribútumok és tulajdonságok hozzáadása és frissítése egy helyen, a termék szervezeten belüli elosztása a csatornákban, ahol az nem áll rendelkezésre.
4. **Termékek hozzáadása szortimentekhez.** Egy szortiment felel egy csatornákban kínált termékkollekciónak. Megadhat egy vagy több szortimentet, és minden termék egy vagy több szortimenthez rendelhető hozzá. Termékek csatornákhoz való hozzárendeléséhez a szortimenteket hozzá kell rendelni a csatornákhoz. Ha létrehoz egy szortimentet, hozzáadhat termékeket, ha azokat még nem adták ki jogi személynek. Mielőtt azonban a termékeket a csatornák számára elérhetővé teheti, ki kell adnia őket egy jogi személy számára.
5. **Termékek hozzáadása a navigációs hierarchiákhoz.** Termékeket a Commerce navigációs hierarchiájában kategorizálni kell, hogy azok tallózhatók legyenek online vagy egy pénztárnál (POS).
6. **Termékek hozzáadása a katalógusokhoz.** Annak ellenére, hogy ez a lépés nem kötelező a POS-hez, az online áruház esetében szükséges, hogy a termékek szerepeljenek legalább egy katalógusban.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
