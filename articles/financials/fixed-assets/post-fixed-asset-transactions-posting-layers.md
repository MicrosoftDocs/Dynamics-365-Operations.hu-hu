---
title: "Tárgyieszköz-tranzakciók feladása a feladási rétegekbe"
description: "Ez a cikk a tárgyi-eszköztranzakciók feladási réteg funkciójába nyújt betekintést."
author: ShylaThompson
manager: AnnBe
ms.date: 04/25/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetBookTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 3001
ms.assetid: 7dabde57-0843-47c3-85ef-f36b6f472e30
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: 22feb15a1891c57576a5809f4ff3f4d089c6dfa4
ms.contentlocale: hu-hu
ms.lasthandoff: 08/07/2018

---

# <a name="post-fixed-asset-transactions-to-posting-layers"></a><span data-ttu-id="e855d-103">Tárgyieszköz-tranzakciók feladása a feladási rétegekbe</span><span class="sxs-lookup"><span data-stu-id="e855d-103">Post fixed asset transactions to posting layers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e855d-104">Ez a cikk a tárgyi-eszköztranzakciók feladási réteg funkciójába nyújt betekintést.</span><span class="sxs-lookup"><span data-stu-id="e855d-104">This article gives an overview of posting layer functionality for fixed asset transactions.</span></span>

<span data-ttu-id="e855d-105">Egy tárgyi eszköz különböző célokat szolgáló értékcsökkenése gyakran különböző módszereket kíván.</span><span class="sxs-lookup"><span data-stu-id="e855d-105">A fixed asset is often depreciated in different ways for different purposes.</span></span> <span data-ttu-id="e855d-106">Az adózási célú értékcsökkenés kiszámítása az érvényes adótörvények szerint történik, hogy adózás előtt a legmagasabb lehetséges értékcsökkenést lehessen elérni, ellenben a jelentés céljából készített értékcsökkenés a könyvelési törvények és szabályok szerint történik.</span><span class="sxs-lookup"><span data-stu-id="e855d-106">Depreciation for tax purposes is calculated by using current tax rules to achieve the highest possible depreciation before taxes, but depreciation for reporting purposes is calculated according to accounting laws and standards.</span></span> <span data-ttu-id="e855d-107">Az értékcsökkenés különböző fajtáinak kiszámítása és rögzítése külön feladási rétegekben történik.</span><span class="sxs-lookup"><span data-stu-id="e855d-107">The various kinds of depreciation are calculated and recorded separately in the posting layers.</span></span>

<span data-ttu-id="e855d-108">A tárgyi eszközhöz csatolt valamennyi könyv egy meghatározott feladási réteghez tartozik, amelynek saját átfogó értékcsökkenési célkitűzése van.</span><span class="sxs-lookup"><span data-stu-id="e855d-108">Each book that is attached to a fixed asset is set up for a particular posting layer that has an overall depreciation objective.</span></span> <span data-ttu-id="e855d-109">Tíz feladási réteg létezik: Aktuális, Műveletek, Adó és hét Egyéni réteg.</span><span class="sxs-lookup"><span data-stu-id="e855d-109">There are ten posting layers: Current, Operations, Tax, and seven Custom layers.</span></span> <span data-ttu-id="e855d-110">Letilthatja a főkönyvbe történő feladást is a könyvnél, ha a Feladás a főkönyvbe mezőt Nem értékre állítja.</span><span class="sxs-lookup"><span data-stu-id="e855d-110">You can also disable posting to the general ledger for the book by setting the Post to general ledger field to No.</span></span> <span data-ttu-id="e855d-111">A Feladási réteg mező értéke automatikusan Nincs lesz.</span><span class="sxs-lookup"><span data-stu-id="e855d-111">The Posting layer field is then automatically set to None.</span></span> <span data-ttu-id="e855d-112">A nem a főkönyvbe feladott könyveket általában adóbevallási célokra használják.</span><span class="sxs-lookup"><span data-stu-id="e855d-112">Typically, books that don’t post to the general ledger are used for tax reporting purposes.</span></span> <span data-ttu-id="e855d-113">Ez a megközelítés további rugalmasságot biztosít az eszközkönyv előzménytranzakcióinak törléséhez, mivel ezek így nem kerültek rögzítésre a főkönyvbe.</span><span class="sxs-lookup"><span data-stu-id="e855d-113">This approach gives you the additional flexibility to delete historical transactions for the asset book, because they haven’t been committed to the general ledger.</span></span>

<span data-ttu-id="e855d-114">A tárgyieszköz-naplókat a Naplónevek lapon a Főkönyv > Napló beállítása > Naplónevek pontban határozhatja meg.</span><span class="sxs-lookup"><span data-stu-id="e855d-114">Fixed asset journals are defined by using the Journal names page at General ledger > Journal setup > Journal names.</span></span> <span data-ttu-id="e855d-115">A naplónév csak egy feladási réteghez kapcsolja az összes olyan naplót, amelybe fel lehet adni értékcsökkenést.</span><span class="sxs-lookup"><span data-stu-id="e855d-115">Each journal that you can post depreciations in is defined by its journal name for only one posting layer.</span></span> <span data-ttu-id="e855d-116">A napló feladási rétege nem módosítható.</span><span class="sxs-lookup"><span data-stu-id="e855d-116">The posting layer in the journal can’t be changed.</span></span> <span data-ttu-id="e855d-117">Ezen korlátozás segítségével garantálható, hogy az egyes feladási rétegek tranzakciói külön legyenek tárolva.</span><span class="sxs-lookup"><span data-stu-id="e855d-117">This restriction helps guarantee that transactions for each posting layer are kept separate.</span></span> <span data-ttu-id="e855d-118">Legalább egy naplónevet minden egyes feladási réteghez létre kell hozni.</span><span class="sxs-lookup"><span data-stu-id="e855d-118">At least one journal name must be created for each posting layer.</span></span> <span data-ttu-id="e855d-119">Ha nem a főkönyvbe feladott könyveket használ, létre kell hoznia egy naplót, ahol a feladási réteg értéke Nincs.</span><span class="sxs-lookup"><span data-stu-id="e855d-119">If you’re using books that don’t post to the general ledger, you must also create a journal where the posting layer is set to None.</span></span>

<span data-ttu-id="e855d-120">Kijelölhet főkönyvi számlákat tárgyieszköz-tranzakciókhoz a Tárgyieszköz-feladási profilok lapon.</span><span class="sxs-lookup"><span data-stu-id="e855d-120">You can designate ledger accounts for fixed asset transactions on the Fixed asset posting profiles page.</span></span> <span data-ttu-id="e855d-121">Minden feladási profilnál jelölje ki a megfelelő tranzakciótípust és a könyvet, majd jelölje ki a főkönyvi számlákat.</span><span class="sxs-lookup"><span data-stu-id="e855d-121">For each posting profile, you must select the relevant transaction type and book, and then designate the ledger accounts.</span></span> <span data-ttu-id="e855d-122">Hozzon létre feladási profil rekordot minden, a főkönyvbe feladott könyvre.</span><span class="sxs-lookup"><span data-stu-id="e855d-122">Set up a posting profile record for each book that will post to the general ledger.</span></span>

> [!NOTE] 
> <span data-ttu-id="e855d-123">A származtatott könyvek használatával egyszerre több feladási rétegre is fel lehet adni a tranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="e855d-123">By using derived books, you can post transactions to different posting layers at the same time.</span></span> <span data-ttu-id="e855d-124">Az elsődleges könyv tranzakcióit egy olyan naplóban kell létrehozni, amelynek a feladási rétege megegyezik a könyv feladási rétegével.</span><span class="sxs-lookup"><span data-stu-id="e855d-124">You create the transactions of the primary book in a journal where the posting layer corresponds to the book posting layer.</span></span> <span data-ttu-id="e855d-125">Feladás során a származtatott könyvtranzakciókat a program feladja a megfelelő feladási rétegekre.</span><span class="sxs-lookup"><span data-stu-id="e855d-125">During posting, the derived book transactions are posted to the appropriate posting layers.</span></span>

<span data-ttu-id="e855d-126">A további tudnivalókat lásd [Származtatott könyvek](derived-books.md) és [Feladás származtatott könyvekbe](post-derived-value-models.md).</span><span class="sxs-lookup"><span data-stu-id="e855d-126">For more information see, [Derived books](derived-books.md) and [Posting with derived books](post-derived-value-models.md).</span></span>




