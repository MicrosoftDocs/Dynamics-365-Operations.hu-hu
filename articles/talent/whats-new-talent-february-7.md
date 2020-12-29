---
title: Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban (2019. február 7.)
description: Ez a témakör a Microsoft Dynamics 365 Talent új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 02/07/2019
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
ms.search.validFrom: 2019-02-07
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 002dcd8253a0ab753ac9002e7027441db6d0b858
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461420"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-february-7-2019"></a>Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban (2019. február 7.)

Ez a témakör a Talent új vagy módosított szolgáltatásait írja le.

## <a name="changes-in-attract"></a>Változások az Attract-ben

### <a name="interview-scheduling-enhancements"></a>Interjú ütemezésével kapcsolatos fejlesztések
Javítások történtek a végponttól végpontig tartó interjúütemezési élményben. Ezután láthatja egy belső jelölt naptárelérhetőségét, és használhatja a belső jelölt naptárát ütemezés ajánlásokhoz. További tudnivalókért lásd: [Interjú ütemezése és visszajelzés](interview-scheduling-feedback.md).

### <a name="job-posting-to-linkedin--company-mismatch-issue-fixed"></a>Állás közzététele a LinkedIn-en – vállalati eltérési hiba javítva.
Egy hiba lett javítva, ahol az Attract alkalmazásból a LinkedIn-en közzétett állások rossz vállalatnéven jelentek meg. További tudnivalókért lásd: [Állás létrehozása, jóváhagyása és közzététele az Attract alkalmazásban](creating-jobs-attract.md).

### <a name="career-site-url-displayed-in-admin-settings"></a>A karrierwebhely URL-címének megjelenítése a felügyeleti beállításokban
A karrierwebhely kezdőlapjának URL-címe mostantól megjelenik a **Felügyeleti beállításokban** a **Karrierwebhely kezelése** alatt.

## <a name="changes-in-core-hr"></a>A Core HR módosításai

**Build 8.1.2134**

### <a name="multiple-compensation-levels-supported-on-jobs"></a>Többféle kompenzációszint támogatott az állásoknál
Ez a változtatás lehetővé teszi egynél több kompenzációs szint definiálásár egy munkánál engedélyezve az alkalmazotti fix kompenzációs tartományokat, amelyek eltérőek lehetnek az ugyanazon munkához tartozó tervek között. 

Példa:    
*Feladat* -Ügyfélfelelős *Kapcsolódó kompenzációs szintek:* B1 és B2 - Minden szinthez tartozik egy meghatározott értéktartomány. B1 = Min. 50 000, közép 60 000, Max. 75 000 és B2 = Min. 65 000, közép 74 000, Max. 85 000. Fix kompenzáció létrehozásakor az alkalmazottakhoz a meghatározott jogosultsági szabályok alapján, az egyes tervek mutathatnak ugyanazon munkára, és a munka különböző szintjeire. Ez lehetővé teszi tervek meghatározását a különböző régiókhoz/vállalatokhoz , és azt, hogy ugyanazon munkára mutassanak, de más tartományokra a munkák duplikálása nélkül ezen eltérések figyelembevételéhez.

### <a name="compensation-level-field-has-been-added-to-the-employee-fixed-compensation-entity"></a>Kompenzációs szint mező hozzá lett adva az Alkalmazott fix kompenzáció entitáshoz 
A frissítéssel az alkalmazotti fix kompenzációs entitás frissítve lett, és tartalmazza a **Kompenzációs szint** mezőt. A kiegészítés megkönnyíti az alkalmazott fix kompenzációs konstrukciók frissítését. 

### <a name="update-job-family-when-updating-and-creating-new-positions"></a>Munkacsalád frissítése a frissítés és új beosztások létrehozása során
Amikor frissíti a munkát egy beosztáshoz, a **Munkacsalád** az kiválasztott munka alapján lesz alapértelmezett.

### <a name="performance-improvements-when-rendering-workspaces"></a>Teljesítménynövelő fejlesztések a munkaterületek megjelenítésekor
Munkaterületek analitika lapjai csak a lapok elérésekor töltenek be. A lap bal felső sarkában egy jelölő jelenik meg az első megjelenítés során.
