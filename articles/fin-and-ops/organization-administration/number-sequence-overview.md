---
title: "Számsorozatok"
description: "A számsorozatokat az azonosítókat igénylő alapadatrekordok és tranzakciórekordok olvasható, egyedi azonosítóinak létrehozására használja a rendszer."
author: MargoC
manager: AnnBe
ms.date: 08/17/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: NumberSequenceTableListPage
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 15461
ms.assetid: 6e19bd1d-192b-4da2-8573-84f6e1ce98ef
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: e978519a86e32d4440b7c0562c4c5069c001ce81
ms.contentlocale: hu-hu
ms.lasthandoff: 01/17/2018

---

# <a name="number-sequences"></a><span data-ttu-id="e6228-103">Számsorozatok</span><span class="sxs-lookup"><span data-stu-id="e6228-103">Number sequences</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="e6228-104">A számsorozatokat az azonosítókat igénylő alapadatrekordok és tranzakciórekordok olvasható, egyedi azonosítóinak létrehozására használja a rendszer.</span><span class="sxs-lookup"><span data-stu-id="e6228-104">Number sequences are used to generate readable, unique identifiers for master data records and transaction records that require identifiers.</span></span> <span data-ttu-id="e6228-105">Az azonosítókat igénylő alapadatokrekordokat és tranzakciós bejegyzéseket *hivatkozásnak* nevezik.</span><span class="sxs-lookup"><span data-stu-id="e6228-105">A master data record or transaction record that requires an identifier is referred to as a *reference*.</span></span>

<span data-ttu-id="e6228-106">Egy hivatkozáshoz tartozó új rekordok létrehozása előtt be kell állítania egy számsorozatot, és a hivatkozáshoz társítani.</span><span class="sxs-lookup"><span data-stu-id="e6228-106">Before you can create new records for a reference, you must set up a number sequence and associate it with the reference.</span></span> <span data-ttu-id="e6228-107">Javasoljuk, hogy a **Szervezeti adminisztráció** űrlapon belül található lapokat használja a számsorozatok beállításakor.</span><span class="sxs-lookup"><span data-stu-id="e6228-107">We recommend that you use the pages in **Organization administration** to set up number sequences.</span></span> <span data-ttu-id="e6228-108">Ha modulspecifikus beállításokat kell megadni, akkor használhatja a paraméterek lapot a modulban, hogy meghatározza az abban a modulban található hivatkozásokhoz tartozó számsorozatokat.</span><span class="sxs-lookup"><span data-stu-id="e6228-108">If module-specific settings are required, you can use the parameters page in a module to specify number sequences for the references in that module.</span></span> <span data-ttu-id="e6228-109">Például a **Kinnlevőségek** és **Kötelezettségek** modulokban beállíthat számsorozat csoportokat, hogy meghatározott számsorozatokat meghatározott vevőkhöz vagy szállítókhoz rendeljen.</span><span class="sxs-lookup"><span data-stu-id="e6228-109">For example, in **Accounts receivable** and **Accounts payable**, you can set up number sequence groups to allocate specific number sequences to specific customers or vendors.</span></span> 

<span data-ttu-id="e6228-110">Számsorozat beállításakor mindig meg kell adnia egy hatókört, ami megadja, mely szervezet használja a számsorozatot.</span><span class="sxs-lookup"><span data-stu-id="e6228-110">When you set up a number sequence, you must specify a scope, which defines which organization uses the number sequence.</span></span> <span data-ttu-id="e6228-111">A hatókör lehet **megosztott**, **vállalat**, **jogi személy**, vagy **operációs egység**.</span><span class="sxs-lookup"><span data-stu-id="e6228-111">The scope can be **Shared**, **Company**, **Legal entity**, or **Operating unit**.</span></span> <span data-ttu-id="e6228-112">A **jogi személy** és **vállalat** hatókörök összevonhatóak a **pénzügyi naptári időszak** modullal, hogy még több meghatározott számsorozatot hozzon létre.</span><span class="sxs-lookup"><span data-stu-id="e6228-112">**Legal entity** and **Company** scopes can be combined with **Fiscal calendar period** to create even more specific number sequences.</span></span> 

<span data-ttu-id="e6228-113">A számsorozatok formátumai szegmensekből állnak.</span><span class="sxs-lookup"><span data-stu-id="e6228-113">Number sequence formats consist of segments.</span></span> <span data-ttu-id="e6228-114">Az olyan számsorozatok, amelyek hatóköre nem **megosztott** tartalmazhatnak olyan szegmenseket, amelyek megfelelnek a hatókörnek.</span><span class="sxs-lookup"><span data-stu-id="e6228-114">Number sequences with a scope other than **Shared** can contain segments that correspond to the scope.</span></span> <span data-ttu-id="e6228-115">Például egy számsorozat a **jogi személy** hatókörrel tartalmazhat egy jogi személy szegmenst.</span><span class="sxs-lookup"><span data-stu-id="e6228-115">For example, a number sequence with a scope of **Legal entity** can contain a legal entity segment.</span></span> <span data-ttu-id="e6228-116">Ha hatókör-szegmenst is felvesz a számsorozat-formátumba, akkor már a szám alapján beazonosíthatja egy adott rekord hatókörét.</span><span class="sxs-lookup"><span data-stu-id="e6228-116">By including a scope segment in the number sequence format, you can identify the scope of a particular record by looking at its number.</span></span> 

<span data-ttu-id="e6228-117">A hatóköröket jelölő szegmenseken kívül a számsorozat-formátumok tartalmazhatnak **állandó** és **alfanumerikus szegmens** értékeket.</span><span class="sxs-lookup"><span data-stu-id="e6228-117">In addition to segments that correspond to scopes, number sequence formats can contain **Constant** and **Alphanumeric segments**.</span></span> <span data-ttu-id="e6228-118">Az **állandó** szegmens olyan betűket, számokat vagy szimbólumokat tartalmaz, amelyek nem változnak.</span><span class="sxs-lookup"><span data-stu-id="e6228-118">A **Constant** segment contains a set of letters, numbers, or symbols that does not change.</span></span> <span data-ttu-id="e6228-119">Az **alfanumerikus** szegmens olyan betűhalmazt vagy számot is tartalmazhat, amely a szám minden új használatakor nő.</span><span class="sxs-lookup"><span data-stu-id="e6228-119">An **Alphanumeric** segment contains a set of letters or numbers that increment every time that a number is used.</span></span> <span data-ttu-id="e6228-120">A kettős kereszt (\#) használatával jelezheti a növekvő számokat, az (&) jellel pedig a növekvő betűket.</span><span class="sxs-lookup"><span data-stu-id="e6228-120">Use a number sign (\#) to represent incrementing numbers and an ampersand (&) to represent incrementing letters.</span></span> <span data-ttu-id="e6228-121">Például a \#\#\#\#\#\_2017 formátum a 00001\_2017, 00002\_2017 és így tovább sorozatot hozza létre.</span><span class="sxs-lookup"><span data-stu-id="e6228-121">For example, the format \#\#\#\#\#\_2017 creates the sequence 00001\_2017, 00002\_2017, and so on.</span></span>

<a name="number-sequence-examples"></a><span data-ttu-id="e6228-122">Példák a számsorozatokra</span><span class="sxs-lookup"><span data-stu-id="e6228-122">Number sequence examples</span></span>
------------------------

<span data-ttu-id="e6228-123">A következő példák bemutatják, hogyan hozhat létre számsorozat-formátumokat szegmensekből.</span><span class="sxs-lookup"><span data-stu-id="e6228-123">The following examples show how to use segments to create number sequence formats.</span></span> <span data-ttu-id="e6228-124">A példákban azt is láthatja, milyen hatása van a hatókörszegmenseknek.</span><span class="sxs-lookup"><span data-stu-id="e6228-124">In particular, the examples demonstrate the effects of using scope segments.</span></span>

### <a name="expense-report-numbers"></a><span data-ttu-id="e6228-125">Költségjelentésszámok</span><span class="sxs-lookup"><span data-stu-id="e6228-125">Expense report numbers</span></span>

<span data-ttu-id="e6228-126">A következő példában költségjelentésszámokat állítunk be egy **CS** nevű jogi személyhez.</span><span class="sxs-lookup"><span data-stu-id="e6228-126">In the following example, expense report numbers are set up for the legal entity that is titled **CS**.</span></span> 

- <span data-ttu-id="e6228-127">**Terület:** Utazás és költség</span><span class="sxs-lookup"><span data-stu-id="e6228-127">**Area:** Travel and expense</span></span> 
- <span data-ttu-id="e6228-128">**Hivatkozás:** A költségjelentés száma</span><span class="sxs-lookup"><span data-stu-id="e6228-128">**Reference:** Expense report number</span></span> 
- <span data-ttu-id="e6228-129">**Hatókör:** Jogi személy</span><span class="sxs-lookup"><span data-stu-id="e6228-129">**Scope:** Legal entity</span></span> 
- <span data-ttu-id="e6228-130">**Jogi személy:** CS</span><span class="sxs-lookup"><span data-stu-id="e6228-130">**Legal entity:** CS</span></span>

| <span data-ttu-id="e6228-131">Szegmensek</span><span class="sxs-lookup"><span data-stu-id="e6228-131">Segments</span></span>  | <span data-ttu-id="e6228-132">Szegmens típusa</span><span class="sxs-lookup"><span data-stu-id="e6228-132">Segment type</span></span> | <span data-ttu-id="e6228-133">Érték</span><span class="sxs-lookup"><span data-stu-id="e6228-133">Value</span></span>     |
|-----------|--------------|-----------|
| <span data-ttu-id="e6228-134">1. szegmens</span><span class="sxs-lookup"><span data-stu-id="e6228-134">Segment 1</span></span> | <span data-ttu-id="e6228-135">Jogi személy</span><span class="sxs-lookup"><span data-stu-id="e6228-135">Legal entity</span></span> | <span data-ttu-id="e6228-136">CS</span><span class="sxs-lookup"><span data-stu-id="e6228-136">CS</span></span>        |
| <span data-ttu-id="e6228-137">2. Szegmens</span><span class="sxs-lookup"><span data-stu-id="e6228-137">Segment 2</span></span> | <span data-ttu-id="e6228-138">Állandó</span><span class="sxs-lookup"><span data-stu-id="e6228-138">Constant</span></span>     | <span data-ttu-id="e6228-139">-KIADAS-</span><span class="sxs-lookup"><span data-stu-id="e6228-139">-EXPENSE-</span></span> |
| <span data-ttu-id="e6228-140">3. szegmens</span><span class="sxs-lookup"><span data-stu-id="e6228-140">Segment 3</span></span> | <span data-ttu-id="e6228-141">Alfanumerikus</span><span class="sxs-lookup"><span data-stu-id="e6228-141">Alphanumeric</span></span> | \#\#\#\#  |

<span data-ttu-id="e6228-142">**Egy példa a számformátum alapján**: CS-KIADAS-0039</span><span class="sxs-lookup"><span data-stu-id="e6228-142">**Example of formatted number**: CS-EXPENSE-0039</span></span> 

<span data-ttu-id="e6228-143">Hasonló számsorozat-formátumot más jogi személyekhez is beállíthat.</span><span class="sxs-lookup"><span data-stu-id="e6228-143">You can set up a similar number sequence format for other legal entities.</span></span> <span data-ttu-id="e6228-144">Így például az **RW** nevű jogi személynél, ha csak a jogi személyre vonatkozó szegmenst változtatja meg, a formázott szám RW-KIADAS-0039 lesz.</span><span class="sxs-lookup"><span data-stu-id="e6228-144">For example, for a legal entity that is named **RW**, if you change only the value of the legal entity segment, the formatted number is RW-EXPENSE-0039.</span></span> <span data-ttu-id="e6228-145">De más jogi személyekre vonatkozóan akár a teljes számsorozat-formátumot megváltoztathatja.</span><span class="sxs-lookup"><span data-stu-id="e6228-145">You can also change the whole number sequence format for other legal entities.</span></span> <span data-ttu-id="e6228-146">Így például kihagyhatja a jogi személyre vonatkozó hatókör szegmensét, így a szám lehet például Kiad-0001.</span><span class="sxs-lookup"><span data-stu-id="e6228-146">For example, you can omit the legal entity scope segment to create a formatted number such as Exp-0001.</span></span>

### <a name="sales-order-numbers"></a><span data-ttu-id="e6228-147">Értékesítési rendelések számai</span><span class="sxs-lookup"><span data-stu-id="e6228-147">Sales order numbers</span></span>

<span data-ttu-id="e6228-148">A következő példában szereplő értékesítésirendelés-számokat a **CEU** vállalatazonosítóhoz hoztuk létre.</span><span class="sxs-lookup"><span data-stu-id="e6228-148">In the following example, sales order numbers are set up for the company ID **CEU**.</span></span> 

- <span data-ttu-id="e6228-149">**Terület:** Értékesítés</span><span class="sxs-lookup"><span data-stu-id="e6228-149">**Area:** Sales</span></span> 
- <span data-ttu-id="e6228-150">**Hivatkozás:** Értékesítési rendelés</span><span class="sxs-lookup"><span data-stu-id="e6228-150">**Reference:** Sales order</span></span> 
- <span data-ttu-id="e6228-151">**Hatókör:** Vállalat</span><span class="sxs-lookup"><span data-stu-id="e6228-151">**Scope:** Company</span></span> 
- <span data-ttu-id="e6228-152">**Vállalat:** CEU-cím</span><span class="sxs-lookup"><span data-stu-id="e6228-152">**Company:** CEU</span></span>

| <span data-ttu-id="e6228-153">Szegmensek</span><span class="sxs-lookup"><span data-stu-id="e6228-153">Segments</span></span>  | <span data-ttu-id="e6228-154">Szegmens típusa</span><span class="sxs-lookup"><span data-stu-id="e6228-154">Segment type</span></span> | <span data-ttu-id="e6228-155">Érték</span><span class="sxs-lookup"><span data-stu-id="e6228-155">Value</span></span>    |
|-----------|--------------|----------|
| <span data-ttu-id="e6228-156">1. szegmens</span><span class="sxs-lookup"><span data-stu-id="e6228-156">Segment 1</span></span> | <span data-ttu-id="e6228-157">Állandó</span><span class="sxs-lookup"><span data-stu-id="e6228-157">Constant</span></span>     | <span data-ttu-id="e6228-158">SO-</span><span class="sxs-lookup"><span data-stu-id="e6228-158">SO-</span></span>      |
| <span data-ttu-id="e6228-159">2. Szegmens</span><span class="sxs-lookup"><span data-stu-id="e6228-159">Segment 2</span></span> | <span data-ttu-id="e6228-160">Alfanumerikus</span><span class="sxs-lookup"><span data-stu-id="e6228-160">Alphanumeric</span></span> | \#\#\#\# |

<span data-ttu-id="e6228-161">**Egy példa a számformátum alapján**: SO-0029</span><span class="sxs-lookup"><span data-stu-id="e6228-161">**Example of formatted number**: SO-0029</span></span> 

<span data-ttu-id="e6228-162">Bár ebben a a formátumban nincs hatókörre vonatkozó szegmens, a számozás minden egyes cégazonosítónál újrakezdődik.</span><span class="sxs-lookup"><span data-stu-id="e6228-162">Even though a scope segment is not included in the format, numbering restarts for each company ID.</span></span> <span data-ttu-id="e6228-163">Ha minden cégazonosítónál ugyanazt a formátumot használja, akkor minden vállalatnál ugyanazokat a számokat kapja.</span><span class="sxs-lookup"><span data-stu-id="e6228-163">If you use the same format for all company IDs, the same numbers are used in each company.</span></span> <span data-ttu-id="e6228-164">Így például a huszonkilencedik értékesítési rendelés száma minden cégnél SO-0029 lesz.</span><span class="sxs-lookup"><span data-stu-id="e6228-164">For example, sales order number SO-0029 is used in each company.</span></span> <span data-ttu-id="e6228-165">Más vállalatazonosítókhoz azonban akár a teljes számsorozat formátumát megváltoztathatja.</span><span class="sxs-lookup"><span data-stu-id="e6228-165">You can also change the whole number sequence format for other company IDs.</span></span>

### <a name="purchase-requisition-numbers"></a><span data-ttu-id="e6228-166">Beszerzési igénylések számai</span><span class="sxs-lookup"><span data-stu-id="e6228-166">Purchase requisition numbers</span></span>

<span data-ttu-id="e6228-167">A következő példában szereplő beszerzésiigénylés-számok a teljes szervezeti szintre vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="e6228-167">In the following example, purchase requisition numbers are organization-wide.</span></span> 

- <span data-ttu-id="e6228-168">**Terület:** Beszerzés</span><span class="sxs-lookup"><span data-stu-id="e6228-168">**Area:** Purchase</span></span> 
- <span data-ttu-id="e6228-169">**Hivatkozás:** Beszerzési igénylés</span><span class="sxs-lookup"><span data-stu-id="e6228-169">**Reference:** Purchase requisition</span></span> 
- <span data-ttu-id="e6228-170">**Hatókör:** Megosztott</span><span class="sxs-lookup"><span data-stu-id="e6228-170">**Scope:** Shared</span></span>

| <span data-ttu-id="e6228-171">Szegmensek</span><span class="sxs-lookup"><span data-stu-id="e6228-171">Segments</span></span>  | <span data-ttu-id="e6228-172">Szegmens típusa</span><span class="sxs-lookup"><span data-stu-id="e6228-172">Segment type</span></span> | <span data-ttu-id="e6228-173">Érték</span><span class="sxs-lookup"><span data-stu-id="e6228-173">Value</span></span>    |
|-----------|--------------|----------|
| <span data-ttu-id="e6228-174">1. szegmens</span><span class="sxs-lookup"><span data-stu-id="e6228-174">Segment 1</span></span> | <span data-ttu-id="e6228-175">Állandó</span><span class="sxs-lookup"><span data-stu-id="e6228-175">Constant</span></span>     | <span data-ttu-id="e6228-176">Besz</span><span class="sxs-lookup"><span data-stu-id="e6228-176">Req</span></span>      |
| <span data-ttu-id="e6228-177">2. Szegmens</span><span class="sxs-lookup"><span data-stu-id="e6228-177">Segment 2</span></span> | <span data-ttu-id="e6228-178">Alfanumerikus</span><span class="sxs-lookup"><span data-stu-id="e6228-178">Alphanumeric</span></span> | \#\#\#\# |

<span data-ttu-id="e6228-179">**Egy példa a számformátum alapján**: Besz0052</span><span class="sxs-lookup"><span data-stu-id="e6228-179">**Example of formatted number**: Req0052</span></span> 

<span data-ttu-id="e6228-180">Mivel a hatókör **Megosztott**, ezért a számsorozat a teljes szervezeten belül így lesz használható.</span><span class="sxs-lookup"><span data-stu-id="e6228-180">Because the scope is **Shared**, the number sequence format is used across the organization.</span></span> <span data-ttu-id="e6228-181">Nem állíthat be a szervezet különböző részei számára más-más számsorozat-formátumot.</span><span class="sxs-lookup"><span data-stu-id="e6228-181">You cannot set up different number sequence formats for different parts of the organization.</span></span> 

<a name="performance-considerations-for-number-sequences"></a><span data-ttu-id="e6228-182">Teljesítménnyel kapcsolatos megfontolások a számsorozatok létrehozásánál</span><span class="sxs-lookup"><span data-stu-id="e6228-182">Performance considerations for number sequences</span></span>
-----------------------------------------------

<span data-ttu-id="e6228-183">A számsorozatok beállítása előtt figyelembe kell venni, hogy a számsorozatok konfigurációja hogyan befolyásolhatja a rendszerteljesítményt.</span><span class="sxs-lookup"><span data-stu-id="e6228-183">Consider the following information about how the configuration of number sequences can affect system performance before you set up number sequences.</span></span>

### <a name="continuous-and-non-continuous-number-sequences"></a><span data-ttu-id="e6228-184">Folyamatos és nem folyamatos számsorozatok</span><span class="sxs-lookup"><span data-stu-id="e6228-184">Continuous and non-continuous number sequences</span></span>

<span data-ttu-id="e6228-185">Egy számsorozat lehet folyamatos vagy nem folyamatos.</span><span class="sxs-lookup"><span data-stu-id="e6228-185">Number sequences can be continuous or non-continuous.</span></span> <span data-ttu-id="e6228-186">A folyamatos számsor nem hagy ki egyetlen számot sem, de nem feltétlenül sorrendben használja a számokat.</span><span class="sxs-lookup"><span data-stu-id="e6228-186">A continuous number sequence does not skip any numbers, but numbers may not be used sequentially.</span></span> <span data-ttu-id="e6228-187">A nem folyamatos számsorozatok ugyan sorban haladnak, de a sorozat időnként ugorhat egy számot.</span><span class="sxs-lookup"><span data-stu-id="e6228-187">Numbers from a non-continuous number sequence are used sequentially, but the number sequence may skip numbers.</span></span> <span data-ttu-id="e6228-188">Így például ha egy felhasználó megszakít egy tranzakciót, akkor a rendszer számot generál hozzá, de nem használja azt.</span><span class="sxs-lookup"><span data-stu-id="e6228-188">For example, if a user cancels a transaction, a number is generated, but not used.</span></span> <span data-ttu-id="e6228-189">A folyamatos számsorozat ezzel később újra felhasználja ezt a számot.</span><span class="sxs-lookup"><span data-stu-id="e6228-189">In a continuous number sequence, that number is recycled later.</span></span> <span data-ttu-id="e6228-190">Nem folyamatos számsorozatnál a rendszer nem használja többé ezt a számot.</span><span class="sxs-lookup"><span data-stu-id="e6228-190">In a non-continuous number sequence, the number is not used.</span></span> 

<span data-ttu-id="e6228-191">A folyamatos számsorozatok általában külső dokumentumoknál hasznosak, mint amilyen a beszerzési rendelés, az értékesítési rendelés, illetve a számlák.</span><span class="sxs-lookup"><span data-stu-id="e6228-191">Continuous number sequences are typically required for external documents, such as purchase orders, sales orders, and invoices.</span></span> <span data-ttu-id="e6228-192">Azonban a folyamatos számsorozatokok lelassíthatják a rendszer válaszidejét, mert a rendszernek minden alkalommal új számot kell kérnie az adatbázisból, valahányszor új dokumentmot vagy rekordot hoznak létre.</span><span class="sxs-lookup"><span data-stu-id="e6228-192">However, continuous number sequences can adversely affect system response times because the system must request a number from the database every time that a new document or record is created.</span></span> 

<span data-ttu-id="e6228-193">Nem folytonos számsor használatakor engedélyezheti az **előzetes lefoglalást** a **teljesítmény** gyorslapon, amelyet a **számsorozatok** lapon talál.</span><span class="sxs-lookup"><span data-stu-id="e6228-193">If you use a non-continuous number sequence, you can enable **Preallocation** on the **Performance** FastTab of the **Number sequences** page.</span></span> <span data-ttu-id="e6228-194">Ha egy adott mennyiségű számot előre lefoglal, akkor a rendszer ezeket kiválasztja és eltárolja a memóriában.</span><span class="sxs-lookup"><span data-stu-id="e6228-194">When you specify a quantity of numbers to preallocate, the system selects those numbers and stores them in memory.</span></span> <span data-ttu-id="e6228-195">Ezek után csak akkor igényel új számokat az adatbázisból, ha az előre lefoglaltakat már felhasználta.</span><span class="sxs-lookup"><span data-stu-id="e6228-195">New numbers are requested from the database only after the preallocated quantity has been used.</span></span> 

<span data-ttu-id="e6228-196">Hacsak nem törvényi előírás a folyamatos számsorozatok használata, akkor a rendszerteljesítmény javítása érdekében érdemesebb a nem folyamatos számozást választani.</span><span class="sxs-lookup"><span data-stu-id="e6228-196">Unless there is a regulatory requirement that you use continuous number sequences, we recommend that you use non-continuous number sequences for better performance.</span></span>

### <a name="automatic-cleanup-of-number-sequences"></a><span data-ttu-id="e6228-197">Számsorozatok automatikus tisztítása</span><span class="sxs-lookup"><span data-stu-id="e6228-197">Automatic cleanup of number sequences</span></span>

<span data-ttu-id="e6228-198">Áramszünet, szoftverhiba vagy egyéb váratlan probléma esetén a rendszer nem tudja automatikusan újrahasznosítani a folyamatos számsorozatok korábbi számait.</span><span class="sxs-lookup"><span data-stu-id="e6228-198">In case of a power failure, an application error, or other unexpected failure, the system cannot recycle numbers automatically for continuous number sequences.</span></span> <span data-ttu-id="e6228-199">Ezért ezen elveszett sorszámok rendbetételéhez manuállis vagy automatikus tisztítási folyamatot futtathat.</span><span class="sxs-lookup"><span data-stu-id="e6228-199">You can run the cleanup process manually or automatically to recover the lost numbers.</span></span> 

<span data-ttu-id="e6228-200">A tisztítási folyamat betervezésekor vegye figyelembe, hogy milyen használati terhelés alatt van éppen a szerver.</span><span class="sxs-lookup"><span data-stu-id="e6228-200">Carefully consider server usage when you plan the cleanup process.</span></span> <span data-ttu-id="e6228-201">Javasolt a tisztítás kötegelt feladatként történő futtatása a csúcsidőn kívüli órákban.</span><span class="sxs-lookup"><span data-stu-id="e6228-201">We recommend that you perform the cleanup as a batch job during non-peak hours.</span></span>






