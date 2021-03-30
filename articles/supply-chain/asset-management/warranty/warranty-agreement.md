---
title: Garanciaszerződések
description: Ez a témakör az Eszközkezelés modulban található garanciaszerződéseket ismerteti.
author: josaw1
manager: tfehr
ms.date: 08/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 35b5c89751d17687bd7e306094a1e4e5e144a8dc
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5245347"
---
# <a name="warranty-agreements"></a><span data-ttu-id="1416a-103">Garanciaszerződések</span><span class="sxs-lookup"><span data-stu-id="1416a-103">Warranty agreements</span></span>

[!include [banner](../../includes/banner.md)]

 


<span data-ttu-id="1416a-104">Az Eszközkezelés modulban beállíthat garanciafeltételeket, amelyeket egy eszközhöz vagy eszköztípushoz kapcsolhat.</span><span class="sxs-lookup"><span data-stu-id="1416a-104">In Asset Management, you can set up warranty terms that can be connected to an asset or an asset type.</span></span> <span data-ttu-id="1416a-105">A garanciafeltételeket meghatározott időpontra hozzák létre.</span><span class="sxs-lookup"><span data-stu-id="1416a-105">Warranty terms are created for a specific period.</span></span> <span data-ttu-id="1416a-106">A garanciát beállíthatja teljes fedezet vagy részleges fedezet biztosítására, és beállíthatja a feltételeket órákhoz, költségekhez és cikkekhez kapcsolódóan.</span><span class="sxs-lookup"><span data-stu-id="1416a-106">Warranty can be set up to provide full coverage or partial coverage, and you can set up terms that are related to hours, expenses, and items.</span></span>

<span data-ttu-id="1416a-107">Első lépésként hozzon létre egy bármilyen szállítói garanciaszerződést, amely a berendezésére vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="1416a-107">The first step is to create any vendor warranty agreements that you have for your equipment.</span></span> <span data-ttu-id="1416a-108">Majd csatoljon garanciaszerződéseket eszközökhöz vagy eszköztípusokhoz.</span><span class="sxs-lookup"><span data-stu-id="1416a-108">You then attach warranty agreements to assets or asset types.</span></span> <span data-ttu-id="1416a-109">A szállítói garanciaszerződések csak tájékoztatási célokat szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="1416a-109">Vendor warranty agreements are used only for informational purposes.</span></span> <span data-ttu-id="1416a-110">Ha egy eszközön be van állítva szállítói garancia, akkor az eszközön látható a garancia fedezeti időszaka.</span><span class="sxs-lookup"><span data-stu-id="1416a-110">If vendor warranty is set up on an asset, you can see the warranty coverage period on the asset.</span></span>

## <a name="create-a-warranty-agreement"></a><span data-ttu-id="1416a-111">Garanciaszerződés létrehozása</span><span class="sxs-lookup"><span data-stu-id="1416a-111">Create a warranty agreement</span></span>

<span data-ttu-id="1416a-112">A garanciaszerződések több szerződéssort is tartalmazhatnak a munkaórák, költségek és cikkek garanciájának fedezésére.</span><span class="sxs-lookup"><span data-stu-id="1416a-112">A warranty agreement can include several agreement lines to cover the warranty for work hours, expenses, and items.</span></span>

1. <span data-ttu-id="1416a-113">Válassza ki az **Eszközkezelés** \> **Beállítás** \> **Eszközök** \> **Garancia** elemet.</span><span class="sxs-lookup"><span data-stu-id="1416a-113">Select **Asset management** \> **Setup** \> **Assets** \> **Warranty**.</span></span>
2. <span data-ttu-id="1416a-114">Válassza az **Új** lehetőséget egy termék létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="1416a-114">Select **New** to create a product.</span></span>
3. <span data-ttu-id="1416a-115">A **Garancia** mezőben adjon meg egy garanciaazonosítót.</span><span class="sxs-lookup"><span data-stu-id="1416a-115">In the **Warranty** field, enter a warranty ID.</span></span> 
4. <span data-ttu-id="1416a-116">A **Név** mezőbe adja meg a leírást.</span><span class="sxs-lookup"><span data-stu-id="1416a-116">In the **Name** field, enter a description.</span></span>

    <span data-ttu-id="1416a-117">A **Garancia** gyorslapon az **Eszközök** mezőben látható azon aktív eszközök száma, amelyek a garanciaszerződést használják.</span><span class="sxs-lookup"><span data-stu-id="1416a-117">On the **Details** FastTab, the **Assets** field shows the number of active assets that use the warranty agreement.</span></span>

5. <span data-ttu-id="1416a-118">A **Garanciasorok** gyorslapon hajtsa végre az alábbi lépéseket a garanciamegállapodásba foglalandó sorok hozzáadásához:</span><span class="sxs-lookup"><span data-stu-id="1416a-118">On the **Warranty lines** FastTab, follow these steps to add lines that should be included in a warranty agreement:</span></span>

    1. <span data-ttu-id="1416a-119">Ha új feltételt szeretne a garanciához hozzáadni, válassza a **Sor hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="1416a-119">Select **Add line** to add a new condition to the warranty.</span></span> <span data-ttu-id="1416a-120">A **Sor** mezőben a sorrendben következő sorszám automatikusan bekerül.</span><span class="sxs-lookup"><span data-stu-id="1416a-120">A sequential line number is automatically entered in the **Line** field.</span></span>
    2. <span data-ttu-id="1416a-121">Az **Időszak** mezőben válassza ki az garancia-időszak típusát.</span><span class="sxs-lookup"><span data-stu-id="1416a-121">In the **Period** field, select the type of warranty period.</span></span>
    3. <span data-ttu-id="1416a-122">Az **Intervallum** mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="1416a-122">In the **Interval** field, enter a number.</span></span> <span data-ttu-id="1416a-123">Ez a mező határozza meg, hogy hány időszakra érvényes a garancia.</span><span class="sxs-lookup"><span data-stu-id="1416a-123">This field defines the number of periods that the warranty should be valid for.</span></span>
    4. <span data-ttu-id="1416a-124">A **Százalék** mezőbe írja be a garanciasor fedezeti százalékát.</span><span class="sxs-lookup"><span data-stu-id="1416a-124">In the **Percent** field, enter the coverage percentage for the warranty line.</span></span> <span data-ttu-id="1416a-125">A százalékos érték azt jelzi, hogy a vállalat mekkora részt fedez.</span><span class="sxs-lookup"><span data-stu-id="1416a-125">The percentage indicates how much is covered by your company.</span></span>

![Garancia lap](media/01-warranty.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]