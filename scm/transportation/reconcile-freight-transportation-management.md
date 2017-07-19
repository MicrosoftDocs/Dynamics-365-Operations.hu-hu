---
title: "Szállítási költség egyeztetése a szállításkezelésben"
description: "A cikk a szállítási költség egyeztetési folyamatot ismerteti."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TMSAuditMaster, TMSFreightBillInvoiceReconcile, TMSFreightBillSummary, TMSFreightBillType, TMSFreightMatchReason, TMSInvoiceTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 89983
ms.assetid: bc34a9b1-0c11-4797-b463-25409cf98ca8
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yuyus
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: ab7d21d7a75e2c954831a254bb339d9cf5746d9d
ms.contentlocale: hu-hu
ms.lasthandoff: 06/13/2017

---

# <a name="reconcile-freight-in-transportation-management"></a>Szállítási költség egyeztetése a szállításkezelésben

[!include[banner](../includes/banner.md)]


A cikk a szállítási költség egyeztetési folyamatot ismerteti.

Szállítási költség egyeztetés elvégezhető manuálisan vagy beállítható automatikusra. Automatikus szállítási egyeztetés használatához vizsgálati alapadatok beállítása szükséges, ahol megadhatja a feltételeket, amelyek meghatározzák, hogy mely fuvarszámla egyeztetése legyen automatikus.

## <a name="the-freight-reconciliation-process"></a>A fuvaregyeztetési folyamat
A szállítási díjakat a megfelelő szállítási fuvarozóval társított díjkalkulátor számítja ki. Rakomány megerősítése esetén a fuvarlevélszámla létrejön, és a szállítási díjak átvitele a fuvarlevélszámlára megtörténik. A fuvardíjak vegyes költségek szerint vannak arányosítva a vonatkozó forrásbizonylat (beszerzési rendelés, értékesítési rendelés és/vagy átmozgatási rendelés) alapján, a rendszeres számlázási folyamat beállításaitól függően. A szállítási költség egyeztetési folyamata elindítható, amint a fuvarszámla megérkezik a szállítmányozótól. A számla elektronikus úton vagy nyomtatott papíron érkezhet. Ha papíralapú számla érkezik, elektronikus számlát hozhat létre a fuvarlevelet használva sablonként. 

[![Fuvaregyeztetési folyamat](./media/freight-reconcilation-process.jpg)](./media/freight-reconcilation-process.jpg)

## <a name="manual-reconciliation"></a>Manuális egyeztetés
Ha az egyeztetést manuálisan végzi, minden számlázási sorral minden fuvarlevélsort vagy a számlázandó rakománysort egyeztetnie kell. Ezt a **Fuvarlevél és számlaegyeztetés** oldalon végezheti el. Ha a számlasor összege nem egyezik meg a fuvardíj összegével, az eltérés egyeztetés okát kell kiválasztania. Ha több egyeztetési ok fordul elő, a nem egyeztetett összeget feloszthatja. Az egyeztetés oka határozza meg, hogyan kerülnek a különbözet összegei feladásra a főkönyvbe. Amikor a teljes számlaösszeg egyeztetése számba lett véve, jóváhagyás céljából elküldik és a napló feladásra kerül. Az alábbi ábra bemutatja, hogyan készíthető szállítási számla és hajtható végre a fuvarlevél-egyeztetés Microsoft Dynamics 365 for Finance and Operations rendszerben. 
[![Fuvaregyeztetési folyamat Dynamics AX rendszerben](./media/processflowforfreightreconciliation.jpg)](./media/processflowforfreightreconciliation.jpg)
## <a name="automatic-reconciliation"></a>Automatikus egyeztetés
Automatikus egyeztetéshez meg kell adnia a használni kívánt egyeztetés, számlák, és szállítmányozók ütemezését. A számlasorok és fuvarlevelek ellenőrzése alapvizsgálat beállításainak és a fuvarlevél típusának megfelelően történik. Az automatikus egyeztetés futtatása után kezelnie kell azokat a számlákat, melyeket a rendszer nem tudott. Manuálisan kell feldolgoznia ezeket a számlákat a kifizetés előtt.




