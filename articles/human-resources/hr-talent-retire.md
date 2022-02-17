---
title: Nyugdíjba vonulása Dynamics 365 Talent - Vonzza és beépített alkalmazásokat
description: Ez a témakör a nyugdíjazását írja le Dynamics 365 Talent - Vonzza és beépített alkalmazásokat.
author: twheeloc
ms.date: 01/27/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmBenefitEligibilityDetail, SysPolicyListPage, SysPolicySourceDocumentRuleType, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 16441
ms.assetid: 4ad0106f-5b07-4fd5-bc1a-5834fa9b198e
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: df33f35f66e356c3c2a99f0d81ebba1d0f34b5d9
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8069404"
---
# <a name="dynamics-365-talent-attract-and-onboard-apps-retirement"></a>Dynamics 365 Talent: Attract és az Onboard alkalmazások nyugdíjazása


2019 decemberében bejelentettük a 2022. február 1-i nyugdíjazását Dynamics 365 Talent - Vonzza és beépített alkalmazásokat, így ügyfeleinknek két évet tervezhetnek.

Az alkalmazások megszüntetésével kapcsolatos további információkért lásd:
 - [Nyugdíjba vonuló Dynamics 365 Talent - Vonzza és Dynamics 365 Talent: Onboard Alkalmazások elemre](https://community.dynamics.com/365/humanresources/b/dynamics365forhumanresources/posts/retiring-dynamics-365-talent-attract-and-onboard-apps)
 - [Sikeresebb munkaerő felépítése Dynamics 365 Human Resources](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/12/06/building-a-more-successful-workforce-with-dynamics-365-human-resources)

Továbbra is támogatjuk Dynamics 365 Human Resources, amely segít ügyfeleinknek olyan munkaerő-betekintést szerezni, amely ahhoz szükséges, hogy több területen is adatvezérelt munkavállalói élményt építsenek ki, például:

- Kompenzáció
- Juttatások
- Szabadság és távollét
- Megfelelés
- Payroll
- Teljesítmény-visszajelzés
- Képzés és tanúsítványok
- Önkiszolgáló programok

## <a name="dynamics-365-talent-apps-retirement-faq"></a>Dynamics 365 Talent alkalmazások nyugdíjba vonulásával kapcsolatos GYIK

### <a name="what-is-the-user-experience-for-both-dynamics-365-talent---attract-and-onboard-apps-starting-february-1-2022"></a>Milyen a felhasználói élmény mindkettőnél Dynamics 365 Talent – 2022. február 1-jétől az Attract és Onboard alkalmazások?

A felhasználók nem fogják tudni használni az alkalmazásokat, és átirányítják őket egy nyugdíjas oldalra.

### <a name="can-customers-continue-to-export-data-for-both-dynamics-365-talent---attract-and-onboard-apps-after-february-1-2022"></a>Továbbra is exportálhatják-e az ügyfelek mindkét adatait Dynamics 365 Talent – 2022. február 1. után vonzza az alkalmazásokat és az Onboard alkalmazásokat?
  
Nem, 2019 decemberében bejelentették a nyugdíjazást, és 2022. február 1-ig biztosították a szükséges exportképességeket. 

### <a name="will-the-customers-data-related-to-both-dynamics-365-talent---attract-and-onboard-apps-in-dataverse-be-deleted-after-february-1-2022"></a>Az ügyfél adatai mindkettőre vonatkoznak Dynamics 365 Talent - Vonzz be és fedélzeti alkalmazásokat Dataverse 2022. február 1. után törölni kell?

Nem, a Dataverse entitások az ügyfélnél maradnak Microsoft Dataverse környezetbe nyugdíjba vonulás után is, hacsak nem törlik vagy távolítják el a Human Capital Management Talent megoldást.

### <a name="i-know-the-name-of-the-talent-environment-how-can-i-see-the-attract-and-onboard-data-in-dataverse"></a>Ismerem a Talent környezet nevét. Hogyan láthatom az Attract és Onboard adatokat Dataverse?

1.  bejelentkezni Power Apps :https://make.powerapps.com
2.  Válassza ki azt a környezetet, amelyben látni szeretné az Attract és Onboard adatokat.
3.  Menj **Dataverse > Táblázatok**. 
4.  Írja be az "msdyn_" parancsot **Keresés**. Ha látja az "msdyn_" + táblanevekkel kezdődő táblák listáját (például: msdyn_candidate), akkor megtalálta az Attract és Onboard adatokat tartalmazó környezetet.

[![Power Apps](./media/Powerapps.png)](./media/Powerapps.png)

### <a name="i-dont-know-the-name-of-the-talent-environment-how-can-i-find-the-environment-that-has-the-data-for-the-dynamics-365-talent-attract-and-dynamics-365-talent-onboard-applications"></a>A Talent környezet nevét nem tudom. Hogyan találhatom meg azt a környezetet, amely tartalmazza a Dynamics 365 Talent: Attract és Dynamics 365 Talent: Onboard alkalmazások?

1)  bejelentkezni Power Platform admin központ:https://admin.powerplatform.microsoft.com/
2)  Válassza a **Környezetek** lehetőséget.
3)  Válasszon ki egy adott környezetet az értékeléshez.
4)  Válassza ki **Erőforrások > Dynamics 365 alkalmazások**.
5)  Ha látod **HCM Talent** megoldás telepítve, ebben a környezetben kell Attract és Onboard adatokat tárolni. 

[![Power Platform](./media/HCMTalent.png)](./media/HCMTalent.png)

> [!NOTE] 
> A **HCM Talent** megoldást is alkalmazzák Dynamics 365 Human Resources.
