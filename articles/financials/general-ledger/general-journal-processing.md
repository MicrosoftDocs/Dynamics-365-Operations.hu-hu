---
title: "Általános napló feldolgozása"
description: "Ez a cikk a Microsoft Dynamics 365 for Finance and Operations, Enterprise kiadásban szereplő funkciókat mutatja be, amelyek megkönnyítik az általános napló feldolgozását, illetve garantálják a megfelelő adatok tárolását, a belső ellenőrzés megfelelő működését."
author: twheeloc
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: c4f5dae90c5fcaaa52a7087d7c20b2de343b7da0
ms.openlocfilehash: 68da281cb4793ed83f70c68d061d327aa8a8c772
ms.contentlocale: hu-hu
ms.lasthandoff: 08/01/2017

---

# <a name="general-journal-processing"></a><span data-ttu-id="d3f06-103">Általános napló feldolgozása</span><span class="sxs-lookup"><span data-stu-id="d3f06-103">General journal processing</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="d3f06-104">Ez a cikk a Microsoft Dynamics 365 for Finance and Operations, Enterprise kiadásban szereplő funkciókat mutatja be, amelyek megkönnyítik az általános napló feldolgozását, illetve garantálják a megfelelő adatok tárolását, a belső ellenőrzés megfelelő működését.</span><span class="sxs-lookup"><span data-stu-id="d3f06-104">This articles describes capabilities in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition that can help make general journal processing easier, and that can also help guarantee that correct data is captured and internal control isn't compromised.</span></span>  

<span data-ttu-id="d3f06-105">Naplónevek</span><span class="sxs-lookup"><span data-stu-id="d3f06-105">Journal names</span></span>

<span data-ttu-id="d3f06-106">Az egyik legfontosabb beállítandó terület a naplónév.</span><span class="sxs-lookup"><span data-stu-id="d3f06-106">One of the most important areas to set up is journal names.</span></span> <span data-ttu-id="d3f06-107">Érdemes minden célhoz külön naplónevet megadni (pl.: vállalatközi, elhatároláskiigazítás és hibajavítás).</span><span class="sxs-lookup"><span data-stu-id="d3f06-107">It's a good idea to define specific journal names for each purpose, such as intercompany, accrual adjustment, and error correction.</span></span> <span data-ttu-id="d3f06-108">A naplónevek személyre szabásával az egyes célokhoz való adatbevitelt egyszerűbbé és biztonságosabbá teheti.</span><span class="sxs-lookup"><span data-stu-id="d3f06-108">You can tailor each journal name to help make data entry for each purpose easy and secure.</span></span> 

<span data-ttu-id="d3f06-109">A **Naplónevek** lapon az alábbi elemeket állíthatja be:</span><span class="sxs-lookup"><span data-stu-id="d3f06-109">On the **Journal names** page, you can set up the following elements:</span></span>

-   <span data-ttu-id="d3f06-110">**Munkafolyamat-jóváhagyás** – A belső ellenőrzés javítása érdekében olyan napló-munkafolyamatokat határozzon meg, amelyek fontossági határokat szabnak az ellenőrzési és jóváhagyási lépésekhez például a tartozás teljes összege alapján.</span><span class="sxs-lookup"><span data-stu-id="d3f06-110">**Workflow approval** – To increase internal control, define journal workflows that establish materiality limits for review and approval steps, based on criteria such as total debit amount.</span></span> <span data-ttu-id="d3f06-111">Az általános naplókhoz a **Főkönyvi munkafolyamatok** lapon állíthat be munkafolyamatokat.</span><span class="sxs-lookup"><span data-stu-id="d3f06-111">You set up workflows for the general journals on the** General ledger workflows** page.</span></span>
-   <span data-ttu-id="d3f06-112">**Alapértelmezett értékek** – Válassza ki az alapértelmezett értékeket az ellenszámlákhoz, pénznemhez és pénzügyi dimenziókhoz.</span><span class="sxs-lookup"><span data-stu-id="d3f06-112">**Default values** – Select default values for offset accounts, currency, and financial dimensions.</span></span>
-   <span data-ttu-id="d3f06-113">**Napló ellenőrzése** – Beállíthat korlátozásokat a vállalatra és a számlatípusra, de akár a szegmensértékekre is.</span><span class="sxs-lookup"><span data-stu-id="d3f06-113">**Journal control** – You can set up restrictions on the company and account type, and also the segment values.</span></span> 

<span data-ttu-id="d3f06-114">**Példák**</span><span class="sxs-lookup"><span data-stu-id="d3f06-114">**Examples**</span></span>

<span data-ttu-id="d3f06-115">A naplónév csak módosításokra használható.</span><span class="sxs-lookup"><span data-stu-id="d3f06-115">A journal name can be used only for adjustments.</span></span> <span data-ttu-id="d3f06-116">Ebben az esetben megadhatja, hogy csak a **Főkönyv** számlatípus legyen érvényes minden vállalat esetében.</span><span class="sxs-lookup"><span data-stu-id="d3f06-116">In this case, you can specify that only the **Ledger** account type is valid across all companies.</span></span> <span data-ttu-id="d3f06-117">[![Napló-ellenőrzési számlatípusok](./media/journal-control-account-types1.png)](./media/journal-control-account-types1.png)</span><span class="sxs-lookup"><span data-stu-id="d3f06-117">[![Journal control account types](./media/journal-control-account-types1.png)](./media/journal-control-account-types1.png)</span></span>

<span data-ttu-id="d3f06-118">A naplónév csak egy adott szegmens vagy egy tartomány esetében használható fő számlákhoz.</span><span class="sxs-lookup"><span data-stu-id="d3f06-118">A journal name can be used only for a specific segment or for a range for main accounts.</span></span> <span data-ttu-id="d3f06-119">[![Naplóellenőrzési szegmens](./media/journal-control-segment1.png)](./media/journal-control-segment1.png)</span><span class="sxs-lookup"><span data-stu-id="d3f06-119">[![Journal control segment](./media/journal-control-segment1.png)](./media/journal-control-segment1.png)</span></span>

<span data-ttu-id="d3f06-120">Az **Automatikus sztornírozás** lehetőség elérhető az általános naplók esetében.</span><span class="sxs-lookup"><span data-stu-id="d3f06-120">The **Automatic reversal** option is available in general journals.</span></span> <span data-ttu-id="d3f06-121">Tegyük fel például, hogy van egy elhatároláskiigazítása, ahol a tényleges dokumentum feldolgozása még nem történt meg (lásd az alábbi ábrán).</span><span class="sxs-lookup"><span data-stu-id="d3f06-121">For example, you have an accrual adjustment where the actual document hasn't yet been processed, as shown in the following illustration.</span></span>
<span data-ttu-id="d3f06-122">[![Általános napló sztornírozása](./media/general-journal-reversing1.png)](./media/general-journal-reversing1.png)</span><span class="sxs-lookup"><span data-stu-id="d3f06-122">[![General journal reversing](./media/general-journal-reversing1.png)](./media/general-journal-reversing1.png)</span></span> 

<span data-ttu-id="d3f06-123">A Microsoft Excel-bővítmény naplóbejegyzésekhez még nagyobb automatizálást és egyszerűbb adatbevitelt tesz lehetővé.</span><span class="sxs-lookup"><span data-stu-id="d3f06-123">The Microsoft Excel add-in for journal entry provides an additional level of automation and makes data entry easier.</span></span> <span data-ttu-id="d3f06-124">A **Sorok megnyitása az Excelben** művelet elérhető az **Általános napló** és **Naplóbizonylat** oldalakon.</span><span class="sxs-lookup"><span data-stu-id="d3f06-124">The **Open lines in Excel** action is available on the **General journal** and **Journal voucher** pages.</span></span> 

<span data-ttu-id="d3f06-125">Az **Időszakos naplók** oldalon beállíthatja az ismétlődő naplókra a naplófeldolgozás automatizálását.</span><span class="sxs-lookup"><span data-stu-id="d3f06-125">On the **Periodic journals** page, you can set up recurring journals to automate journal processing.</span></span> 

<span data-ttu-id="d3f06-126">Bizonylatsorokat bármikor használhat.</span><span class="sxs-lookup"><span data-stu-id="d3f06-126">You can use voucher templates at any time.</span></span> <span data-ttu-id="d3f06-127">Az **Általános naplók** oldalon a **Mentés** és **Bizonylatsablon kiválasztása** műveleteket a **Bizonylatsablon** oldalon találja, a bizonylatsorok **Funkciók** lehetősége alatt.</span><span class="sxs-lookup"><span data-stu-id="d3f06-127">On the **General journals** page, the **Save** and **Select voucher template** actions are found on the **Journal voucher** page, under **Functions** for the voucher lines.</span></span>

## <a name="related-setup"></a><span data-ttu-id="d3f06-128">Kapcsolódó beállítások</span><span class="sxs-lookup"><span data-stu-id="d3f06-128">Related setup</span></span>
<span data-ttu-id="d3f06-129">A következő beállítások nem csak az általános naplókra vonatkoznak, de segítik a helyes és egyszerű adatbevitelt.</span><span class="sxs-lookup"><span data-stu-id="d3f06-129">The following setup isn't specific to general journals, but will help guarantee that data entry is correct data and easy.</span></span>

### <a name="main-account"></a><span data-ttu-id="d3f06-130">Fő számla</span><span class="sxs-lookup"><span data-stu-id="d3f06-130">Main account</span></span>

<span data-ttu-id="d3f06-131">A fő számla beállítás számos lehetőséget nyújt az általános napló feldolgozására:</span><span class="sxs-lookup"><span data-stu-id="d3f06-131">The main account setup provides many options for general journal processing:</span></span>

-   <span data-ttu-id="d3f06-132">**DC/CR követelmény** – Ezt a beállítást akkor használja, ha a fő számla terhelési vagy jóváírási tranzakciókra van korlátozva.</span><span class="sxs-lookup"><span data-stu-id="d3f06-132">**DC/CR requirement** – Use this option if a main account is limited to debit or credit transactions.</span></span> <span data-ttu-id="d3f06-133">A beállítás jóváhagyása a napló ellenőrzése vagy feladása alkalmával történik.</span><span class="sxs-lookup"><span data-stu-id="d3f06-133">The setup is verified when a journal is validated or posted.</span></span>
-   <span data-ttu-id="d3f06-134">**Alapértelmezett ellenszámla**</span><span class="sxs-lookup"><span data-stu-id="d3f06-134">**Default offset account**</span></span>
-   <span data-ttu-id="d3f06-135">**Felfüggesztett** – Felfüggeszti egy fő számla adatbevitelét minden vállalatnál vagy egy adott vállalatnál/jogi személynél.</span><span class="sxs-lookup"><span data-stu-id="d3f06-135">**Suspended** – Suspend a main account for data entry across all companies or for a specific company/legal entities.</span></span>
-   <span data-ttu-id="d3f06-136">**Manuális bevitel tiltása** – Megakadályozza, hogy a felhasználók maguk adjanak meg értékeket a számlához a naplókban.</span><span class="sxs-lookup"><span data-stu-id="d3f06-136">**Do not allow manual entry** – Prevent users from manually entering a value for the account in journals.</span></span>
-   <span data-ttu-id="d3f06-137">**Pénznem alapértelmezése/érvényesítése**</span><span class="sxs-lookup"><span data-stu-id="d3f06-137">**Default/Validate currency**</span></span>
-   <span data-ttu-id="d3f06-138">**Jogi személy felülbírálása** – Ez a beállítás csak a meghatározott vállalatra vagy jogi személyre vonatkozik:</span><span class="sxs-lookup"><span data-stu-id="d3f06-138">**Legal entity override** – This setup is specific to the defined company/legal entity:</span></span>
    -   <span data-ttu-id="d3f06-139">**Áfa alapértelmezése/érvényesítése**</span><span class="sxs-lookup"><span data-stu-id="d3f06-139">**Default/Validate sales tax**</span></span>
    -   <span data-ttu-id="d3f06-140">**Alapértelmezett dimenzió** – **Nem rögzített** vagy **Rögzített érték**.</span><span class="sxs-lookup"><span data-stu-id="d3f06-140">**Default dimension** – **Not fixed** or **Fixed value**.</span></span> <span data-ttu-id="d3f06-141">**Rögzített érték** segítségével garantálható, hogy a feladások mind a fő számlához mindig olyan dimenzióértéket használjanak, amely **Rögzített** beállítású.</span><span class="sxs-lookup"><span data-stu-id="d3f06-141">**Fixed value** will help guarantee that all postings for this main account always use any dimension value that is set up as **Fixed**.</span></span>
-   <span data-ttu-id="d3f06-142">**Feladás ellenőrzése**</span><span class="sxs-lookup"><span data-stu-id="d3f06-142">**Posting validation**</span></span>
    -   <span data-ttu-id="d3f06-143">**Felhasználó érvényesítése** – Ez a beállítás szabályozza, hogy mely felhasználók jogosultak olyan a fő számlára való feladásra.</span><span class="sxs-lookup"><span data-stu-id="d3f06-143">**User validation** – This option controls which users are allowed to post to a main account.</span></span>
    -   <span data-ttu-id="d3f06-144">**Feladási típus érvényesítése** – Ez a beállítás szabályozza, hogy mely feladási típusok megengedettek a fő számlához.</span><span class="sxs-lookup"><span data-stu-id="d3f06-144">**Posting type validation** – This option controls which posting types are allowed for a main account.</span></span>

### <a name="accounting-structures-and-advanced-rules-structures"></a><span data-ttu-id="d3f06-145">Könyvelési szerkezetek és a speciális szabályok szerkezetei</span><span class="sxs-lookup"><span data-stu-id="d3f06-145">Accounting structures and advanced rules structures</span></span>

<span data-ttu-id="d3f06-146">A könyvelési szerkezetek és a speciális szabályok szerkezetei rendkívül fontosak, mert ezekkel biztosítható, hogy a pénzügyi jelentés készítéséhez és teljesítéskövetéséhez szükséges adatok rögzítése megtörténik az általános napló vagy bármilyen dokumentum feldolgozása során.</span><span class="sxs-lookup"><span data-stu-id="d3f06-146">Accounting structures and advanced rules structures are extremely important for guaranteeing that the data that is required for financial reporting and performance tracking is captured during general journal processing and any documentation.</span></span> <span data-ttu-id="d3f06-147">A könyvelési szerkezetek és a speciális szabályok szerkezetei segítségével személyre szabhatja az adatbeviteli élményt.</span><span class="sxs-lookup"><span data-stu-id="d3f06-147">Accounting structures and advanced rules structures let you tailor the data entry experience.</span></span> <span data-ttu-id="d3f06-148">Megszabhatja, hogy csak a helyzethez kapcsolódó pénzügyi dimenziók adatbevitele legyen lehetséges, és kötelezővé teheti azt a feltételt, mely alapján a megfelelő adat mindig rögzítésre kerül.</span><span class="sxs-lookup"><span data-stu-id="d3f06-148">You can allow data entry only for financial dimensions that are relevant in each situation, and can also enforce the requirement that mandatory and correct data always be captured.</span></span>

<span data-ttu-id="d3f06-149">További információ a következő témakörökben olvasható:</span><span class="sxs-lookup"><span data-stu-id="d3f06-149">For more information, see the following topics:</span></span>
- <span data-ttu-id="d3f06-150">[Tervezés: számlatükör](plan-chart-of-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="d3f06-150">[Planning: Chart of accounts](plan-chart-of-accounts.md).</span></span> 
- [<span data-ttu-id="d3f06-151">Speciális szabályok létrehozása naplók részére</span><span class="sxs-lookup"><span data-stu-id="d3f06-151">Create advanced rules for journals</span></span>](tasks/create-advanced-rules-journals.md)
- [<span data-ttu-id="d3f06-152">Naplóbejegyzés létrehozása sablon alapján</span><span class="sxs-lookup"><span data-stu-id="d3f06-152">Create a journal entry using a template</span></span>](tasks/create-journal-entry-template.md)
- [<span data-ttu-id="d3f06-153">Naplók létrehozása és érvényesítése</span><span class="sxs-lookup"><span data-stu-id="d3f06-153">Create and validate journals</span></span>](tasks/create-validate-journals.md)
- [<span data-ttu-id="d3f06-154">Időszaki naplók közzététele</span><span class="sxs-lookup"><span data-stu-id="d3f06-154">Post periodic journals</span></span>](tasks/post-periodic-journals.md)
- [<span data-ttu-id="d3f06-155">Főkönyvi felosztási napló feldolgozása</span><span class="sxs-lookup"><span data-stu-id="d3f06-155">Process ledger allocation journal</span></span>](tasks/process-ledger-allocation-journal.md)



