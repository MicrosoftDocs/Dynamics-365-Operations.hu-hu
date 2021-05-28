---
title: Hibás mezőérték a TaxTrans mezőben
description: Ez a témakör a TaxTrans hibás mezőértékeivel kapcsolatos hibaelhárítással kapcsolatban tartalmaz tájékoztatást.
author: bijian
ms.date: 04/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 488ff54f1dd99208db940024a2fe8b2d25861f44
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020163"
---
# <a name="incorrect-field-value-in-taxtrans"></a><span data-ttu-id="55eda-103">Hibás mezőérték a TaxTrans mezőben</span><span class="sxs-lookup"><span data-stu-id="55eda-103">Incorrect field value in TaxTrans</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="55eda-104">Ha a **TaxTrans** egy mezőértéke helytelen, a témakörben található információk alapján próbálja meg megoldani a problémát.</span><span class="sxs-lookup"><span data-stu-id="55eda-104">If a field value in **TaxTrans** is incorrect, use the information in this topic to try to resolve the issue.</span></span>

## <a name="overview-of-values"></a><span data-ttu-id="55eda-105">Értékek áttekintése</span><span class="sxs-lookup"><span data-stu-id="55eda-105">Overview of values</span></span>
<span data-ttu-id="55eda-106">Az alábbi lista bemutatja, hogy a **TaxTrans**, a **TaxUncommitted** és a **TmpTaxWorkTrans** ugyan hasonló adatkészletek, mégis eltérő módon működnek.</span><span class="sxs-lookup"><span data-stu-id="55eda-106">The following list shows how **TaxTrans**, **TaxUncommitted**, and **TmpTaxWorkTrans** are similar data sets, but in work differently.</span></span>

  - <span data-ttu-id="55eda-107">A **TaxTrans** az adatbázisban megmaradó végső feladott adótranzakció-eredmény.</span><span class="sxs-lookup"><span data-stu-id="55eda-107">**TaxTrans** is the final posted tax transaction result persisted in the database.</span></span>
  - <span data-ttu-id="55eda-108">A **TaxUncommitted** az adatbázisban (ha van) megőrzött köztes számított adó eredmény, amelyet a feladáshoz később lesz használva.</span><span class="sxs-lookup"><span data-stu-id="55eda-108">**TaxUncommitted** is the intermediate calculated tax result persisted in the database (if applicable), which will be used later in posting.</span></span>
  - <span data-ttu-id="55eda-109">A **TmpTaxWorkTrans** az ideiglenes számított adó eredménye a memóriában található táblában (Táblatípus = InMemory).</span><span class="sxs-lookup"><span data-stu-id="55eda-109">**TmpTaxWorkTrans** is the temporary calculated tax result in the in-memory table (Table Type = InMemory).</span></span>

<span data-ttu-id="55eda-110">Ha helytelen **TaxTrans** oszlop kiváltó okát megtalálja, akkor a hibás **TaxUncommitted** vagy **TmpTaxWorkTrans** oszlop kiváltó okát is megtalálta.</span><span class="sxs-lookup"><span data-stu-id="55eda-110">If you find the root cause of an incorrect **TaxTrans** column, you've also found the root cause of an incorrect **TaxUncommitted** or **TmpTaxWorkTrans** column.</span></span> <span data-ttu-id="55eda-111">Ennek az az oka, hogy a három oszlop egymásból van másolva.</span><span class="sxs-lookup"><span data-stu-id="55eda-111">This is because the three columns are copied from each other.</span></span>

<span data-ttu-id="55eda-112">Az adószámítás során általában létrejön a **TmpTaxWorkTrans**, majd – ha szükséges – a **TaxUncommitted** is.</span><span class="sxs-lookup"><span data-stu-id="55eda-112">Typically, during tax calculation, **TmpTaxWorkTrans** is generated, and then, if applicable, **TaxUncommitted** is generated.</span></span> <span data-ttu-id="55eda-113">Az adófeladás során a **TaxTrans** generálódik.</span><span class="sxs-lookup"><span data-stu-id="55eda-113">During tax posting, **TaxTrans** is generated.</span></span>


## <a name="add-breakpoints"></a><span data-ttu-id="55eda-114">Töréspontok hozzáadása</span><span class="sxs-lookup"><span data-stu-id="55eda-114">Add breakpoints</span></span>
<span data-ttu-id="55eda-115">Töréspontok hozzáadását a következő lépésekkel végezheti el:</span><span class="sxs-lookup"><span data-stu-id="55eda-115">To add breakpoints, complete the following steps:</span></span> 

1. <span data-ttu-id="55eda-116">Bővítmények és töréspontok hozzáadása az *insert()* és *update()* alá a bővítményekben az alábbiak szerint.</span><span class="sxs-lookup"><span data-stu-id="55eda-116">Add extensions and breakpoints in *insert()* and *update()* in the extensions as shown below.</span></span>

     - <span data-ttu-id="55eda-117">**TaxTrans**</span><span class="sxs-lookup"><span data-stu-id="55eda-117">**TaxTrans**</span></span>

        ```x++
        [ExtensionOf(tableStr(TaxTrans))]
        public final class TaxTrans_Extension
        {
            public void insert()
            {
                next insert();
            }
        
            public void update()
            {
                next update();
            }
        
        }
        ```

     - <span data-ttu-id="55eda-118">**TaxUncommitted**</span><span class="sxs-lookup"><span data-stu-id="55eda-118">**TaxUncommitted**</span></span>

        ```x++
        [ExtensionOf(tableStr(TaxUncommitted))]
        public final class TaxUncommitted_Extension
        {
            public void insert()
            {
                next insert();
            }
        
            public void update()
            {
                next update();
            }
        
        }
        ```

     - <span data-ttu-id="55eda-119">**TmpTaxWorkTrans**</span><span class="sxs-lookup"><span data-stu-id="55eda-119">**TmpTaxWorkTrans**</span></span>

        ```x++
        [ExtensionOf(tableStr(TmpTaxWorkTrans))]
        public final class TmpTaxWorkTrans_Extension
        {
            public void insert(boolean _ignoreCalculatedSalesTax)
            {
                next insert(_ignoreCalculatedSalesTax);
            }
        
            public void update(boolean _ignoreCalculatedSalesTax)
            {
                next update(_ignoreCalculatedSalesTax);
            }
        
        }
        
        ```

2. <span data-ttu-id="55eda-120">Másik megoldásként közvetlenül is hozzá lehet adni töréspontokat, ha a **TaxUncommitted** nem szerepel.</span><span class="sxs-lookup"><span data-stu-id="55eda-120">Alternatively, you can add breakpoints directly when **TaxUncommitted** is not included.</span></span>

     - <span data-ttu-id="55eda-121">*TaxTrans.insert()*, *TaxTrans.update()*</span><span class="sxs-lookup"><span data-stu-id="55eda-121">*TaxTrans.insert()*, *TaxTrans.update()*</span></span>
     - <span data-ttu-id="55eda-122">*TmpTaxWorkTrans.insert()*, *TmpTaxWorkTrans.update()*</span><span class="sxs-lookup"><span data-stu-id="55eda-122">*TmpTaxWorkTrans.insert()*, *TmpTaxWorkTrans.update()*</span></span>

## <a name="reproduce-and-debug"></a><span data-ttu-id="55eda-123">Reprodukálás és hibakeresés</span><span class="sxs-lookup"><span data-stu-id="55eda-123">Reproduce and debug</span></span>

<span data-ttu-id="55eda-124">A töréspontok beállítása után minden adatperzisztenciás változás látható a hibakeresés során.</span><span class="sxs-lookup"><span data-stu-id="55eda-124">After the breakpoints are set, every data persistency change is visible during debugging.</span></span> <span data-ttu-id="55eda-125">Ha a **TaxTrans**, a **TaxUncommitted** vagy a **TmpTaxWorkTrans** oszlop hibájának kiváltó okát kell megtalálni ellenőrizze és jegyezze fel a következő elemeket:</span><span class="sxs-lookup"><span data-stu-id="55eda-125">To find the root cause of an incorrect column of **TaxTrans**, **TaxUncommitted**, or **TmpTaxWorkTrans**, review and note the following items:</span></span>

- <span data-ttu-id="55eda-126">Az utolsó töréspont, ahol az oszlop helyes.</span><span class="sxs-lookup"><span data-stu-id="55eda-126">The last breakpoint where the column is correct.</span></span>
- <span data-ttu-id="55eda-127">Az első töréspont, ahol az oszlop helytelen.</span><span class="sxs-lookup"><span data-stu-id="55eda-127">The first breakpoint where the column is incorrect.</span></span>
- <span data-ttu-id="55eda-128">Mi történik e két pont között.</span><span class="sxs-lookup"><span data-stu-id="55eda-128">What happens in between those two points.</span></span>

## <a name="determine-whether-customization-exists"></a><span data-ttu-id="55eda-129">Annak meghatározása, hogy létezik-e testreszabás</span><span class="sxs-lookup"><span data-stu-id="55eda-129">Determine whether customization exists</span></span>
<span data-ttu-id="55eda-130">Ha az előző szakaszokban már befejezte a lépéseket, de nem sikerült megoldani a problémát, határozza meg, hogy van-e testreszabás.</span><span class="sxs-lookup"><span data-stu-id="55eda-130">If you've completed the steps in the previous sections but have not been able to resolve the issue, determine whether customization exists.</span></span> <span data-ttu-id="55eda-131">Ha nincs testreszabás, forduljon segítségért a Microsoft támogatási szolgálatához.</span><span class="sxs-lookup"><span data-stu-id="55eda-131">If no customization exists, contact Microsoft Support for assistance.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

