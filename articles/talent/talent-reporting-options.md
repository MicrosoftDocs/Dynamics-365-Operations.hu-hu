---
title: "Jelentéskészítési beállítások a Talent szolgáltatásban"
description: "Ez a témakör ismerteti a probléma megoldását, ahol a vevő személyre akarja szabni a Microsoft Dynamics 365 for Talent jelentéseit vagy új jelentéseket akar létrehozni."
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: d3f974f94b6c327fd70b8098d24f9e1f1e1e8eeb
ms.openlocfilehash: 2007e6adec7255b0b3abda7490c2103a8583393f
ms.contentlocale: hu-hu
ms.lasthandoff: 12/04/2018

---

# <a name="reporting-options-in-talent"></a><span data-ttu-id="69e73-103">Jelentéskészítési beállítások a Talent szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="69e73-103">Reporting options in Talent</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="69e73-104">**Környezet részletes adatai**</span><span class="sxs-lookup"><span data-stu-id="69e73-104">**Environment details**</span></span>

<span data-ttu-id="69e73-105">A probléma minden környezetre vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="69e73-105">This issue applies to all environments.</span></span>

<span data-ttu-id="69e73-106">**Tünet**</span><span class="sxs-lookup"><span data-stu-id="69e73-106">**Symptom**</span></span>

<span data-ttu-id="69e73-107">A vevő személyre akarja szabni a Microsoft Dynamics 365 for Talent jelentéseit vagy új jelentéseket akar létrehozni.</span><span class="sxs-lookup"><span data-stu-id="69e73-107">The customer wants to customize Microsoft Dynamics 365 for Talent reports or create new reports.</span></span>

<span data-ttu-id="69e73-108">**Probléma**</span><span class="sxs-lookup"><span data-stu-id="69e73-108">**Issue**</span></span>

<span data-ttu-id="69e73-109">A felhasználó nem tudja testreszabni a beágyazott Microsoft Power BI jelentéseket.</span><span class="sxs-lookup"><span data-stu-id="69e73-109">The user can't customize the embedded Microsoft Power BI reports.</span></span>

<span data-ttu-id="69e73-110">**Megoldás**</span><span class="sxs-lookup"><span data-stu-id="69e73-110">**Solution**</span></span>

- <span data-ttu-id="69e73-111">A Core HR szolgáltatás adatairól, amelyek a Common Data Service for Apps szolgáltatásba kerül átvitelre, jelentés készülhet a PowerApps CDS csatlakozón keresztül a Power BI Desktop szolgáltatáshoz.</span><span class="sxs-lookup"><span data-stu-id="69e73-111">The Core HR data that flows to Common Data Service for Apps can be reported on via the PowerApps CDS connector to Power BI Desktop.</span></span> <span data-ttu-id="69e73-112">Vegye figyelembe, hogy a Common Data Service for Apps tartalmazza a Core HR adatainak egy részhalmazást.</span><span class="sxs-lookup"><span data-stu-id="69e73-112">Note that Common Data Service for Apps contains a subset of Core HR data.</span></span> <span data-ttu-id="69e73-113">A Power BI szolgáltatással és az irányítópultokkal kapcsolatos további információkért lásd: [Power BI-jelentések és irányítópultok létrehozása PowerApps Common Data Service használatával](https://powerapps.microsoft.com/en-us/blog/cdsconnectortopowerbi).</span><span class="sxs-lookup"><span data-stu-id="69e73-113">For more information about Power BI and dashboards, see [Create Power BI reports and dashboards with PowerApps Common Data Service](https://powerapps.microsoft.com/en-us/blog/cdsconnectortopowerbi).</span></span>
- <span data-ttu-id="69e73-114">Elektronikus jelentéskészítés (ER) a Talent egyes jelentéseihez elérhető.</span><span class="sxs-lookup"><span data-stu-id="69e73-114">Electronic reporting (ER) is available for some reports in Talent.</span></span> <span data-ttu-id="69e73-115">A vevőközpontú testreszabások az ER konfigurációs beállításainak segítségével végezhetők el.</span><span class="sxs-lookup"><span data-stu-id="69e73-115">Customer-driven customizations can be done via the ER configuration options.</span></span>
- <span data-ttu-id="69e73-116">Az adatokat exportálni lehet Microsoft Excel vagy Microsoft Word szolgáltatásba a Microsoft Office-integráción keresztül a Talent által kínált különböző adatentitások segítségével.</span><span class="sxs-lookup"><span data-stu-id="69e73-116">Data can be exported to Microsoft Excel or Microsoft Word by using the various data entities that Talent provides through the Microsoft Office integration.</span></span>

<span data-ttu-id="69e73-117">**Hosszú távú megoldás**</span><span class="sxs-lookup"><span data-stu-id="69e73-117">**Long-term solution**</span></span>

<span data-ttu-id="69e73-118">További Power BI-beállítások lesznek elérhetők, és több adat és entitás lesz a Common Data Service for Apps része.</span><span class="sxs-lookup"><span data-stu-id="69e73-118">Additional Power BI options will be available, and more data and entities will be part of Common Data Service for Apps.</span></span>

