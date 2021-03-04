---
title: Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban (2020. január 7.)
description: Ez a cikk a Microsoft Dynamics 365 Talent új vagy módosított funkcióit írja le.
author: Darinkramer
manager: AnnBe
ms.date: 01/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2020-01-07
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e227c614fdbfe6f3dd410f1a533c593979abf1ec
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461407"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-january-7-2020"></a>Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban (2020. január 7.)

Ez a cikk a Dynamics 365 Talent szolgáltatásban található új vagy módosított funkciókat írja le.

## <a name="changes-in-attract"></a>Változások az Attract-ben

A kiadás a Dynamics 365 Talent: Attract apró hibáinak javításait is tartalmazza.

## <a name="changes-in-onboard"></a>Változások az Onboard alkalmazásban

A kiadás a Dynamics 365 Talent: Onboard apró hibáinak javításait is tartalmazza.

## <a name="changes-in-core-hr"></a>A Core HR módosításai

A szakaszban ismertetett módosítások a 8.1.2697-ös buildre vonatkoznak. A néhány fejlécben látható, zárójelben lévő számok az Microsoft Dynamics Lifecycle Services (LCS) támogatási számaira vonatkoznak.

 
### <a name="cant-delete-workers-that-dont-have-employment-records---386157"></a>Nem törölhet olyan alkalmazottakat, akiknél nem szerepelnek a foglalkoztatási rekordok – (386157)

Ez a módosítás hozzáad egy törlési beállítást **Munkanélküli dolgozók** képernyőjéhez. A dolgozók akkor jelennek meg ezen a képernyőn, ha a dolgozóhoz nem léteznek jövőbeli, aktív vagy múltbeli munkaviszonyok. Ebben a verzióban a törlés csak a rendszergazdák számára engedélyezett. A következő heti kiadásban azonban a biztonsági frissítés minden HR-segéd szerepkörrel rendelkező felhasználó számára lehetővé teszi, hogy a foglalkoztatás nélküli alkalmazottakat eltávolítsa. Ezeket a változtatásokat manuálisan is elvégezheti a következő lépéseket követve.

1. Ugrás a **Biztonsági konfiguráció** elemre.
2. A **Jogosultságok** lapon szűrje a **Jogosultságok** listáját a **Dolgozók karbantartása** céljából.
3. Válassza a **Hivatkozások** oszlopban a **Megjelenítendő menüelemek** elemet.
4. A **Megjelenítendő menüelemek** közül válassza ki a **HcmWOrkersWithoutEmployment** elemet.
5. A **Törlési** engedélyt módosítsa Engedélyezre.
6. Válassza ki a **Nem közzétett objektumok** lapot.
7. Válassza az **Összes közzététele** lehetőséget.


[!INCLUDE[footer-include](../includes/footer-banner.md)]