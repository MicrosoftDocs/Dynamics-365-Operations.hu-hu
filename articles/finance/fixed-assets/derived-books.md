---
title: Származtatott könyvek
description: Ez a cikk a származtatott könyv funkcióról nyújt áttekintést.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetBookTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 3401
ms.assetid: 862d6450-187b-497f-9822-cce45f2c65a9
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4a649fdbc355b3382bc6c80be03f8b37a06d5226
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2178080"
---
# <a name="derived-books"></a><span data-ttu-id="baa44-103">Származtatott könyvek</span><span class="sxs-lookup"><span data-stu-id="baa44-103">Derived books</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="baa44-104">Ez a cikk a származtatott könyv funkcióról nyújt áttekintést.</span><span class="sxs-lookup"><span data-stu-id="baa44-104">This article provides an overview of derived book functionality.</span></span>

<span data-ttu-id="baa44-105">A származtatott könyvek célja az, hogy egyszerűbb legyen a tárgyi eszközök tranzakcióinak rendszeres időközönként tervezett feladása.</span><span class="sxs-lookup"><span data-stu-id="baa44-105">The purpose of derived books is to simplify the posting of fixed asset book transactions that are planned for regular intervals.</span></span>  <span data-ttu-id="baa44-106">Elsődleges könyvként egy könyvet választhat ki.</span><span class="sxs-lookup"><span data-stu-id="baa44-106">You choose one book as the primary book.</span></span> <span data-ttu-id="baa44-107">Ez általában az értékcsökkenés könyveléséhez használatos könyv.</span><span class="sxs-lookup"><span data-stu-id="baa44-107">This usually is the book that is used for accounting depreciation.</span></span> <span data-ttu-id="baa44-108">Ezután hozzákapcsolhatja ezt más könyvekhez, amelyek úgy vannak beállítva, hogy az elsődleges könyvvel megegyező időintervallumokban adjanak fel tranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="baa44-108">You then attach to it other books that are set up to post transactions in the same intervals as the primary book.</span></span> <span data-ttu-id="baa44-109">Az adózási szempontú értékcsökkenés könyvei gyakran származtatott könyvként vannak beállítva.</span><span class="sxs-lookup"><span data-stu-id="baa44-109">Tax depreciation books are often set up as derived books.</span></span> 

<span data-ttu-id="baa44-110">A származtatott könyvekkel feladott leggyakoribb tranzakciók a beszerzések, a beszerzési helyesbítések és a kivezetések.</span><span class="sxs-lookup"><span data-stu-id="baa44-110">The most common transactions to set up to post to derived books are acquisitions, acquisition adjustments, and disposals.</span></span> 

## <a name="example"></a><span data-ttu-id="baa44-111">Példa</span><span class="sxs-lookup"><span data-stu-id="baa44-111">Example</span></span>

<span data-ttu-id="baa44-112">A B és C könyvek beállítása a származtatott könyvként van beállítva az A könyvhöz, amelynek tranzakciótípusa beszerzés.</span><span class="sxs-lookup"><span data-stu-id="baa44-112">Book B and book C are set up as derived books for book A for the Acquisition transaction type.</span></span> <span data-ttu-id="baa44-113">Az A könyvbe vigyen be egy beszerzési tranzakciót a 123-as tárgyi eszközhöz 1500,00 értékben.</span><span class="sxs-lookup"><span data-stu-id="baa44-113">In book A, you enter an acquisition transaction for asset 123 for 1,500.00.</span></span> 

<span data-ttu-id="baa44-114">A tranzakció feladása során a program a B könyvben és a C könyvben is létrehoz és felad egy beszerzési tranzakciót a 123-as tárgyi eszközzel, 1500,00 értékben.</span><span class="sxs-lookup"><span data-stu-id="baa44-114">When the transaction is posted, an acquisition transaction is generated and posted in asset 123 for book B and in asset 123 for book C for 1,500.00.</span></span> <span data-ttu-id="baa44-115">Amikor előkészíti az elsődleges könyv tranzakcióit a tárgyieszköz-naplóba történő feladáshoz, a származtatott könyvek tranzakcióit is megtekintheti és módosíthatja.</span><span class="sxs-lookup"><span data-stu-id="baa44-115">When you prepare the transactions of the primary book for posting in the fixed asset journal, you can also view and modify the transactions of the derived books.</span></span> <span data-ttu-id="baa44-116">Ha egy másik naplóban készíti elő az elsődleges könyv tranzakcióit, akkor a származtatott értékek tranzakciói nem jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="baa44-116">If you prepare the primary book transactions in another journal, the transactions of the derived value are not displayed.</span></span> <span data-ttu-id="baa44-117">A program azonban az elsődleges könyv tranzakcióinak feladása során feladja őket a megfelelő számlákra és feladási rétegekbe.</span><span class="sxs-lookup"><span data-stu-id="baa44-117">However, they are posted to the appropriate accounts and posting layers when you post the primary book transactions.</span></span>

> [!NOTE]                                                                                                                               
> <span data-ttu-id="baa44-118">Azokat a könyveket, amelyek úgy vannak beállítva, hogy az elsődleges könyv feladási időközeitől eltérő időközönként adják fel a tranzakciókat, külön könyvként (nem származtatott könyvként) kell a tárgyi eszközhöz társítani.</span><span class="sxs-lookup"><span data-stu-id="baa44-118">Books that are set up to post transactions at intervals other than the primary book intervals must be attached to the fixed asset as separate books and not as derived books.</span></span>  

<span data-ttu-id="baa44-119">További információért lásd: [Feladás származtatott könyvekkel](post-derived-value-models.md).</span><span class="sxs-lookup"><span data-stu-id="baa44-119">For more information, see [Posting with derived books](post-derived-value-models.md).</span></span>



