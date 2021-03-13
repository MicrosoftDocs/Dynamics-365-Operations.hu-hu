---
title: Pénzügyi jelentéskészítés
description: A Pénzügyi jelentéskészítés lehetővé teszi üzleti és pénzügyi szakembereknek pénzügyi kimutatások létrehozását, karbantartását, telepítését és megtekintését.
author: aprilolson
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FinanicalReportingSetup
audience: Application User
ms.reviewer: kfend
ms.custom: 68813
ms.assetid: fe8b27e7-a40a-4689-ac6a-7f7401c387f5
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 0b1db953165bd745a00f68048767a2b19fcc2f38
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093951"
---
# <a name="financial-reporting"></a><span data-ttu-id="380a6-103">Pénzügyi jelentéskészítés</span><span class="sxs-lookup"><span data-stu-id="380a6-103">Financial reporting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="380a6-104">A Pénzügyi jelentéskészítés az alkalmazáshoz lehetővé teszi üzleti és pénzügyi szakembereknek pénzügyi kimutatások létrehozását, karbantartását, telepítését és megtekintését.</span><span class="sxs-lookup"><span data-stu-id="380a6-104">Financial reporting for the application allows financial and business professionals to create, maintain, deploy, and view financial statements.</span></span> <span data-ttu-id="380a6-105">A hagyományos jelentési korlátokon túlmenően különböző típusú jelentések hatékony tervezésében nyújt segítséget.</span><span class="sxs-lookup"><span data-stu-id="380a6-105">It moves beyond traditional reporting constraints to help you efficiently design various types of reports.</span></span>

<span data-ttu-id="380a6-106">Pénzügyi jelentéskészítés tartalmazza a dimenzió támogatást.</span><span class="sxs-lookup"><span data-stu-id="380a6-106">Financial reporting includes dimension support.</span></span> <span data-ttu-id="380a6-107">Ezért a számlaszegmensek vagy dimenziók azonnal elérhetők.</span><span class="sxs-lookup"><span data-stu-id="380a6-107">Therefore, account segments or dimensions are immediately available.</span></span> <span data-ttu-id="380a6-108">További eszközök vagy konfigurációs lépések nem szükségesek.</span><span class="sxs-lookup"><span data-stu-id="380a6-108">No additional tools or configuration steps are required.</span></span>

## <a name="financial-reporting-setup"></a><span data-ttu-id="380a6-109">Pénzügyi jelentéskészítés beállítása</span><span class="sxs-lookup"><span data-stu-id="380a6-109">Financial reporting setup</span></span>
<span data-ttu-id="380a6-110">A **Pénzügyi jelentéskészítés beállítása** lapja tartalmazza a rendszer összes pénzügyi dimenziójának listáját.</span><span class="sxs-lookup"><span data-stu-id="380a6-110">The **Financial reporting setup** page has a list of all financial dimensions in the system.</span></span> <span data-ttu-id="380a6-111">**Főkönyv** \> **Főkönyv beállításai** \> **Pénzügyi jelentéskészítés beállítása**.</span><span class="sxs-lookup"><span data-stu-id="380a6-111">**General ledger** \> **Ledger setup** \> **Financial reporting setup**.</span></span>

<span data-ttu-id="380a6-112">A **Pénzügyi jelentéskészítés beállítása** lap két részből áll, amelyek meghatározzák a pénzügyi jelentésekben jelentésre kerülő adatokat:</span><span class="sxs-lookup"><span data-stu-id="380a6-112">The **Financial reporting setup** page has two sections that determine the data you report on in Financial reporting:</span></span>

- <span data-ttu-id="380a6-113">**Dimenziók lap** – Mivel a különböző vállalatok különböző dimenziókat és számlastruktúrákat használnak, nem lehet meghatározni, hogy a felhasználók milyen sorrendben akarják megtekinteni az összes pénzügyi dimenziót a jelentéseken.</span><span class="sxs-lookup"><span data-stu-id="380a6-113">**Dimensions tab** - Because different companies use different dimensions and account structures, there is no way to determine the order in which users want to view all financial dimensions on reports.</span></span> <span data-ttu-id="380a6-114">Ezen a lapon beállítható, hogy a pénzügyi dimenziók milyen sorrendben jelenjenek meg, amikor jelentést készít vagy tekint meg a pénzügyi jelentésekben.</span><span class="sxs-lookup"><span data-stu-id="380a6-114">This page allows you set the order in which you want financial dimensions to appear when you build and view a report in Financial reporting.</span></span>
- <span data-ttu-id="380a6-115">**Attribútumok lap** – Itt választható ki, hogy **Szállítók** vagy a **Vevők** legyen használva attribútumként a szűréshez és a jelentéstervezéséhez.</span><span class="sxs-lookup"><span data-stu-id="380a6-115">**Attributes tab** is where you can select whether you want the ability to use **Vendors** and **Customers** as attributes for filtering and report design.</span></span> <span data-ttu-id="380a6-116">A jelentéskészítés szállítók és vevők szerint csak akkor hasznos, ha nem ad meg több szállítót vagy vevőt egy bizonylaton a tranzakciók feladásakor.</span><span class="sxs-lookup"><span data-stu-id="380a6-116">Reporting on Vendor and Customer will only be valuable if you do not enter multiple vendors or customers in a single voucher when posting transactions.</span></span> <span data-ttu-id="380a6-117">A Szállító és/vagy a Vevő kiválasztása növeli az integrációs időt.</span><span class="sxs-lookup"><span data-stu-id="380a6-117">Choosing Vendor and/or Customer will add additional time to the integration.</span></span>

## <a name="financial-reporting-components"></a><span data-ttu-id="380a6-118">A pénzügyi jelentés összetevői</span><span class="sxs-lookup"><span data-stu-id="380a6-118">Financial reporting components</span></span>
<span data-ttu-id="380a6-119">A pénzügyi jelentéskészítés következő elemeivel a jelentések létrehozása, megtekintése és ütemezése rendkívül egyszerűvé válik.</span><span class="sxs-lookup"><span data-stu-id="380a6-119">The following components of financial reporting make it easy to create, view, and schedule reports.</span></span>

| <span data-ttu-id="380a6-120">Összetevő</span><span class="sxs-lookup"><span data-stu-id="380a6-120">Component</span></span>        | <span data-ttu-id="380a6-121">Függvények</span><span class="sxs-lookup"><span data-stu-id="380a6-121">Functions</span></span> | <span data-ttu-id="380a6-122">További információk</span><span class="sxs-lookup"><span data-stu-id="380a6-122">Additional information</span></span> |
|------------------|-----------|------------------------|
| <span data-ttu-id="380a6-123">Jelentéstervező</span><span class="sxs-lookup"><span data-stu-id="380a6-123">Report Designer</span></span>  | <span data-ttu-id="380a6-124">A jelentések építőelemeit hozhatja létre ezzel, amelyekből később jelentést határozhat meg és hozhat létre.</span><span class="sxs-lookup"><span data-stu-id="380a6-124">Create report building blocks that can be combined to define and generate a report.</span></span> <span data-ttu-id="380a6-125">A jelentésvarázsló a kevésbé tapasztalt felhasználókat kalauzolja végig a tervezési folyamaton.</span><span class="sxs-lookup"><span data-stu-id="380a6-125">The report wizard guides less experienced users through the design process.</span></span> <span data-ttu-id="380a6-126">A haladó felhasználók létrehozhatnak új jelentés-építőelemeket vagy kedvükre módosíthatják a meglévő építőelemeket.</span><span class="sxs-lookup"><span data-stu-id="380a6-126">Advanced users can create new report building blocks or modify existing building blocks to meet their requirements.</span></span> | |
| <span data-ttu-id="380a6-127">Jelentésütemezések</span><span class="sxs-lookup"><span data-stu-id="380a6-127">Report schedules</span></span> | <span data-ttu-id="380a6-128">Ütemezzen egyetlen jelentést vagy jelentéscsoportot úgy, hogy az rendszeressé váljon.</span><span class="sxs-lookup"><span data-stu-id="380a6-128">Schedule a single report or a group of reports so that it is generated on a regular basis.</span></span> | [<span data-ttu-id="380a6-129">Pénzügyi jelentések létrehozása</span><span class="sxs-lookup"><span data-stu-id="380a6-129">Generate financial reports</span></span>](generate-financial-report.md) |

## <a name="features"></a><span data-ttu-id="380a6-130">Jellemzők</span><span class="sxs-lookup"><span data-stu-id="380a6-130">Features</span></span>
<table>
<thead>
<tr>
<th><span data-ttu-id="380a6-131">Szolgáltatás</span><span class="sxs-lookup"><span data-stu-id="380a6-131">Feature</span></span></th>
<th><span data-ttu-id="380a6-132">Leírás</span><span class="sxs-lookup"><span data-stu-id="380a6-132">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="380a6-133">Rugalmas jelentéstervezés</span><span class="sxs-lookup"><span data-stu-id="380a6-133">Report design flexibility</span></span></td>
<td><span data-ttu-id="380a6-134">A jelentéstervező jelentés tervezésekor az alábbi jelentési beállításokat nyújtja:</span><span class="sxs-lookup"><span data-stu-id="380a6-134">Report Designer provides the following reporting options when you design a report:</span></span>
<ul>
<li><span data-ttu-id="380a6-135">Dimenziókombinációk mentése, azok későbbi használata több jelentéshez.</span><span class="sxs-lookup"><span data-stu-id="380a6-135">Save dimension combinations, and reuse the dimensions for multiple reports.</span></span></li>
<li><span data-ttu-id="380a6-136">Szabályozhatja a dimenzióleírások formázását és megjelenítését.</span><span class="sxs-lookup"><span data-stu-id="380a6-136">Control how dimension descriptions are formatted and displayed.</span></span></li>
<li><span data-ttu-id="380a6-137">Azonosíthatja a számlákat és dimenziókat, amelyek kimaradtak a jelentések építőelemeiből.</span><span class="sxs-lookup"><span data-stu-id="380a6-137">Identify accounts or dimensions that have been omitted from report building blocks.</span></span></li>
<li><span data-ttu-id="380a6-138">Formázhatja a fejléceket a gördülő előrejelzésekhez.</span><span class="sxs-lookup"><span data-stu-id="380a6-138">Format headers for rolling forecasts.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="380a6-139">Pénzügyi jelentési együttműködés</span><span class="sxs-lookup"><span data-stu-id="380a6-139">Financial report collaboration</span></span></td>
<td><span data-ttu-id="380a6-140">Az alábbi funkciók segítségével szabályozhatja a jelentések létrehozását és felosztását:</span><span class="sxs-lookup"><span data-stu-id="380a6-140">The following features help you manage the generation and distribution of reports:</span></span>
<ul>
<li><span data-ttu-id="380a6-141">Jelentések ütemezése a napi, heti, havi vagy éves létrehozás beállításához.</span><span class="sxs-lookup"><span data-stu-id="380a6-141">Schedule reports so that they are automatically generated on a daily, weekly, monthly, or annual basis.</span></span></li>
<li><span data-ttu-id="380a6-142">Exportálás csak olvasható XPS formátumba, amely nagyobb dokumentumbiztonságot nyújt digitális aláírással.</span><span class="sxs-lookup"><span data-stu-id="380a6-142">Export to the read-only XPS format, which provides better document security through digital signatures.</span></span></li>
<li><span data-ttu-id="380a6-143">Exportálja egy Microsoft Excel-munkalapra.</span><span class="sxs-lookup"><span data-stu-id="380a6-143">Export to a Microsoft Excel worksheet.</span></span></li>
<li><span data-ttu-id="380a6-144">A jelentések megosztásához létrehozhat e-maileket, amelyek a jelentésre mutató hivatkozást tartalmaznak.</span><span class="sxs-lookup"><span data-stu-id="380a6-144">To share reports, you can create email messages that contain links to the reports.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="380a6-145">Jelentések interaktív megtekintése</span><span class="sxs-lookup"><span data-stu-id="380a6-145">Interactive report viewing</span></span></td>
<td><span data-ttu-id="380a6-146">Az interaktív funkciók segítségével az alábbi műveleteket végezeti el:</span><span class="sxs-lookup"><span data-stu-id="380a6-146">Interactive features let you perform the following tasks:</span></span>
<ul>
<li><span data-ttu-id="380a6-147">Módosítsa a jelentés dátumát a jelentésben, melyet éppen megtekint.</span><span class="sxs-lookup"><span data-stu-id="380a6-147">Change the report date for the report that you're viewing.</span></span></li>
<li><span data-ttu-id="380a6-148">Módosítsa a pénznemet a jelentésben, melyet éppen megtekint.</span><span class="sxs-lookup"><span data-stu-id="380a6-148">Change the currency of the report that you're viewing.</span></span></li>
<li><span data-ttu-id="380a6-149">A jelentés összefoglaló vagy részletes nézetben való megtekintése.</span><span class="sxs-lookup"><span data-stu-id="380a6-149">View the report in either a summary view or a detailed view.</span></span></li>
<li><span data-ttu-id="380a6-150">Dimenzió-szűrés hozzáadása jelentés tartalmának egy adott dimenzióra vagy a dimenziók kombinációjára való korlátozására.</span><span class="sxs-lookup"><span data-stu-id="380a6-150">Add dimension filters to limit the report content to a specific dimension or combination of dimensions.</span></span></li>
<li><span data-ttu-id="380a6-151">Attribútum-szűrés hozzáadása jelentés tartalmának egy adott attribútumra vagy a attribútumok kombinációjára való korlátozására.</span><span class="sxs-lookup"><span data-stu-id="380a6-151">Add attribute filters to limit the report content to a specific attribute or combination of attributes.</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a><span data-ttu-id="380a6-152">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="380a6-152">Additional resources</span></span>
[<span data-ttu-id="380a6-153">Pénzügyi jelentések létrehozása</span><span class="sxs-lookup"><span data-stu-id="380a6-153">Generate financial reports</span></span>](generate-financial-report.md)
