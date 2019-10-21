---
title: Új vagy módosult elemek a Dynamics 365 Talent – Core HR szolgáltatásban (2018. október 16.)
description: Ez a témakör a Microsoft Dynamics 365 Talent – Core HR új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 10/22/2018
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
ms.search.validFrom: 2018-10-22
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 13e89faa3f8470125010ccdb40a6f01c0a9c4fe7
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/23/2019
ms.locfileid: "2008777"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-core-hr-october-19-2018"></a>Új vagy módosult elemek a Dynamics 365 Talent: Core HR szolgáltatásban (2018. október 19.)

[!include[banner](includes/banner.md)]

**Build 8.1.1067**

Ez a témakör a Core HR aktuális verziójában található új vagy módosított szolgáltatásokat írja le.

## <a name="allow-managers-to-update-time-off-requests"></a>A távollétkérelmek frissítésének engedélyezése a vezetők számára

Az alkalmazotti távollétkérelmeket kell frissíteni kell a munkafolyamatban történő jóváhagyást követően. Sok esetben a vezető végzi ezeket a frissítéseket, az alkalmazott nevében. Ez a funkció lehetővé teszi a vezetőknek a távollét frissítését vagy a távollétkérelmek visszavonását a munkavállalóik nevében. Ezt a funkciót a **Munka más nevében** paraméter szabályozza, amely az **Emberi erőforrások - paraméterek** oldalon állítható be. 
 
## <a name="allow-hr-to-update-time-off-requests"></a>A távollétkérelmek frissítésének engedélyezése a HR számára

Hasonlóan a fenti funkcióhoz, szükséges lehet, hogy a HR frissítse a a munkavállalók távollétkérelmét miután azok jóváhagyták-e a munkafolyamaton keresztül. Ez a funkció lehetővé teszi a HR-felhasználók számára a távollétkérelmek frissítését. Ez a képesség a **Személyek** munkaterületen és a **Dolgozó** lapon kapcsolható be a **Távollét megtekintése** beállítással. Ezeken az oldalakon HR felhasználók megtekinthetik és frissíthetik a távollét-tranzakciókat, hasonlóan ahhoz, ahogy a vezetők elvégezhetik ezeket a műveleteket.

A biztonsági feladat, amely szabályozza a hozzáférést ehhez a funkcióhoz a következő:
- Feladat: Dolgozóspecifikus szabadság- és távolléti folyamatok karbantartása
- Jogosultság: Szabadság- és távolléti kérelmek karbantartása az összes dolgozó számára

## <a name="other-changes"></a>Egyéb változtatások
Ebben a verzióban a következő frissítések történtek :
- Dolgozók felvételi műveletekkel kapcsolatos módosítások, hogy azok ne „ragadjanak be” a **Munkafolyamat befejezve** állapotba.
- Alkalmazotti rekord mostantól a foglalkoztatás kezdő dátuma nélkül is létrehozható.
- A Dynamics 365 Talent regisztrációs dátuma, amely megjelenik az Alkalmazotti önkiszolgáló rendszer, mostantól alkalmazza az időzóna eltolását a dátumhoz képest.
- Excel-fájlok importálhatók többször is hibák nélkül az **Alkalmazott entitás** használatával.

## <a name="known-issue"></a>Ismert probléma

- **Probléma**:Egy új csatolmány hozzáadásakor egy dolgozóhoz az **Új** és **Szerkesztés** gombok szürkén jelennek meg. 
- **Megoldás:** A melléklet lap megnyitása, előtt ellenőrizze, hogy az adatterületek a **Dolgozó** lapon le vannak-e zárva. Ha a ténymezők be vannak zárva, amikor a **Dolgozó** lap be van töltve, akkor a mellékletek gombjai engedélyezettek. (Ezt a problémát kijavítjuk a következő platformfrissítéssel.)
