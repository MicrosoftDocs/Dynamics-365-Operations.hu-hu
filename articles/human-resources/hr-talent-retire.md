---
title: Nyugdíjazás Dynamics 365 Talent – and onboard alkalmazások ki nyugdíjazása
description: Ez a cikk a – visszajelző Dynamics 365 Talent és a hajó fedélzetre telepített alkalmazások ki- és nyugdíjazását írja le.
author: twheeloc
ms.date: 01/27/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmBenefitEligibilityDetail, SysPolicyListPage, SysPolicySourceDocumentRuleType, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 16441
ms.assetid: 4ad0106f-5b07-4fd5-bc1a-5834fa9b198e
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 3039b0a837335a777cdd6ff22b8b6e7c014ef956
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8845084"
---
# <a name="dynamics-365-talent-attract-and-onboard-apps-retirement"></a>Dynamics 365 Talent: Attract és a hajó fedélzetre telepített alkalmazásai – nyugdíjazás


2019. decemberben leirasztjuk a 2022 Dynamics 365 Talent . február 1-jén kivetkedő – önzoktató és a hajóra telepített alkalmazásokat, így a vevőknek két év áll a tervben.

Az alkalmazások kivetlével kapcsolatos további tudnivalókat lásd:
 - [Retiing Dynamics 365 Talent – visszahozaat és alkalmazások Dynamics 365 Talent: Onboard](https://community.dynamics.com/365/humanresources/b/dynamics365forhumanresources/posts/retiring-dynamics-365-talent-attract-and-onboard-apps)
 - [Sikeresebb munkaerő építését a Dynamics 365 Human Resources](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/12/06/building-a-more-successful-workforce-with-dynamics-365-human-resources)

A rendszer továbbra Dynamics 365 Human Resources is támogatja a tapasztalatokat, amelyek segítséget nyújtanak a vevőknek ahhoz, hogy több területen adatvezérelt alkalmazotti tapasztalatokat készítsenek, például:

- Kompenzáció
- Juttatások
- Szabadság és távollét
- Megfelelés
- Bérszámfejtés
- Teljesítmény-visszajelzés
- Képzés és tanúsítványok
- Önkiszolgáló programok

## <a name="dynamics-365-talent-apps-retirement-faq"></a>Dynamics 365 Talent alkalmazások – nyugdíjazás – gyakori kérdések

### <a name="what-is-the-user-experience-for-both-dynamics-365-talent---attract-and-onboard-apps-starting-february-1-2022"></a>Milyen felhasználói élményben lesz része Dynamics 365 Talent a 2022. február 1.-jén kezdődő Mindkét alkalmazásnak – Az 2022. február 1-jén kezdődően?

A felhasználók nem tudják használni a pályázatokat, ezért a rendszer egy nyugdíjazási lapra irányítják át őket.

### <a name="can-customers-continue-to-export-data-for-both-dynamics-365-talent---attract-and-onboard-apps-after-february-1-2022"></a>A vevők továbbra is exportálni Dynamics 365 Talent tudjanak adatokat mind az - után, hogy 2022. február 1.,
  
Nem, a nyugdíjazás 2019 decemberében volt szükséges, 2022. február 1-ig. 

### <a name="will-the-customers-data-related-to-both-dynamics-365-talent---attract-and-onboard-apps-in-dataverse-be-deleted-after-february-1-2022"></a>Törlődnek a vevő Dynamics 365 Talent Dataverse adatai mind a - megfelelő, mind a külső alkalmazásokból 2022. február 1.után?

Nem, az entitások Dataverse Microsoft Dataverse a kivezetés után is a vevő környezetében maradnak, hacsak nincs törölve vagy eltávolítva a Human Capital Management Talent megoldás.

### <a name="i-know-the-name-of-the-talent-environment-how-can-i-see-the-attract-and-onboard-data-in-dataverse"></a>Jól ismeri a Tehetség környezet nevét. Hogyan lehet látni a 2019-et és a hajóra vonatkozó adatokat Dataverse?

1.  Power Apps bejelentkezés:https://make.powerapps.com
2.  Válassza ki, hogy milyen környezetben szeretné látni a berakodva és a hajóra vonatkozó adatokat.
3.  Ugrás a **Dataverse > táblákra** 
4.  Írja be a "msdyn_" ot a **keresésbe**. Ha a "msdyn_" és a táblanevek (például: msdyn_candidate) nevével kezdődő táblák listáját látja, akkor a környezetben a Megfelelő és a Onboard adatok találhatók.

[![Power Apps](./media/Powerapps.png)](./media/Powerapps.png)

### <a name="i-dont-know-the-name-of-the-talent-environment-how-can-i-find-the-environment-that-has-the-data-for-the-dynamics-365-talent-attract-and-dynamics-365-talent-onboard-applications"></a>Nem tudom a Tehetség környezet nevét. Hogyan lehet megtalálni azt a környezetet, amely az adatokat és az alkalmazásokat Dynamics 365 Talent: Attract Dynamics 365 Talent: Onboard tartalmaz?

1)  Jelentkezzen be a rendszergazdai Power Platform központba: https://admin.powerplatform.microsoft.com/
2)  Válassza a **Környezetek** lehetőséget.
3)  Válassza ki az értékelni kívánt környezetet.
4)  Válassza az **Erőforrások > Dynamics 365-alkalmazásokhoz**.
5)  Ha azt látja, hogy **a HCM Talent megoldás** telepítve van, akkor ebben a környezetben tárolni kell a Megfelelő és a Onboard adatokat. 

[![Power Platform](./media/HCMTalent.png)](./media/HCMTalent.png)

> [!NOTE] 
> A **HCM Talent megoldás** a következőben is használatos:Dynamics 365 Human Resources
