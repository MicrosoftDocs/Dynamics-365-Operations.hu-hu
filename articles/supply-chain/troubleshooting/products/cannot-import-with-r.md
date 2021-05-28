---
title: A Kiadott termékek V2 entitás használatával nem lehet cikket importálni
description: A Kiadott termékek V2 entitás használatával nem lehet cikket importálni.
author: t-benebo
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: EcoResProductDetailsExtended, DataManagementWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 8182f2f83f6a3e4cf54fe6fa64b25a2f461ff541
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026567"
---
# <a name="you-cant-import-an-item-by-using-the-released-products-v2-entity"></a><span data-ttu-id="17093-103">A Kiadott termékek V2 entitás használatával nem lehet cikket importálni</span><span class="sxs-lookup"><span data-stu-id="17093-103">You can't import an item by using the Released products V2 entity</span></span>

<span data-ttu-id="17093-104">Tudásbáziscikk száma: 4611825</span><span class="sxs-lookup"><span data-stu-id="17093-104">KB number: 4611825</span></span>

## <a name="symptoms"></a><span data-ttu-id="17093-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="17093-105">Symptoms</span></span>

<span data-ttu-id="17093-106">Amikor a *Kiadott termékek V2* entitás használatával próbál importálni egy cikket, a következő példához hasonló hibaüzenet jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="17093-106">When you try to import an item by using the *Released products V2* entity, you receive an error message that resembles the following example:</span></span>

> <span data-ttu-id="17093-107">Nem hozható létre rekord a Cikkek – nyomon követési dimenziócsoportok (EcoResTrackingDimensionGroupItem) alatt.</span><span class="sxs-lookup"><span data-stu-id="17093-107">Cannot create a record in Items - tracking dimension groups (EcoResTrackingDimensionGroupItem).</span></span> <span data-ttu-id="17093-108">Cikkszám: 2040663, Köteg.</span><span class="sxs-lookup"><span data-stu-id="17093-108">Item number: 2040663, Batch.</span></span> <span data-ttu-id="17093-109">A rekord már létezik.</span><span class="sxs-lookup"><span data-stu-id="17093-109">The record already exists.</span></span>

## <a name="resolution"></a><span data-ttu-id="17093-110">Felbontás</span><span class="sxs-lookup"><span data-stu-id="17093-110">Resolution</span></span>

<span data-ttu-id="17093-111">Új kiadott termékek importálásához a *Kiadott termék létrehozása V2* entitást kell használnia a *Kiadott termékek V2* entitás helyett.</span><span class="sxs-lookup"><span data-stu-id="17093-111">To import new released products, you must use the *Released product creation V2* entity instead of the *Released products V2* entity.</span></span>
