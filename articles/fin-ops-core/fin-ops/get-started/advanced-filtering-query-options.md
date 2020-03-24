---
title: Speciális szűrési és lekérdezési szintaxis
description: A témakör ismerteti a szűrési és lekérdezési beállításokat, amelyek elérhetők a Speciális szűrés/rendezés párbeszédpanelen vagy az egyezések operátor vagy a rács oszlop fejléce szűrők használata esetén.
author: jasongre
manager: AnnBe
ms.date: 03/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysQueryForm
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 3811
ms.assetid: b4969b30-2fe1-4a3c-bbea-725dc37c8b60
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7a525422a091efe8ea88f42e91dc52488430cfe5
ms.sourcegitcommit: 48c39c0c0949fe48b3536d9d2d0e451d561ff5c6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2020
ms.locfileid: "3112191"
---
# <a name="advanced-filtering-and-query-syntax"></a><span data-ttu-id="efe48-103">Speciális szűrési és lekérdezési szintaxis</span><span class="sxs-lookup"><span data-stu-id="efe48-103">Advanced filtering and query syntax</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="efe48-104">A témakör ismerteti a szűrési és lekérdezési beállításokat, amelyek elérhetők a Speciális szűrés/rendezés párbeszédpanelen vagy az **egyezések** operátor vagy a rács oszlop fejléce szűrők használata esetén.</span><span class="sxs-lookup"><span data-stu-id="efe48-104">This topic describes the filtering and query options that are available when you use the Advanced filter/sort dialog or the **matches** operator in the Filter pane or grid column header filters.</span></span>

## <a name="advanced-query-syntax"></a><span data-ttu-id="efe48-105">Speciális lekérdezési szintaxis</span><span class="sxs-lookup"><span data-stu-id="efe48-105">Advanced query syntax</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="efe48-106">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="efe48-106">Syntax</span></span></th>
<th><span data-ttu-id="efe48-107">Működése</span><span class="sxs-lookup"><span data-stu-id="efe48-107">Character description</span></span></th>
<th><span data-ttu-id="efe48-108">Leírás</span><span class="sxs-lookup"><span data-stu-id="efe48-108">Description</span></span></th>
<th><span data-ttu-id="efe48-109">Példa</span><span class="sxs-lookup"><span data-stu-id="efe48-109">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="efe48-110"><em>Érték</em></span><span class="sxs-lookup"><span data-stu-id="efe48-110"><em>value</em></span></span></td>
<td><span data-ttu-id="efe48-111">Megegyezik a beírt értékkel.</span><span class="sxs-lookup"><span data-stu-id="efe48-111">Equal to the value that is entered</span></span></td>
<td><span data-ttu-id="efe48-112">Írja be a keresendő érték.</span><span class="sxs-lookup"><span data-stu-id="efe48-112">Type the value to find.</span></span></td>
<td><span data-ttu-id="efe48-113">A <strong>Kovács</strong> keresésére a program a &quot;Kovács&quot; értéket találja meg.</span><span class="sxs-lookup"><span data-stu-id="efe48-113"><strong>Smith</strong> finds &quot;Smith&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="efe48-114">!<em>érték</em> (felkiáltójel)</span><span class="sxs-lookup"><span data-stu-id="efe48-114">!<em>value</em> (exclamation point)</span></span></td>
<td><span data-ttu-id="efe48-115">Nem egyezik meg a beírt értékkel</span><span class="sxs-lookup"><span data-stu-id="efe48-115">Not equal to the value that is entered</span></span></td>
<td><span data-ttu-id="efe48-116">Írjon be egy felkiáltójelet az elé az érték elé, amelyet szeretne kizárni a keresésből.</span><span class="sxs-lookup"><span data-stu-id="efe48-116">Type an exclamation point and then the value to exclude.</span></span></td>
<td><span data-ttu-id="efe48-117">A <strong>!Kovács</strong> keresésére a program a &quot;Kovács&quot; érték kivételével az összes értéket megtalálja.</span><span class="sxs-lookup"><span data-stu-id="efe48-117"><strong>!Smith</strong> finds all values except &quot;Smith&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="efe48-118"><em>Kezdő érték</em>..<em>Záró érték</em> (két pont)</span><span class="sxs-lookup"><span data-stu-id="efe48-118"><em>from-value</em>..<em>to-value</em> (double period)</span></span></td>
<td><span data-ttu-id="efe48-119">A két ponttal elválaszott értékek között keres</span><span class="sxs-lookup"><span data-stu-id="efe48-119">Between the two values that are separated by double periods</span></span></td>
<td><span data-ttu-id="efe48-120">Írja be a „-tól” értéket, majd két pontot, végül az „-ig” értéket.</span><span class="sxs-lookup"><span data-stu-id="efe48-120">Type the from-value, then two periods, and then the to-value.</span></span></td>
<td><span data-ttu-id="efe48-121"><strong>1..10</strong> keresése esetén az 1 és 10 közötti összes értéket megtalálja a program.</span><span class="sxs-lookup"><span data-stu-id="efe48-121"><strong>1..10</strong> finds all values from 1 through 10.</span></span> <span data-ttu-id="efe48-122">Karakterláncmezőkben azonban az <strong>A..C</strong> keresése esetén az összes &quot;A&quot; és &quot;B&quot; kezdetű értéket, valamint a &quot;C&quot; értékkel pontosan megegyező értékeket találja meg a program (a „Ca” értéket például nem fogja megtalálni).</span><span class="sxs-lookup"><span data-stu-id="efe48-122">However, in a string field, <strong>A..C</strong> finds all values that start with &quot;A&quot; and &quot;B&quot;, and values that are exactly equal to &quot;C&quot;.</span></span> <span data-ttu-id="efe48-123">Ez a lekérdezés például nem fogja megtalálni a &quot;Ca&quot; értéket.</span><span class="sxs-lookup"><span data-stu-id="efe48-123">For example, this query won't find &quot;Ca&quot;.</span></span> <span data-ttu-id="efe48-124">Hogy minden értéket megtaláljon &quot;A<em>&quot; értéktől &quot;C</em>&quot; értékig, írja be, hogy: <strong>A..D</strong>.</span><span class="sxs-lookup"><span data-stu-id="efe48-124">To find all values from &quot;A<em>&quot; through &quot;C</em>&quot;, type <strong>A..D</strong>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="efe48-125">..<em>érték</em> (két pont)</span><span class="sxs-lookup"><span data-stu-id="efe48-125">..<em>value</em> (double period)</span></span></td>
<td><span data-ttu-id="efe48-126">Megkeresi a beírt értékkel egyenlő, vagy annál kisebb értékeket</span><span class="sxs-lookup"><span data-stu-id="efe48-126">Less than or equal to the value that is entered</span></span></td>
<td><span data-ttu-id="efe48-127">Írjon be két pontot majd az értéket.</span><span class="sxs-lookup"><span data-stu-id="efe48-127">Type two periods and then the value.</span></span></td>
<td><span data-ttu-id="efe48-128"><strong>..1000</strong> keresése esetén a program minden olyan számot megtalál, amely kisebb vagy egyenlő, mint 1000 - például &quot;100&quot;, &quot;999,95&quot; és &quot;1000&quot;.</span><span class="sxs-lookup"><span data-stu-id="efe48-128"><strong>..1000</strong> finds any number that is less than or equal to 1000, such as &quot;100&quot;, &quot;999.95&quot;, and &quot;1,000&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="efe48-129"><em>érték</em>..</span><span class="sxs-lookup"><span data-stu-id="efe48-129"><em>value</em>..</span></span> <span data-ttu-id="efe48-130">(két pont)</span><span class="sxs-lookup"><span data-stu-id="efe48-130">(double period)</span></span></td>
<td><span data-ttu-id="efe48-131">A beírt értékkel megegyező vagy annál nagyobb értékeket találja meg</span><span class="sxs-lookup"><span data-stu-id="efe48-131">Greater than or equal to the value that is entered</span></span></td>
<td><span data-ttu-id="efe48-132">Írja be az értéket, majd két pontot.</span><span class="sxs-lookup"><span data-stu-id="efe48-132">Type the value and then two periods.</span></span></td>
<td><span data-ttu-id="efe48-133"><strong>1000..</strong></span><span class="sxs-lookup"><span data-stu-id="efe48-133"><strong>1000..</strong></span></span> <span data-ttu-id="efe48-134">keresése esetén a program minden olyan számot megtalál, amely nagyobb, mint 1000 vagy pontosan annyi, például a következőket: &quot;1000&quot;, &quot;1000,01&quot; és &quot;1 000 000&quot;.</span><span class="sxs-lookup"><span data-stu-id="efe48-134">finds any number that is greater than or equal to 1000, such as &quot;1,000&quot;, &quot;1,000.01&quot;, and &quot;1,000,000&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="efe48-135">&gt;<em>jel</em> (nagyobb mint jel)</span><span class="sxs-lookup"><span data-stu-id="efe48-135">&gt;<em>value</em> (greater than sign)</span></span></td>
<td><span data-ttu-id="efe48-136">Nagyobb, mint a beírt érték.</span><span class="sxs-lookup"><span data-stu-id="efe48-136">Greater than the value that is entered</span></span></td>
<td><span data-ttu-id="efe48-137">Írja be a „nagyobb” (<strong>&gt;</strong>) jelet, majd az értéket.</span><span class="sxs-lookup"><span data-stu-id="efe48-137">Type a greater than sign (<strong>&gt;</strong>) and then the value.</span></span></td>
<td><span data-ttu-id="efe48-138"><strong>&gt;1000</strong> keresésére esetén a program minden olyan számot megtalál, amely nagyobb, mint 1000 vagy pontosan annyi, például a következőket: &quot;1000,01&quot;, &quot;20 000&quot; és &quot;1 000 000&quot;.</span><span class="sxs-lookup"><span data-stu-id="efe48-138"><strong>&gt;1000</strong> finds any number that is greater than 1000, such as &quot;1000.01&quot;, &quot;20,000&quot;, and &quot;1,000,000&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="efe48-139">&lt;<em>érték</em> (kisebb mint jel)</span><span class="sxs-lookup"><span data-stu-id="efe48-139">&lt;<em>value</em> (less than sign)</span></span></td>
<td><span data-ttu-id="efe48-140">Kisebb, mint a beírt érték</span><span class="sxs-lookup"><span data-stu-id="efe48-140">Less than the value that is entered</span></span></td>
<td><span data-ttu-id="efe48-141">Írja be a „kisebb” (<strong>&lt;</strong>) jelet, majd az értéket.</span><span class="sxs-lookup"><span data-stu-id="efe48-141">Type a less than sign (<strong>&lt;</strong>) and then the value.</span></span></td>
<td><span data-ttu-id="efe48-142"><strong>&lt;1000</strong> keresésére a program minden olyan számot megtalál, amely kisebb, mint 1000, például a következőket: &quot;999,99&quot;, &quot;1&quot; és &quot;-200&quot;.</span><span class="sxs-lookup"><span data-stu-id="efe48-142"><strong>&lt;1000</strong> finds any number that is less than 1000, such as &quot;999.99&quot;, &quot;1&quot;, and &quot;-200&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="efe48-143"><em>érték</em>\* (csillag)</span><span class="sxs-lookup"><span data-stu-id="efe48-143"><em>value</em>\* (asterisk)</span></span></td>
<td><span data-ttu-id="efe48-144">A beírt értéktől kezdve</span><span class="sxs-lookup"><span data-stu-id="efe48-144">Starting from the value that is entered</span></span></td>
<td><span data-ttu-id="efe48-145">Írja be a kezdő értéket, majd egy csillagot (<strong>\*</strong>).</span><span class="sxs-lookup"><span data-stu-id="efe48-145">Type the starting value and then an asterisk (<strong>\*</strong>).</span></span></td>
<td><span data-ttu-id="efe48-146"><strong>S\*</strong> keresése esetén a program minden &quot;S&quot;-sel kezdődő karakterláncot megtalál, például a következőket: &quot;Stockholm&quot;, &quot;Sydney&quot; és &quot;San Francisco&quot;.</span><span class="sxs-lookup"><span data-stu-id="efe48-146"><strong>S\*</strong> finds any string that starts with &quot;S&quot;, such as &quot;Stockholm&quot;, &quot;Sydney&quot;, and &quot;San Francisco&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="efe48-147">\*<em>érték</em> (csillag)</span><span class="sxs-lookup"><span data-stu-id="efe48-147">\*<em>value</em> (asterisk)</span></span></td>
<td><span data-ttu-id="efe48-148">A beírt értékre végződő</span><span class="sxs-lookup"><span data-stu-id="efe48-148">Ending with the value that is entered</span></span></td>
<td><span data-ttu-id="efe48-149">Írjon be egy csillagot, majd a végződésként szereplő értéket.</span><span class="sxs-lookup"><span data-stu-id="efe48-149">Type an asterisk and then the ending value.</span></span></td>
<td><span data-ttu-id="efe48-150"><strong>\*kelet</strong> keresése esetén a program minden olyan karakterláncot megtalál, amely a &quot;kelet&quot; szóra végződik, például a következőket: &quot;északkelet&quot;, &quot;délkelet&quot;.</span><span class="sxs-lookup"><span data-stu-id="efe48-150"><strong>\*east</strong> finds any string that ends with &quot;east&quot;, such as &quot;Northeast&quot; and &quot;Southeast&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="efe48-151">*<em>érték</em>* (csillag)</span><span class="sxs-lookup"><span data-stu-id="efe48-151">*<em>value</em>* (asterisk)</span></span></td>
<td><span data-ttu-id="efe48-152">Tartalmazza a beírt értéket</span><span class="sxs-lookup"><span data-stu-id="efe48-152">Containing the value that is entered</span></span></td>
<td><span data-ttu-id="efe48-153">Írjon be egy csillagot, egy értéket, majd egy másik csillagot.</span><span class="sxs-lookup"><span data-stu-id="efe48-153">Type an asterisk, then a value, and then another asterisk.</span></span></td>
<td><span data-ttu-id="efe48-154"><strong>*nt*</strong> keresése esetén a program minden olyan karakterláncot megtalál, amelyben szerepel az &quot;nt&quot; érték, például a következőket: &quot;Dunántúl&quot; és &quot;Tiszántúl&quot;.</span><span class="sxs-lookup"><span data-stu-id="efe48-154"><strong>*th*</strong> finds any string that contains &quot;th&quot;, such as &quot;Northeast&quot; and &quot;Southeast&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="efe48-155">?</span><span class="sxs-lookup"><span data-stu-id="efe48-155">?</span></span> <span data-ttu-id="efe48-156">(kérdőjel)</span><span class="sxs-lookup"><span data-stu-id="efe48-156">(question mark)</span></span></td>
<td><span data-ttu-id="efe48-157">Egy vagy több ismeretlen karakter szerepel benne.</span><span class="sxs-lookup"><span data-stu-id="efe48-157">Having one or more unknown characters</span></span></td>
<td><span data-ttu-id="efe48-158">Írjon be egy kérdőjelet az ismeretlen karakternek az értéken belüli helyére.</span><span class="sxs-lookup"><span data-stu-id="efe48-158">Type a question mark at the position of the unknown character in the value.</span></span></td>
<td><span data-ttu-id="efe48-159"><strong>Cseh?</strong> keresése esetén a program a &quot;Csehi&quot; és a &quot;Csehy&quot; értéket is megjeleníti.</span><span class="sxs-lookup"><span data-stu-id="efe48-159"><strong>Sm?th</strong> finds &quot;Smith&quot; and &quot;Smyth&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="efe48-160"><em>érték</em>,<em>érték</em> (vessző)</span><span class="sxs-lookup"><span data-stu-id="efe48-160"><em>value</em>,<em>value</em> (comma)</span></span></td>
<td><span data-ttu-id="efe48-161">A vesszővel elválasztott értékekkel megegyező értékek</span><span class="sxs-lookup"><span data-stu-id="efe48-161">Matching the values that are separated by commas</span></span></td>
<td><span data-ttu-id="efe48-162">Írja be az összes keresési feltételt vesszővel elválasztva.</span><span class="sxs-lookup"><span data-stu-id="efe48-162">Type all your criteria, and separate them by using commas.</span></span></td>
<td><span data-ttu-id="efe48-163"><strong>A, D, F, G</strong> keresése esetén a program az &quot;A&quot;, &quot;D&quot;, &quot;F&quot; és &quot;G&quot; értékeket találja meg.</span><span class="sxs-lookup"><span data-stu-id="efe48-163"><strong>A, D, F, G</strong> finds exactly &quot;A&quot;, &quot;D&quot;, &quot;F&quot;, and &quot;G&quot;.</span></span> <span data-ttu-id="efe48-164"><strong>10, 20, 30, 100</strong> keresése esetén a &quot;10, 20, 30, 100&quot; értékeket találja meg a program.</span><span class="sxs-lookup"><span data-stu-id="efe48-164"><strong>10, 20, 30, 100</strong> finds exactly &quot;10, 20, 30, 100&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="efe48-165">"" (kettő dupla idézőjel)</span><span class="sxs-lookup"><span data-stu-id="efe48-165">"" (two double quotes)</span></span></td>
<td><span data-ttu-id="efe48-166">Üres érték egyeztetése</span><span class="sxs-lookup"><span data-stu-id="efe48-166">Matching a blank value</span></span></td>
<td><span data-ttu-id="efe48-167">Írjon be két egymást követő idézőjelet a mező üres értékeinek szűréséhez.</span><span class="sxs-lookup"><span data-stu-id="efe48-167">Type two consecutive double quotes to filter for blank values in that field.</span></span></td>
<td><span data-ttu-id="efe48-168">A két egymást követő dupla idézőjel (<strong>""</strong>) olyan sorokat keres, amelyeknek nincs értéke az aktuális oszlopban.</span><span class="sxs-lookup"><span data-stu-id="efe48-168">Two consecutive double quotes (<strong>""</strong>) finds rows with no value for the current column.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="efe48-169">(<span class="code">Finance and Operations lekérdezés</span>) (Finance and Operations zárójelek közti lekérdezés)</span><span class="sxs-lookup"><span data-stu-id="efe48-169">(<span class="code">Finance and Operations query</span>) (Finance and Operations query between parentheses)</span></span></td>
<td><span data-ttu-id="efe48-170">A megadott lekérdezésnek megfelelő.</span><span class="sxs-lookup"><span data-stu-id="efe48-170">Matching a defined query</span></span></td>
<td><span data-ttu-id="efe48-171">Írjon be egy lekérdezést a zárójelek közötti SQL-utasításként a Finance and Operations lekérdezési nyelvével.</span><span class="sxs-lookup"><span data-stu-id="efe48-171">Type a query as an SQL statement between parentheses using the Finance and Operations query language.</span></span></td>
  <td><span data-ttu-id="efe48-172"><strong><span class="code">((AccountNum LIKE "US *") && (DirPartyTable.Name LIKE "Cont*"))</span></strong></span><span class="sxs-lookup"><span data-stu-id="efe48-172"><strong><span class="code">((AccountNum LIKE "US *") && (DirPartyTable.Name LIKE "Cont*"))</span></strong></span></span><br><br> 
       <span data-ttu-id="efe48-173">példaként egy szűrő feltételének szintaxisára a gyökérszintű adatforrás mezőjéből, valamint egy másik adatforrásmezőből (az összes vevő laphoz)</span><span class="sxs-lookup"><span data-stu-id="efe48-173">as an example of syntax for a filter condition on a field from the root datasource as well as a field from a different datasource (for the All customers page)</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="efe48-174">K</span><span class="sxs-lookup"><span data-stu-id="efe48-174">T</span></span></td>
<td><span data-ttu-id="efe48-175">Mai dátum</span><span class="sxs-lookup"><span data-stu-id="efe48-175">Today's date</span></span></td>
<td><span data-ttu-id="efe48-176"><strong>T</strong> típus.</span><span class="sxs-lookup"><span data-stu-id="efe48-176">Type <strong>T</strong>.</span></span></td>
<td><span data-ttu-id="efe48-177"><strong>T</strong> megegyezik a mai dátummal.</span><span class="sxs-lookup"><span data-stu-id="efe48-177"><strong>T</strong> matches today's date.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="efe48-178">(methodName(parameters)) (<strong>SysQueryRangeUtil</strong> zárójelek közötti mód)</span><span class="sxs-lookup"><span data-stu-id="efe48-178">(methodName(parameters)) (<strong>SysQueryRangeUtil</strong> method between parentheses)</span></span></td>
<td><span data-ttu-id="efe48-179">Az érték vagy a paraméterek a <strong>SysQueryRangeUtil</strong> metódus által megadott értékek</span><span class="sxs-lookup"><span data-stu-id="efe48-179">Matching the value or range of values that are specified by the parameters of the <strong>SysQueryRangeUtil</strong> method</span></span></td>
<td><span data-ttu-id="efe48-180">Az érték vagy a paraméterek a <strong>SysQueryRangeUtil</strong> metódus által megadott értékek</span><span class="sxs-lookup"><span data-stu-id="efe48-180">Type a <strong>SysQueryRangeUtil</strong> method that has parameters that specify the value or range of values.</span></span></td>
<td>
<ol>
<li><span data-ttu-id="efe48-181">Ugorjon a következőre: <strong>Kinnlévőségek</strong> &gt; <strong>Számlák</strong> &gt; <strong>Nyitott vevői számlák</strong>.</span><span class="sxs-lookup"><span data-stu-id="efe48-181">Click <strong>Accounts receivable</strong> &gt; <strong>Invoices</strong> &gt; <strong>Open customer invoices</strong>.</span></span></li>
<li><span data-ttu-id="efe48-182">Nyomja le a Ctrl+Shift+F3 nyissa meg a <strong>Lekérdezési</strong> oldalon.</span><span class="sxs-lookup"><span data-stu-id="efe48-182">Press Ctrl+Shift+F3 to open the <strong>Inquiry</strong> page.</span></span></li>
<li><span data-ttu-id="efe48-183">Kattintson a <strong>Tartomány</strong> lap <strong>Hozzáadás</strong> gombjára.</span><span class="sxs-lookup"><span data-stu-id="efe48-183">On the <strong>Range</strong> tab, click <strong>Add</strong>.</span></span></li>
<li><span data-ttu-id="efe48-184">A <strong>Táblázat</strong> mezőben válassza a <strong>Nyitott vevői tranzakciók</strong> opciót.</span><span class="sxs-lookup"><span data-stu-id="efe48-184">In the <strong>Table</strong> field, select <strong>Open customer transactions</strong>.</span></span></li>
<li><span data-ttu-id="efe48-185">A <strong>Mező</strong> mezőben válassza a <strong>Határidő</strong> lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="efe48-185">In the <strong>Field</strong> field, select <strong>Due date</strong>.</span></span></li>
<li><span data-ttu-id="efe48-186">A <strong>Kritérium</strong> mezőbe írja be a <strong>(yearRange(-2,0))</strong> szót.</span><span class="sxs-lookup"><span data-stu-id="efe48-186">In the <strong>Criteria</strong> field, enter <strong>(yearRange(-2,0))</strong>.</span></span></li>
<li><span data-ttu-id="efe48-187">Kattintson az <strong>OK</strong> gombra.</span><span class="sxs-lookup"><span data-stu-id="efe48-187">Click <strong>OK</strong>.</span></span> <span data-ttu-id="efe48-188">A lista lap azoknak a feltételeknek megfelelő számlák frissítése.</span><span class="sxs-lookup"><span data-stu-id="efe48-188">The list page is updated and lists the invoices that match the criterion that you entered.</span></span> <span data-ttu-id="efe48-189">Ebben a példában az volt az előző két év az esedékes számlák szerepelnek a lista lap.</span><span class="sxs-lookup"><span data-stu-id="efe48-189">For this example, invoices that were due in the previous two years are listed.</span></span></li>
</ol>
<span data-ttu-id="efe48-190">A tábla a következő szakaszban további részletekért lásd <strong>SysQueryRangeUtil</strong> dátum metódusok és több példák.</span><span class="sxs-lookup"><span data-stu-id="efe48-190">See the table in the next section for additional details about <strong>SysQueryRangeUtil</strong> date methods, and several examples.</span></span></td>
</tr>
</tbody>
</table>

## <a name="advanced-date-queries-that-use-sysqueryrangeutil-methods"></a><span data-ttu-id="efe48-191">Speciális dátum lekérdezések SysQueryRangeUtil módszerek használata</span><span class="sxs-lookup"><span data-stu-id="efe48-191">Advanced date queries that use SysQueryRangeUtil methods</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="efe48-192">Mód</span><span class="sxs-lookup"><span data-stu-id="efe48-192">Method</span></span></th>
<th><span data-ttu-id="efe48-193">Leírás</span><span class="sxs-lookup"><span data-stu-id="efe48-193">Description</span></span></th>
<th><span data-ttu-id="efe48-194">Példa</span><span class="sxs-lookup"><span data-stu-id="efe48-194">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="efe48-195">Nap (_relativeDays = 0)</span><span class="sxs-lookup"><span data-stu-id="efe48-195">Day (_relativeDays=0)</span></span></td>
<td><span data-ttu-id="efe48-196">Dátum képest a munkamenet dátuma található.</span><span class="sxs-lookup"><span data-stu-id="efe48-196">Find a date relative to the session date.</span></span> <span data-ttu-id="efe48-197">A pozitív értékek jelezheti a jövőben esedékes, valamint a negatív értékek múltbeli dátumok.</span><span class="sxs-lookup"><span data-stu-id="efe48-197">Positive values indicate future dates, and negative values indicate past dates.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="efe48-198"><strong>Másnap</strong> – Írja be <strong>(Nap(1))</strong>.</span><span class="sxs-lookup"><span data-stu-id="efe48-198"><strong>Tomorrow</strong> – Enter <strong>(Day(1))</strong>.</span></span></li>
<li><span data-ttu-id="efe48-199"><strong>Ma</strong> – Írja be <strong>(Nap(0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="efe48-199"><strong>Today</strong> – Enter <strong>(Day(0))</strong>.</span></span></li>
<li><span data-ttu-id="efe48-200"><strong>Tegnap</strong> – Írja be <strong>(Nap(-1))</strong>.</span><span class="sxs-lookup"><span data-stu-id="efe48-200"><strong>Yesterday</strong> – Enter <strong>(Day(-1))</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="efe48-201">DayRange (_relativeDaysFrom=0, _relativeDaysTo=0)</span><span class="sxs-lookup"><span data-stu-id="efe48-201">DayRange (_relativeDaysFrom=0, _relativeDaysTo=0)</span></span></td>
<td><span data-ttu-id="efe48-202">Dátum képest a munkamenet dátuma található.</span><span class="sxs-lookup"><span data-stu-id="efe48-202">Find a range of dates relative to the session date.</span></span> <span data-ttu-id="efe48-203">A pozitív értékek jelezheti a jövőben esedékes, valamint a negatív értékek múltbeli dátumok.</span><span class="sxs-lookup"><span data-stu-id="efe48-203">Positive values indicate future dates, and negative values indicate past dates.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="efe48-204"><strong>Elmúlt 30 nap</strong> – Írja be <strong>(DayRange(-30,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="efe48-204"><strong>Last 30 days</strong> – Enter <strong>(DayRange(-30,0))</strong>.</span></span></li>
<li><span data-ttu-id="efe48-205"><strong>Az elmúlt 30 nap, és a következő 30 nap</strong> – Írja be <strong>(DayRange(-30,30))</strong>.</span><span class="sxs-lookup"><span data-stu-id="efe48-205"><strong>Previous 30 days and next 30 days</strong> – Enter <strong>(DayRange(-30,30))</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="efe48-206">GreaterThanDate (_relativeDays=0) GreaterThanUtcDate (_relativeDays=0)</span><span class="sxs-lookup"><span data-stu-id="efe48-206">GreaterThanDate (_relativeDays=0) GreaterThanUtcDate (_relativeDays=0)</span></span></td>
<td><span data-ttu-id="efe48-207">A megadott relatív dátum után minden dátumra található.</span><span class="sxs-lookup"><span data-stu-id="efe48-207">Find all dates after the specified relative date.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="efe48-208"><strong>Több mint 30 nap múlva</strong> – Írja be <strong>(GreaterThanDate(30))</strong>.</span><span class="sxs-lookup"><span data-stu-id="efe48-208"><strong>More than 30 days from now</strong> – Enter <strong>(GreaterThanDate(30))</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="efe48-209">GreaterThanUtcNow ()</span><span class="sxs-lookup"><span data-stu-id="efe48-209">GreaterThanUtcNow ()</span></span></td>
<td><span data-ttu-id="efe48-210">Az összes dátum/idő bejegyzés található a mostani idő utánra.</span><span class="sxs-lookup"><span data-stu-id="efe48-210">Find all date/time entries after the current time.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="efe48-211"><strong>Az összes jövőbeni dátumot és időpontot</strong> – Írja be <strong>(GreaterThanUtcNow())</strong>.</span><span class="sxs-lookup"><span data-stu-id="efe48-211"><strong>All future date/times</strong> – Enter <strong>(GreaterThanUtcNow())</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="efe48-212">LessThanDate (_relativeDays=0) LessThanUtcDate (_relativeDays=0)</span><span class="sxs-lookup"><span data-stu-id="efe48-212">LessThanDate (_relativeDays=0) LessThanUtcDate (_relativeDays=0)</span></span></td>
<td><span data-ttu-id="efe48-213">A megadott relatív dátum előtt minden dátumra található.</span><span class="sxs-lookup"><span data-stu-id="efe48-213">Find all dates before the specified relative date.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="efe48-214"><strong>Kisebb, mint hét nap múlva</strong> – Írja be <strong>(LessThanDate(7))</strong>.</span><span class="sxs-lookup"><span data-stu-id="efe48-214"><strong>Less than seven days from now</strong> – Enter <strong>(LessThanDate(7))</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="efe48-215">LessThanUtcNow ()</span><span class="sxs-lookup"><span data-stu-id="efe48-215">LessThanUtcNow ()</span></span></td>
<td><span data-ttu-id="efe48-216">Az összes dátum/idő bejegyzés található a mostani idő utánra.</span><span class="sxs-lookup"><span data-stu-id="efe48-216">Find all date/time entries before the current time.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="efe48-217"><strong>Minden korábbi dátum/időpont</strong> – Írja be <strong>(LessThanUtcNow())</strong>.</span><span class="sxs-lookup"><span data-stu-id="efe48-217"><strong>All past date/times</strong> – Enter <strong>(LessThanUtcNow())</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="efe48-218">MonthRange (_relativeFrom=0, _relativeTo=0)</span><span class="sxs-lookup"><span data-stu-id="efe48-218">MonthRange (_relativeFrom=0, _relativeTo=0)</span></span></td>
<td><span data-ttu-id="efe48-219">A dátumtartomány alapján hónapok az aktuális hónap képest található.</span><span class="sxs-lookup"><span data-stu-id="efe48-219">Find a range of dates, based on months relative to the current month.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="efe48-220"><strong>Megelőző két hónap</strong> – Írja be <strong>(MonthRange(-2,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="efe48-220"><strong>Previous two months</strong> – Enter <strong>(MonthRange(-2,0))</strong>.</span></span></li>
<li><span data-ttu-id="efe48-221"><strong>Következő három hónap</strong> – Írja be <strong>(MonthRange(0,3))</strong>.</span><span class="sxs-lookup"><span data-stu-id="efe48-221"><strong>Next three months</strong> – Enter <strong>(MonthRange(0,3))</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="efe48-222">YearRange (_relativeFrom=0, _relativeTo=0)</span><span class="sxs-lookup"><span data-stu-id="efe48-222">YearRange (_relativeFrom=0, _relativeTo=0)</span></span></td>
<td><span data-ttu-id="efe48-223">A dátumtartomány alapján hónapok az aktuális hónap képest található.</span><span class="sxs-lookup"><span data-stu-id="efe48-223">Find a range of dates, based on years relative to the current year.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="efe48-224"><strong>Következő év</strong> – Írja be <strong>(YearRange(0, 1))</strong>.</span><span class="sxs-lookup"><span data-stu-id="efe48-224"><strong>Next year</strong> – Enter <strong>(YearRange(0, 1))</strong>.</span></span></li>
<li><span data-ttu-id="efe48-225"><strong>Előző év</strong> – Írja be <strong>(YearRange(-1,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="efe48-225"><strong>Previous year</strong> – Enter <strong>(YearRange(-1,0))</strong>.</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>
