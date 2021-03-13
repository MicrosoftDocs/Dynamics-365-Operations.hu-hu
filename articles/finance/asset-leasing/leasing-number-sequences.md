---
title: Számsorozatok hozzárendelése
description: Ez a témakör bemutatja, hogyan hozhat létre számsorozatokat a lízingazonosítókhoz. Azt is bemutatja, hogyan hozhat létre egyedi azonosítókat, amelyeket az index átértékelési folyamatában használnak.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: c21b7a55ff611a5d3ab745f3af5e2e855240531b
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/06/2021
ms.locfileid: "5128955"
---
# <a name="assign-number-sequences"></a><span data-ttu-id="b563c-104">Számsorozatok hozzárendelése</span><span class="sxs-lookup"><span data-stu-id="b563c-104">Assign number sequences</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b563c-105">Ez a témakör bemutatja, hogyan hozhat létre számsorozatokat a lízingazonosítókhoz.</span><span class="sxs-lookup"><span data-stu-id="b563c-105">This topic explains how to create number sequences for lease IDs.</span></span> <span data-ttu-id="b563c-106">Azt is bemutatja, hogyan hozhat létre egyedi azonosítókat, amelyeket az index átértékelési folyamatában használnak.</span><span class="sxs-lookup"><span data-stu-id="b563c-106">It also explains how to create unique IDs that are used in the index revaluation process.</span></span>

1. <span data-ttu-id="b563c-107">Nyissa meg az **Eszközlízing \> Beállítás \> Eszközlízing paraméterei** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b563c-107">Go to **Asset leasing \> Setup \> Asset leasing parameters**.</span></span>
2. <span data-ttu-id="b563c-108">Válassza a **Számsorozatok** oldalsó fület.</span><span class="sxs-lookup"><span data-stu-id="b563c-108">Select the **Number sequences** side tab.</span></span>
3. <span data-ttu-id="b563c-109">Válassza a **Számsorozatok** lehetőséget az oldalsó sávban.</span><span class="sxs-lookup"><span data-stu-id="b563c-109">Select **Number sequences** in the side bar.</span></span>
4. <span data-ttu-id="b563c-110">Válassza ki a **Lízingazonosító** referencia számsorozatát.</span><span class="sxs-lookup"><span data-stu-id="b563c-110">Select the number sequence for the **Lease ID** reference.</span></span> <span data-ttu-id="b563c-111">Ez a számsorozat fogja használni az egyes lízingek egyedi azonosítójának létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="b563c-111">This number sequence will be used to generate the unique identifier for each lease.</span></span>
5. <span data-ttu-id="b563c-112">Válassza ki a **Folyamatazonosító** referencia számsorozatát.</span><span class="sxs-lookup"><span data-stu-id="b563c-112">Select the number sequence for the **Process ID** reference.</span></span> <span data-ttu-id="b563c-113">Ez a számsorozat fogja használni az egyes indexek átértékelsi folyamat egyedi azonosítójának létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="b563c-113">This number sequence will be used to generate the unique identifier for each index revaluation process.</span></span>
6. <span data-ttu-id="b563c-114">Válassza ki a **Megszüntetési javaslat azonosítója** referencia számsorozatát.</span><span class="sxs-lookup"><span data-stu-id="b563c-114">Select the number sequence for the **Termination Proposal ID** reference.</span></span> <span data-ttu-id="b563c-115">Ez a számsorozat fogja használni az egyes megszüntetési javaslatok egyedi azonosítójának létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="b563c-115">This number sequence will be used to generate the unique identifier for each termination proposal.</span></span>
