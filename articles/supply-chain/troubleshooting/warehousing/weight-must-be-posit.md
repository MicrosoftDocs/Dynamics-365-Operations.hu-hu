---
title: A súly csak pozitív érték lehet.
description: A súly csak pozitív érték lehet.
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSContainerCloseDiag_canClose
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: dcbcde3143cb509b68b277cb7c709263e2659b5b
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924303"
---
# <a name="weight-must-be-positive"></a><span data-ttu-id="777d2-103">A súly csak pozitív érték lehet.</span><span class="sxs-lookup"><span data-stu-id="777d2-103">Weight must be positive</span></span>

<span data-ttu-id="777d2-104">Hibakód: WeightMustBePositive</span><span class="sxs-lookup"><span data-stu-id="777d2-104">Error code: WeightMustBePositive</span></span>

## <a name="symptoms"></a><span data-ttu-id="777d2-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="777d2-105">Symptoms</span></span>

<span data-ttu-id="777d2-106">A rendszer a következő hibaüzenetet jeleníti meg:</span><span class="sxs-lookup"><span data-stu-id="777d2-106">The system shows the following error message:</span></span>

> <span data-ttu-id="777d2-107">A súly csak pozitív érték lehet.</span><span class="sxs-lookup"><span data-stu-id="777d2-107">Weight must be positive.</span></span>

## <a name="cause"></a><span data-ttu-id="777d2-108">Ok</span><span class="sxs-lookup"><span data-stu-id="777d2-108">Cause</span></span>

<span data-ttu-id="777d2-109">A **Bruttó tömeg** mező értéke *0* (nulla) vagy negatív érték.</span><span class="sxs-lookup"><span data-stu-id="777d2-109">The **Gross Weight** field is set to *0* (zero) or a negative value.</span></span>

## <a name="resolution"></a><span data-ttu-id="777d2-110">Felbontás</span><span class="sxs-lookup"><span data-stu-id="777d2-110">Resolution</span></span>

<span data-ttu-id="777d2-111">Súly meghatározásához hajtsa végre az alábbi lépések valamelyikét.</span><span class="sxs-lookup"><span data-stu-id="777d2-111">To specify a weight, follow one of these steps.</span></span>

- <span data-ttu-id="777d2-112">A **Bruttó tömeg** mezőben állítsa be az értéket.</span><span class="sxs-lookup"><span data-stu-id="777d2-112">In the **Gross weight** field, set a value.</span></span> <span data-ttu-id="777d2-113">Válasszon egy egységet a legördülő listából.</span><span class="sxs-lookup"><span data-stu-id="777d2-113">Then select a unit in the drop-down list.</span></span>
- <span data-ttu-id="777d2-114">Válassza a **rendszertömeg beolvasása** lehetőséget a **Bruttó tömeg** értékének kiszámításához.</span><span class="sxs-lookup"><span data-stu-id="777d2-114">Select **Get system weight** to calculate the **Gross weight** value.</span></span>
