---
title: Feladás származtatott könyvekkel
description: Ez a cikk a származtatott könyvek használatának módját ismerteti.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetBookTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 3421
ms.assetid: f5187c21-eec5-4148-b178-b8a5feff7f23
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ff1dbf67a53a5639e448da707898b55cd00cba94
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "339142"
---
# <a name="post-with-derived-books"></a><span data-ttu-id="2bcfa-103">Feladás származtatott könyvekkel</span><span class="sxs-lookup"><span data-stu-id="2bcfa-103">Post with derived books</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2bcfa-104">Ez a cikk a származtatott könyvek használatának módját ismerteti.</span><span class="sxs-lookup"><span data-stu-id="2bcfa-104">This article describes how to use derived books.</span></span>

<span data-ttu-id="2bcfa-105">Ha származtatott könyvet tartalmazó értékmodellhez ad fel tranzakciókat, a származtatott tranzakciókat a program automatikusan feladja a naplókból, a beszerzési rendelésekből vagy a szabadszöveges számlázásokból.</span><span class="sxs-lookup"><span data-stu-id="2bcfa-105">When you post transactions for a book that contains derived books, the derived book transactions are posted automatically in journals, purchase orders, or free text invoices.</span></span> <span data-ttu-id="2bcfa-106">Azonban ha Tárgyieszköz-naplóban készíti elő az elsődleges könyvtranzakciókat, akkor megtekintheti és módosíthatja a származtatott tranzakciók összegeit, mielőtt feladja őket.</span><span class="sxs-lookup"><span data-stu-id="2bcfa-106">However, if you prepare the primary book transactions in the Fixed assets journal, you can view and modify the amounts of the derived transactions before you post them.</span></span>
-   <span data-ttu-id="2bcfa-107">Bizonyos számlákat, így az áfaszámlát és a vevői vagy szállítói számlákat a program csak egyszer – az elsődleges könyv feladása során – frissít.</span><span class="sxs-lookup"><span data-stu-id="2bcfa-107">Certain accounts, such as sales tax and customer or vendor accounts, are updated only once by postings of the primary book.</span></span> <span data-ttu-id="2bcfa-108">A származtatott könyvtranzakciók feladásra kerülnek azokhoz a számlákhoz, amelyek a származtatott könyvhöz lettek meghatározva a Tárgyi eszköz feladási profilok lapon.</span><span class="sxs-lookup"><span data-stu-id="2bcfa-108">The derived book transactions are posted to the accounts that have been defined for the derived book in the Fixed asset posting profiles page.</span></span>
-   <span data-ttu-id="2bcfa-109">A beszerzés gyakran a származtatott könyvek tranzakciótípusa.</span><span class="sxs-lookup"><span data-stu-id="2bcfa-109">Acquisition is often used as the transaction type for the derived books.</span></span> <span data-ttu-id="2bcfa-110">Ezt akkor lehet használni, amikor a tárgyi eszköz beszerzésének az idejétől a könyvet és a származtatott könyvet kell alkalmazni a tárgyi eszközre.</span><span class="sxs-lookup"><span data-stu-id="2bcfa-110">You use this when the book and the derived book should be applied to the fixed asset from the time of the acquisition of the fixed asset.</span></span>
-   <span data-ttu-id="2bcfa-111">A tranzakciótípus egyéb felvehető értékei.</span><span class="sxs-lookup"><span data-stu-id="2bcfa-111">Other values for the transaction type can also apply.</span></span> <span data-ttu-id="2bcfa-112">Ha például az elsődleges könyv és a származtatott könyvek az értékesítést és a kivezetést illetően ugyanazokat az intervallumokat használják, akkor az összes tranzakciótípus rendelkezésre áll a származtatott értékcsökkenés könyv beállítása során.</span><span class="sxs-lookup"><span data-stu-id="2bcfa-112">For example, if the primary book and the derived books have the same intervals regarding sale or disposal, all fixed asset transaction types are available for the setup of a derived book.</span></span>

> [!WARNING]
> <span data-ttu-id="2bcfa-113">A származtatott könyvbe feladott összeg megegyezik az elsődleges könyvbe feladott összeggel.</span><span class="sxs-lookup"><span data-stu-id="2bcfa-113">Depreciation posted in the derived book will be the same amount as was posted for the primary book.</span></span> <span data-ttu-id="2bcfa-114">Ha a könyvek értékcsökkenési módszere eltérő, akkor nem ajánlott a származtatott eljárással készíteni értékcsökkenési tranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="2bcfa-114">If the depreciation methods are different between the books, you should not generate depreciation transactions using the derived process.</span></span> |

## <a name="example"></a><span data-ttu-id="2bcfa-115">Példa</span><span class="sxs-lookup"><span data-stu-id="2bcfa-115">Example</span></span> 
<span data-ttu-id="2bcfa-116">A következő adatok leírják, hogyan állítson be beszerzési tranzakciókat a származtatott könyv funkcióval.</span><span class="sxs-lookup"><span data-stu-id="2bcfa-116">The following information describes how to set up acquisition transactions with the derived book functionality.</span></span>

1.  <span data-ttu-id="2bcfa-117">Az áfakönyvek létrehozása a Könyvek lapon.</span><span class="sxs-lookup"><span data-stu-id="2bcfa-117">Create the books on the Books page.</span></span>
    -   <span data-ttu-id="2bcfa-118">A könyvelési könyv: VM 1, Jelenlegi feladási réteg</span><span class="sxs-lookup"><span data-stu-id="2bcfa-118">The book for accounting: VM 1, Current posting layer</span></span>
    -   <span data-ttu-id="2bcfa-119">Az adózáshoz használt könyv: VM 2, Adó feladási réteg</span><span class="sxs-lookup"><span data-stu-id="2bcfa-119">The book for tax purposes: VM 2, Tax posting layer</span></span>

2.  <span data-ttu-id="2bcfa-120">Kattintson az ÉM 1 Származtatott könyvek fülére. Válassza ki az ÉM 2 elemet a Könyv mezőben, és a Beszerzés elemet a Tranzakció típusa mezőben.</span><span class="sxs-lookup"><span data-stu-id="2bcfa-120">On VM 1, click the Derived books tab. Select VM 2 in the Book field, and Acquisition in the Transaction type field.</span></span>

<span data-ttu-id="2bcfa-121">A könyveket ezután csatolni lehet meghatározott tárgyi eszközökhöz.</span><span class="sxs-lookup"><span data-stu-id="2bcfa-121">The books then can be attached to specific fixed assets.</span></span> 

<span data-ttu-id="2bcfa-122">Ha felad egy, az ÉM 1 könyvet használó tárgyi eszközre vonatkozó beszerzést, akkor a program a beszerzést nem csak az ÉM 1-be, hanem ÉM 2 származtatott könyvbe is feladja.</span><span class="sxs-lookup"><span data-stu-id="2bcfa-122">When an acquisition is posted for a fixed asset with book VM 1, the acquisition is posted not only on VM 1, but also on the derived book VM 2.</span></span> <span data-ttu-id="2bcfa-123">Mindkét tárgyi eszközök könyv állapota frissül Nyitottra.</span><span class="sxs-lookup"><span data-stu-id="2bcfa-123">The status of both fixed asset books is updated to Open.</span></span>

> [!NOTE]                                                                                                         
> <span data-ttu-id="2bcfa-124">Ha nem használ származtatott értékcsökkenési könyveket, akkor a VM 1 értékmodellbe és VM 2 könyvbe is fel kell adni a tárgyieszköz-beszerzést.</span><span class="sxs-lookup"><span data-stu-id="2bcfa-124">If you do not use derived books, you must post the acquisition of the fixed asset both for book VM 1 and book VM 2.</span></span>

<span data-ttu-id="2bcfa-125">További információért lásd: [Származtatott könyvek](derived-books.md)</span><span class="sxs-lookup"><span data-stu-id="2bcfa-125">For more information, see [Derived books](derived-books.md)</span></span>



