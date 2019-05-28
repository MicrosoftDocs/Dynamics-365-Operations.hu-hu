---
title: A toborzási adatok változásainak nyomon követése
description: A folyamat-ellenőrzési funkció segítségével nyomon követheti a jelentkezők, a álláslehetőségek vagy a pályázatok jelentési vagy megfelelési okokból történő változását.
author: tracykeya
manager: AnnBe
ms.date: 04/17/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application user
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.search.region: Global
ms.author: trkeya
ms.search.validFrom: 2018-04-30
ms.dyn365.ops.version: AX 7.1.0, Talent April 2019 update
ms.openlocfilehash: 803c935493a4080b8c1d0ef92bbe7db601f3ca03
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2019
ms.locfileid: "1518178"
---
# <a name="track-changes-in-recruiting-data"></a>A toborzási adatok változásainak nyomon követése

Nyomon követheti a jelentkezők, álláslehetőségek vagy a pályázatok változásait a könyvvizsgálati feldolgozással. Ez a jelentésekhez és a megfelelési célból is használható.

A nyomon követett adatok az OData-csatlakozó használatával tekintheti meg a Power BI megoldásban. További tájékoztatás: [OData-folyamok csatlakoztatása Power BI Desktop](https://docs.microsoft.com/en-us/power-bi/desktop-connect-odata) megoldásban.

## <a name="track-changes"></a>Változások követése
Ha be szeretné állítani a toborzási adatok nyomon követését, hajtsa végre az alábbi lépéseket:

1. A [PowerApps](https://web.powerapps.com) megoldásban válassza ki a megfelelő környezetet.

2. Válassza a **Beállítások** (fogaskerék ikon), válassz a **Speciális testreszabások** elemet, majd válassza ki az **Erőforrások elemet** a **Fejlesztői erőforrások** alatt. 

3. A **Fejlesztői erőforrások** lapon másolja át az értéket a **Példány webes API-értéke** mezőbe. Például az érték így nézhet ki: https://yourorgname.api.crm.dynamics.com/api/data/v9.1/.

4. Ezután a következő entitások egyikének adatait lekérdezheti:
  - Álláslehetőség előzményei (msdyn_jobopeninghistories)
  - Pályázat előzményei (msdyn_jobapplicationhistories) 
  - Pályázói előzmények (msdyn_candidatehistories)

## <a name="data-reported"></a>Jelentett adatok

A következő adatok érhetők el a folyamatok auditálásával.

| Jelentett adatok | Leírás |
| --- | --- |
| Módosította (msdyn_ChangedbyId) | Hivatkozás a felhasználóra |
| Létrehozás dátuma (createdon) |  Dátum és időpont UTC-ben, amikor a változás megtörtént. |
| Módosítás típusa (msdyn_changetype) | Milyen módosítás történt. |
| Gyakori értékek a jelöltekhez és nyitott állásokhoz <br></br>és pályázatokhoz | Létrehozva<br></br>Frissítve |
| Álláspályázat előzményei | Műtermék hozzáadva <br></br>Műtermék eltávolítva |
| Álláslehetőségek előzményei | TODO: feladás hozzáadva <br></br>TODO: feladás eltávolítva <br></br>TODO: feladás frissítve <br></br>TODO: résztvevő hozzáadva <br></br>TODO: résztvevő eltávolítva |
| Jelentkezők előzményei | Műtermék hozzáadva <br></br>Műtermék eltávolítva <br></br>Munkatapasztalat hozzáadva <br></br>Munkatapasztalat eltávolítva <br></br>Végzettség hozzáadva <br></br>Végzettség eltávolítva <br></br>Szakértelem hozzáadva <br></br>Szakértelem eltávolítva <br></br>Címke hozzáadva <br></br>Címke eltávolítva <br></br>Közösségi hálózat hozzáadva <br></br>Közösségi hálózat eltávolítva <br></br>Személyi adatok hozzáadva <br></br>Személyi adatok frissítve<br></br> |
| Módosított mezők (msdyn_changedfields) | A JSON objektum felsorolja a módosított mezőket, előfordulhat, hogy az összes mező értékeit nem tárolja.<br></br><br></br>A „létrehozva” és a „Frissítve” módosítás esetén a program listázza a létrehozott vagy módosított rekord mezőit.<br></br><br></br>A „Hozzáadott” típusú módosításokhoz a program felsorolja azokat a mezőket, amelyek a gyermek rekordon szerepelnek.<br></br><br></br>**Példa:**<br></br><br></br>{<br></br>  "msdyn_applyurl": { "newValue": "" },<br></br>  "msdyn_description": { "valueOmitted": true } <br></br>} |
|Álláspályázat előzményei | Pályázat (msdyn_JobapplicatonId)<br></br>Állapot (msdyn_status) <br></br>Állapot oka (msdyn_statusreason) <br></br>Elutasítás oka (msdyn_rejectionreason) |
| Álláslehetőségek előzményei | Álláslehetőség (msdyn_JobopeningId) <br></br>Állapot (msdyn_jobopeningstatus) <br></br>Állapot oka (msdyn_jobopeningstatusreason) |
| Jelentkezők előzményei | Pályázó (msdyn_CandidateId) |
