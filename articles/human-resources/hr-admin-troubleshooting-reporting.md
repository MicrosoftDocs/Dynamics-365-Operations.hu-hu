---
title: Jelentési funkciók
description: Ez a cikk ismerteti a probléma megoldását, ahol a vevő személyre kívánja szabni a Microsoft Dynamics 365 Human Resources jelentéseit vagy új jelentéseket kíván létrehozni.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 51d84df5c3c29510e2742148b8c260a2cf402639
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527717"
---
# <a name="reporting-options"></a><span data-ttu-id="3797b-103">Jelentési funkciók</span><span class="sxs-lookup"><span data-stu-id="3797b-103">Reporting options</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="3797b-104">**Környezet részletes adatai**</span><span class="sxs-lookup"><span data-stu-id="3797b-104">**Environment details**</span></span>

<span data-ttu-id="3797b-105">A probléma minden környezetre vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="3797b-105">This issue applies to all environments.</span></span>

<span data-ttu-id="3797b-106">**Tünet**</span><span class="sxs-lookup"><span data-stu-id="3797b-106">**Symptom**</span></span>

<span data-ttu-id="3797b-107">A vevő személyre akarja szabni a Microsoft Dynamics 365 Human Resources jelentéseit vagy új jelentéseket akar létrehozni.</span><span class="sxs-lookup"><span data-stu-id="3797b-107">The customer wants to customize Microsoft Dynamics 365 Human Resources reports or create new reports.</span></span>

<span data-ttu-id="3797b-108">**Kibocsátás**</span><span class="sxs-lookup"><span data-stu-id="3797b-108">**Issue**</span></span>

<span data-ttu-id="3797b-109">A felhasználó nem tudja testreszabni a beágyazott Microsoft Power BI jelentéseket.</span><span class="sxs-lookup"><span data-stu-id="3797b-109">The user can't customize the embedded Microsoft Power BI reports.</span></span>

<span data-ttu-id="3797b-110">**Megoldás**</span><span class="sxs-lookup"><span data-stu-id="3797b-110">**Solution**</span></span>

- <span data-ttu-id="3797b-111">A Human Resources szolgáltatás Common Data Service szolgáltatásba továbbított adatairól jelentés készíthető a Power Apps Common Data Service csatlakozón keresztül a Power BI Desktop szolgáltatáshoz.</span><span class="sxs-lookup"><span data-stu-id="3797b-111">The Human Resources data that flows to Common Data Service can be reported on via the Power Apps Common Data Service connector to Power BI Desktop.</span></span> <span data-ttu-id="3797b-112">Vegye figyelembe, hogy a Common Data Service a Human Resources adatainak részhalmazát tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="3797b-112">Note that Common Data Service contains a subset of Human Resources data.</span></span> <span data-ttu-id="3797b-113">Ha további tájékoztatást szeretne a Power BI szolgáltatásról és irányítópultokról, lásd: [A Power BI jelentések és irányítópultok létrehozása a Power Apps Common Data Service szolgáltatással](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).</span><span class="sxs-lookup"><span data-stu-id="3797b-113">For more information about Power BI and dashboards, see [Create Power BI reports and dashboards with Power Apps Common Data Service](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).</span></span>
- <span data-ttu-id="3797b-114">Az elektronikus jelentéskészítés (ER) a Human Resources egyes jelentéseihez érhető el.</span><span class="sxs-lookup"><span data-stu-id="3797b-114">Electronic reporting (ER) is available for some reports in Human Resources.</span></span> <span data-ttu-id="3797b-115">A vevőközpontú testreszabások az ER konfigurációs beállításainak segítségével végezhetők el.</span><span class="sxs-lookup"><span data-stu-id="3797b-115">Customer-driven customizations can be done via the ER configuration options.</span></span>
- <span data-ttu-id="3797b-116">Az adatokat exportálni lehet a Microsoft Excel vagy a Microsoft Word alkalmazásba a Microsoft Office-integráción keresztül a Human Resources által kínált különböző adatentitások segítségével.</span><span class="sxs-lookup"><span data-stu-id="3797b-116">Data can be exported to Microsoft Excel or Microsoft Word by using the various data entities that Human Resources provides through the Microsoft Office integration.</span></span>

<span data-ttu-id="3797b-117">**Hosszú távú megoldás**</span><span class="sxs-lookup"><span data-stu-id="3797b-117">**Long-term solution**</span></span>

<span data-ttu-id="3797b-118">További Power BI beállítások lesznek elérhetők, és több adat és entitás lesz a Common Data Service része.</span><span class="sxs-lookup"><span data-stu-id="3797b-118">Additional Power BI options will be available, and more data and entities will be part of Common Data Service.</span></span>
