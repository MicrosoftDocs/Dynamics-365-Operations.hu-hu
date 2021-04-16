---
title: Számsorozatok hozzárendelése
description: Ez a témakör bemutatja, hogyan hozhat létre számsorozatokat a lízingazonosítókhoz. Azt is bemutatja, hogyan hozhat létre egyedi azonosítókat, amelyeket az index átértékelési folyamatában használnak.
author: moaamer
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: a0b5d622df1e5dcdf7f1322328bce7e185f8edb8
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5819818"
---
# <a name="assign-number-sequences"></a><span data-ttu-id="76ecb-104">Számsorozatok hozzárendelése</span><span class="sxs-lookup"><span data-stu-id="76ecb-104">Assign number sequences</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="76ecb-105">Ez a témakör bemutatja, hogyan hozhat létre számsorozatokat a lízingazonosítókhoz.</span><span class="sxs-lookup"><span data-stu-id="76ecb-105">This topic explains how to create number sequences for lease IDs.</span></span> <span data-ttu-id="76ecb-106">Azt is bemutatja, hogyan hozhat létre egyedi azonosítókat, amelyeket az index átértékelési folyamatában használnak.</span><span class="sxs-lookup"><span data-stu-id="76ecb-106">It also explains how to create unique IDs that are used in the index revaluation process.</span></span>

1. <span data-ttu-id="76ecb-107">Nyissa meg az **Eszközlízing \> Beállítás \> Eszközlízing paraméterei** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="76ecb-107">Go to **Asset leasing \> Setup \> Asset leasing parameters**.</span></span>
2. <span data-ttu-id="76ecb-108">Válassza a **Számsorozatok** oldalsó fület.</span><span class="sxs-lookup"><span data-stu-id="76ecb-108">Select the **Number sequences** side tab.</span></span>
3. <span data-ttu-id="76ecb-109">Válassza a **Számsorozatok** lehetőséget az oldalsó sávban.</span><span class="sxs-lookup"><span data-stu-id="76ecb-109">Select **Number sequences** in the side bar.</span></span>
4. <span data-ttu-id="76ecb-110">Válassza ki a **Lízingazonosító** referencia számsorozatát.</span><span class="sxs-lookup"><span data-stu-id="76ecb-110">Select the number sequence for the **Lease ID** reference.</span></span> <span data-ttu-id="76ecb-111">Ez a számsorozat fogja használni az egyes lízingek egyedi azonosítójának létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="76ecb-111">This number sequence will be used to generate the unique identifier for each lease.</span></span>
5. <span data-ttu-id="76ecb-112">Válassza ki a **Folyamatazonosító** referencia számsorozatát.</span><span class="sxs-lookup"><span data-stu-id="76ecb-112">Select the number sequence for the **Process ID** reference.</span></span> <span data-ttu-id="76ecb-113">Ez a számsorozat fogja használni az egyes indexek átértékelsi folyamat egyedi azonosítójának létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="76ecb-113">This number sequence will be used to generate the unique identifier for each index revaluation process.</span></span>
6. <span data-ttu-id="76ecb-114">Válassza ki a **Megszüntetési javaslat azonosítója** referencia számsorozatát.</span><span class="sxs-lookup"><span data-stu-id="76ecb-114">Select the number sequence for the **Termination Proposal ID** reference.</span></span> <span data-ttu-id="76ecb-115">Ez a számsorozat fogja használni az egyes megszüntetési javaslatok egyedi azonosítójának létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="76ecb-115">This number sequence will be used to generate the unique identifier for each termination proposal.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]