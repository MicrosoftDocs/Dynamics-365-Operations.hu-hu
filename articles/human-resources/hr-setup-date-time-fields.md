---
title: Dátuma és Idő mezők ismertetése
description: Annak megértése, mire számíthat, ha a Microsoft Dynamics 365 Human Resources megoldásban dátum-és időmezőket használ. Megtudhatja, hogy mire számíthat, ha az Emberi erőforrások egy űrlapján külső forrásból vagy a Common Data Service szolgáltatásból származó adatokkal dolgozik.
author: Darinkramer
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9dd80415f33a4d671bdc2662704799775daad177
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009244"
---
# <a name="understand-date-and-time-fields"></a><span data-ttu-id="b9d4c-104">Dátuma és Idő mezők ismertetése</span><span class="sxs-lookup"><span data-stu-id="b9d4c-104">Understand Date and Time fields</span></span>

<span data-ttu-id="b9d4c-105">**A dátum és Idő** mezők alapvető fontosságúak a Dynamics 365 Human Resources megoldásban.</span><span class="sxs-lookup"><span data-stu-id="b9d4c-105">**Date and Time** fields are a fundamental concept in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="b9d4c-106">Fontos, hogy megtanulja, hogyan dolgozzon a **Dátum és idő** adatokkal Dynamics 365 Human Resources űrlapokon, a Common Data Service szolgáltatásban és külső forrásokon.</span><span class="sxs-lookup"><span data-stu-id="b9d4c-106">It's important to understand how to work with **Date and Time** data in Dynamics 365 Human Resources forms, Common Data Service, and external sources.</span></span>

## <a name="understanding-the-difference-between-date-and-date-and-time-field-data-types"></a><span data-ttu-id="b9d4c-107">A Dátum és a Dátum és az idő mező adattípusai különbségeinek megértése</span><span class="sxs-lookup"><span data-stu-id="b9d4c-107">Understanding the difference between Date and Date and Time field data types</span></span>

<span data-ttu-id="b9d4c-108">A **Dátum és idő** mező időzóna-információt tartalmaz, míg a **Dátum** mezők nem.</span><span class="sxs-lookup"><span data-stu-id="b9d4c-108">**Date and Time** fields contain time zone information, while **Date** fields don't.</span></span> <span data-ttu-id="b9d4c-109">A **Dátum** mezők bármilyen helyen ugyanazt az információt jelenítik meg.</span><span class="sxs-lookup"><span data-stu-id="b9d4c-109">**Date** fields display the same information in any location.</span></span> <span data-ttu-id="b9d4c-110">Amikor dátumot ír be a **Dátum** mezőbe, az Emberi erőforrások ugyanazt a dátumot írja az adatbázisba.</span><span class="sxs-lookup"><span data-stu-id="b9d4c-110">When you enter a date into a **Date** field, Human Resources writes that same date to the database.</span></span>

<span data-ttu-id="b9d4c-111">Amikor egy **Dátumot és idő** mezőben adatokat jeleníti meg, az Emberi erőforrások a **Felhasználói beállítások** képernyőn (**Közös > Beállítás > Felhasználói beállítások**) megadott időzóna alapján módosítja a dátumot és az időt.</span><span class="sxs-lookup"><span data-stu-id="b9d4c-111">When displaying data in a **Date and Time** field, Human Resources adjusts the date and time based on the user's time zone set in the **User Options** form (**Common > Setup > User Options**).</span></span> <span data-ttu-id="b9d4c-112">Előfordulhat, hogy a mezőben megadott dátum-és időadatok nem egyeznek meg az adatbázisba írt adatokkal.</span><span class="sxs-lookup"><span data-stu-id="b9d4c-112">The date and time information you enter in the field might not be the same as the information written to the database.</span></span>

<span data-ttu-id="b9d4c-113">[![Felhasználói beállítások képernyő](./media/useroptionsform.png)](./media/useroptionsform.png)</span><span class="sxs-lookup"><span data-stu-id="b9d4c-113">[![User options form](./media/useroptionsform.png)](./media/useroptionsform.png)</span></span>

## <a name="understanding-date-and-time-fields-in-forms"></a><span data-ttu-id="b9d4c-114">Dátum és Idő mezők képernyőkön</span><span class="sxs-lookup"><span data-stu-id="b9d4c-114">Understanding Date and Time fields in forms</span></span> 

<span data-ttu-id="b9d4c-115">Amikor a **Dátumot és idő** mezőbe írja be az adatokat, a képernyőn megjelenő adatok nem egyeznek meg az adatbázisban tárolt adatokkal, ha a felhasználó időzónája nem az univerzális világidő (UTC) szerint van állítva.</span><span class="sxs-lookup"><span data-stu-id="b9d4c-115">When entering data in a **Date and Time** field, the data displayed on the screen isn't the same as the data stored in the database if the user's time zone isn't set to Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="b9d4c-116">A **Dátum és idő** mezők adatait mindig UTC-ben tárolja a program.</span><span class="sxs-lookup"><span data-stu-id="b9d4c-116">Data in **Date and Time** fields is always stored as UTC.</span></span>

<span data-ttu-id="b9d4c-117">[![Dolgozó képernyő](./media/worker-form.png)](./media/worker-form.png)</span><span class="sxs-lookup"><span data-stu-id="b9d4c-117">[![Worker form](./media/worker-form.png)](./media/worker-form.png)</span></span>

## <a name="understand-date-and-time-fields-in-the-database"></a><span data-ttu-id="b9d4c-118">A Dátum és Idő mezők működés az adatbázisban</span><span class="sxs-lookup"><span data-stu-id="b9d4c-118">Understand Date and Time fields in the database</span></span> 

<span data-ttu-id="b9d4c-119">Amikor az Emberi erőforrások egy **Dátumot és idő** értéket ír az adatbázisba, az adatokat a UTC-ben tárolja.</span><span class="sxs-lookup"><span data-stu-id="b9d4c-119">When Human Resources writes a **Date and time** value to the database, it stores the data in UTC.</span></span> <span data-ttu-id="b9d4c-120">Ez lehetővé teszi a felhasználók számára , hogy a felhasználói beállításaiban megadott időzónához viszonyítva jelenítsenek meg minden **Dátum és idő** adatot.</span><span class="sxs-lookup"><span data-stu-id="b9d4c-120">This allows users to see any **Date and Time** data relative to the time zone defined in their user options.</span></span>
 
<span data-ttu-id="b9d4c-121">A fenti példában a kezdési időpont egy időpont, nem pedig egy adott dátum.</span><span class="sxs-lookup"><span data-stu-id="b9d4c-121">In the example above, the start time is a point in time, not a particular date.</span></span> <span data-ttu-id="b9d4c-122">Ha módosítja a bejelentkezett felhasználó időzónáját a GMT + 12:00 értékről GMT UTC értékre, akkor az imént létrehozott rekord ugyanaz a rekord, 04/30/2019 12:00:00 értéket mutat 05/01/2019 12:00:00 időpont helyett.</span><span class="sxs-lookup"><span data-stu-id="b9d4c-122">By changing the time zone of the logged in user from GMT +12:00 to GMT UTC, the same record just created shows 04/30/2019 12:00:00 instead of 05/01/2019 12:00:00.</span></span>
  
<span data-ttu-id="b9d4c-123">Az alábbi példában a 000724 számú alkalmazott munkaviszonya az időzónatól függetlenül aktívvá válik ugyanabban az időpontban.</span><span class="sxs-lookup"><span data-stu-id="b9d4c-123">In the example below, employee 000724’s employment becomes active at the same time regardless of time zone.</span></span> <span data-ttu-id="b9d4c-124">Az alkalmazott aktív lesz 2019. 04. 30-án a GMT-időzónában, amely ugyanaz, mint a 2019. 05. 01. a GMT + 12:00 időzónában.</span><span class="sxs-lookup"><span data-stu-id="b9d4c-124">The employee will be active on 04/30/2019 in the GMT time zone, which is the same as 05/01/2019 in GMT+12:00 time zone.</span></span> <span data-ttu-id="b9d4c-125">Mindkettő ugyanarra az idő pontra hivatkozik, és nem egy adott dátumra.</span><span class="sxs-lookup"><span data-stu-id="b9d4c-125">Both refer to the same point in time and not a particular date.</span></span> 

<span data-ttu-id="b9d4c-126">[![Dolgozó képernyő](./media/worker-form2.png)](./media/worker-form2.png)</span><span class="sxs-lookup"><span data-stu-id="b9d4c-126">[![Worker form](./media/worker-form2.png)](./media/worker-form2.png)</span></span>

## <a name="date-and-time-data-in-data-management-framework-excel-common-data-service-and-power-bi"></a><span data-ttu-id="b9d4c-127">Dátum-és időadatok az adatkezelési keretrendszerben, Excel programban, Common Data Service és Power BI szolgáltatásokban</span><span class="sxs-lookup"><span data-stu-id="b9d4c-127">Date and Time data in Data Management Framework, Excel, Common Data Service, and Power BI</span></span> 

<span data-ttu-id="b9d4c-128">Az adatkezelési keretrendszer, az Excel-bővítmény, a Common Data Service és a Power BI és a jelentéskészítés mind az adatbázis szintjén, közvetlenül az adatokkal való együttműködésre szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="b9d4c-128">The Data Management Framework, Excel Add-In, Common Data Service, and Power BI reporting are all designed to interact with data directly on the database level.</span></span> <span data-ttu-id="b9d4c-129">Mivel a felhasználó időzónájában nincs ügyfél a **Dátum és idő** adatok helyesbítésére, az összes **Dátum és idő** érték UTC-ben van, ami helytelen feltételezésekhez vezethet az adatok beírása vagy megtekintése során.</span><span class="sxs-lookup"><span data-stu-id="b9d4c-129">Since there is no client to adjust **Date and Time** data to the time zone of the user, all **Date and Time** values are in UTC, which can lead to some incorrect assumptions when entering or viewing data.</span></span>  
 
<span data-ttu-id="b9d4c-130">A **Dátum és idő** adatok, amelyek DMF, Excel, vagy Common Data Service szolgáltatáson keresztül lettek beküldve UTC-nek vannak tekintve az adatbázisban.</span><span class="sxs-lookup"><span data-stu-id="b9d4c-130">**Date and Time** data that is submitted via DMF, Excel, or Common Data Service is assumed to be in UTC by the database.</span></span> <span data-ttu-id="b9d4c-131">Ez némi zavart okozhat, ha a benyújtott **dátum-és időérték** nem a várt módon jelenik meg, mert az adatokat megjelenítő felhasználó időzónája nem UTC értékre van állítva.</span><span class="sxs-lookup"><span data-stu-id="b9d4c-131">This can cause some confusion when the submitted **Date and Time** value doesn't display as expected because the user viewing the data doesn't have their user time zone  set to UTC.</span></span> 
 
<span data-ttu-id="b9d4c-132">Ugyanaz a dolog történik meg visszafelé az adatok exportálásakor.</span><span class="sxs-lookup"><span data-stu-id="b9d4c-132">The same thing can happen in reverse when data is exported.</span></span> <span data-ttu-id="b9d4c-133">Az exportált DMF entitás **Dátum-és idő** adatai különbözőek lehetnek attól ami a Dynamics ügyfélben látható.</span><span class="sxs-lookup"><span data-stu-id="b9d4c-133">The **Date and Time** data in the exported DMF entity can be different then what is displayed in the Dynamics client.</span></span> 
 
<span data-ttu-id="b9d4c-134">Ha olyan külső forrásokat használ, mint a DMF az adatok szerkesztéséhez vagy létrehozásához, akkor fontos szem előtt tartani, hogy a **Dátum-és idő** értékek alapértelmezetten UTC-nek vannak tekintve a felhasználó számítógépének időzónájától vagy az aktuális felhasználói időzóna beállításaitól függetlenül.</span><span class="sxs-lookup"><span data-stu-id="b9d4c-134">When using external sources like DMF to view or author data, it is important to keep in mind that the **Date and Time** values are considered by default to be in UTC regardless of the time zone of the user's computer or their current user time zone settings.</span></span> 

## <a name="examples-of-the-same-record-being-displayed-in-different-product-areas"></a><span data-ttu-id="b9d4c-135">Példák ugyanarra a rekordra, amely a különböző terméktartományoknak vannak megjelenítve.</span><span class="sxs-lookup"><span data-stu-id="b9d4c-135">Examples of the same record being displayed in different product areas</span></span> 

<span data-ttu-id="b9d4c-136">**Az Emberi erőforrások időzónája UTC értékre van állítva**</span><span class="sxs-lookup"><span data-stu-id="b9d4c-136">**Human Resources with user time zone set to UTC**</span></span>

<span data-ttu-id="b9d4c-137">[![Dolgozó képernyő](./media/worker-form3.png)](./media/worker-form3.png)</span><span class="sxs-lookup"><span data-stu-id="b9d4c-137">[![Worker form](./media/worker-form3.png)](./media/worker-form3.png)</span></span>

<span data-ttu-id="b9d4c-138">**Az Emberi erőforrások időzónája GMT +12:00 értékre van állítva**</span><span class="sxs-lookup"><span data-stu-id="b9d4c-138">**Human Resources with user time zone set to GMT +12:00**</span></span> 

<span data-ttu-id="b9d4c-139">[![Dolgozó képernyő](./media/worker-form4.png)](./media/worker-form4.png)</span><span class="sxs-lookup"><span data-stu-id="b9d4c-139">[![Worker form](./media/worker-form4.png)](./media/worker-form4.png)</span></span>

<span data-ttu-id="b9d4c-140">**Excel-OData-n keresztül**</span><span class="sxs-lookup"><span data-stu-id="b9d4c-140">**Excel Via OData**</span></span>

<span data-ttu-id="b9d4c-141">[![Excel-OData-n keresztül](./media/Excelviaodata.png)](./media/Excelviaodata.png)</span><span class="sxs-lookup"><span data-stu-id="b9d4c-141">[![Excel Via OData](./media/Excelviaodata.png)](./media/Excelviaodata.png)</span></span>

<span data-ttu-id="b9d4c-142">**DMF-előkészítés**</span><span class="sxs-lookup"><span data-stu-id="b9d4c-142">**DMF Staging**</span></span>

<span data-ttu-id="b9d4c-143">[![DMF-előkészítés](./media/DMFStaging.png)](./media/DMFStaging.png)</span><span class="sxs-lookup"><span data-stu-id="b9d4c-143">[![DMF Staging](./media/DMFStaging.png)](./media/DMFStaging.png)</span></span>

<span data-ttu-id="b9d4c-144">**DMF-exportálás**</span><span class="sxs-lookup"><span data-stu-id="b9d4c-144">**DMF Export**</span></span>

<span data-ttu-id="b9d4c-145">[![DMF-előkészítés](./media/DMFexport.png)](./media/DMFexport.png)</span><span class="sxs-lookup"><span data-stu-id="b9d4c-145">[![DMF Staging](./media/DMFexport.png)](./media/DMFexport.png)</span></span>

<span data-ttu-id="b9d4c-146">**Excel Common Data Service szolgáltatáson keresztül**</span><span class="sxs-lookup"><span data-stu-id="b9d4c-146">**Excel via Common Data Service**</span></span>

<span data-ttu-id="b9d4c-147">[![Excel Common Data Service szolgáltatáson keresztül](./media/ExcelCDS.png)](./media/ExcelCDS.png)</span><span class="sxs-lookup"><span data-stu-id="b9d4c-147">[![Excel via Common Data Service](./media/ExcelCDS.png)](./media/ExcelCDS.png)</span></span>

## <a name="see-also"></a><span data-ttu-id="b9d4c-148">Lásd még</span><span class="sxs-lookup"><span data-stu-id="b9d4c-148">See also</span></span>

[<span data-ttu-id="b9d4c-149">Dátum- és időadatok</span><span class="sxs-lookup"><span data-stu-id="b9d4c-149">Date and time data</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/organization-administration/date-time-zones)<br></br>
[<span data-ttu-id="b9d4c-150">A felhasználó preferált időzónái</span><span class="sxs-lookup"><span data-stu-id="b9d4c-150">User preferred time zones</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/organization-administration/tasks/set-users-preferred-time-zone) 
