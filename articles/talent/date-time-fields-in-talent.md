---
title: Munka a dátumokkal és időpontokkal a Microsoft Dynamics 365 Talent alkalmazásban
description: Annak megértése, mire számíthat, ha a Microsoft Dynamics 365 Talent megoldásban dátum-és időmezőket használ. Megtudhatja, hogy mire számíthat, ha a Talent egy űrlapján külső forrásból vagy a Common Data Service szolgáltatásból származó adatokkal dolgozik.
author: Darinkramer
manager: AnnBe
ms.date: 06/24/2019
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
ms.search.validFrom: 2019-06-06
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 5f5bb3432ba3e57a4ef08dfa3c25cb61705efc33
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/06/2019
ms.locfileid: "2898758"
---
# <a name="work-with-date-and-time-in-microsoft-dynamics-365-talent"></a><span data-ttu-id="02aa1-104">Munka a dátumokkal és időpontokkal a Microsoft Dynamics 365 Talent alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="02aa1-104">Work with date and time in Microsoft Dynamics 365 Talent</span></span>

<span data-ttu-id="02aa1-105">**A dátum és Idő** mezők alapvető fontosságúak a Dynamics 365 Talent megoldásban.</span><span class="sxs-lookup"><span data-stu-id="02aa1-105">**Date and Time** fields are a fundamental concept in Dynamics 365 Talent.</span></span> <span data-ttu-id="02aa1-106">Fontos, hogy megtanulja, hogyan dolgozzon a **Dátum és idő** adatokkal egy Dynamics 365 űrlapon, a Common Data Service szolgáltatásban és külső forrásokból.</span><span class="sxs-lookup"><span data-stu-id="02aa1-106">It's important to understand how to work with **Date and Time** data in a Dynamics 365 form, Common Data Service, and external sources.</span></span>

## <a name="understanding-the-difference-between-date-and-date-and-time-field-data-types"></a><span data-ttu-id="02aa1-107">A Dátum és a Dátum és az idő mező adattípusai különbségeinek megértése</span><span class="sxs-lookup"><span data-stu-id="02aa1-107">Understanding the difference between Date and Date and Time field data types</span></span>

<span data-ttu-id="02aa1-108">A **Dátum és idő** mező időzóna-információt tartalmaz, míg a **Dátum** mezők nem.</span><span class="sxs-lookup"><span data-stu-id="02aa1-108">**Date and Time** fields contain time zone information, while **Date** fields don't.</span></span> <span data-ttu-id="02aa1-109">A **Dátum** mezők bármilyen helyen ugyanazt az információt jelenítik meg.</span><span class="sxs-lookup"><span data-stu-id="02aa1-109">**Date** fields display the same information in any location.</span></span> <span data-ttu-id="02aa1-110">Amikor dátumot ír be a **Dátum** mezőbe, a Talent ugyanazt a dátumot írja az adatbázisba.</span><span class="sxs-lookup"><span data-stu-id="02aa1-110">When you enter a date into a **Date** field, Talent writes that same date to the database.</span></span>

<span data-ttu-id="02aa1-111">Amikor egy **Dátumot és idő** mezőben adatokat jeleníti meg, a Talent a **Felhasználói beállítások** képernyőn (**Közös > Beállítás > Felhasználói beállítások**) megadott időzóna alapján módosítja a dátumot és az időt.</span><span class="sxs-lookup"><span data-stu-id="02aa1-111">When displaying data in a **Date and Time** field, Talent adjusts the date and time based on the user's time zone set in the **User Options** form (**Common > Setup > User Options**).</span></span> <span data-ttu-id="02aa1-112">Előfordulhat, hogy a mezőben megadott dátum-és időadatok nem egyeznek meg az adatbázisba írt adatokkal.</span><span class="sxs-lookup"><span data-stu-id="02aa1-112">The date and time information you enter in the field might not be the same as the information written to the database.</span></span>

<span data-ttu-id="02aa1-113">[![Felhasználói beállítások képernyő](./media/useroptionsform.png)](./media/useroptionsform.png)</span><span class="sxs-lookup"><span data-stu-id="02aa1-113">[![User options form](./media/useroptionsform.png)](./media/useroptionsform.png)</span></span>

## <a name="understanding-date-and-time-fields-in-forms"></a><span data-ttu-id="02aa1-114">Dátum és Idő mezők képernyőkön</span><span class="sxs-lookup"><span data-stu-id="02aa1-114">Understanding Date and Time fields in forms</span></span> 

<span data-ttu-id="02aa1-115">Amikor a **Dátumot és idő** mezőbe írja be az adatokat, a képernyőn megjelenő adatok nem egyeznek meg az adatbázisban tárolt adatokkal, ha a felhasználó időzónája nem az univerzális világidő (UTC) szerint van állítva.</span><span class="sxs-lookup"><span data-stu-id="02aa1-115">When entering data in a **Date and Time** field, the data displayed on the screen isn't the same as the data stored in the database if the user's time zone isn't set to Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="02aa1-116">A **Dátum és idő** mezők adatait mindig UTC-ben tárolja a program.</span><span class="sxs-lookup"><span data-stu-id="02aa1-116">Data in **Date and Time** fields is always stored as UTC.</span></span>

<span data-ttu-id="02aa1-117">[![Dolgozó képernyő](./media/worker-form.png)](./media/worker-form.png)</span><span class="sxs-lookup"><span data-stu-id="02aa1-117">[![Worker form](./media/worker-form.png)](./media/worker-form.png)</span></span>

## <a name="understand-date-and-time-fields-in-the-database"></a><span data-ttu-id="02aa1-118">A Dátum és Idő mezők működés az adatbázisban</span><span class="sxs-lookup"><span data-stu-id="02aa1-118">Understand Date and Time fields in the database</span></span> 

<span data-ttu-id="02aa1-119">Amikor a Talent egy **Dátumot és idő** értéket ír az adatbázisba, az adatokat a UTC-ben tárolja.</span><span class="sxs-lookup"><span data-stu-id="02aa1-119">When Talent writes a **Date and time** value to the database, it stores the data in UTC.</span></span> <span data-ttu-id="02aa1-120">Ez lehetővé teszi a felhasználók számára , hogy a felhasználói beállításaiban megadott időzónához viszonyítva jelenítsenek meg minden **Dátum és idő** adatot.</span><span class="sxs-lookup"><span data-stu-id="02aa1-120">This allows users to see any **Date and Time** data relative to the time zone defined in their user options.</span></span>
 
<span data-ttu-id="02aa1-121">A fenti példában a kezdési időpont egy időpont, nem pedig egy adott dátum.</span><span class="sxs-lookup"><span data-stu-id="02aa1-121">In the example above, the start time is a point in time, not a particular date.</span></span> <span data-ttu-id="02aa1-122">Ha módosítja a bejelentkezett felhasználó időzónáját a GMT + 12:00 értékről GMT UTC értékre, akkor az imént létrehozott rekord ugyanaz a rekord, 04/30/2019 12:00:00 értéket mutat 05/01/2019 12:00:00 időpont helyett.</span><span class="sxs-lookup"><span data-stu-id="02aa1-122">By changing the time zone of the logged in user from GMT +12:00 to GMT UTC, the same record just created shows 04/30/2019 12:00:00 instead of 05/01/2019 12:00:00.</span></span>
  
<span data-ttu-id="02aa1-123">Az alábbi példában a 000724 számú alkalmazott munkaviszonya az időzónatól függetlenül aktívvá válik ugyanabban az időpontban.</span><span class="sxs-lookup"><span data-stu-id="02aa1-123">In the example below, employee 000724’s employment becomes active at the same time regardless of time zone.</span></span> <span data-ttu-id="02aa1-124">Az alkalmazott aktív lesz 2019. 04. 30-án a GMT-időzónában, amely ugyanaz, mint a 2019. 05. 01. a GMT + 12:00 időzónában.</span><span class="sxs-lookup"><span data-stu-id="02aa1-124">The employee will be active on 04/30/2019 in the GMT time zone, which is the same as 05/01/2019 in GMT+12:00 time zone.</span></span> <span data-ttu-id="02aa1-125">Mindkettő ugyanarra az idő pontra hivatkozik, és nem egy adott dátumra.</span><span class="sxs-lookup"><span data-stu-id="02aa1-125">Both refer to the same point in time and not a particular date.</span></span> 

<span data-ttu-id="02aa1-126">[![Dolgozó képernyő](./media/worker-form2.png)](./media/worker-form2.png)</span><span class="sxs-lookup"><span data-stu-id="02aa1-126">[![Worker form](./media/worker-form2.png)](./media/worker-form2.png)</span></span>

## <a name="date-and-time-data-in-data-management-framework-excel-common-data-service-and-power-bi"></a><span data-ttu-id="02aa1-127">Dátum-és időadatok az adatkezelési keretrendszerben, Excel programban, Common Data Service és Power BI szolgáltatásokban</span><span class="sxs-lookup"><span data-stu-id="02aa1-127">Date and Time data in Data Management Framework, Excel, Common Data Service, and Power BI</span></span> 

<span data-ttu-id="02aa1-128">Az adatkezelési keretrendszer, az Excel-bővítmény, a Common Data Service és a Power BI és a jelentéskészítés mind az adatbázis szintjén, közvetlenül az adatokkal való együttműködésre szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="02aa1-128">The Data Management Framework, Excel Add-In, Common Data Service, and Power BI reporting are all designed to interact with data directly on the database level.</span></span> <span data-ttu-id="02aa1-129">Mivel a felhasználó időzónájában nincs ügyfél a **Dátum és idő** adatok helyesbítésére, az összes **Dátum és idő** érték UTC-ben van, ami helytelen feltételezésekhez vezethet az adatok beírása vagy megtekintése során.</span><span class="sxs-lookup"><span data-stu-id="02aa1-129">Since there is no client to adjust **Date and Time** data to the time zone of the user, all **Date and Time** values are in UTC, which can lead to some incorrect assumptions when entering or viewing data.</span></span>  
 
<span data-ttu-id="02aa1-130">A **Dátum és idő** adatok, amelyek DMF, Excel, vagy Common Data Service szolgáltatáson keresztül lettek beküldve UTC-nek vannak tekintve az adatbázisban.</span><span class="sxs-lookup"><span data-stu-id="02aa1-130">**Date and Time** data that is submitted via DMF, Excel, or Common Data Service is assumed to be in UTC by the database.</span></span> <span data-ttu-id="02aa1-131">Ez némi zavart okozhat, ha a benyújtott **dátum-és időérték** nem a várt módon jelenik meg, mert az adatokat megjelenítő felhasználó időzónája nem UTC értékre van állítva.</span><span class="sxs-lookup"><span data-stu-id="02aa1-131">This can cause some confusion when the submitted **Date and Time** value doesn't display as expected because the user viewing the data doesn't have their user time zone  set to UTC.</span></span> 
 
<span data-ttu-id="02aa1-132">Ugyanaz a dolog történik meg visszafelé az adatok exportálásakor.</span><span class="sxs-lookup"><span data-stu-id="02aa1-132">The same thing can happen in reverse when data is exported.</span></span> <span data-ttu-id="02aa1-133">Az exportált DMF entitás **Dátum-és idő** adatai különbözőek lehetnek attól ami a Dynamics ügyfélben látható.</span><span class="sxs-lookup"><span data-stu-id="02aa1-133">The **Date and Time** data in the exported DMF entity can be different then what is displayed in the Dynamics client.</span></span> 
 
<span data-ttu-id="02aa1-134">Ha olyan külső forrásokat használ, mint a DMF az adatok szerkesztéséhez vagy létrehozásához, akkor fontos szem előtt tartani, hogy a **Dátum-és idő** értékek alapértelmezetten UTC-nek vannak tekintve a felhasználó számítógépének időzónájától vagy az aktuális felhasználói időzóna beállításaitól függetlenül.</span><span class="sxs-lookup"><span data-stu-id="02aa1-134">When using external sources like DMF to view or author data, it is important to keep in mind that the **Date and Time** values are considered by default to be in UTC regardless of the time zone of the user's computer or their current user time zone settings.</span></span> 

## <a name="examples-of-the-same-record-being-displayed-in-different-product-areas"></a><span data-ttu-id="02aa1-135">Példák ugyanarra a rekordra, amely a különböző terméktartományoknak vannak megjelenítve.</span><span class="sxs-lookup"><span data-stu-id="02aa1-135">Examples of the same record being displayed in different product areas</span></span> 

<span data-ttu-id="02aa1-136">**A Talent időzónája UTC értékre van állítva**</span><span class="sxs-lookup"><span data-stu-id="02aa1-136">**Talent with user time zone set to UTC**</span></span>

<span data-ttu-id="02aa1-137">[![Dolgozó képernyő](./media/worker-form3.png)](./media/worker-form3.png)</span><span class="sxs-lookup"><span data-stu-id="02aa1-137">[![Worker form](./media/worker-form3.png)](./media/worker-form3.png)</span></span>

<span data-ttu-id="02aa1-138">**A Talent időzónája GMT + 12:00 értékre van állítva**</span><span class="sxs-lookup"><span data-stu-id="02aa1-138">**Talent with user time zone set to GMT +12:00**</span></span> 

<span data-ttu-id="02aa1-139">[![Dolgozó képernyő](./media/worker-form4.png)](./media/worker-form4.png)</span><span class="sxs-lookup"><span data-stu-id="02aa1-139">[![Worker form](./media/worker-form4.png)](./media/worker-form4.png)</span></span>

<span data-ttu-id="02aa1-140">**Excel-OData-n keresztül**</span><span class="sxs-lookup"><span data-stu-id="02aa1-140">**Excel Via OData**</span></span>

<span data-ttu-id="02aa1-141">[![Excel-OData-n keresztül](./media/Excelviaodata.png)](./media/Excelviaodata.png)</span><span class="sxs-lookup"><span data-stu-id="02aa1-141">[![Excel Via OData](./media/Excelviaodata.png)](./media/Excelviaodata.png)</span></span>

<span data-ttu-id="02aa1-142">**DMF-előkészítés**</span><span class="sxs-lookup"><span data-stu-id="02aa1-142">**DMF Staging**</span></span>

<span data-ttu-id="02aa1-143">[![DMF-előkészítés](./media/DMFStaging.png)](./media/DMFStaging.png)</span><span class="sxs-lookup"><span data-stu-id="02aa1-143">[![DMF Staging](./media/DMFStaging.png)](./media/DMFStaging.png)</span></span>

<span data-ttu-id="02aa1-144">**DMF-exportálás**</span><span class="sxs-lookup"><span data-stu-id="02aa1-144">**DMF Export**</span></span>

<span data-ttu-id="02aa1-145">[![DMF-előkészítés](./media/DMFexport.png)](./media/DMFexport.png)</span><span class="sxs-lookup"><span data-stu-id="02aa1-145">[![DMF Staging](./media/DMFexport.png)](./media/DMFexport.png)</span></span>

<span data-ttu-id="02aa1-146">**Excel Common Data Service szolgáltatáson keresztül**</span><span class="sxs-lookup"><span data-stu-id="02aa1-146">**Excel via Common Data Service**</span></span>

<span data-ttu-id="02aa1-147">[![Excel Common Data Service szolgáltatáson keresztül](./media/ExcelCDS.png)](./media/ExcelCDS.png)</span><span class="sxs-lookup"><span data-stu-id="02aa1-147">[![Excel via Common Data Service](./media/ExcelCDS.png)](./media/ExcelCDS.png)</span></span>

### <a name="see-also"></a><span data-ttu-id="02aa1-148">Lásd még</span><span class="sxs-lookup"><span data-stu-id="02aa1-148">See also</span></span>

[<span data-ttu-id="02aa1-149">Dátum- és időadatok</span><span class="sxs-lookup"><span data-stu-id="02aa1-149">Date and time data</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/organization-administration/date-time-zones)<br></br>
[<span data-ttu-id="02aa1-150">A felhasználó preferált időzónái</span><span class="sxs-lookup"><span data-stu-id="02aa1-150">User preferred time zones</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/organization-administration/tasks/set-users-preferred-time-zone) 
