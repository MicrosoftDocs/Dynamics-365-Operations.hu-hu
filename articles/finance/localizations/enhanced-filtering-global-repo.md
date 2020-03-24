---
title: Továbbfejlesztett szűrés a RCS/globális tárházban
description: Ez a témakör a RCS globális tárház továbbfejlesztett szűrési képességeit írja le, amelyek a további szűrőket is kaptak.
author: JaneA07
manager: AnnBe
ms.date: 03/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: ed5a217b8844bfc76d53370ab4c4c339f5bece36
ms.sourcegitcommit: 0dcdfedec7125562f6b33deb009a3e044a1243eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/04/2020
ms.locfileid: "3099867"
---
# <a name="enhanced-filtering-options-for-finding-configurations-in-the-global-repository"></a><span data-ttu-id="80414-103">A globális tárházban a konfigurációk megkeresésére szolgáló továbbfejlesztett szűrési lehetőségek</span><span class="sxs-lookup"><span data-stu-id="80414-103">Enhanced filtering options for finding configurations in the Global repository</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="80414-104">Ez a témakör a Regulatory Configuration Service (RCS) globális tárház továbbfejlesztett szűrési képességeit írja le, amelyek a következő szűrőkkel lettek továbbfejlesztve:</span><span class="sxs-lookup"><span data-stu-id="80414-104">This topic describes enhanced filtering capabilities for Regulatory Configuration Services (RCS) Global repository, which have been improved to include the following filters:</span></span> 
- <span data-ttu-id="80414-105">**Ország/terület** – ISO-országkódok alapján</span><span class="sxs-lookup"><span data-stu-id="80414-105">**Country/region** - based on ISO country codes</span></span>  
- <span data-ttu-id="80414-106">**Címkék** -a funkcionális/jellemző területen; Ipar; Üzleti dokumentum típusa</span><span class="sxs-lookup"><span data-stu-id="80414-106">**Tags** - for functional/feature area; Industry; Business document type</span></span> 

<span data-ttu-id="80414-107">Szűrőket egyenként vagy csoportosan is alkalmazhatja a adott vagy kapcsolódó konfigurációk megtalálására.</span><span class="sxs-lookup"><span data-stu-id="80414-107">You can apply filters, either individually or in groups, to find specific or related configurations.</span></span> <span data-ttu-id="80414-108">Például a szállítói számlákhoz kapcsolódó összes konfigurálható üzleti dokumentum megkereséséhez alkalmazhatja az **Üzleti dokumentum típusa** szűrőt.</span><span class="sxs-lookup"><span data-stu-id="80414-108">For example, to find all configurable business documents related to vendor invoices, you can apply the **Business document type** filter.</span></span> 

<span data-ttu-id="80414-109">A keresést tovább finomíthatja, ha kiválasztja az országkódot, majd a **Szűrő alkalmazása** elemre kattint.</span><span class="sxs-lookup"><span data-stu-id="80414-109">You can further refine a search by selecting the country code and clicking **Apply filter**.</span></span>  

<span data-ttu-id="80414-110">[![Szűrő szakasz a globális tárházhoz](media/rcs-enhanced-filter-section.JPG)](./media/rcs-enhanced-filter-section.JPG)</span><span class="sxs-lookup"><span data-stu-id="80414-110">[![Filter section for Global repository](media/rcs-enhanced-filter-section.JPG)](./media/rcs-enhanced-filter-section.JPG)</span></span> 

<span data-ttu-id="80414-111">A következő példa azt jeleníti meg , hogy milyen eredmények szerepelnek az **Üzleti dokumentum típusa** elemre szűrés során.</span><span class="sxs-lookup"><span data-stu-id="80414-111">The following example shows the results when filtering on **Business document type**.</span></span> 

<span data-ttu-id="80414-112">[![Alkalmazott szűrő és Importálás az üzleti dokumentum típushoz](media/rcs-enhanced-filtering-applied.JPG)](./media/rcs-enhanced-filtering-applied.JPG)</span><span class="sxs-lookup"><span data-stu-id="80414-112">[![Applied filter and Import for business document type](media/rcs-enhanced-filtering-applied.JPG)](./media/rcs-enhanced-filtering-applied.JPG)</span></span> 

<span data-ttu-id="80414-113">A szűrt eredmények a importálhatók az RCS vagy Dynamics 365 Finance környezetbe, akár egyenként, akár egy készletként (a konfigurációk csoportjának kiválasztásával), majd az **Importálás** elemre kattintással.</span><span class="sxs-lookup"><span data-stu-id="80414-113">Filtered results can be imported into users RCS or Dynamics 365 Finance environment, either individually or as a set (by selecting the group of configurations) and clicking **Import**.</span></span>






