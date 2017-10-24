--- 
title: "Könyvek beállítása"
description: "Ez az eljárás bemutatja, hogyan hozzon létre új tárgyieszköz-könyvet, és hogyan társítsa azt tárgyieszköz-csoporthoz."
author: saraschi2
manager: AnnBe
ms.date: 10/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: a29cae6cdcd03903359a3a468243c6ad03c7adc6
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-books"></a><span data-ttu-id="b2e6a-103">Könyvek beállítása</span><span class="sxs-lookup"><span data-stu-id="b2e6a-103">Set up books</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b2e6a-104">Ez az eljárás bemutatja, hogyan hozzon létre új tárgyieszköz-könyvet, és hogyan társítsa azt tárgyieszköz-csoporthoz.</span><span class="sxs-lookup"><span data-stu-id="b2e6a-104">This procedure shows you to how create a new fixed asset book and associate it with a fixed asset group.</span></span> <span data-ttu-id="b2e6a-105">Ez a könyvelői szerepkört és a bemutató adatokat használja a USMF jogi személyhez.</span><span class="sxs-lookup"><span data-stu-id="b2e6a-105">It uses the accountant role and demo data for the USMF legal entity.</span></span>


## <a name="create-a-book"></a><span data-ttu-id="b2e6a-106">Könyv létrehozása</span><span class="sxs-lookup"><span data-stu-id="b2e6a-106">Create a book</span></span>
1. <span data-ttu-id="b2e6a-107">Nyissa meg a következőt: Tárgyi eszközök > Beállítás > Könyvek.</span><span class="sxs-lookup"><span data-stu-id="b2e6a-107">Go to Fixed assets > Setup > Books.</span></span>
2. <span data-ttu-id="b2e6a-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b2e6a-108">Click New.</span></span>
3. <span data-ttu-id="b2e6a-109">A Könyv mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="b2e6a-109">In the Book field, type a value.</span></span>
4. <span data-ttu-id="b2e6a-110">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="b2e6a-110">In the Description field, type a value.</span></span>
    * <span data-ttu-id="b2e6a-111">Az Értékcsökkenés kiszámítása lehetőség kiválasztása esetén a társított eszközkönyv bekerül az értékcsökkenési javaslatokba.</span><span class="sxs-lookup"><span data-stu-id="b2e6a-111">If Calculate depreciation is selected, the associated asset book will be included in depreciation proposals.</span></span> <span data-ttu-id="b2e6a-112">Ellenkező esetben az eszközkönyv értékcsökkenése nem lesz automatikus.</span><span class="sxs-lookup"><span data-stu-id="b2e6a-112">If it is not selected, the asset book will not be automatically depreciated.</span></span>  
5. <span data-ttu-id="b2e6a-113">Válassza az Igen lehetőséget az Értékcsökkenés számítása mezőben.</span><span class="sxs-lookup"><span data-stu-id="b2e6a-113">Select Yes in the Calculate depreciation field.</span></span>
6. <span data-ttu-id="b2e6a-114">Az Értékcsökkenés mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="b2e6a-114">In the Depreciation profile field, enter or select a value.</span></span>
    * <span data-ttu-id="b2e6a-115">Az alternatív értékcsökkenési profil az értékcsökkenés alternatív módszereként is ismert.</span><span class="sxs-lookup"><span data-stu-id="b2e6a-115">An alternative depreciation profile is also known as a switchover method of depreciation.</span></span> <span data-ttu-id="b2e6a-116">Az értékcsökkenési javaslat akkor vált erre a profilra, ha az alternatív profil az alapértelmezett értékcsökkenési profillal megegyező, vagy annál nagyobb értékcsökkenési összeget eredményez.</span><span class="sxs-lookup"><span data-stu-id="b2e6a-116">The depreciation proposal will switch to this profile when the alternative profile calculates a depreciation amount that is equal to or greater than the default depreciation profile.</span></span>  
    * <span data-ttu-id="b2e6a-117">A Rendkívüli értékcsökkenési profil egy adott eszköz további értékcsökkenéséhez használható nem szokványos körülmények esetén.</span><span class="sxs-lookup"><span data-stu-id="b2e6a-117">The Extraordinary depreciation profile is used for additional depreciation of an asset in unusual circumstances.</span></span> <span data-ttu-id="b2e6a-118">Ezt például akkor alkalmazhatja, ha természeti katasztrófa okozta értékcsökkenést kell rögzítenie.</span><span class="sxs-lookup"><span data-stu-id="b2e6a-118">For example, you might use this to record depreciation that results from a natural disaster.</span></span>  
    * <span data-ttu-id="b2e6a-119">Az Értékcsökkenés kiigazítása az értékcsökkenési alap kiigazításával lehetőség kiválasztása esetén a rendszer automatikusan létrehozza az értékcsökkenés-kiigazítást az eszköz értékének frissítésekor.</span><span class="sxs-lookup"><span data-stu-id="b2e6a-119">If Create depreciation adjustments with basis adjustments is selected, depreciation adjustments will be automatically created when the value of the asset is updated.</span></span> <span data-ttu-id="b2e6a-120">Ellenkező esetben a tárgyi eszköz frissített értéke csak az ezt követő értékcsökkenés számításokra lesz kihatással.</span><span class="sxs-lookup"><span data-stu-id="b2e6a-120">If it is not selected, the updated asset value will only affect depreciation calculations going forward.</span></span>  
7. <span data-ttu-id="b2e6a-121">Az Értékcsökkenés kiigazítása az értékcsökkenési alap kiigazításával mezőben válassza az Igen lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b2e6a-121">Select Yes in the Create depreciation adjustments with basis adjustments field.</span></span>
    * <span data-ttu-id="b2e6a-122">Alapértelmezés szerint a tárgyi eszközök tranzakciói a főkönyvbe kerülnek feladásra.</span><span class="sxs-lookup"><span data-stu-id="b2e6a-122">By default, fixed asset book transactions will post to the general ledger.</span></span> <span data-ttu-id="b2e6a-123">A főkönyvbe történő feladás a könyvnél letiltható, ha a Feladás a főkönyvbe mezőt Nem értékre állítja.</span><span class="sxs-lookup"><span data-stu-id="b2e6a-123">You can disable posting to the general ledger for the book by setting the Post to general ledger field to No.</span></span> <span data-ttu-id="b2e6a-124">A nem a főkönyvbe feladott könyveket általában adóbevallási célokra használják.</span><span class="sxs-lookup"><span data-stu-id="b2e6a-124">Books that do not post to the general ledger are typically used for tax reporting purposes.</span></span> <span data-ttu-id="b2e6a-125">Ez további rugalmasságot biztosít az eszközkönyv előzménytranzakcióinak törléséhez, mivel ezek így nem kerültek rögzítésre a főkönyvbe.</span><span class="sxs-lookup"><span data-stu-id="b2e6a-125">This gives you additional flexibility to delete historical transactions for the asset book because they have not been committed to the general ledger.</span></span>  
    * <span data-ttu-id="b2e6a-126">A feladási réteg alapértelmezése az Aktuális réteg, ha a könyv feladásra kerül a főkönyvbe, és Nincs, ha nem kerül feladásra.</span><span class="sxs-lookup"><span data-stu-id="b2e6a-126">The Posting layer defaults to the Current layer if the book posts to general ledger, and None if it does not post to general ledger.</span></span> <span data-ttu-id="b2e6a-127">Frissítse a Feladási réteget, ha a könyvhöz kapcsolódó tranzakciókat eltérő rétegbe szeretné feladni.</span><span class="sxs-lookup"><span data-stu-id="b2e6a-127">Update Posting layer if you need transactions for this book to be posted to a different layer.</span></span>  
8. <span data-ttu-id="b2e6a-128">A Naptárak mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="b2e6a-128">In the Calendar field, enter or select a value.</span></span>
    * <span data-ttu-id="b2e6a-129">A származtatott könyvek tranzakcióinak feladása egyszerre különböző könyvekbe történik.</span><span class="sxs-lookup"><span data-stu-id="b2e6a-129">Derived books will post transactions to different books at the same time.</span></span> <span data-ttu-id="b2e6a-130">A tranzakció létrehozása az elsődleges könyvvel történik, feladás közben pedig a tranzakció pontos másolata kerül feladásra a származtatott könyvbe.</span><span class="sxs-lookup"><span data-stu-id="b2e6a-130">You create the transactions with the primary book and during posting, an exact copy of the transaction is posted to the derived book.</span></span> <span data-ttu-id="b2e6a-131">A származtatott könyvbeli tranzakcióknál nincs újraszámítás, így értékcsökkenési tranzakciókhoz ezeket nem szabad használni.</span><span class="sxs-lookup"><span data-stu-id="b2e6a-131">There is no recalculation with derived book transactions, so it should not be used for depreciation transactions.</span></span>  

## <a name="associate-the-book-with-a-fixed-asset-group"></a><span data-ttu-id="b2e6a-132">Társítsa a könyvet egy tárgyieszköz-csoporthoz</span><span class="sxs-lookup"><span data-stu-id="b2e6a-132">Associate the book with a fixed asset group</span></span>
1. <span data-ttu-id="b2e6a-133">Kattintson a Tárgyieszköz-csoportok elemre.</span><span class="sxs-lookup"><span data-stu-id="b2e6a-133">Click Fixed asset groups.</span></span>
2. <span data-ttu-id="b2e6a-134">A Tárgyieszköz-csoport mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="b2e6a-134">In the Fixed asset group field, enter or select a value.</span></span>
3. <span data-ttu-id="b2e6a-135">Adjon meg egy számot az Élettartam mezőben.</span><span class="sxs-lookup"><span data-stu-id="b2e6a-135">In the Service life field, enter a number.</span></span>
    * <span data-ttu-id="b2e6a-136">Ügyeljen, hogy az Értékcsökkenési időszakok értéke az Élettartam beállítását követően kerül kiszámításra.</span><span class="sxs-lookup"><span data-stu-id="b2e6a-136">Note that Depreciation periods is calculated after setting the Service life.</span></span>  
    * <span data-ttu-id="b2e6a-137">Az értékcsökkenési szabályok beállíthatók az adózási szabályokkal összhangban.</span><span class="sxs-lookup"><span data-stu-id="b2e6a-137">You are able to set the depreciation convention as required for tax purposes.</span></span>  

