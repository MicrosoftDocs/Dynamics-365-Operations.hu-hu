---
title: "Könyvvizsgálati irányelvszabály"
description: "Naplózási házirendek segítségével kiértékelhet költségjelentéseket, szállítói számlákat és beszerzési rendeléseket, hogy így meggyőződhessen arról, hogy azok megfelelnek-e az Ön által létrehozandó irányelvszabályoknak. Minden olyan szabály, amelyhez egy könyvvizsgálati irányelv van társítva, kötegelt módban van futtatva a megadott ütemezés szerint.  Minden egyes irányelvszabály egy irányelvszabály-típus egy példánya. Minden egyes irányelvszabály-típusra nézve csak egy irányelvszabály lehet aktív egyszerre."
author: ryansandness
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AuditPolicyAdditionalOption, AuditPolicyRule
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 12991
ms.assetid: 8d787017-71dc-418f-b8c2-4ea9763d9978
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 04217e162090720d2a48c96aa9356cea2dbfa230
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="audit-policy-rules"></a><span data-ttu-id="3b85d-106">Könyvvizsgálati irányelvszabály</span><span class="sxs-lookup"><span data-stu-id="3b85d-106">Audit policy rules</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="3b85d-107">Naplózási házirendek segítségével kiértékelhet költségjelentéseket, szállítói számlákat és beszerzési rendeléseket, hogy így meggyőződhessen arról, hogy azok megfelelnek-e az Ön által létrehozandó irányelvszabályoknak.</span><span class="sxs-lookup"><span data-stu-id="3b85d-107">You can use audit policies to evaluate expense reports, vendor invoices, and purchase orders to make sure that they comply with policy rules that you create.</span></span> <span data-ttu-id="3b85d-108">Minden olyan szabály, amelyhez egy könyvvizsgálati irányelv van társítva, kötegelt módban van futtatva a megadott ütemezés szerint.</span><span class="sxs-lookup"><span data-stu-id="3b85d-108">All of the rules that are associated with an audit policy are run in batch mode, according to a schedule that you specify.</span></span>  <span data-ttu-id="3b85d-109">Minden egyes irányelvszabály egy irányelvszabály-típus egy példánya.</span><span class="sxs-lookup"><span data-stu-id="3b85d-109">Each policy rule is an instance of a policy rule type.</span></span> <span data-ttu-id="3b85d-110">Minden egyes irányelvszabály-típusra nézve csak egy irányelvszabály lehet aktív egyszerre.</span><span class="sxs-lookup"><span data-stu-id="3b85d-110">For each policy rule type, only one policy rule can be active at a time.</span></span> 

<a name="queries-and-query-types"></a><span data-ttu-id="3b85d-111">Lekérdezések és a lekérdezéstípusok</span><span class="sxs-lookup"><span data-stu-id="3b85d-111">Queries and query types</span></span>
-----------------------

<span data-ttu-id="3b85d-112">Ha könyvvizsgálati irányelvszabályt hoz létre, először irányelvszabály-típust választ.</span><span class="sxs-lookup"><span data-stu-id="3b85d-112">When you create an audit policy rule, you first select a policy rule type.</span></span> <span data-ttu-id="3b85d-113">Az irányelvszabály-típus megadja az irányelvszabályok létrehozásának kiinduló pontjaként használandó alkalmazásobjektum-fa (AOT) lekérdezést.</span><span class="sxs-lookup"><span data-stu-id="3b85d-113">The policy rule type specifies the Application Object Tree (AOT) query to use as the starting point for creating the policy rule.</span></span> <span data-ttu-id="3b85d-114">Az irányelvszabályhoz használandó lekérdezés típusát is megadja.</span><span class="sxs-lookup"><span data-stu-id="3b85d-114">It also specifies the query type to use for the policy rule.</span></span> <span data-ttu-id="3b85d-115">A lekérdezés meghatározza azt a forrásbizonylatot, amit az irányelvszabály kiértékel.</span><span class="sxs-lookup"><span data-stu-id="3b85d-115">The query determines the source document that the policy rule evaluates.</span></span> <span data-ttu-id="3b85d-116">Azokat a mezőket is megadja a forrásdokumentumban, amelyek mind a jogi személyt mind a használandó dátumot azonosítják, amikor dokumentumokat választanak ki ellenőrzésre.</span><span class="sxs-lookup"><span data-stu-id="3b85d-116">It also specifies the fields in the source document that identify both the legal entity and the date to use when documents are selected for audit.</span></span> <span data-ttu-id="3b85d-117">A lekérdezéstípus meghatározza a lekérdezési oldalon és a Könyvviteli irányelvszabály oldalon levő alapértelmezett mezőket.</span><span class="sxs-lookup"><span data-stu-id="3b85d-117">The query type controls the default fields in the query page and in the Audit policy rule page.</span></span> <span data-ttu-id="3b85d-118">Az alábbi táblázatban az audit-irányelvszabályokhoz elérhető lekérdezéstípusok felsorolása található.</span><span class="sxs-lookup"><span data-stu-id="3b85d-118">The following table shows the query types that are available for audit policy rules.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3b85d-119">Lekérdezés típusa</span><span class="sxs-lookup"><span data-stu-id="3b85d-119">Query type</span></span></th>
<th><span data-ttu-id="3b85d-120">Cél</span><span class="sxs-lookup"><span data-stu-id="3b85d-120">Purpose</span></span></th>
<th><span data-ttu-id="3b85d-121">További információ</span><span class="sxs-lookup"><span data-stu-id="3b85d-121">More information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="3b85d-122">Feltételes</span><span class="sxs-lookup"><span data-stu-id="3b85d-122">Conditional</span></span></td>
<td><span data-ttu-id="3b85d-123">Értékelje ki a forrásdokumentum attribútumait megadott értékek ellenében.</span><span class="sxs-lookup"><span data-stu-id="3b85d-123">Evaluate source document attributes against specified values.</span></span></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3b85d-124">Összesítés</span><span class="sxs-lookup"><span data-stu-id="3b85d-124">Aggregate</span></span></td>
<td><span data-ttu-id="3b85d-125">A numerikus értékek összesítésével értékelje a többszörös forrásbizonylatokat vagy forrásbizonylat-sorokat az irányelvszabállyal összehasonlítva.</span><span class="sxs-lookup"><span data-stu-id="3b85d-125">Evaluate multiple source documents or source document lines against a policy rule by aggregating numeric values.</span></span></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="3b85d-126">Mintavétel</span><span class="sxs-lookup"><span data-stu-id="3b85d-126">Sampling</span></span></td>
<td><span data-ttu-id="3b85d-127">Az irányelvszegések megállapításához válasszon ki véletlenszerűen egy meghatározott százalékarányú forrásbizonylatot.</span><span class="sxs-lookup"><span data-stu-id="3b85d-127">Randomly select a specified percentage of the source documents to evaluate for policy violations.</span></span></td>
<td><span data-ttu-id="3b85d-128">Ha ezt a lehetőséget választja, a Könyvviteli irányelvszabály oldalon adja meg az ellenőrzésre véletlenszerűen kiválasztandó bizonylatok százalékos arányát.</span><span class="sxs-lookup"><span data-stu-id="3b85d-128">When you select this option, use the Audit policy rule page to specify the percentage of documents to randomly select for audit.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3b85d-129">Másolat</span><span class="sxs-lookup"><span data-stu-id="3b85d-129">Duplicate</span></span></td>
<td><span data-ttu-id="3b85d-130">Értékelje a forrásbizonylatokat abból a szempontból, hogy tartalmaznak-e a megadott mezőkben ismétlődő bejegyzéseket.</span><span class="sxs-lookup"><span data-stu-id="3b85d-130">Evaluate source documents to determine whether they contain duplicate entries in specified fields.</span></span></td>
<td><span data-ttu-id="3b85d-131">Ha ezt a lehetőséget választja, használja a Könyvviteli irányelvszabály oldalt a bizonylatok kiválasztásához megadandó dátumtartomány kezdetéhez hozzáadandó napok számának megadásához, amikor a bizonylatokban ismétlődő bejegyzéseket keres.</span><span class="sxs-lookup"><span data-stu-id="3b85d-131">When you select this option, use the Audit policy rule page to specify the number of days to add to the start of the document selection date range when documents are evaluated for duplicate entries.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="3b85d-132">Keresés listán</span><span class="sxs-lookup"><span data-stu-id="3b85d-132">List search</span></span></td>
<td><span data-ttu-id="3b85d-133">Konkrét entitások forrásbizonylatainak kiértékelése.</span><span class="sxs-lookup"><span data-stu-id="3b85d-133">Evaluate source documents for specific entities.</span></span></td>
<td><span data-ttu-id="3b85d-134">A lekérdezés főbizonylata meghatározza azt a bizonylatot, amely auditálás alatt áll.</span><span class="sxs-lookup"><span data-stu-id="3b85d-134">The root document of the query defines the document that is being audited.</span></span> <span data-ttu-id="3b85d-135">A lekérdezésnek a listalekérdezésnek kell lennie, amely tartalmaz egy hivatkozást a dirpartytable táblázatba.</span><span class="sxs-lookup"><span data-stu-id="3b85d-135">The query must be a list query that includes a reference to the dirpartytable table.</span></span> <span data-ttu-id="3b85d-136">Ez a lehetőség csak a következő alkalmazásobjektum-fa lekérdezések esetén használható:</span><span class="sxs-lookup"><span data-stu-id="3b85d-136">This option can be used only with the following AOT queries:</span></span>
<ul>
<li><span data-ttu-id="3b85d-137"><span class="ui">AuditPolicyExpenseList</span> (Költségjelentéssel ellenőrzött alkalmazottak)</span><span class="sxs-lookup"><span data-stu-id="3b85d-137"><span class="ui">AuditPolicyExpenseList</span> (Expense report monitored employees)</span></span></li>
<li><span data-ttu-id="3b85d-138"><span class="ui">AuditPolicyPurchList</span> (Beszerzési rendeléssel ellenőrzött szállítók)</span><span class="sxs-lookup"><span data-stu-id="3b85d-138"><span class="ui">AuditPolicyPurchList</span> (Purchase order monitored vendors)</span></span></li>
<li><span data-ttu-id="3b85d-139"><span class="ui">AuditPolicyVendInvoiceList</span> (Szállítói számlával ellenőrzött szállítók)</span><span class="sxs-lookup"><span data-stu-id="3b85d-139"><span class="ui">AuditPolicyVendInvoiceList</span> (Vendor invoice monitored vendors)</span></span></li>
</ul>
<span data-ttu-id="3b85d-140">Ha ezt a lehetőséget választja, adja meg a figyelt entitásokat a Könyvviteli irányelvszabály lapon.</span><span class="sxs-lookup"><span data-stu-id="3b85d-140">When you select this option, specify the monitored entities in the Audit policy rule page.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3b85d-141">Kulcsszó keresése</span><span class="sxs-lookup"><span data-stu-id="3b85d-141">Keyword search</span></span></td>
<td><span data-ttu-id="3b85d-142">Értékelje a forrásbizonylatokat abból a szempontból, hogy tartalmaznak-e bizonyos szavakat.</span><span class="sxs-lookup"><span data-stu-id="3b85d-142">Evaluate source documents to determine whether they contain certain words.</span></span></td>
<td><span data-ttu-id="3b85d-143">Ha ezt a lehetőséget választja, adja meg a keresett szavakat a Könyvviteli irányelvszabály lapon.</span><span class="sxs-lookup"><span data-stu-id="3b85d-143">When you select this option, enter the words to look for in the Audit policy rule page.</span></span> <span data-ttu-id="3b85d-144">A Könyvviteli irányelvszabály lap olyan lehetőségeket kínál, amelyek lehetővé teszik, hogy megadhassa az Ön által beírt szavak kiértékeléséhez szükséges táblákat és mezőket.</span><span class="sxs-lookup"><span data-stu-id="3b85d-144">The Audit policy rule page also includes options that let you specify the tables and fields to evaluate for the words you entered.</span></span></td>
</tr>
</tbody>
</table>

## <a name="common-parameters"></a><span data-ttu-id="3b85d-145">Gyakori paraméterek</span><span class="sxs-lookup"><span data-stu-id="3b85d-145">Common parameters</span></span>
<span data-ttu-id="3b85d-146">Az egy adott auditirányelvre vonatkozó összes irányelvszabály ugyanazon kötegparaméterekkel és ugyanazon bizonylat-kiválasztási dátumtartománnyal rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="3b85d-146">All of the policy rules for a particular audit policy share the same batch parameters and the same document selection date range.</span></span> <span data-ttu-id="3b85d-147">Ezek a paraméterek megadásra kerülnek az irányelvre a Könyvviteli irányelvszabály lapon.</span><span class="sxs-lookup"><span data-stu-id="3b85d-147">These parameters are specified for the policy in the Additional options page.</span></span>



<a name="see-also"></a><span data-ttu-id="3b85d-148">Lásd még</span><span class="sxs-lookup"><span data-stu-id="3b85d-148">See also</span></span>
--------

<span data-ttu-id="3b85d-149">[Könyvvizsgálati irányelvmegsértések és esetek](audit-policy-violations-cases.md)
[Naplózási házirendek meghatározása a forrásbizonylatok számára](tasks/define-audit-policies-source-documents.md)</span><span class="sxs-lookup"><span data-stu-id="3b85d-149">[Audit policy violations and cases](audit-policy-violations-cases.md)
[Define audit policies for source documents](tasks/define-audit-policies-source-documents.md)</span></span>



