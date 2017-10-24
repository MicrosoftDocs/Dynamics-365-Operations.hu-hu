---
title: "Speciális szűrési és lekérdezési szintaxis"
description: "A cikk ismerteti a szűrési és lekérdezési beállítások, amelyek elérhetők a Speciális szűrés/rendezés párbeszédpanel \"egyezések\" operátor használata esetén."
author: jasongre
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysQueryForm
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 3811
ms.assetid: b4969b30-2fe1-4a3c-bbea-725dc37c8b60
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 616366009ce7bf7135704e980becc331617cf5af
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="advanced-filtering-and-query-syntax"></a><span data-ttu-id="4e136-103">Speciális szűrési és lekérdezési szintaxis</span><span class="sxs-lookup"><span data-stu-id="4e136-103">Advanced filtering and query syntax</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="4e136-104">A cikk ismerteti a szűrési és lekérdezési beállítások, amelyek elérhetők a Speciális szűrés/rendezés párbeszédpanel "egyezések" operátor használata esetén.</span><span class="sxs-lookup"><span data-stu-id="4e136-104">This article describes the filtering and query options that are available when you use the "matches" operator in the Advanced filter/sort dialog.</span></span>

<a name="advanced-query-syntax"></a><span data-ttu-id="4e136-105">Speciális lekérdezési szintaxis</span><span class="sxs-lookup"><span data-stu-id="4e136-105">Advanced query syntax</span></span>
---------------------

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4e136-106">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="4e136-106">Syntax</span></span></th>
<th><span data-ttu-id="4e136-107">Működése</span><span class="sxs-lookup"><span data-stu-id="4e136-107">Character description</span></span></th>
<th><span data-ttu-id="4e136-108">Leírás</span><span class="sxs-lookup"><span data-stu-id="4e136-108">Description</span></span></th>
<th><span data-ttu-id="4e136-109">Példa</span><span class="sxs-lookup"><span data-stu-id="4e136-109">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="4e136-110"><em>Érték</em></span><span class="sxs-lookup"><span data-stu-id="4e136-110"><em>value</em></span></span></td>
<td><span data-ttu-id="4e136-111">Megegyezik a beírt értékkel.</span><span class="sxs-lookup"><span data-stu-id="4e136-111">Equal to the value that is entered</span></span></td>
<td><span data-ttu-id="4e136-112">Írja be a keresendő érték.</span><span class="sxs-lookup"><span data-stu-id="4e136-112">Type the value to find.</span></span></td>
<td><span data-ttu-id="4e136-113">A <strong>Kovács</strong> keresésére a program a &quot;Kovács&quot; értéket találja meg.</span><span class="sxs-lookup"><span data-stu-id="4e136-113"><strong>Smith</strong> finds &quot;Smith&quot;.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4e136-114">!<em>érték</em> (felkiáltójel)</span><span class="sxs-lookup"><span data-stu-id="4e136-114">!<em>value</em> (exclamation point)</span></span></td>
<td><span data-ttu-id="4e136-115">Nem egyezik meg a beírt értékkel</span><span class="sxs-lookup"><span data-stu-id="4e136-115">Not equal to the value that is entered</span></span></td>
<td><span data-ttu-id="4e136-116">Írjon be egy felkiáltójelet az elé az érték elé, amelyet szeretne kizárni a keresésből.</span><span class="sxs-lookup"><span data-stu-id="4e136-116">Type an exclamation point and then the value to exclude.</span></span></td>
<td><span data-ttu-id="4e136-117">A <strong>!Kovács</strong> keresésére a program a &quot;Kovács&quot; érték kivételével az összes értéket megtalálja.</span><span class="sxs-lookup"><span data-stu-id="4e136-117"><strong>!Smith</strong> finds all values except &quot;Smith&quot;.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="4e136-118"><em>Kezdő érték</em>..<em>Záró érték</em> (két pont)</span><span class="sxs-lookup"><span data-stu-id="4e136-118"><em>from-value</em>..<em>to-value</em> (double period)</span></span></td>
<td><span data-ttu-id="4e136-119">A két ponttal elválaszott értékek között keres</span><span class="sxs-lookup"><span data-stu-id="4e136-119">Between the two values that are separated by double periods</span></span></td>
<td><span data-ttu-id="4e136-120">Írja be a „-tól” értéket, majd két pontot, végül az „-ig” értéket.</span><span class="sxs-lookup"><span data-stu-id="4e136-120">Type the from-value, then two periods, and then the to-value.</span></span></td>
<td><span data-ttu-id="4e136-121"><strong>1..10</strong> keresése esetén az 1 és 10 közötti összes értéket megtalálja a program.</span><span class="sxs-lookup"><span data-stu-id="4e136-121"><strong>1..10</strong> finds all values from 1 through 10.</span></span> <span data-ttu-id="4e136-122">Karakterláncmezőkben azonban az <strong>A..C</strong> keresése esetén az összes &quot;A&quot; és &quot;B&quot; kezdetű értéket, valamint a &quot;C&quot; értékkel pontosan megegyező értékeket találja meg a program (a „Ca” értéket például nem fogja megtalálni).</span><span class="sxs-lookup"><span data-stu-id="4e136-122">However, in a string field, <strong>A..C</strong> finds all values that start with &quot;A&quot; and &quot;B&quot;, and values that are exactly equal to &quot;C&quot;.</span></span> <span data-ttu-id="4e136-123">Ez a lekérdezés például nem fogja megtalálni a &quot;Ca&quot; értéket.</span><span class="sxs-lookup"><span data-stu-id="4e136-123">For example, this query won't find &quot;Ca&quot;.</span></span> <span data-ttu-id="4e136-124">Hogy minden értéket megtaláljon &quot;A*&quot; értéktől &quot;C*&quot; értékig, írja be, hogy: <strong>A..D</strong>.</span><span class="sxs-lookup"><span data-stu-id="4e136-124">To find all values from &quot;A*&quot; through &quot;C*&quot;, type <strong>A..D</strong>.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4e136-125">..<em>érték</em> (két pont)</span><span class="sxs-lookup"><span data-stu-id="4e136-125">..<em>value</em> (double period)</span></span></td>
<td><span data-ttu-id="4e136-126">Megkeresi a beírt értékkel egyenlő, vagy annál kisebb értékeket</span><span class="sxs-lookup"><span data-stu-id="4e136-126">Less than or equal to the value that is entered</span></span></td>
<td><span data-ttu-id="4e136-127">Írjon be két pontot majd az értéket.</span><span class="sxs-lookup"><span data-stu-id="4e136-127">Type two periods and then the value.</span></span></td>
<td><span data-ttu-id="4e136-128"><strong>..1000</strong> keresése esetén a program minden olyan számot megtalál, amely kisebb vagy egyenlő, mint 1000 - például &quot;100&quot;, &quot;999,95&quot; és &quot;1000&quot;.</span><span class="sxs-lookup"><span data-stu-id="4e136-128"><strong>..1000</strong> finds any number that is less than or equal to 1000, such as &quot;100&quot;, &quot;999.95&quot;, and &quot;1,000&quot;.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="4e136-129"><em>érték</em>..</span><span class="sxs-lookup"><span data-stu-id="4e136-129"><em>value</em>..</span></span> <span data-ttu-id="4e136-130">(két pont)</span><span class="sxs-lookup"><span data-stu-id="4e136-130">(double period)</span></span></td>
<td><span data-ttu-id="4e136-131">A beírt értékkel megegyező vagy annál nagyobb értékeket találja meg</span><span class="sxs-lookup"><span data-stu-id="4e136-131">Greater than or equal to the value that is entered</span></span></td>
<td><span data-ttu-id="4e136-132">Írja be az értéket, majd két pontot.</span><span class="sxs-lookup"><span data-stu-id="4e136-132">Type the value and then two periods.</span></span></td>
<td><span data-ttu-id="4e136-133"><strong>1000..</strong></span><span class="sxs-lookup"><span data-stu-id="4e136-133"><strong>1000..</strong></span></span> <span data-ttu-id="4e136-134">keresése esetén a program minden olyan számot megtalál, amely nagyobb, mint 1000 vagy pontosan annyi, például a következőket: &quot;1000&quot;, &quot;1000,01&quot; és &quot;1 000 000&quot;.</span><span class="sxs-lookup"><span data-stu-id="4e136-134">finds any number that is greater than or equal to 1000, such as &quot;1,000&quot;, &quot;1,000.01&quot;, and &quot;1,000,000&quot;.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4e136-135">&gt;<em>jel</em> (nagyobb mint jel)</span><span class="sxs-lookup"><span data-stu-id="4e136-135">&gt;<em>value</em> (greater than sign)</span></span></td>
<td><span data-ttu-id="4e136-136">Nagyobb, mint a beírt érték.</span><span class="sxs-lookup"><span data-stu-id="4e136-136">Greater than the value that is entered</span></span></td>
<td><span data-ttu-id="4e136-137">Írja be a „nagyobb” (<strong>&gt;</strong>) jelet, majd az értéket.</span><span class="sxs-lookup"><span data-stu-id="4e136-137">Type a greater than sign (<strong>&gt;</strong>) and then the value.</span></span></td>
<td><span data-ttu-id="4e136-138"><strong>&gt;1000</strong> keresésére esetén a program minden olyan számot megtalál, amely nagyobb, mint 1000 vagy pontosan annyi, például a következőket: &quot;1000,01&quot;, &quot;20 000&quot; és &quot;1 000 000&quot;.</span><span class="sxs-lookup"><span data-stu-id="4e136-138"><strong>&gt;1000</strong> finds any number that is greater than 1000, such as &quot;1000.01&quot;, &quot;20,000&quot;, and &quot;1,000,000&quot;.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="4e136-139">&lt;<em>érték</em> (kisebb mint jel)</span><span class="sxs-lookup"><span data-stu-id="4e136-139">&lt;<em>value</em> (less than sign)</span></span></td>
<td><span data-ttu-id="4e136-140">Kisebb, mint a beírt érték</span><span class="sxs-lookup"><span data-stu-id="4e136-140">Less than the value that is entered</span></span></td>
<td><span data-ttu-id="4e136-141">Írja be a „kisebb” (<strong>&lt;</strong>) jelet, majd az értéket.</span><span class="sxs-lookup"><span data-stu-id="4e136-141">Type a less than sign (<strong>&lt;</strong>) and then the value.</span></span></td>
<td><span data-ttu-id="4e136-142"><strong>&lt;1000</strong> keresésére a program minden olyan számot megtalál, amely kisebb, mint 1000, például a következőket: &quot;999,99&quot;, &quot;1&quot; és &quot;-200&quot;.</span><span class="sxs-lookup"><span data-stu-id="4e136-142"><strong>&lt;1000</strong> finds any number that is less than 1000, such as &quot;999.99&quot;, &quot;1&quot;, and &quot;-200&quot;.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4e136-143"><em>érték</em>* (csillag)</span><span class="sxs-lookup"><span data-stu-id="4e136-143"><em>value</em>* (asterisk)</span></span></td>
<td><span data-ttu-id="4e136-144">A beírt értéktől kezdve</span><span class="sxs-lookup"><span data-stu-id="4e136-144">Starting from the value that is entered</span></span></td>
<td><span data-ttu-id="4e136-145">Írja be a kezdő értéket, majd egy csillagot (<strong>*</strong>).</span><span class="sxs-lookup"><span data-stu-id="4e136-145">Type the starting value and then an asterisk (<strong>*</strong>).</span></span></td>
<td><span data-ttu-id="4e136-146"><strong>S*</strong> keresése esetén a program minden &quot;S&quot;-sel kezdődő karakterláncot megtalál, például a következőket: &quot;Stockholm&quot;, &quot;Sydney&quot; és &quot;San Francisco&quot;.</span><span class="sxs-lookup"><span data-stu-id="4e136-146"><strong>S*</strong> finds any string that starts with &quot;S&quot;, such as &quot;Stockholm&quot;, &quot;Sydney&quot;, and &quot;San Francisco&quot;.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="4e136-147">*<em>érték</em> (csillag)</span><span class="sxs-lookup"><span data-stu-id="4e136-147">*<em>value</em> (asterisk)</span></span></td>
<td><span data-ttu-id="4e136-148">A beírt értékre végződő</span><span class="sxs-lookup"><span data-stu-id="4e136-148">Ending with the value that is entered</span></span></td>
<td><span data-ttu-id="4e136-149">Írjon be egy csillagot, majd a végződésként szereplő értéket.</span><span class="sxs-lookup"><span data-stu-id="4e136-149">Type an asterisk and then the ending value.</span></span></td>
<td><span data-ttu-id="4e136-150"><strong>*kelet</strong> keresése esetén a program minden olyan karakterláncot megtalál, amely a &quot;kelet&quot; szóra végződik, például a következőket: &quot;északkelet&quot;, &quot;délkelet&quot;.</span><span class="sxs-lookup"><span data-stu-id="4e136-150"><strong>*east</strong> finds any string that ends with &quot;east&quot;, such as &quot;Northeast&quot; and &quot;Southeast&quot;.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4e136-151">*<em>érték</em>* (csillag)</span><span class="sxs-lookup"><span data-stu-id="4e136-151">*<em>value</em>* (asterisk)</span></span></td>
<td><span data-ttu-id="4e136-152">Tartalmazza a beírt értéket</span><span class="sxs-lookup"><span data-stu-id="4e136-152">Containing the value that is entered</span></span></td>
<td><span data-ttu-id="4e136-153">Írjon be egy csillagot, egy értéket, majd egy másik csillagot.</span><span class="sxs-lookup"><span data-stu-id="4e136-153">Type an asterisk, then a value, and then another asterisk.</span></span></td>
<td><span data-ttu-id="4e136-154"><strong>*nt*</strong> keresése esetén a program minden olyan karakterláncot megtalál, amelyben szerepel az &quot;nt&quot; érték, például a következőket: &quot;Dunántúl&quot; és &quot;Tiszántúl&quot;.</span><span class="sxs-lookup"><span data-stu-id="4e136-154"><strong>*th*</strong> finds any string that contains &quot;th&quot;, such as &quot;Northeast&quot; and &quot;Southeast&quot;.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="4e136-155">?</span><span class="sxs-lookup"><span data-stu-id="4e136-155">?</span></span> <span data-ttu-id="4e136-156">(kérdőjel)</span><span class="sxs-lookup"><span data-stu-id="4e136-156">(question mark)</span></span></td>
<td><span data-ttu-id="4e136-157">Egy vagy több ismeretlen karakter szerepel benne.</span><span class="sxs-lookup"><span data-stu-id="4e136-157">Having one or more unknown characters</span></span></td>
<td><span data-ttu-id="4e136-158">Írjon be egy kérdőjelet az ismeretlen karakternek az értéken belüli helyére.</span><span class="sxs-lookup"><span data-stu-id="4e136-158">Type a question mark at the position of the unknown character in the value.</span></span></td>
<td><span data-ttu-id="4e136-159"><strong>Cseh?</strong> keresése esetén a program a &quot;Csehi&quot; és a &quot;Csehy&quot; értéket is megjeleníti.</span><span class="sxs-lookup"><span data-stu-id="4e136-159"><strong>Sm?th</strong> finds &quot;Smith&quot; and &quot;Smyth&quot;.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4e136-160"><em>érték</em>,<em>érték</em> (vessző)</span><span class="sxs-lookup"><span data-stu-id="4e136-160"><em>value</em>,<em>value</em> (comma)</span></span></td>
<td><span data-ttu-id="4e136-161">A vesszővel elválasztott értékekkel megegyező értékek</span><span class="sxs-lookup"><span data-stu-id="4e136-161">Matching the values that are separated by commas</span></span></td>
<td><span data-ttu-id="4e136-162">Írja be az összes keresési feltételt vesszővel elválasztva.</span><span class="sxs-lookup"><span data-stu-id="4e136-162">Type all your criteria, and separate them by using commas.</span></span></td>
<td><span data-ttu-id="4e136-163"><strong>A, D, F, G</strong> keresése esetén a program az &quot;A&quot;, &quot;D&quot;, &quot;F&quot; és &quot;G&quot; értékeket találja meg.</span><span class="sxs-lookup"><span data-stu-id="4e136-163"><strong>A, D, F, G</strong> finds exactly &quot;A&quot;, &quot;D&quot;, &quot;F&quot;, and &quot;G&quot;.</span></span> <span data-ttu-id="4e136-164"><strong>10, 20, 30, 100</strong> keresése esetén a &quot;10, 20, 30, 100&quot; értékeket találja meg a program.</span><span class="sxs-lookup"><span data-stu-id="4e136-164"><strong>10, 20, 30, 100</strong> finds exactly &quot;10, 20, 30, 100&quot;.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="4e136-165">(<span class="code">SQL-utasítás</span>) (Zárójelben SQL utasítás)</span><span class="sxs-lookup"><span data-stu-id="4e136-165">(<span class="code">SQL statement</span>) (SQL statement between parentheses)</span></span></td>
<td><span data-ttu-id="4e136-166">A megadott lekérdezésnek megfelelő.</span><span class="sxs-lookup"><span data-stu-id="4e136-166">Matching a defined query</span></span></td>
<td><span data-ttu-id="4e136-167">Írjon be zárójelek között egy SQL-lekérdezést.</span><span class="sxs-lookup"><span data-stu-id="4e136-167">Type a query as an SQL statement between parentheses.</span></span></td>
<td><span data-ttu-id="4e136-168"><strong><span class="code">(adatforrás.Mezőnév != &quot;A&quot;)</span></strong></span><span class="sxs-lookup"><span data-stu-id="4e136-168"><strong><span class="code">(data source.Fieldname != &quot;A&quot;)</span></strong></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4e136-169">C</span><span class="sxs-lookup"><span data-stu-id="4e136-169">T</span></span></td>
<td><span data-ttu-id="4e136-170">Mai dátum</span><span class="sxs-lookup"><span data-stu-id="4e136-170">Today's date</span></span></td>
<td><span data-ttu-id="4e136-171"><strong>T</strong> típus.</span><span class="sxs-lookup"><span data-stu-id="4e136-171">Type <strong>T</strong>.</span></span></td>
<td><span data-ttu-id="4e136-172"><strong>T</strong> megegyezik a mai dátummal.</span><span class="sxs-lookup"><span data-stu-id="4e136-172"><strong>T</strong> matches today's date.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="4e136-173">(methodName(parameters)) (<strong>SysQueryRangeUtil</strong> zárójelek közötti mód)</span><span class="sxs-lookup"><span data-stu-id="4e136-173">(methodName(parameters)) (<strong>SysQueryRangeUtil</strong> method between parentheses)</span></span></td>
<td><span data-ttu-id="4e136-174">Az érték vagy a paraméterek a <strong>SysQueryRangeUtil</strong> metódus által megadott értékek</span><span class="sxs-lookup"><span data-stu-id="4e136-174">Matching the value or range of values that are specified by the parameters of the <strong>SysQueryRangeUtil</strong> method</span></span></td>
<td><span data-ttu-id="4e136-175">Az érték vagy a paraméterek a <strong>SysQueryRangeUtil</strong> metódus által megadott értékek</span><span class="sxs-lookup"><span data-stu-id="4e136-175">Type a <strong>SysQueryRangeUtil</strong> method that has parameters that specify the value or range of values.</span></span></td>
<td><ol>
<li><span data-ttu-id="4e136-176">Ugorjon a következőre: <strong>Kinnlévőségek</strong> &gt; <strong>Számlák</strong> &gt; <strong>Nyitott vevői számlák</strong>.</span><span class="sxs-lookup"><span data-stu-id="4e136-176">Click <strong>Accounts receivable</strong> &gt; <strong>Invoices</strong> &gt; <strong>Open customer invoices</strong>.</span></span></li>
<li><span data-ttu-id="4e136-177">Nyomja le a Ctrl+Shift+F3 nyissa meg a <strong>Lekérdezési</strong> oldalon.</span><span class="sxs-lookup"><span data-stu-id="4e136-177">Press Ctrl+Shift+F3 to open the <strong>Inquiry</strong> page.</span></span></li>
<li><span data-ttu-id="4e136-178">Kattintson a <strong>Tartomány</strong> lap <strong>Hozzáadás</strong> gombjára.</span><span class="sxs-lookup"><span data-stu-id="4e136-178">On the <strong>Range</strong> tab, click <strong>Add</strong>.</span></span></li>
<li><span data-ttu-id="4e136-179">A <strong>Táblázat</strong> mezőben válassza a <strong>Nyitott vevői tranzakciók</strong> opciót.</span><span class="sxs-lookup"><span data-stu-id="4e136-179">In the <strong>Table</strong> field, select <strong>Open customer transactions</strong>.</span></span></li>
<li><span data-ttu-id="4e136-180">A <strong>Mező</strong> mezőben válassza a <strong>Határidő</strong> lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4e136-180">In the <strong>Field</strong> field, select <strong>Due date</strong>.</span></span></li>
<li><span data-ttu-id="4e136-181">A <strong>Kritérium</strong> mezőbe írja be a <strong>(yearRange(-2,0))</strong> szót.</span><span class="sxs-lookup"><span data-stu-id="4e136-181">In the <strong>Criteria</strong> field, enter <strong>(yearRange(-2,0))</strong>.</span></span></li>
<li><span data-ttu-id="4e136-182">Kattintson az <strong>OK</strong> gombra.</span><span class="sxs-lookup"><span data-stu-id="4e136-182">Click <strong>OK</strong>.</span></span> <span data-ttu-id="4e136-183">A lista lap azoknak a feltételeknek megfelelő számlák frissítése.</span><span class="sxs-lookup"><span data-stu-id="4e136-183">The list page is updated and lists the invoices that match the criterion that you entered.</span></span> <span data-ttu-id="4e136-184">Ebben a példában az volt az előző két év az esedékes számlák szerepelnek a lista lap.</span><span class="sxs-lookup"><span data-stu-id="4e136-184">For this example, invoices that were due in the previous two years are listed.</span></span></li>
</ol>
<span data-ttu-id="4e136-185">A tábla a következő szakaszban további részletekért lásd <strong>SysQueryRangeUtil</strong> dátum metódusok és több példák.</span><span class="sxs-lookup"><span data-stu-id="4e136-185">See the table in the next section for additional details about <strong>SysQueryRangeUtil</strong> date methods, and several examples.</span></span></td>
</tr>
</tbody>
</table>

## <a name="advanced-date-queries-that-use-sysqueryrangeutil-methods"></a><span data-ttu-id="4e136-186">Speciális dátum lekérdezések SysQueryRangeUtil módszerek használata</span><span class="sxs-lookup"><span data-stu-id="4e136-186">Advanced date queries that use SysQueryRangeUtil methods</span></span>
<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4e136-187">Mód</span><span class="sxs-lookup"><span data-stu-id="4e136-187">Method</span></span></th>
<th><span data-ttu-id="4e136-188">Leírás</span><span class="sxs-lookup"><span data-stu-id="4e136-188">Description</span></span></th>
<th><span data-ttu-id="4e136-189">Példa</span><span class="sxs-lookup"><span data-stu-id="4e136-189">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="4e136-190">Nap (_relativeDays = 0)</span><span class="sxs-lookup"><span data-stu-id="4e136-190">Day (_relativeDays=0)</span></span></td>
<td><span data-ttu-id="4e136-191">Dátum képest a munkamenet dátuma található.</span><span class="sxs-lookup"><span data-stu-id="4e136-191">Find a date relative to the session date.</span></span> <span data-ttu-id="4e136-192">A pozitív értékek jelezheti a jövőben esedékes, valamint a negatív értékek múltbeli dátumok.</span><span class="sxs-lookup"><span data-stu-id="4e136-192">Positive values indicate future dates, and negative values indicate past dates.</span></span></td>
<td><ul>
<li><span data-ttu-id="4e136-193"><strong>Másnap</strong> – Írja be <strong>(Nap(1))</strong>.</span><span class="sxs-lookup"><span data-stu-id="4e136-193"><strong>Tomorrow</strong> – Enter <strong>(Day(1))</strong>.</span></span></li>
<li><span data-ttu-id="4e136-194"><strong>Ma</strong> – Írja be <strong>(Nap(0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="4e136-194"><strong>Today</strong> – Enter <strong>(Day(0))</strong>.</span></span></li>
<li><span data-ttu-id="4e136-195"><strong>Tegnap</strong> – Írja be <strong>(Nap(-1))</strong>.</span><span class="sxs-lookup"><span data-stu-id="4e136-195"><strong>Yesterday</strong> – Enter <strong>(Day(-1))</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4e136-196">DayRange (_relativeDaysFrom=0, _relativeDaysTo=0)</span><span class="sxs-lookup"><span data-stu-id="4e136-196">DayRange (_relativeDaysFrom=0, _relativeDaysTo=0)</span></span></td>
<td><span data-ttu-id="4e136-197">Dátum képest a munkamenet dátuma található.</span><span class="sxs-lookup"><span data-stu-id="4e136-197">Find a range of dates relative to the session date.</span></span> <span data-ttu-id="4e136-198">A pozitív értékek jelezheti a jövőben esedékes, valamint a negatív értékek múltbeli dátumok.</span><span class="sxs-lookup"><span data-stu-id="4e136-198">Positive values indicate future dates, and negative values indicate past dates.</span></span></td>
<td><ul>
<li><span data-ttu-id="4e136-199"><strong>Elmúlt 30 nap</strong> – Írja be <strong>(DayRange(-30,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="4e136-199"><strong>Last 30 days</strong> – Enter <strong>(DayRange(-30,0))</strong>.</span></span></li>
<li><span data-ttu-id="4e136-200"><strong>Az elmúlt 30 nap, és a következő 30 nap</strong> – Írja be <strong>(DayRange(-30,30))</strong>.</span><span class="sxs-lookup"><span data-stu-id="4e136-200"><strong>Previous 30 days and next 30 days</strong> – Enter <strong>(DayRange(-30,30))</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="4e136-201">GreaterThanDate (_relativeDays=0) GreaterThanUtcDate (_relativeDays=0)</span><span class="sxs-lookup"><span data-stu-id="4e136-201">GreaterThanDate (_relativeDays=0) GreaterThanUtcDate (_relativeDays=0)</span></span></td>
<td><span data-ttu-id="4e136-202">A megadott relatív dátum után minden dátumra található.</span><span class="sxs-lookup"><span data-stu-id="4e136-202">Find all dates after the specified relative date.</span></span></td>
<td><ul>
<li><span data-ttu-id="4e136-203"><strong>Több mint 30 nap múlva</strong> – Írja be <strong>(GreaterThanDate(30))</strong>.</span><span class="sxs-lookup"><span data-stu-id="4e136-203"><strong>More than 30 days from now</strong> – Enter <strong>(GreaterThanDate(30))</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4e136-204">GreaterThanUtcNow ()</span><span class="sxs-lookup"><span data-stu-id="4e136-204">GreaterThanUtcNow ()</span></span></td>
<td><span data-ttu-id="4e136-205">Az összes dátum/idő bejegyzés található a mostani idő utánra.</span><span class="sxs-lookup"><span data-stu-id="4e136-205">Find all date/time entries after the current time.</span></span></td>
<td><ul>
<li><span data-ttu-id="4e136-206"><strong>Az összes jövőbeni dátumot és időpontot</strong> – Írja be <strong>(GreaterThanUtcNow())</strong>.</span><span class="sxs-lookup"><span data-stu-id="4e136-206"><strong>All future date/times</strong> – Enter <strong>(GreaterThanUtcNow())</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="4e136-207">LessThanDate (_relativeDays=0) LessThanUtcDate (_relativeDays=0)</span><span class="sxs-lookup"><span data-stu-id="4e136-207">LessThanDate (_relativeDays=0) LessThanUtcDate (_relativeDays=0)</span></span></td>
<td><span data-ttu-id="4e136-208">A megadott relatív dátum előtt minden dátumra található.</span><span class="sxs-lookup"><span data-stu-id="4e136-208">Find all dates before the specified relative date.</span></span></td>
<td><ul>
<li><span data-ttu-id="4e136-209"><strong>Kisebb, mint hét nap múlva</strong> – Írja be <strong>(LessThanDate(7))</strong>.</span><span class="sxs-lookup"><span data-stu-id="4e136-209"><strong>Less than seven days from now</strong> – Enter <strong>(LessThanDate(7))</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4e136-210">LessThanUtcNow ()</span><span class="sxs-lookup"><span data-stu-id="4e136-210">LessThanUtcNow ()</span></span></td>
<td><span data-ttu-id="4e136-211">Az összes dátum/idő bejegyzés található a mostani idő utánra.</span><span class="sxs-lookup"><span data-stu-id="4e136-211">Find all date/time entries before the current time.</span></span></td>
<td><ul>
<li><span data-ttu-id="4e136-212"><strong>Minden korábbi dátum/időpont</strong> – Írja be <strong>(LessThanUtcNow())</strong>.</span><span class="sxs-lookup"><span data-stu-id="4e136-212"><strong>All past date/times</strong> – Enter <strong>(LessThanUtcNow())</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="4e136-213">MonthRange (_relativeFrom=0, _relativeTo=0)</span><span class="sxs-lookup"><span data-stu-id="4e136-213">MonthRange (_relativeFrom=0, _relativeTo=0)</span></span></td>
<td><span data-ttu-id="4e136-214">A dátumtartomány alapján hónapok az aktuális hónap képest található.</span><span class="sxs-lookup"><span data-stu-id="4e136-214">Find a range of dates, based on months relative to the current month.</span></span></td>
<td><ul>
<li><span data-ttu-id="4e136-215"><strong>Megelőző két hónap</strong> – Írja be <strong>(MonthRange(-2,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="4e136-215"><strong>Previous two months</strong> – Enter <strong>(MonthRange(-2,0))</strong>.</span></span></li>
<li><span data-ttu-id="4e136-216"><strong>Következő három hónap</strong> – Írja be <strong>(MonthRange(0,3))</strong>.</span><span class="sxs-lookup"><span data-stu-id="4e136-216"><strong>Next three months</strong> – Enter <strong>(MonthRange(0,3))</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4e136-217">YearRange (_relativeFrom=0, _relativeTo=0)</span><span class="sxs-lookup"><span data-stu-id="4e136-217">YearRange (_relativeFrom=0, _relativeTo=0)</span></span></td>
<td><span data-ttu-id="4e136-218">A dátumtartomány alapján hónapok az aktuális hónap képest található.</span><span class="sxs-lookup"><span data-stu-id="4e136-218">Find a range of dates, based on years relative to the current year.</span></span></td>
<td><ul>
<li><span data-ttu-id="4e136-219"><strong>Következő év</strong> – Írja be <strong>(YearRange(0, 1))</strong>.</span><span class="sxs-lookup"><span data-stu-id="4e136-219"><strong>Next year</strong> – Enter <strong>(YearRange(0, 1))</strong>.</span></span></li>
<li><span data-ttu-id="4e136-220"><strong>Előző év</strong> – Írja be <strong>(YearRange(-1,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="4e136-220"><strong>Previous year</strong> – Enter <strong>(YearRange(-1,0))</strong>.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>





