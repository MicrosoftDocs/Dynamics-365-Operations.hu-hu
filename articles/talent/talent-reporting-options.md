---
title: Jelentéskészítési beállítások a Talent szolgáltatásban
description: Ez a témakör ismerteti a probléma megoldását, ahol a vevő személyre akarja szabni a Microsoft Dynamics 365 for Talent jelentéseit vagy új jelentéseket akar létrehozni.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 7e00a6e4fc01f72e1ef2347e08754997135215ed
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2019
ms.locfileid: "1518198"
---
# <a name="reporting-options-in-talent"></a><span data-ttu-id="81a27-103">Jelentéskészítési lehetőségek a Talent szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="81a27-103">Reporting options in Talent</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="81a27-104">**Környezet részletes adatai**</span><span class="sxs-lookup"><span data-stu-id="81a27-104">**Environment details**</span></span>

<span data-ttu-id="81a27-105">A probléma minden környezetre vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="81a27-105">This issue applies to all environments.</span></span>

<span data-ttu-id="81a27-106">**Tünet**</span><span class="sxs-lookup"><span data-stu-id="81a27-106">**Symptom**</span></span>

<span data-ttu-id="81a27-107">A vevő személyre akarja szabni a Microsoft Dynamics 365 for Talent jelentéseit vagy új jelentéseket akar létrehozni.</span><span class="sxs-lookup"><span data-stu-id="81a27-107">The customer wants to customize Microsoft Dynamics 365 for Talent reports or create new reports.</span></span>

<span data-ttu-id="81a27-108">**Kibocsátás**</span><span class="sxs-lookup"><span data-stu-id="81a27-108">**Issue**</span></span>

<span data-ttu-id="81a27-109">A felhasználó nem tudja testreszabni a beágyazott Microsoft Power BI jelentéseket.</span><span class="sxs-lookup"><span data-stu-id="81a27-109">The user can't customize the embedded Microsoft Power BI reports.</span></span>

<span data-ttu-id="81a27-110">**Megoldás**</span><span class="sxs-lookup"><span data-stu-id="81a27-110">**Solution**</span></span>

- <span data-ttu-id="81a27-111">A Core HR szolgáltatás adatairól, amelyek a Common Data Service szolgáltatásba kerül átvitelre, jelentés készülhet a PowerApps Common Data Service csatlakozón keresztül a Power BI Desktop szolgáltatáshoz.</span><span class="sxs-lookup"><span data-stu-id="81a27-111">The Core HR data that flows to Common Data Service can be reported on via the PowerApps Common Data Service connector to Power BI Desktop.</span></span> <span data-ttu-id="81a27-112">Vegye figyelembe, hogy a Common Data Service tartalmazza a Core HR adatainak egy részhalmazást.</span><span class="sxs-lookup"><span data-stu-id="81a27-112">Note that Common Data Service contains a subset of Core HR data.</span></span> <span data-ttu-id="81a27-113">Ha további tájékoztatást szeretne a Power BI irányítópultokról, lásd: [A Power BI jelentések és irányítópultok létrehozása a PowerApps Common Data Service](https://powerapps.microsoft.com/en-us/blog/cdsconnectortopowerbi) szolgáltatással.</span><span class="sxs-lookup"><span data-stu-id="81a27-113">For more information about Power BI and dashboards, see [Create Power BI reports and dashboards with PowerApps Common Data Service](https://powerapps.microsoft.com/en-us/blog/cdsconnectortopowerbi).</span></span>
- <span data-ttu-id="81a27-114">Elektronikus jelentéskészítés (ER) a Talent egyes jelentéseihez elérhető.</span><span class="sxs-lookup"><span data-stu-id="81a27-114">Electronic reporting (ER) is available for some reports in Talent.</span></span> <span data-ttu-id="81a27-115">A vevőközpontú testreszabások az ER konfigurációs beállításainak segítségével végezhetők el.</span><span class="sxs-lookup"><span data-stu-id="81a27-115">Customer-driven customizations can be done via the ER configuration options.</span></span>
- <span data-ttu-id="81a27-116">Az adatokat exportálni lehet Microsoft Excel vagy Microsoft Word szolgáltatásba a Microsoft Office-integráción keresztül a Talent által kínált különböző adatentitások segítségével.</span><span class="sxs-lookup"><span data-stu-id="81a27-116">Data can be exported to Microsoft Excel or Microsoft Word by using the various data entities that Talent provides through the Microsoft Office integration.</span></span>

<span data-ttu-id="81a27-117">**Hosszú távú megoldás**</span><span class="sxs-lookup"><span data-stu-id="81a27-117">**Long-term solution**</span></span>

<span data-ttu-id="81a27-118">További Power BI beállítások lesznek elérhetők, és több adat és entitás lesz a Common Data Service része.</span><span class="sxs-lookup"><span data-stu-id="81a27-118">Additional Power BI options will be available, and more data and entities will be part of Common Data Service.</span></span>
