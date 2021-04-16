---
title: Feladásdefiníciók
description: A cikk feladás-definíciókról, valamint azok meghatározásáról és linkeléséről biztosít információt. A támogatott feladási típusok és dokumentumok esetében feladásdefiníciókat használhat a feladási profilok helyett, és ezekkel osztályozhatja a fő számlákat és a pénzügyi dimenziókat a könyvelési tételekben.
author: ShylaThompson
ms.date: 09/03/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JournalizingDefinition, JournalizingDefinitionTrans, LedgerParameters
audience: Application User
ms.reviewer: roschlom
ms.custom: 15741
ms.assetid: 1495e7e0-2e39-464c-8da9-f55b1ca1c6bb
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 80477fc123c562de71f58c8bd45ad7c4ea4e6fec
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815500"
---
# <a name="posting-definitions"></a><span data-ttu-id="d1083-104">Feladásdefiníciók</span><span class="sxs-lookup"><span data-stu-id="d1083-104">Posting definitions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d1083-105">A cikk feladás-definíciókról, valamint azok meghatározásáról és linkeléséről biztosít információt.</span><span class="sxs-lookup"><span data-stu-id="d1083-105">This article provides information about posting definitions, and how to define and link them.</span></span>
<span data-ttu-id="d1083-106">A támogatott feladási típusok és dokumentumok esetében feladásdefiníciókat használhat a feladási profilok helyett, és ezekkel osztályozhatja a fő számlákat és a pénzügyi dimenziókat a könyvelési tételekben.</span><span class="sxs-lookup"><span data-stu-id="d1083-106">For supported posting types and documents, you can use posting definitions instead of posting profiles to classify main accounts and financial dimensions on accounting entries.</span></span> <span data-ttu-id="d1083-107">A támogatott dokumentumok és feladási típusok listáját a **Tranzakció-feladásdefiníciók** oldalon tekintheti meg.</span><span class="sxs-lookup"><span data-stu-id="d1083-107">You can view the supported documents and posting types on the **Transaction posting definitions** page.</span></span> 

<span data-ttu-id="d1083-108">A feladásdefiníciók használatának megkezdéséhez jelölje be a **Feladásdefiníciók használata** opciót a **Főkönyvi paraméterek** oldalon.</span><span class="sxs-lookup"><span data-stu-id="d1083-108">To start using posting definitions, select the **Use posting definitions** option on the **General ledger parameters** page.</span></span> <span data-ttu-id="d1083-109">Még a feladásdefiníciók használata esetén is kell definiálnia feladási profilokat az eredeti bejegyzések és a nem támogatott feladási típusok és dokumentumok számára.</span><span class="sxs-lookup"><span data-stu-id="d1083-109">Even when you use posting definitions, you must still define posting profiles for the originating entries and non-supported posting types and documents.</span></span> 

<span data-ttu-id="d1083-110">Feladásdefiníciókat kell használnia annak érdekében, hogy lehetővé tegye a kötelezettségvállalás-könyvelést a beszerzési rendeléseknél, és a használja, és a pre-kötelezettségvállalási könyvelsét beszerzési igényléseknél.</span><span class="sxs-lookup"><span data-stu-id="d1083-110">You must use posting definitions in order to enable encumbrance accounting for purchase orders and pre-encumbrance accounting for purchase requisitions.</span></span>

## <a name="defining-posting-definitions"></a><span data-ttu-id="d1083-111">Feladásdefiníciók meghatározása</span><span class="sxs-lookup"><span data-stu-id="d1083-111">Defining posting definitions</span></span>
<span data-ttu-id="d1083-112">A **Feladásdefiníciók** lapon adhatja meg az egyeztetési feltételeket és határozhatja meg azokat a bejegyzéseket, amelyeket a rendszer egyezés esetén kell generáljon.</span><span class="sxs-lookup"><span data-stu-id="d1083-112">Use the **Posting definitions** page to specify the match criteria and define the entries that should be generated when a match occurs.</span></span> <span data-ttu-id="d1083-113">A egyezési feltételeket az eredeti bejegyzésekre vonatkozóan könyvelési felosztásként értékeli a rendszer.</span><span class="sxs-lookup"><span data-stu-id="d1083-113">The match criteria are evaluated for the originating entries as accounting distributions.</span></span> 

<span data-ttu-id="d1083-114">A **Feladásdefiníciók** lapon prioritási számértékeket is hozzárendelhet a beérkezési sorokhoz, így vezérelheti, hogy milyen sorrendben értékelje őket a rendszer.</span><span class="sxs-lookup"><span data-stu-id="d1083-114">On the **Posting definitions** page, you can also assign priority numbers to entry lines to control the order in which the lines are evaluated.</span></span> <span data-ttu-id="d1083-115">A legalacsonyabb prioritási számú sorokat fogja először értékelni.</span><span class="sxs-lookup"><span data-stu-id="d1083-115">The lines that have the lowest priority number are evaluated first.</span></span> <span data-ttu-id="d1083-116">Így például először az 1. prioritási számú sorok következnek, majd a 2. számúak, satöbbi.</span><span class="sxs-lookup"><span data-stu-id="d1083-116">For example, all lines that have a priority of 1 are evaluated, and then lines that have a priority of 2, and so on.</span></span> <span data-ttu-id="d1083-117">Egyezés esetén a többi egyezési feltétel figyelmen kívül lesz hagyva.</span><span class="sxs-lookup"><span data-stu-id="d1083-117">When a match is found, the other match criteria are ignored.</span></span> <span data-ttu-id="d1083-118">Emellett csak azon feltétel generál majd bejegyzést, amely az eredeti tranzakcióval is egyezik.</span><span class="sxs-lookup"><span data-stu-id="d1083-118">Additionally, only the criteria in the group that match the originating transaction create generated entries.</span></span> 

<span data-ttu-id="d1083-119">A feladásdefiníciókat a **Tesztelje a feladásdefiníciót** varázsló segítségével ellenőrizheti.</span><span class="sxs-lookup"><span data-stu-id="d1083-119">You can validate your posting definitions by using the **Test posting definition** wizard.</span></span> <span data-ttu-id="d1083-120">Miután definiált egy mintaként szolgáló eredeti bejegyzést a feladásdefinícióhoz, megjelennek a létrehozott bejegyzések.</span><span class="sxs-lookup"><span data-stu-id="d1083-120">After you define a sample originating entry for a posting definition, you'll see the generated entries.</span></span> 

<span data-ttu-id="d1083-121">A feladásdefiníció-verziókat érvényességi dátumokkal együtt használhatja.</span><span class="sxs-lookup"><span data-stu-id="d1083-121">You can use posting definition versions together with effective dates.</span></span> <span data-ttu-id="d1083-122">Példáu létrehozhat egy jövőbeli verziót egy feladásdefinícióból, amelyet az új pénzügyi évben egy másik főkönyvre való feladásokhoz használhat.</span><span class="sxs-lookup"><span data-stu-id="d1083-122">For example, you can create a future version of a posting definition to post to a different ledger account in a new fiscal year.</span></span> 

<span data-ttu-id="d1083-123">A **Tranzakció-feladásdefiníciók** oldalon rendelhet hozzá feladásdefiníciókat a tranzakciótípusokhoz.</span><span class="sxs-lookup"><span data-stu-id="d1083-123">Use the **Transaction posting definitions** page to assign posting definitions to transaction types.</span></span>

## <a name="linking-posting-definitions"></a><span data-ttu-id="d1083-124">Feladásdefiníciók összekapcsolása</span><span class="sxs-lookup"><span data-stu-id="d1083-124">Linking posting definitions</span></span>
<span data-ttu-id="d1083-125">A feladásdefiníciók létrehozásakor hozzá is kapcsolhatja azokat egy másikhoz.</span><span class="sxs-lookup"><span data-stu-id="d1083-125">You can link from one posting definition to another when you create posting definitions.</span></span> <span data-ttu-id="d1083-126">A rendszer ezek után az aktuális feladásdefiníció feltételeinek kiegészítéseként figyelembe veszi a hozzákapcsolt definíció feltételeit is.</span><span class="sxs-lookup"><span data-stu-id="d1083-126">The criteria for the definition that you linked to are then considered in addition to the criteria for the current posting definition.</span></span> <span data-ttu-id="d1083-127">Ezzel a funkcióval idő takarítható meg, mert nem kell ismételten megadnia a feltételeket az akatuális feladásdefinícióhoz a **Bejegyzések** gyorslapon a **Feladásdefiníciók** oldalon, ha azokat egy másik definícióban már rögzítette.</span><span class="sxs-lookup"><span data-stu-id="d1083-127">This feature helps save you time, because you don't have to reenter criteria on the **Entries** FastTab on the **Posting definitions** page for the current posting definition if you already entered those lines for another definition.</span></span> 

<span data-ttu-id="d1083-128">A diagramokon és a táblákban rögzítsen minden hivatkozást, amelyet a későbbiekben még használni szeretne.</span><span class="sxs-lookup"><span data-stu-id="d1083-128">In the diagrams or tables, include any links that you might use.</span></span> <span data-ttu-id="d1083-129">Az aktuális feladásdefinícióval való ütközés elkerülése érdekében ügyeljen rá, hogy minden hivatkozott feladásdefiníció sorai egyedi legyen.</span><span class="sxs-lookup"><span data-stu-id="d1083-129">To avoid conflicts with the current posting definition, make sure that the lines in any posting definitions that you link to are unique.</span></span> 

<span data-ttu-id="d1083-130">Az alábbi korlátozásokkal kell számolnia a feladásdefiníció-összekapcsolások létrehozásakor:</span><span class="sxs-lookup"><span data-stu-id="d1083-130">The following restrictions apply when you create links in posting definitions:</span></span>

-   <span data-ttu-id="d1083-131">Egy adott feladásdefinícióból vagy egy másikra hivatkozhat, vagy egy másikból hivatkozhat erre, de nem lehet mindkettő.</span><span class="sxs-lookup"><span data-stu-id="d1083-131">A given posting definition can either link to another posting definition or be linked to from another posting definition, but not both.</span></span> <span data-ttu-id="d1083-132">Egy feladásdefiníció azoban több másikra is hivatkozhat.</span><span class="sxs-lookup"><span data-stu-id="d1083-132">However, a posting definition can link to multiple posting definitions.</span></span>
-   <span data-ttu-id="d1083-133">Csak olyan feladásdefiníciók között állíthat fel kapcsolatot, amelyek ugyanabban a modulban találhatóak.</span><span class="sxs-lookup"><span data-stu-id="d1083-133">You can set up links only among posting definitions that are in the same module.</span></span>
-   <span data-ttu-id="d1083-134">Egy feladásdefiníciót bármely tranzakciótípushoz hozzárendelhet, de a tranzakciótípus is ugyanabban a modulban kell legyen, mint a feladásdefiníció.</span><span class="sxs-lookup"><span data-stu-id="d1083-134">You can assign a posting definition to any transaction type, but the transaction type must be in the same module as the posting definition.</span></span> <span data-ttu-id="d1083-135">Használja a **Tranzakció-feladásdefiníciók** lapot, ahol láthatja, melyik modulban szerepel egy adott tranzakciótípus.</span><span class="sxs-lookup"><span data-stu-id="d1083-135">Use the **Transaction posting definitions** page to see what module a transaction type is in.</span></span>


<span data-ttu-id="d1083-136">További információkért lásd: [A feladásdefiníció példái](example-posting-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="d1083-136">For more information, see [Posting definition examples](example-posting-definitions.md).</span></span> 




[!INCLUDE[footer-include](../../includes/footer-banner.md)]