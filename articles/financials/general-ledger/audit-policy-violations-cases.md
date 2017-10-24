---
title: "A könyvvizsgálati irányelvmegsértések és esetek"
description: "Ez a cikk bemutatja, hogyan jönnek létre a naplózási ügyek a naplózási irányelvszabályok megsértése által. Információkat tartalmaz továbbá arról, hogyan alkalmazzák a naplózási irányelvek a dokumentumok határidő-intervallum szerinti kiválasztását."
author: ryansandness
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AuditPolicyAdditionalOption, AuditPolicyRule
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 13091
ms.assetid: e0e66c6d-c396-4a9d-b3b6-3641d130fdc0
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 24ee0dbf01208f8decc167e11e84191eaae03edf
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="audit-policy-violations-and-cases"></a><span data-ttu-id="b92d8-104">A könyvvizsgálati irányelvmegsértések és esetek</span><span class="sxs-lookup"><span data-stu-id="b92d8-104">Audit policy violations and cases</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="b92d8-105">Ez a cikk bemutatja, hogyan jönnek létre a naplózási ügyek a naplózási irányelvszabályok megsértése által.</span><span class="sxs-lookup"><span data-stu-id="b92d8-105">The article explains how audit cases are generated from violations of audit policy rules.</span></span> <span data-ttu-id="b92d8-106">Információkat tartalmaz továbbá arról, hogyan alkalmazzák a naplózási irányelvek a dokumentumok határidő-intervallum szerinti kiválasztását.</span><span class="sxs-lookup"><span data-stu-id="b92d8-106">It also includes information about the various ways that audit policies use the document selection date range.</span></span>

<a name="how-audit-cases-are-generated"></a><span data-ttu-id="b92d8-107">Könyvvizsgálati esetek létrehozásának módja</span><span class="sxs-lookup"><span data-stu-id="b92d8-107">How audit cases are generated</span></span>
-----------------------------

<span data-ttu-id="b92d8-108">Könyvelési irányelvek használatával azonosítani lehet a költségjelentéseket, a beszerzési rendeléseket és a szállítói számlákat, amelyek nem felelnek meg az irányelvszabályként meghatározott és konfigurált üzleti szabályoknak.</span><span class="sxs-lookup"><span data-stu-id="b92d8-108">Audit policies are used to identify expense reports, purchase orders, and vendor invoices that don't comply with business rules that you define and configure as audit policy rules.</span></span> 

<span data-ttu-id="b92d8-109">A könyvvizsgálati irányelvek kötegelt módban futnak.</span><span class="sxs-lookup"><span data-stu-id="b92d8-109">Audit policies are run in batch mode.</span></span> <span data-ttu-id="b92d8-110">A könyvvizsgálati irányelv futtatásakor, az irányelv összes irányelvszabálya egyszerre fut.</span><span class="sxs-lookup"><span data-stu-id="b92d8-110">When you run an audit policy, all the policy rules that are part of that policy are run at the same time.</span></span>

<span data-ttu-id="b92d8-111">Minden egyes irányelvszabály értékel egy dokumentumbeállítást.</span><span class="sxs-lookup"><span data-stu-id="b92d8-111">Each policy rule evaluates a set of documents.</span></span> <span data-ttu-id="b92d8-112">Az irányelvszabály a dokumentumkiválasztási dátumtartományból választ dokumentumot, amely megfelel a megadott feltételnek.</span><span class="sxs-lookup"><span data-stu-id="b92d8-112">The policy rule selects documents that are in the document selection date range and that match the specified criteria.</span></span> <span data-ttu-id="b92d8-113">Például egy irányelvszabály kiválaszthat költség jelentéseker, amelyeknél az étkezések száma meghaladta az 50,00-t.</span><span class="sxs-lookup"><span data-stu-id="b92d8-113">For example, one policy rule might select expense reports that have meals that exceed 50.00.</span></span> <span data-ttu-id="b92d8-114">Egy másik irányelvszabály kiválaszthatja a szállítói számlákat, amelyek fizethetőek egy adott szállítóra.</span><span class="sxs-lookup"><span data-stu-id="b92d8-114">Another policy rule might select vendor invoices that are payable to a specific vendor.</span></span> <span data-ttu-id="b92d8-115">Minden dokumentumhoz, amely a készletben ki van jelölve, megszegés generálódik.</span><span class="sxs-lookup"><span data-stu-id="b92d8-115">For each document that is selected in the set, a violation is generated.</span></span> <span data-ttu-id="b92d8-116">A megsértés egy rekordot, amelyben egy adott dokumentum, például számla 12345, az irányelvszabálynak nem felel meg.</span><span class="sxs-lookup"><span data-stu-id="b92d8-116">That violation is a record that a particular document, such as invoice 12345, doesn't comply with the policy rule.</span></span> 

<span data-ttu-id="b92d8-117">Több könyvelési megsértéssel rendelkező rekordok együtt csoportosítottak és könyvelési esetekhez rendeltek.</span><span class="sxs-lookup"><span data-stu-id="b92d8-117">Multiple audit violation records are grouped together and associated with audit cases.</span></span> <span data-ttu-id="b92d8-118">Alapértelmezés szerint az egyes könyvvizsgálati irányelv esetek könyvvizsgálati irányelvszabály szerint vannak csoportosítva.</span><span class="sxs-lookup"><span data-stu-id="b92d8-118">By default, cases for each audit policy are grouped by audit policy rule.</span></span> <span data-ttu-id="b92d8-119">Ha azt szeretné, be lehet állítani más csoportosítási feltételeket az **Esetcsoportosítási feltételek** lap használatával.</span><span class="sxs-lookup"><span data-stu-id="b92d8-119">If you prefer, you can select other grouping criteria by using the **Case grouping criteria** page.</span></span> <span data-ttu-id="b92d8-120">Például csoportosíthatja a költségfejléceket projektazonosító alapján és a szállítói számlákat szállítókód alapján.</span><span class="sxs-lookup"><span data-stu-id="b92d8-120">For example, you can group expense headers by project ID and vendor invoices by vendor account.</span></span> <span data-ttu-id="b92d8-121">Ebben az esetben az összes a megegyező projektazonosítójú költségfejléc-szabálysértés ugyanahhoz az esethez lesz csoportosítva, és az összes szállítói számla, amelynek azonos a szállítókódja, ugyanahhoz az esethez lesz csoportosítva.</span><span class="sxs-lookup"><span data-stu-id="b92d8-121">In this case, all expense header violations that have the same project ID will be grouped in the same case, and all vendor invoices that have the same vendor account will be grouped in the same case.</span></span> 

> [!NOTE]
> <span data-ttu-id="b92d8-122">A **Másolat** lekérdezéstípuson alapuló könyvvizsgálati irányelvszabály miatt a megszegések nem csoportosulnak irányelvszabály vagy az **Esetcsoportosítási feltételek** lapon megadott feltételek szerint.</span><span class="sxs-lookup"><span data-stu-id="b92d8-122">For audit policy rules that are based on a **Duplicate** query type, violations aren't grouped by policy rule or by the criteria that are specified on the **Case grouping criteria** page.</span></span> <span data-ttu-id="b92d8-123">Ehelyett a könyvvizsgálati irányelvszabályban megadott feltétel alapján csoportosulnak.</span><span class="sxs-lookup"><span data-stu-id="b92d8-123">Instead, they are grouped by the criteria that are built into the audit policy rule.</span></span> <span data-ttu-id="b92d8-124">Például ha egy irányelvszabály értékeli a költségjelentéseket az azonos összeg, kereskedő azonosítója vagy dátum ismétlődő költségeihez, az összes költség, amelynek az értéke megegyezik, egy eset lesz.</span><span class="sxs-lookup"><span data-stu-id="b92d8-124">For example, if a policy rule evaluates expense reports for duplicate expenses of the same amount, merchant ID, and date, all expenses that have the same values in those fields will be one case.</span></span> <span data-ttu-id="b92d8-125">Különböző értékekkel rendelkező kiadások külön esetek lesznek.</span><span class="sxs-lookup"><span data-stu-id="b92d8-125">Any expenses that have different values will be a separate case.</span></span>

<span data-ttu-id="b92d8-126">A Könyvvizsgálati esetek elkészülte az esetkezelés tipikus folyamatának használatával kidásra kerülnek.</span><span class="sxs-lookup"><span data-stu-id="b92d8-126">After the audit cases have been generated, they are handled by using the typical processes for case management.</span></span>

## <a name="document-selection-date-ranges"></a><span data-ttu-id="b92d8-127">Dokumentumkiválasztás dátumtartományok</span><span class="sxs-lookup"><span data-stu-id="b92d8-127">Document selection date ranges</span></span>
<span data-ttu-id="b92d8-128">A könyvvizsgálati irányelv futtatásakor minden irányelvszabály kijelöl adott típusú dokumentumokat, amelyek dátumai a dokumentumkiválasztási dátumtartományba esnek.</span><span class="sxs-lookup"><span data-stu-id="b92d8-128">When an audit policy is run, each policy rule selects documents of the specified type that have a date that is in the document selection date range.</span></span> <span data-ttu-id="b92d8-129">A dokumentumkiválasztási dátumtartományt a **További lehetőségek** oldalon adhatja meg.</span><span class="sxs-lookup"><span data-stu-id="b92d8-129">The document selection date range is specified on the **Additional options** page.</span></span> <span data-ttu-id="b92d8-130">Sok dokumentumhoz több dátum is tartozik.</span><span class="sxs-lookup"><span data-stu-id="b92d8-130">Many documents have more than one date associated with them.</span></span> <span data-ttu-id="b92d8-131">A dátum mező, amelyet könyvvizsgálati irányelvszabály, az **Irányelvszabály-típus** oldalon van megadva.</span><span class="sxs-lookup"><span data-stu-id="b92d8-131">The date field that the audit policy rule uses is specified on the **Policy rule type** page.</span></span>

<span data-ttu-id="b92d8-132">Íme néhány további mód, ahogy a költségvetési irányelv a dokumentumkiválasztási dátumtartományt használja:</span><span class="sxs-lookup"><span data-stu-id="b92d8-132">Here are some other ways that an audit policy uses the document selection date range:</span></span>

-   <span data-ttu-id="b92d8-133">Az irányelv az összes irányelvszabályt alkalmazza, amely érvényes a dokumentumkiválasztási dátumtartomány utolsó napján.</span><span class="sxs-lookup"><span data-stu-id="b92d8-133">The policy uses the version of each policy rule that is effective on the last day of the document selection date range.</span></span> <span data-ttu-id="b92d8-134">Megtekintheti az egyes irányelvszabályok érvényességi dátumait a **Könyvviteli irányelvek** listaoldalán.</span><span class="sxs-lookup"><span data-stu-id="b92d8-134">You can view the effective dates for each policy rule on the **Audit policies** list page.</span></span>
-   <span data-ttu-id="b92d8-135">A irányelv használja a szervezeti csomópontokat, amelyek az irányelvhez társítottak a dokumentumkiválasztási dátumtartomány utolsó napján.</span><span class="sxs-lookup"><span data-stu-id="b92d8-135">The policy uses the organization nodes that are associated with the policy on the last day of the document selection date range.</span></span> <span data-ttu-id="b92d8-136">Csak az irányelv jelenleg kapcsolódó szervezeti csomópontok jelennek meg a **Könyvviteli irányelvek** listaoldalán.</span><span class="sxs-lookup"><span data-stu-id="b92d8-136">Only the organization nodes that are currently associated with the policy appear on the **Audit policies** list page.</span></span>
-   <span data-ttu-id="b92d8-137">Az irányelvszabályok, amelyek **Keresés lista** lekérdezés típuson alapszanak, az irányelv értékeli a dokumentumokat a figyelt entitásokhoz, amelyek érvényesek a dokumentumkiválasztási dátumtartomány utolsó napján.</span><span class="sxs-lookup"><span data-stu-id="b92d8-137">For policy rules that are based on a **List search** query type, the policy evaluates documents for monitored entities that are effective on the last day of the document selection date range.</span></span>


<span data-ttu-id="b92d8-138">További információ: [Könyvvizsgálati irányelvszabály](audit-policy-rules.md)</span><span class="sxs-lookup"><span data-stu-id="b92d8-138">For more information, see [Audit policy rules](audit-policy-rules.md)</span></span>



