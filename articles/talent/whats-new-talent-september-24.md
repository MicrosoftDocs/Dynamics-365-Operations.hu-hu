---
title: Új vagy módosult elemek a Dynamics 365 Talent – Core HR szolgáltatásban (2018. szeptember 24.)
description: Ez a témakör a Microsoft Dynamics 365 Talent – Core HR új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 09/21/2018
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
ms.search.validFrom: 2018-09-30
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e0c1a3bf7613db4887e0943a70ad6262a70997f0
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/06/2019
ms.locfileid: "2898966"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-september-24-2018"></a>Új vagy módosult elemek a Dynamics 365 Talent – Core HR szolgáltatásban (2018. szeptember 24.)

**Build 8.1.1015.0**

Ez a témakör a Core HR aktuális verziójában található új vagy módosított szolgáltatásokat írja le.

## <a name="currency-added-to-benefits"></a>Pénznem hozzáadva a Juttatásokhoz

A juttatáscsomagokat frissítettük, hogy tartalmazzák a juttatás pénznemét. Ez az új mező a dolgozó regisztrált juttatásainál is megtalálható. Ez az új mező a Juttatások karbantartása és a Juttatások listájának megtekintése biztonsági jogosultság része.

## <a name="update-proration-process--leave-and-absence"></a>A prorációs folyamat frissítése – Szabadság- és távollét

A szervezetek eltérően ítélhetik oda a szabadságot attól függően, hogy mikor csatlakoznak az alkalmazottak a vállalathoz, illetve mikor hagyják el azt. A szervezetet elhagyó alkalmazottak esetében egyeseknek esetleg be kell fejezniük a díjat a megszűnési időpontban, míg másoknak az utolsó napot is ki kell használniuk az elhatárolási folyamat leállítása érdekében. Ezek a módosítások lehetőséget biztosítanak a szervezetek számára, hogy kiválasszák, mikor szeretnék befejezni a regisztrációt a felmondási folyamat során. Ezek az új lehetőségek részei a Dolgozó elbocsátása és a Dolgozó elbocsátása a vezetői önkiszolgáló felületről jogosultságoknak. 

## <a name="other-changes"></a>Egyéb változások

Ebben a verzióban számos további hibajavítás is található.

## <a name="known-issue"></a>Ismert probléma

-   **Probléma:** Amikor új mellékletet ad egy dolgozóhoz, az **Új** és **Szerkesztés** gombok kiszürkítve jelennek meg. **Megoldás:** Mielőtt megnyitná a melléklet lapját, győződjön meg róla, hogy be vannak zárva a **Dolgozó** lap ténymezői. Ha a ténymezők be vannak zárva, amikor a **Dolgozó** lap be van töltve, akkor a mellékletek gombjai engedélyezettek. (Ezt a problémát kijavítjuk a következő platformfrissítéssel.)
