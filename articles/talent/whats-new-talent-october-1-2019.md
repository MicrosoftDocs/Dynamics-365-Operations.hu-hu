---
title: Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban (2019. október 1.)
description: Ez a témakör a Microsoft Dynamics 365 Talent új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 10/01/2019
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
ms.search.validFrom: 2019-10-01
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 4c8392973e7f9c55d425dbe3efb9c8858f71e345
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550159"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-october-1-2019"></a>Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban (2019. október 1.)

[!include [banner](includes/banner.md)]

Ez a témakör a Dynamics 365 Talent új vagy módosított szolgáltatásait írja le.

## <a name="changes-in-attract"></a>Változások az Attract-ben

A kiadás a Dynamics 365 Talent: Attract apró hibáinak javításait is tartalmazza.

## <a name="changes-in-onboard"></a>Változások az Onboard alkalmazásban

A kiadás a Dynamics 365 Talent: Onboard apró hibáinak javításait is tartalmazza.

## <a name="changes-in-core-hr"></a>A Core HR módosításai

A szakaszban ismertetett módosítások a 8.1.2509-ös buildre vonatkoznak. A néhány fejlécben látható, zárójelben lévő számok az Microsoft Dynamics Lifecycle Services (LCS) támogatási számaira vonatkoznak.

### <a name="streamlined-employee-entry-and-navigation"></a>Korszerű alkalmazotti belépés és navigálás

Ez a funkció jelenleg minden környezetben elérhető. A funkció bekapcsolásához navigáljon a **Rendszer-adminisztráció > Hivatkozások > Beállítás > Rendszerparaméterek > előnézeti funkciók** ponthoz. Válassza a **Továbbfejlesztett dolgozói képernyő és navigáció** lehetőséget. Ez minden felhasználó számára engedélyezi ezeket a változtatásokat. Ezt a beállítást bármikor ki lehet kapcsolni.

További tájékoztatás: [Korszerű alkalmazotti belépés és navigálás](./streamlined-employee-entry.md). Ha meg szeretne tekinteni a változásokról szóló videót, tekintse meg a következőt: [Dynamics 365 for Talent 2019. második kiadási hullám áttekintése](https://aka.ms/ROGT19RW2ROV).

### <a name="you-can-enable-preview-features-in-sandbox-and-trial-environments"></a>Az előzetes funkciókat tesztkörnyezetekben és próbakörnyezetekben is engedélyezheti

Amikor új Talent-példányt hoz létre, megadhatja, hogy a példány Termelési vagy Védőfal típusú legyen-e. A Védőfal típusú példányokkal az új szolgáltatások próbatesztelése végezhető el. Ha a meglévő példányokat Védőfal típusúra szeretné frissíteni, kérje az ügyfélszolgálat segítségét.

További információ a módosítások közzétételéről: [A Talent létesítése](./provisioning-talent.md).

### <a name="compensation-date-defaults-to-a-different-date-than-the-position-assignment-337694"></a>A kompenzációs dátum alapértelmezett értéke eltér a pozíció-hozzárendelés dátumától (337694)

Ezzel a változtatással most alapértelmezés szerint a kompenzáció kezdő dátuma a pozíció-hozzárendelés kezdő dátuma lesz.

### <a name="not-able-to-end-compensation-along-with-its-position-assignment-328993"></a>Nem lehet lezárni a kompenzációt a hozzá tartozó pozíció-hozzárendeléssel (328993)

Ezzel a módosítással lezárhatja a kompenzációt a pozíció-hozzárendelés befejezésekor a **Hozzárendelés befejezése** funkció használatával a **Dolgozó pozíció-hozzárendelései** oldalon, ha a személyzeti műveletek be vannak kapcsolva.

### <a name="bank-account-validation-requires-routing-and-account-numbers-in-all-locations-340403"></a>A bankszámla-ellenőrzéshez minden helyen szükségesek az útvonaltervezési- és számlaszámok (340403)

Az eheti módosításokkal új konfigurációs beállítás került hozzáadásra, amellyel letiltható az **Útvonaltervezési szám** és a **Számlaszám** kötelező ellenőrzése. 

### <a name="attachments-are-not-enabled-in-mss-performance-journals-for-performance-feedback-341794"></a>Nem engedélyezettek a mellékletek az MSS teljesítménynaplóiban a teljesítmény-visszajelzésnél (341794)

Az eheti kiadástól kezdve a visszajelzési elemeknél engedélyezettek a mellékletek a teljesítménynapló oldalán.

### <a name="leave-request-details-dont-sync-from-common-data-service-to-talent-369608"></a>A szabadságkérelem részleteit a rendszer nem szinkronizálja a Common Data Service szolgáltatásból a Talent szolgáltatásba (369608)

Ezekkel a módosításokkal a Common Data Service programban frissített szabadságkérelem-adatok szinkronizálódnak a Talent szolgáltatással.

### <a name="job-description-doesnt-display-for-the-job-in-the-skill-gap-analysis-page-369398"></a>A Munkaköri leírás nem jelenik meg a feladatnál a Szakértelmek hiányelemzése oldalon (369398)

Az eheti buildben a leírás megjelenik a kiválasztott feladatnál a **Szakértelmek hiányelemzése** oldalon.

## <a name="coming-soon"></a>Hamarosan

### <a name="print-performance-reviews"></a>Teljesítményértékelések nyomtatása

Az alkalmazottak, a vezetők és a HR szakemberek kinyomtathatják az alkalmazottak teljesítménykimutatását.
