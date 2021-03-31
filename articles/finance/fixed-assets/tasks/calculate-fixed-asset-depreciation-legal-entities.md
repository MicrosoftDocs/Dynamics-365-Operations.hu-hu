---
title: Tárgyi eszköz értékcsökkenésének kiszámítása jogi személyek között
description: Tárgyi eszköz értékcsökkenése egyetlen lépésben futtatható jogi személyek között.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetParameters, AssetProposalDepreciation, DefaultDashboard, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8d228c387e8a6bf956f729a69e2296130db32dbd
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5210047"
---
# <a name="calculate-fixed-asset-depreciation-across-legal-entities"></a><span data-ttu-id="d1e89-103">Tárgyi eszköz értékcsökkenésének kiszámítása jogi személyek között</span><span class="sxs-lookup"><span data-stu-id="d1e89-103">Calculate fixed asset depreciation across legal entities</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d1e89-104">Tárgyi eszköz értékcsökkenése egyetlen lépésben futtatható jogi személyek között.</span><span class="sxs-lookup"><span data-stu-id="d1e89-104">Fixed asset depreciation can be run across legal entities in a single step.</span></span> <span data-ttu-id="d1e89-105">Ez a témakör bemutatja, hogy hogyan állíthatja be és futtathatja több jogi személynél a folyamatot.</span><span class="sxs-lookup"><span data-stu-id="d1e89-105">This procedure shows you to how set up and run the process for multiple legal entities.</span></span> <span data-ttu-id="d1e89-106">Ez a könyvelői szerepkört és a bemutató adatokat használja a USMF jogi személyhez.</span><span class="sxs-lookup"><span data-stu-id="d1e89-106">It uses the accountant role and demo data for the USMF legal entity.</span></span>


## <a name="set-up-cross-company-depreciation-run-journals"></a><span data-ttu-id="d1e89-107">Vállalatközi vállalati értékcsökkenés-futtatási naplók beállítása</span><span class="sxs-lookup"><span data-stu-id="d1e89-107">Set up cross company depreciation run journals</span></span>
1. <span data-ttu-id="d1e89-108">Ugorjon a Tárgyi eszközök > Beállítás > Tárgyi eszköz paraméterek pontra.</span><span class="sxs-lookup"><span data-stu-id="d1e89-108">Go to Fixed assets > Setup > Fixed assets parameters.</span></span>
2. <span data-ttu-id="d1e89-109">Bontsa ki a tárgyieszköz-javaslatok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="d1e89-109">Expand the Fixed asset proposals section.</span></span>
3. <span data-ttu-id="d1e89-110">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="d1e89-110">Click Add.</span></span>
4. <span data-ttu-id="d1e89-111">A Feladási réget mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d1e89-111">In the Posting layer field, enter or select a value.</span></span>
5. <span data-ttu-id="d1e89-112">A Napló neve mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d1e89-112">In the Journal name field, enter or select a value.</span></span>
    * <span data-ttu-id="d1e89-113">Ismételje meg a napló beállítását a tárgyi eszköz paraméterei lapon az egyes jogi személyekhez.</span><span class="sxs-lookup"><span data-stu-id="d1e89-113">Repeat the journal setup on the Fixed asset parameters page in each legal entity.</span></span>  

## <a name="depreciation-run"></a><span data-ttu-id="d1e89-114">Értékcsökkenés futtatása</span><span class="sxs-lookup"><span data-stu-id="d1e89-114">Depreciation run</span></span>
1. <span data-ttu-id="d1e89-115">Ugorjon a Tárgyi eszközök > Naplóbejegyzések > Értékcsökkenési javaslat létrehozása pontra.</span><span class="sxs-lookup"><span data-stu-id="d1e89-115">Go to Fixed assets > Journal entries > Create depreciation proposal.</span></span>
2. <span data-ttu-id="d1e89-116">A Feladási réget mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d1e89-116">In the Posting layer field, enter or select a value.</span></span>
    * <span data-ttu-id="d1e89-117">A napló neve alapértelmezésben a tárgyi eszköz paramétereiből jön.</span><span class="sxs-lookup"><span data-stu-id="d1e89-117">The journal name will default from the Fixed asset parameters.</span></span> <span data-ttu-id="d1e89-118">Itt módosítható az aktuális jogi személyhez.</span><span class="sxs-lookup"><span data-stu-id="d1e89-118">It can be changed here for the current legal entity.</span></span>  
3. <span data-ttu-id="d1e89-119">Adja meg a dátumot a „Záró dátum” mezőben.</span><span class="sxs-lookup"><span data-stu-id="d1e89-119">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="d1e89-120">Válassza ki az értékcsökkenés futtatásába felvenni kívánt jogi személyeket.</span><span class="sxs-lookup"><span data-stu-id="d1e89-120">Select the legal entities to be included in the depreciation run.</span></span>  
    * <span data-ttu-id="d1e89-121">A listában csak a tárgyieszköz-javaslatokhoz a tárgyi eszköz paraméterei lapon beállított naplókkal rendelkező jogi személyek fognak megjelenni.</span><span class="sxs-lookup"><span data-stu-id="d1e89-121">Only legal entities with journals set up for Fixed asset proposals on the Fixed asset parameters page will be shown in the list.</span></span>  
4. <span data-ttu-id="d1e89-122">Válassza ki az Igen lehetőséget a Naplók feladása mezőben.</span><span class="sxs-lookup"><span data-stu-id="d1e89-122">Select Yes in the Post journals field.</span></span>
    * <span data-ttu-id="d1e89-123">A szűrőmezőkbe beletartozik az összes tárgyi eszköz, a csoportok és a könyvek az értékcsökkenési futtatáshoz kiválasztott a jogi személyekhez.</span><span class="sxs-lookup"><span data-stu-id="d1e89-123">Filtering fields include all fixed assets, groups, and books for the legal entities selected for this depreciation run.</span></span>  
    * <span data-ttu-id="d1e89-124">A kötegelt feldolgozási beállítás alapértelmezés szerint engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="d1e89-124">The Batch processing option is enabled by default.</span></span> <span data-ttu-id="d1e89-125">Ha ez a beállítás engedélyezve van, az értékcsökkenési napló létrehozása és feladása a háttérben fog futni.</span><span class="sxs-lookup"><span data-stu-id="d1e89-125">When this option is enabled, the depreciation journal creation and posting will run in the background.</span></span>  
5. <span data-ttu-id="d1e89-126">Kattintson a Napló létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d1e89-126">Click Create journal.</span></span>
6. <span data-ttu-id="d1e89-127">Ugorjon a Tárgyi eszközök > Naplóbejegyzések > Tárgyi eszközök naplója pontra.</span><span class="sxs-lookup"><span data-stu-id="d1e89-127">Go to Fixed assets > Journal entries > Fixed assets journal.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]