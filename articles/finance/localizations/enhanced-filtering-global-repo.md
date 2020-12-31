---
title: RCS továbbfejlesztett szűrés a RCS/globális tárházban
description: Ez a témakör a RCS globális tárház továbbfejlesztett szűrési képességeit írja le, amelyek a további szűrőket is kaptak.
author: JaneA07
manager: AnnBe
ms.date: 04/24/2020
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
ms.openlocfilehash: 1913b661c46af5e34da1a2939cb2a5d5b4e46411
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443853"
---
# <a name="rcs-enhanced-filtering-options-for-finding-configurations-in-the-rcsglobal-repository"></a><span data-ttu-id="a8acc-103">RCS által továbbfejlesztési szűrési lehetőségek a konfigurációk az RCS-ben/globális tárházban való keresése esetén</span><span class="sxs-lookup"><span data-stu-id="a8acc-103">RCS enhanced filtering options for finding configurations in the RCS/Global repository</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a8acc-104">Ez a témakör a Regulatory Configuration Service (RCS) globális tárház továbbfejlesztett szűrési képességeit írja le, amelyek a következő feltételek alapján történő szűrőkkel lettek továbbfejlesztve:</span><span class="sxs-lookup"><span data-stu-id="a8acc-104">This topic describes enhanced filtering capabilities for Regulatory Configuration Services (RCS) Global repository, which have been improved to include the ability to filter with the following criteria:</span></span> 
- <span data-ttu-id="a8acc-105">**Ország/terület** – ISO-országkódok alapján</span><span class="sxs-lookup"><span data-stu-id="a8acc-105">**Country/region** - Based on ISO country codes</span></span>  
- <span data-ttu-id="a8acc-106">**Címkék** típusai a következőkhöz:</span><span class="sxs-lookup"><span data-stu-id="a8acc-106">**Tags** types for:</span></span>
  - <span data-ttu-id="a8acc-107">Működési terület</span><span class="sxs-lookup"><span data-stu-id="a8acc-107">Functional area</span></span>
  - <span data-ttu-id="a8acc-108">Szolgáltatásterület</span><span class="sxs-lookup"><span data-stu-id="a8acc-108">Feature area</span></span>
  - <span data-ttu-id="a8acc-109">Ágazat</span><span class="sxs-lookup"><span data-stu-id="a8acc-109">Industry</span></span> 
  - <span data-ttu-id="a8acc-110">Üzleti dokumentum</span><span class="sxs-lookup"><span data-stu-id="a8acc-110">Business document</span></span> 

<span data-ttu-id="a8acc-111">Szűrőket egyenként vagy csoportosan is alkalmazhatja az adott vagy kapcsolódó konfigurációk könnyebb megtalálására.</span><span class="sxs-lookup"><span data-stu-id="a8acc-111">To make it easier to discover specific or related configurations you can apply filters, either individually or as a group.</span></span> <span data-ttu-id="a8acc-112">Ha például a szállítói számlákhoz kapcsolódó konfigurálható üzleti dokumentumok egyetlen típusát szeretné megkeresni, akkor a dokumentumtípus megkereséséhez alkalmazhatja az **Üzleti dokumentum típusa** szűrőt.</span><span class="sxs-lookup"><span data-stu-id="a8acc-112">For example, to find a single type of 'configurable business documents that are related to vendor invoices, you could apply a **Business document type** filter to search for that type of document.</span></span> 

<span data-ttu-id="a8acc-113">[![Szűrő szakasz a globális tárházhoz](media/rcs-enhanced-filter-section.JPG)](./media/rcs-enhanced-filter-section.JPG)</span><span class="sxs-lookup"><span data-stu-id="a8acc-113">[![Filter section for Global repository](media/rcs-enhanced-filter-section.JPG)](./media/rcs-enhanced-filter-section.JPG)</span></span> 

<span data-ttu-id="a8acc-114">A keresés tovább finomítható a dokumentumtípus kiválasztásával, például "szállítói számla", mjad a **szűrő alkalmazása** parancsra kattintva.</span><span class="sxs-lookup"><span data-stu-id="a8acc-114">You can further refine the search by selecting document type, for example 'vendor invoice' and clicking **Apply filter**.</span></span> <span data-ttu-id="a8acc-115">A következő példa azt jeleníti meg, hogy milyen eredmények szerepelnek az **Üzleti dokumentum típusa** elemre szűrés során, ha a dokumentumtípust is hozzáadja.</span><span class="sxs-lookup"><span data-stu-id="a8acc-115">The following example shows the results when filtering on **Business document type** with the document type added.</span></span> 

<span data-ttu-id="a8acc-116">[![Alkalmazott szűrő és Importálás az üzleti dokumentum típushoz](media/rcs-enhanced-filtering-applied.JPG)](./media/rcs-enhanced-filtering-applied.JPG)</span><span class="sxs-lookup"><span data-stu-id="a8acc-116">[![Applied filter and Import for business document type](media/rcs-enhanced-filtering-applied.JPG)](./media/rcs-enhanced-filtering-applied.JPG)</span></span> 

<span data-ttu-id="a8acc-117">A szűrt eredmények importálhatók egy felhasználó RCS-adattárába vagy egy Dynamics 365 Finance-környezetbe, egyesével vagy csoportban is.</span><span class="sxs-lookup"><span data-stu-id="a8acc-117">Filtered results can be imported into a users RCS repository or a Dynamics 365 Finance environment, either individually or as a set.</span></span> <span data-ttu-id="a8acc-118">Ehhez válassza ki a konfigurációk csoportját, majd kattintson az **importálás** gombra.</span><span class="sxs-lookup"><span data-stu-id="a8acc-118">To do this, select the group of configurations, and click **Import**.</span></span>
