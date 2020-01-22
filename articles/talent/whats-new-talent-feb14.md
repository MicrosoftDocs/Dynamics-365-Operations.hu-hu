---
title: Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban (2019. február 14.)
description: Ez a témakör a Microsoft Dynamics 365 Talent új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 02/14/2019
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
ms.search.validFrom: 2019-02-14
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 32f3bab38233833498ed566fa1558a023b3bc0dd
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/06/2019
ms.locfileid: "2899220"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-february-14-2019"></a>Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban (2019. február 14.)

Ez a témakör a Talent új vagy módosított szolgáltatásait írja le.

## <a name="changes-in-attract"></a>Változások az Attract-ben
Vannak kisebb hibajavítások ebben a verzióban.

## <a name="changes-in-onboarding"></a>Változások az Onboarding alkalmazásban
Vannak kisebb hibajavítások ebben a verzióban.
 
## <a name="changes-in-core-hr"></a>A Core HR módosításai 
**Build 8.1.2146**

### <a name="employee-fixed-compensation-entity-doesnt-export-all-records"></a>Alkalmazott fix kompenzációs entitás nem exportálja az összes rekordot
Ezzel a módosítással az **Alkalmazotti fix kompenzáció** entitás exportálja az összes rekordot. Az entitás használható alkalmazottakhoz tartozó meglévő fix kompenzációs rekord létrehozására és frissítésére. 

### <a name="employment-end-date-doesnt-honor-employee-preferred-time-zone-settings"></a>Munkaviszony záró dátuma nem figyelembe veszi az alkalmazott preferált időzóna-beállításait
Munkaviszony záró dátumai mostantól figyelembe veszik a felhasználó által előnyben részesített időzónát munkaviszony létrehozásakor vagy befejezésekor a vállalatnál.
 
### <a name="uk-addresses-display-in-analytics-as-eastern-switzerland-addresses"></a>Egyesült Királysági címek közép-kelet-Svájc címként jelennek meg az analitikában
Ebben a verzióban, a változtatás történt a címekben rossz hozzárendelésének megoldására a **Személyzeti kezelése** "Létszám hely alapján" jelentésben.
 
### <a name="termination-code-is-not-populated-on-the-worker-position-assignment-record-when-ending-the-position"></a>Felmondási kód nem lett kitöltve a dolgozó beosztáshozzárendelési rekordján a beosztás befejezésekor.
Módosítás történt a „Felmondás oka” kód alapértelmezett feltűntetése érdekében, amikor az alkalmazott beosztáshozzárendelése megszűnik.

### <a name="new-entity-created-for-job-compensation-levels"></a>Új entitiás lett létrehozva a feladatkompenzációs szintekhez
Új datamanagement framework (DMF) entitás lett létrehozva. Az entitás lehetőséget biztosít kompenzációs szintek, a piaci érték és felmérési adatok létrehozására és frissítésére a rendszerben definiált egyes munkákhoz.
