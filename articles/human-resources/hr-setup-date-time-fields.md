---
title: Dátuma és Idő mezők ismertetése
description: Annak megértése, mire számíthat, ha a Microsoft Dynamics 365 Human Resources megoldásban dátum-és időmezőket használ.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b7e5726f7e4beea1584b9a8e142212531ba1db56
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6051737"
---
# <a name="understand-date-and-time-fields"></a><span data-ttu-id="77266-103">Dátum és Idő mezők ismertetése</span><span class="sxs-lookup"><span data-stu-id="77266-103">Understand Date and Time fields</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="77266-104">**A dátum és Idő** mezők alapvető fontosságúak a Dynamics 365 Human Resources megoldásban.</span><span class="sxs-lookup"><span data-stu-id="77266-104">**Date and Time** fields are a fundamental concept in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="77266-105">Fontos, hogy megtanulja, hogyan dolgozzon a **Dátum és idő** adatokkal űrlapokon, a Dataverse szolgáltatásban és külső forrásokon.</span><span class="sxs-lookup"><span data-stu-id="77266-105">It's important to understand how to work with **Date and Time** data in forms, Dataverse, and external sources.</span></span>

## <a name="understanding-the-difference-between-date-and-date-and-time-field-data-types"></a><span data-ttu-id="77266-106">A Dátum és a Dátum és az idő mező adattípusai különbségeinek megértése</span><span class="sxs-lookup"><span data-stu-id="77266-106">Understanding the difference between Date and Date and Time field data types</span></span>

<span data-ttu-id="77266-107">A **Dátum és idő** mező időzóna-információt tartalmaz, míg a **Dátum** mezők nem.</span><span class="sxs-lookup"><span data-stu-id="77266-107">**Date and Time** fields contain time zone information, while **Date** fields don't.</span></span> <span data-ttu-id="77266-108">A **Dátum** mezők bármilyen helyen ugyanazt az információt jelenítik meg.</span><span class="sxs-lookup"><span data-stu-id="77266-108">**Date** fields display the same information in any location.</span></span> <span data-ttu-id="77266-109">Amikor dátumot ír be a **Dátum** mezőbe, az Emberi erőforrások ugyanazt a dátumot írja az adatbázisba.</span><span class="sxs-lookup"><span data-stu-id="77266-109">When you enter a date into a **Date** field, Human Resources writes that same date to the database.</span></span>

<span data-ttu-id="77266-110">Amikor egy **Dátumot és idő** mezőben adatokat jeleníti meg, az Emberi erőforrások a **Felhasználói beállítások** képernyőn (**Közös > Beállítás > Felhasználói beállítások**) megadott időzóna alapján módosítja a dátumot és az időt.</span><span class="sxs-lookup"><span data-stu-id="77266-110">When displaying data in a **Date and Time** field, Human Resources adjusts the date and time based on the user's time zone set in the **User Options** form (**Common > Setup > User Options**).</span></span> <span data-ttu-id="77266-111">Előfordulhat, hogy a mezőben megadott dátum-és időadatok nem egyeznek meg az adatbázisba írt adatokkal.</span><span class="sxs-lookup"><span data-stu-id="77266-111">The date and time information you enter in the field might not be the same as the information written to the database.</span></span>

<span data-ttu-id="77266-112">[![Felhasználói beállítások képernyő](./media/useroptionsform.png)](./media/useroptionsform.png)</span><span class="sxs-lookup"><span data-stu-id="77266-112">[![User options form](./media/useroptionsform.png)](./media/useroptionsform.png)</span></span>

## <a name="understanding-date-and-time-fields-in-forms"></a><span data-ttu-id="77266-113">Dátum és Idő mezők képernyőkön</span><span class="sxs-lookup"><span data-stu-id="77266-113">Understanding Date and Time fields in forms</span></span> 

<span data-ttu-id="77266-114">A **Dátum és idő** mezőben a képernyőn megjelenő adatok nem egyeznek meg az adatbázisban tárolt adatokkal, ha a felhasználó időzónája nem az univerzális világidő (UTC) szerint van állítva.</span><span class="sxs-lookup"><span data-stu-id="77266-114">**Date and Time** data displayed on the screen isn't the same as the data stored in the database if the user's time zone isn't set to Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="77266-115">A **Dátum és idő** mezők adatait mindig UTC-ben tárolja a program.</span><span class="sxs-lookup"><span data-stu-id="77266-115">Data in **Date and Time** fields is always stored as UTC.</span></span>

<span data-ttu-id="77266-116">[![Dolgozói űrlap UTC](./media/worker-form.png)](./media/worker-form.png)</span><span class="sxs-lookup"><span data-stu-id="77266-116">[![Worker form UTC](./media/worker-form.png)](./media/worker-form.png)</span></span>

## <a name="understand-date-and-time-fields-in-the-database"></a><span data-ttu-id="77266-117">A Dátum és Idő mezők működés az adatbázisban</span><span class="sxs-lookup"><span data-stu-id="77266-117">Understand Date and Time fields in the database</span></span> 

<span data-ttu-id="77266-118">Amikor a Human Resources alkalmazás egy **Dátum és idő** értéket ír az adatbázisba, az adatokat UTC-ben tárolja.</span><span class="sxs-lookup"><span data-stu-id="77266-118">When Human Resources writes a **Date and Time** value to the database, it stores the data in UTC.</span></span> <span data-ttu-id="77266-119">Ez lehetővé teszi a felhasználók számára , hogy a felhasználói beállításaiban megadott időzónához viszonyítva jelenítsenek meg minden **Dátum és idő** adatot.</span><span class="sxs-lookup"><span data-stu-id="77266-119">This allows users to see any **Date and Time** data relative to the time zone defined in their user options.</span></span>
 
<span data-ttu-id="77266-120">A fenti példában a kezdési időpont egy időpont, nem pedig egy adott dátum.</span><span class="sxs-lookup"><span data-stu-id="77266-120">In the example above, the start time is a point in time, not a particular date.</span></span> <span data-ttu-id="77266-121">Ha módosítja a bejelentkezett felhasználó időzónáját a GMT + 12:00 értékről GMT UTC értékre, akkor ugyanaz a rekord 04/30/2019 12:00:00 értéket mutat 05/01/2019 12:00:00 időpont helyett.</span><span class="sxs-lookup"><span data-stu-id="77266-121">By changing the time zone of the logged in user from GMT +12:00 to GMT UTC, the same record shows 04/30/2019 12:00:00 instead of 05/01/2019 12:00:00.</span></span>
  
<span data-ttu-id="77266-122">Az alábbi példában a 000724 számú alkalmazott munkaviszonya az időzónatól függetlenül aktívvá válik ugyanabban az időpontban.</span><span class="sxs-lookup"><span data-stu-id="77266-122">In the example below, employee 000724’s employment becomes active at the same time regardless of time zone.</span></span> <span data-ttu-id="77266-123">Az alkalmazott aktív lesz 2019. 04. 30-án a GMT-időzónában, amely ugyanaz, mint a 2019. 05. 01. a GMT + 12:00 időzónában.</span><span class="sxs-lookup"><span data-stu-id="77266-123">The employee will be active on 04/30/2019 in the GMT time zone, which is the same as 05/01/2019 in GMT+12:00 time zone.</span></span> <span data-ttu-id="77266-124">Mindkettő ugyanarra az idő pontra hivatkozik, és nem egy adott dátumra.</span><span class="sxs-lookup"><span data-stu-id="77266-124">Both refer to the same point in time and not a particular date.</span></span> 

<span data-ttu-id="77266-125">[![Dolgozói űrlap GMT](./media/worker-form2.png)](./media/worker-form2.png)</span><span class="sxs-lookup"><span data-stu-id="77266-125">[![Worker form GMT](./media/worker-form2.png)](./media/worker-form2.png)</span></span>

## <a name="date-and-time-data-in-data-management-framework-excel-dataverse-and-power-bi"></a><span data-ttu-id="77266-126">Dátum-és időadatok az adatkezelési keretrendszerben, Excel programban, Dataverse és Power BI szolgáltatásokban</span><span class="sxs-lookup"><span data-stu-id="77266-126">Date and Time data in Data Management Framework, Excel, Dataverse, and Power BI</span></span> 

<span data-ttu-id="77266-127">Az adatkezelési keretrendszer, az Excel-bővítmény, a Dataverse és a Power BI és a jelentéskészítés mind az adatbázis szintjén, közvetlenül az adatokkal való együttműködésre szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="77266-127">The Data Management Framework, Excel Add-In, Dataverse, and Power BI reporting are all designed to interact with data directly on the database level.</span></span> <span data-ttu-id="77266-128">Mivel a felhasználó időzónájában nincs ügyfél a **Dátum és idő** adatok helyesbítésére, az összes **Dátum és idő** érték UTC-ben van, ami helytelen feltételezésekhez vezethet az adatok beírása vagy megtekintése során.</span><span class="sxs-lookup"><span data-stu-id="77266-128">Since there's no client to adjust **Date and Time** data to the time zone of the user, all **Date and Time** values are in UTC, which can lead to some incorrect assumptions when entering or viewing data.</span></span>  
 
<span data-ttu-id="77266-129">A **Dátum és idő** adatokat, amelyeket DMF, Excel, vagy Dataverse szolgáltatáson keresztül küldtek be, az adatbázis UTC-nek tekinti.</span><span class="sxs-lookup"><span data-stu-id="77266-129">**Date and Time** data submitted via DMF, Excel, or Dataverse is assumed to be in UTC by the database.</span></span> <span data-ttu-id="77266-130">Ez némi zavart okozhat, ha a benyújtott **dátum-és időérték** nem a várt módon jelenik meg, mert az adatokat megjelenítő felhasználó időzónája nem UTC értékre van állítva.</span><span class="sxs-lookup"><span data-stu-id="77266-130">This can cause some confusion when the submitted **Date and Time** value doesn't display as expected because the user viewing the data doesn't have their user time zone  set to UTC.</span></span> 
 
<span data-ttu-id="77266-131">Ugyanaz a dolog történik meg visszafelé az adatok exportálásakor.</span><span class="sxs-lookup"><span data-stu-id="77266-131">The same thing can happen in reverse when data is exported.</span></span> <span data-ttu-id="77266-132">Az exportált DMF-entitás **Dátum és idő** adatai eltérhetnek attól, ami a Dynamics-ügyfélben látható.</span><span class="sxs-lookup"><span data-stu-id="77266-132">The **Date and Time** data in the exported DMF entity can be different than what is displayed in the Dynamics client.</span></span> 
 
<span data-ttu-id="77266-133">Ha a DMF-hez hasonló külső forrásokat használ az adatok szerkesztéséhez vagy létrehozásához, fontos szem előtt tartani, hogy a **Dátum és idő** értékek alapértelmezetten UTC-nek vannak tekintve a felhasználó számítógépének időzónájától vagy az aktuális felhasználói időzóna beállításaitól függetlenül.</span><span class="sxs-lookup"><span data-stu-id="77266-133">When using external sources like DMF to view or author data, keep in mind that the **Date and Time** values are considered by default to be in UTC regardless of the time zone of the user's computer or their current user time zone settings.</span></span> 

## <a name="examples-of-the-same-record-being-displayed-in-different-product-areas"></a><span data-ttu-id="77266-134">Példák ugyanarra a rekordra, amely a különböző terméktartományoknak vannak megjelenítve.</span><span class="sxs-lookup"><span data-stu-id="77266-134">Examples of the same record being displayed in different product areas</span></span> 

<span data-ttu-id="77266-135">**Az Emberi erőforrások időzónája UTC értékre van állítva**</span><span class="sxs-lookup"><span data-stu-id="77266-135">**Human Resources with user time zone set to UTC**</span></span>

<span data-ttu-id="77266-136">[![Dolgozói űrlap UTC-formátumra állítva](./media/worker-form3.png)](./media/worker-form3.png)</span><span class="sxs-lookup"><span data-stu-id="77266-136">[![Worker form set to UTC](./media/worker-form3.png)](./media/worker-form3.png)</span></span>

<span data-ttu-id="77266-137">**Az Emberi erőforrások időzónája GMT +12:00 értékre van állítva**</span><span class="sxs-lookup"><span data-stu-id="77266-137">**Human Resources with user time zone set to GMT +12:00**</span></span> 

<span data-ttu-id="77266-138">[![Dolgozói űrlap GMT-formátumra állítva](./media/worker-form4.png)](./media/worker-form4.png)</span><span class="sxs-lookup"><span data-stu-id="77266-138">[![Worker form set to GMT](./media/worker-form4.png)](./media/worker-form4.png)</span></span>

<span data-ttu-id="77266-139">**Excel-OData-n keresztül**</span><span class="sxs-lookup"><span data-stu-id="77266-139">**Excel Via OData**</span></span>

<span data-ttu-id="77266-140">[![Excel-OData-n keresztül](./media/Excelviaodata.png)](./media/Excelviaodata.png)</span><span class="sxs-lookup"><span data-stu-id="77266-140">[![Excel Via OData](./media/Excelviaodata.png)](./media/Excelviaodata.png)</span></span>

<span data-ttu-id="77266-141">**DMF-előkészítés**</span><span class="sxs-lookup"><span data-stu-id="77266-141">**DMF Staging**</span></span>

<span data-ttu-id="77266-142">[![DMF-előkészítés](./media/DMFStaging.png)](./media/DMFStaging.png)</span><span class="sxs-lookup"><span data-stu-id="77266-142">[![DMF Staging](./media/DMFStaging.png)](./media/DMFStaging.png)</span></span>

<span data-ttu-id="77266-143">**DMF-exportálás**</span><span class="sxs-lookup"><span data-stu-id="77266-143">**DMF Export**</span></span>

<span data-ttu-id="77266-144">[![DMF exportálása](./media/DMFexport.png)](./media/DMFexport.png)</span><span class="sxs-lookup"><span data-stu-id="77266-144">[![DMF Export](./media/DMFexport.png)](./media/DMFexport.png)</span></span>

<span data-ttu-id="77266-145">**Excel Dataverse szolgáltatáson keresztül**</span><span class="sxs-lookup"><span data-stu-id="77266-145">**Excel via Dataverse**</span></span>

<span data-ttu-id="77266-146">[![Excel Dataverse szolgáltatáson keresztül](./media/ExcelCDS.png)](./media/ExcelCDS.png)</span><span class="sxs-lookup"><span data-stu-id="77266-146">[![Excel via Dataverse](./media/ExcelCDS.png)](./media/ExcelCDS.png)</span></span>

## <a name="see-also"></a><span data-ttu-id="77266-147">Lásd még</span><span class="sxs-lookup"><span data-stu-id="77266-147">See also</span></span>

[<span data-ttu-id="77266-148">Dátum- és időadatok</span><span class="sxs-lookup"><span data-stu-id="77266-148">Date and time data</span></span>](/dynamics365/unified-operations/fin-and-ops/organization-administration/date-time-zones)<br></br>
[<span data-ttu-id="77266-149">A felhasználó preferált időzónái</span><span class="sxs-lookup"><span data-stu-id="77266-149">User preferred time zones</span></span>](/dynamics365/unified-operations/fin-and-ops/organization-administration/tasks/set-users-preferred-time-zone) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]