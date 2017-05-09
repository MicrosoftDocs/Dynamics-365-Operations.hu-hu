---
title: "Toborzási Power BI-tartalom"
description: "Ez a témakör a következőt ismerteti: Dynamics 365 for Operations - Toborzási Power BI-tartalom. Leírja, hogy hogyan kell hozzáférni a tartalmi csomagban szereplő jelentésekhez, és információkat nyújt a tartalmi csomag összeállításához előzőleg használt entitásokkal és adatmodellekkel kapcsolatban."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations
ms.custom: 263934
ms.assetid: 38e6827b-0819-473c-bc47-821a1ec482b8
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: d307733193b388149f83dd420cc7003edcf7749a
ms.lasthandoff: 03/31/2017


---

# <a name="recruiting-power-bi-content"></a>Toborzási Power BI-tartalom

[!include[banner](../includes/banner.md)]


Ez a témakör a következőt ismerteti: Dynamics 365 for Operations - Toborzási Power BI-tartalom. Leírja, hogy hogyan kell hozzáférni a tartalmi csomagban szereplő jelentésekhez, és információkat nyújt a tartalmi csomag összeállításához előzőleg használt entitásokkal és adatmodellekkel kapcsolatban.

<a name="accessing-the-content-pack"></a>A tartalmi csomag elérése
--------------------------

A toborzás tartalomcsomagot a Microsoft Dynamics Lifecycle Services (LCS) megosztott eszközök könyvtárban található. A tartalomcsomag letöltésére és a Microsoft Dynamics 365 for Operations adataival való összekapcsolásra vonatkozó további információért lásd: [Power BI-tartalom az LCS megoldásban a Microsofttól és a partnerektől](power-bi-content-microsoft-partners.md).

## <a name="reports-that-are-included-in-the-content-pack"></a>A tartalomcsomag által tartalmazott jelentések
Miután csatlakoztatta a tartalmi csomagot a Dynamics 365 for Operations rendszer adataihoz, a jelentések megjelenítik a szervezet adatait. Ha még soha nem használt Microsoft Power BI-t, többet megtudhat róla az [Irányított tanulás a Power BI-hez oldalon](https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData). A csomag által tartalmazott a jelentések táblázatokkal és diagramokkal jelenítenek meg információkat. Az alábbi táblázatban található ezeknek a jelentéseknek az ismertetése.

| Jelentés                       | Tartalom                                                                                               |
|------------------------------|--------------------------------------------------------------------------------------------------------|
| Pályázóelemzés           | Pályázók munka szerint, pályázóforrások, pályázók hely szerint, és pályázók összes száma           |
| Pályázó állapota             | Pályázók típus és állapot szerint és a pályázó állapota                                                    |
| Pályázó demográfiai adatai       | Pályázók életkor és nem szerint, és kérelmezők végzettségi szint és állapot szerint                             |
| Toborzási elemzés          | Nettó felvételi arány, felvételig tartó napok átlagos száma, rossz felvételek százaléka és toborzási költségek                    |
| Toborzási projekt elemzése | Toborzási projektek száma, nyitott pozíciók toborzási projekt szerint, pályázók toborzási projekt szerint |

Az e jelentésekben szereplő diagramokat és csempéket szűrheti, a diagramokat és csempéket pedig rögzítheti az irányítópulton. A szűréssel és a Power BI-n történő rögzítéssel kapcsolatos információkért lépjen az [Irányírópult létrehozására és konfigurálása](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards) lehetőségre.

## <a name="understanding-the-data-model-and-entities"></a>Adatmodell, illetve entitások ismertetése
A toborzás tartalomcsomag jelentéseinek feltöltésére a Dynamics 365 for Operations adatok szolgálnak. A következő táblázat mutatja az entitásokat, amelyeken a csomag alapul.

| Entitás                          | Tartalom                                                         | Más entitásokkal való kapcsolatok                                                                                                                                                                                                                 |
|---------------------------------|------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Toborzás\_Pályázó           | Pályázók, felvett pályázók, nettó felvételi arány és költségek          | Felvétel\_ApplicantName felvétel\_Vállalati toborzás\_CalendarOffset toborzás\_Toborzás dátuma\_GeographicLocation toborzás\_Toborzási demográfia\_Toborzás munka\_Media toborzás\_RecruitmentProject                                |
| Toborzás\_ApplicantName       | Pályázó utóneve, vezetékneve és teljes neve                   | Toborzás\_Pályázó toborzás\_EmployedApplicant toborzás\_TerminatedApplicant                                                                                                                                                               |
| Toborzás\_CalendarOffset      | Naptáreltolások, részletes jelentések                                | Toborzás\_Pályázó toborzás\_EmployedApplicant toborzás\_TerminatedApplicant                                                                                                                                                               |
| Toborzás\_Vállalat             | Vállalatok a jelentések szűréséhez                                   | Toborzás\_Pályázó toborzás\_EmployedApplicant toborzás\_TerminatedApplicant                                                                                                                                                               |
| Toborzás\_Dátum                | Napok, hetek, hónapok és évek                                   | Toborzás\_Pályázó toborzás\_EmployedApplicant toborzás\_TerminatedApplicant                                                                                                                                                               |
| Toborzás\_Demográfiai adatok        | Születési idő, nemek, etnikaum és családi állapot         | Toborzás\_Pályázó toborzás\_EmployedApplicant toborzás\_TerminatedApplicant                                                                                                                                                               |
| Toborzás\_EmployedApplicant   | Pályázó, teljesítmény, kezdődátum és pályázó típusa           | Toborzás\_Vállalat toborzás\_CalendarOffset toborzás\_Dátum toborzás\_GeographicLocation toborzás\_ApplicantName toborzás\_Foglalkoztatás toborzás\_Teljesítmény toborzás\_Munka toborzás\_Média toborzás\_RecruitmentProject          |
| Toborzás\_Foglalkoztatás          | Kezdő dátum, záró dátum és átállási dátum                        | Toborzás\_Pályázó toborzás\_EmployedApplicant toborzás\_TerminatedApplicant                                                                                                                                                               |
| Toborzás\_GeographicLocation  | Város, megye, irányítószám és állam vagy megye                 | Toborzás\_Pályázó toborzás\_EmployedApplicant toborzás\_TerminatedApplicant                                                                                                                                                               |
| Toborzás\_Munka                 | Funkció, típus és a cím                                        | Toborzás\_Pályázó toborzás\_EmployedApplicant toborzás\_TerminatedApplicant                                                                                                                                                               |
| Toborzás\_Média               | Pályázók forrása                                             | Toborzás\_Pályázó toborzás\_EmployedApplicant toborzás\_TerminatedApplicant                                                                                                                                                               |
| Toborzás\_Teljesítmény         | Minősítési, leírás és minősítési modell                            | Toborzás\_Pályázó toborzás\_EmployedApplicant toborzás\_TerminatedApplicant                                                                                                                                                               |
| Toborzás\_RecruitmentProject  | Projekt leírása, projekt állapota és nyitott pozíciók                | Toborzás\_Pályázó toborzás\_EmployedApplicant toborzás\_TerminatedApplicant                                                                                                                                                               |
| Toborzás\_TerminatedApplicant | Megszűnt pályázók, ok, teljesítmény és a megszűnés dátuma | Toborzás\_Vállalat toborzás\_CalendarOffset toborzás\_Dátum toborzás\_GeographicLocation toborzás\_Teljesítmény toborzás\_Demográfia toborzás\_Foglalkoztatás toborzás\_Média toborzás\_RecruitmentProject toborzás\_ApplicantName |

Ezeket az entitásokat számított mértékek létrehozására használták. E kiszámított mértékek aztán a fő teljesítménymutatók (KPI-k) és a tartalmi csomagban használt jelentések kiszámításához használatosak. Ha szeretné felvenni a további számításokat a jelentésekbe és irányítópultokba, töltse le és módosítsa a Recruiting.pbix fájlt a LCS-ből. Ez a fájl azon alapértelmezett adatmodell, amelyet a tartalmi csomag létrehozásához használtak. Miután elvégezte a módosításokat, szervezeti tartalmi csomagot és a felvett adatokat tartalmazó irányítópultot hozhat létre.

## <a name="additional-resources"></a>További erőforrások
Az alábbiakban néhány hasznos, entitásokkal és kiemelt Üzletiintelligencia-tartalommal kapcsolatos hivatkozást találhat:

-   [Adatentitások](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/)
-   [Szervezeti tartalmi csomagok létrehozása](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Adatmodellezés az üzleti Intelligencia használatával](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Kiemelt Üzletiintelligencia-lapok hozzáadása munkaterületekhez](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/07/06/pinning-power-bi-reports-to-dynamics-ax-client/)





