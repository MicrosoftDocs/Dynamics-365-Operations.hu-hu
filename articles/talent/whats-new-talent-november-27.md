---
title: Új vagy módosult elemek a Dynamics 365 Talent – Core HR szolgáltatásban (2018. november 27.)
description: Ez a témakör a Microsoft Dynamics 365 Talent – Core HR új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 11/27/2018
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
ms.search.validFrom: 2018-11-27
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 1d6b5f5f7b62c400679df5eb014dee05f02e11d0
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461379"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-november-27-2018"></a>Új vagy módosult elemek a Dynamics 365 Talent – Core HR szolgáltatásban (2018. november 27.)

**Build 8.1.2064**

Ez a témakör a Core HR aktuális verziójában található új vagy módosított szolgáltatásokat írja le.


## <a name="changes"></a>Változások

### <a name="unable-to-create-a-note-in-case-management"></a>Nem sikerült megjegyzés létrehozása a Case Management alkalmazásban

Módosítás történt egy problémával kapcsolatban, amely akkor merül fel, amikor az Esetkezelés esetnaplójában megjegyzést hoznak létre vagy szerkesztenek.

### <a name="misspelled-word-on-the-analytics-tab-in-the-compensation-workspace"></a>Elírt szó a kompenzációs munkaterület Elemzések lapján 

Módosítás történt a kompenzációs munkaterület kompenzációs elemzés diagramján, a helytelenül írt 'Ethnic Origin' szó helyesírását javítottuk.

### <a name="employee-self-service-workspace-not-displaying-when-a-user-isnt-assigned-to-a-worker"></a>Az alkalmazott önkiszolgáló munkaterülete nem jelenik meg, amikor a felhasználó nincs hozzárendelve egy dolgozóhoz 

Módosítás történt a következő problémával kapcsolatban: amikor az **Alkalmazotti önkiszolgáló rendszer** munkaterületet kiválasztják, mint az indításkor megjelenő jezdőoldal egy olyan felhasználó esetén, aki nincs hozzárendelve egy dolgozóhoz. Ebben az esetben az alapértelmezett irányítópult fog megjelenni.

### <a name="leave-and-absence-error-object-reference-not-set-to-an-instance-of-an-object"></a>Szabadság és távollét hibája: Az objektumhivatkozás nincs beállítva egy objektum példányához

Módosítások történtek a Szabadság és távollét funkcióban, a szabadság és távollét rekordok **Hozzám rendelt munkatételek** menüpontban való jóváhagyása után felmerülő hibát javították.

### <a name="unable-to-recall-an-image-workflow"></a>Nem lehet egy képmunkafolyamatot visszahívni

Egy képmunkafolyamat visszahívása után a munkafolyamat „visszavonva” beállítást kap, és a létező kérést törölni lehet az alkalmazotti önkiszolgáló rendszer munkaterületen.

### <a name="rehired-employees-or-contractors-show-up-multiple-times-after-termination"></a>Újra felvett alkalmazottak vagy alvállalkozók többször jelennek meg a munkaviszony megszűnése után 

Ezzel a frissítéssel azok az alkalmazottak, akiknek megszűnt a munkaviszonyuk, majd újra felvették őket, csak egyszer jelennek majd meg a kilépettek listájában. 

## <a name="known-issue"></a>Ismert probléma

- **Probléma**:Egy új csatolmány hozzáadásakor egy dolgozóhoz az **Új** és **Szerkesztés** gombok szürkén jelennek meg. 
- **Megoldás:** A melléklet lap megnyitása, előtt ellenőrizze, hogy az adatterületek a **Dolgozó** lapon le vannak-e zárva. Ha a ténymezők be vannak zárva, amikor a **Dolgozó** lap be van töltve, akkor a mellékletek gombjai engedélyezettek. (Ezt a problémát kijavítjuk a következő platformfrissítéssel.)
