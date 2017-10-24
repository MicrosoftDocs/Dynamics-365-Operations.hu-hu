---
title: "Fizetési ellenőrző fájlok beállítása és létrehozása"
description: "Ez a cikk ismerteti az ellenőrzött fizetések beállítását és az ellenőrzött fizetési fájlok létrehozását."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 88433
ms.assetid: 73f3dcf6-040a-44ad-9512-7b3e0d17a571
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 8294eb2861f48402c8489b84cc5f139408a22262
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="set-up-and-generate-positive-pay-files"></a><span data-ttu-id="e23f0-103">Fizetési ellenőrző fájlok beállítása és létrehozása</span><span class="sxs-lookup"><span data-stu-id="e23f0-103">Set up and generate positive pay files</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="e23f0-104">Ez a cikk ismerteti az ellenőrzött fizetések beállítását és az ellenőrzött fizetési fájlok létrehozását.</span><span class="sxs-lookup"><span data-stu-id="e23f0-104">This article explains how to set up positive pay and generate positive pay files.</span></span> 

<span data-ttu-id="e23f0-105">A fizetési ellenőrzés beállítása elektronikus csekklista generálásához, amely a banknak elküldhető.</span><span class="sxs-lookup"><span data-stu-id="e23f0-105">Set up positive pay to generate an electronic list of checks that is provided to the bank.</span></span> <span data-ttu-id="e23f0-106">Ezután, amikor egy csekket bemutatnak a banknak a bank összehasonlítja azt a csekklistával.</span><span class="sxs-lookup"><span data-stu-id="e23f0-106">Then, when a check is presented to the bank, the bank compares it with the list of checks.</span></span> <span data-ttu-id="e23f0-107">Ha a csekk megfelel a listában szereplő csekkel a bank törli azt.</span><span class="sxs-lookup"><span data-stu-id="e23f0-107">If the check matches a check in the list, the bank clears it.</span></span> <span data-ttu-id="e23f0-108">Ha a csekk nem egyezik meg a listában szereplő csekkel, akkor a bank bent tartja ellenőrzésre.</span><span class="sxs-lookup"><span data-stu-id="e23f0-108">If the check doesn't match a check in the list, the bank holds it for review.</span></span>

## <a name="security-for-positive-pay-files"></a><span data-ttu-id="e23f0-109">A fizetési ellenőrző fájlok biztonsága</span><span class="sxs-lookup"><span data-stu-id="e23f0-109">Security for positive pay files</span></span>
<span data-ttu-id="e23f0-110">Az ellenőrzött fizetési fájlok bizalmas információt tartalmazhatnak a kedvezményezettekről és a csekk-összegekről.</span><span class="sxs-lookup"><span data-stu-id="e23f0-110">Positive pay files can contain sensitive information about payees and check amounts.</span></span> <span data-ttu-id="e23f0-111">Ezért győződjön meg róla, hogy a megfelelő biztonsági intézkedéseket használja attól az időponttól, hogy a fájlok létrejönnek addig, amíg a bank meg nem kapja őket.</span><span class="sxs-lookup"><span data-stu-id="e23f0-111">Therefore, make sure that you use appropriate security measures from the time that the files are generated until they are received by the bank.</span></span> <span data-ttu-id="e23f0-112">A fizetési ellenőrző fájlok a webböngészője által megadott helyre lesznek letöltve.</span><span class="sxs-lookup"><span data-stu-id="e23f0-112">Positive pay files are downloaded to the location that is specified by your web browser.</span></span> <span data-ttu-id="e23f0-113">Mivel a fizetési ellenőrző fájlok bizalmas adatokat is tartalmazhatnak, fontos, hogy csak engedéllyel rendelkező felhasználók férjenek hozzá ezen információk létrehozásához és megtekintéséhez a Microsoft Dynamics 365 Finance and Operations Enterprise edition programban.</span><span class="sxs-lookup"><span data-stu-id="e23f0-113">Because positive pay files can contain sensitive information, it's important that only authorized users have access to generate and view this information in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span></span> <span data-ttu-id="e23f0-114">A következő táblázat segítségével határozza meg a szükséges jogosultságokkal.</span><span class="sxs-lookup"><span data-stu-id="e23f0-114">Use the following table to help you determine the privileges that are required.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e23f0-115">Feladat</span><span class="sxs-lookup"><span data-stu-id="e23f0-115">Task</span></span></th>
<th><span data-ttu-id="e23f0-116">Jogosultság</span><span class="sxs-lookup"><span data-stu-id="e23f0-116">Privilege</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="e23f0-117">Fizetési ellenőrző fájlok létrehozása a <strong>Bankszámlák</strong> listaoldalon vagy a <strong>Bankszámlák</strong> lapon.</span><span class="sxs-lookup"><span data-stu-id="e23f0-117">Generate positive pay files from the <strong>Bank accounts</strong> list page or the <strong>Bank accounts</strong> page.</span></span></td>
<td><ul>
<li><span data-ttu-id="e23f0-118"><strong>Banki ellenőrzött fizetési információk karbantartása</strong> (BankPositivePayProcess)</span><span class="sxs-lookup"><span data-stu-id="e23f0-118"><strong>Maintain bank positive pay information</strong> (BankPositivePayProcess)</span></span></li>
<li><span data-ttu-id="e23f0-119"><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</span><span class="sxs-lookup"><span data-stu-id="e23f0-119"><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e23f0-120">Ellenőrzött fizetési fájlok létrehozása több jogi személyhez és bankszámlához a <strong>Fizetési ellenőrző fájl létrehozása</strong> oldalon.</span><span class="sxs-lookup"><span data-stu-id="e23f0-120">Generate positive pay files for multiple legal entities and bank accounts from the <strong>Generate a positive pay file</strong> page.</span></span></td>
<td><ul>
<li><span data-ttu-id="e23f0-121"><strong>Banki ellenőrzött fizetési információk karbantartása</strong> (BankPositivePayProcess)</span><span class="sxs-lookup"><span data-stu-id="e23f0-121"><strong>Maintain bank positive pay information</strong> (BankPositivePayProcess)</span></span></li>
<li><span data-ttu-id="e23f0-122"><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</span><span class="sxs-lookup"><span data-stu-id="e23f0-122"><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="e23f0-123">Fizetési ellenőrző fájlok megtekintése a <strong>Fizetési ellenőrző fájl összegzése</strong> oldalon.</span><span class="sxs-lookup"><span data-stu-id="e23f0-123">View positive pay files on the <strong>Positive pay file summary</strong> page.</span></span></td>
<td><span data-ttu-id="e23f0-124"><strong>Banki ellenőrzött fizetési információk megtekintése több jogi személynél</strong> (BankPositivePayView)</span><span class="sxs-lookup"><span data-stu-id="e23f0-124"><strong>View bank positive pay information for multiple legal entities</strong> (BankPositivePayView)</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e23f0-125">Fizetési ellenőrző fájlok visszaigazolása a <strong>Fizetési ellenőrző fájl összegzése</strong> oldalon.</span><span class="sxs-lookup"><span data-stu-id="e23f0-125">Confirm a bank positive pay file on the <strong>Positive pay file summary</strong> page.</span></span></td>
<td><span data-ttu-id="e23f0-126"><strong>Fizetési ellenőrző fájl visszaigazolása</strong> (BankPositivePayConfirm)</span><span class="sxs-lookup"><span data-stu-id="e23f0-126"><strong>Confirm positive payment file</strong> (BankPositivePayConfirm)</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="e23f0-127">Fizetési ellenőrző fájlok visszahívása a <strong>Fizetési ellenőrző fájl összegzése</strong> oldalon.</span><span class="sxs-lookup"><span data-stu-id="e23f0-127">Recall a bank positive pay file on the <strong>Positive pay file summary</strong> page.</span></span></td>
<td><span data-ttu-id="e23f0-128"><strong>Fizetési ellenőrző fájl visszahívása</strong> (BankPositivePayRecall)</span><span class="sxs-lookup"><span data-stu-id="e23f0-128"><strong>Recall positive pay file</strong> (BankPositivePayRecall)</span></span></td>
</tr>
</tbody>
</table>

## <a name="set-up-a-positive-pay-format"></a><span data-ttu-id="e23f0-129">Ellenőrzött fizetési formátum beállítása</span><span class="sxs-lookup"><span data-stu-id="e23f0-129">Set up a positive pay format</span></span>
<span data-ttu-id="e23f0-130">Az ellenőrzött fizetési fájlok adatentitások használatával jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="e23f0-130">Positive pay files are created by using data entities.</span></span> <span data-ttu-id="e23f0-131">Mielőtt készíthetne egy fizetési ellenőrző fájlt, be kell állítania egy átalakítási bemeneti formátumot, amely ahhoz lesz használatos, hogy a csekk információit olyan formátumra fordítsa, amely képes kommunikálni a bankkal.</span><span class="sxs-lookup"><span data-stu-id="e23f0-131">Before you can generate a positive pay file, you must set up a transformation input format that will be used to translate the check information into a format that can communicate with the bank.</span></span> <span data-ttu-id="e23f0-132">Az **Ellenőrzött fizetési formátum** lapon létrehozhat egy fájlformátum-azonosítót és egy leírást.</span><span class="sxs-lookup"><span data-stu-id="e23f0-132">On the **Positive pay format** page, you can create a file format identifier and a description.</span></span> <span data-ttu-id="e23f0-133">Az átalakítási bemeneti formátumnak XML típusúnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="e23f0-133">The transformation input format must be of the XML type.</span></span> <span data-ttu-id="e23f0-134">Az adott formátum az Ön által használt átalakító fájltól függ.</span><span class="sxs-lookup"><span data-stu-id="e23f0-134">The specific format depends on the transformation file that you're using.</span></span> <span data-ttu-id="e23f0-135">Vegyük például a bővíthető stíluslap-nyelv transzformációt (XSLT) fájlt, amelyhez meg van adva, hogy az **XML-elem** formátumot használja.</span><span class="sxs-lookup"><span data-stu-id="e23f0-135">For example, the sample Extensible Stylesheet Language Transformations (XSLT) file that is provided uses the **XML-Element** format.</span></span> <span data-ttu-id="e23f0-136">Használja az **Az átalakításhoz használt fájl feltöltése** műveletet hogy megadja az átalakítási fájl helyét azon formátumhoz, amelyet a bankja igényel.</span><span class="sxs-lookup"><span data-stu-id="e23f0-136">Use the **Upload file used for transformation** action to specify the location of the transform file for the format that your bank requires.</span></span>

## <a name="example-xslt-file-for-positive-pay-file"></a><span data-ttu-id="e23f0-137">Példa: XSLT-fájl az ellenőrzött fizetési fájlhoz.</span><span class="sxs-lookup"><span data-stu-id="e23f0-137">Example: XSLT file for positive pay file</span></span>
    <xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform" xmlns:msxsl="urn:schemas-microsoft-com:xslt" exclude-result-prefixes="msxsl xslthelper" xmlns="urn:iso:std:iso:20022:tech:xsd:pain.001.001.02" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xslthelper="http://schemas.microsoft.com/BizTalk/2003/xslthelper">
      <xsl:output method="xml" omit-xml-declaration="no" version="1.0" encoding="utf-8"/>
      <xsl:template match="/">
        <xsl:value-of select="'
    '" />
        <Document>
          <xsl:value-of select="'
    '" />
          <!--Header Begin-->
          <xsl:value-of select='string("Vendor ID,Vendor Name,Voided,Document Type,Check Date,Check Number,Check Amount,Checkbook ID,Vendor Class ID,Posted Date")'/>
          <xsl:value-of select="'
    '" />
          <!--Header End-->
          <xsl:for-each select="Document/BankPositivePayExportEntity">
            <!--Cheque Detail begin-->
            <xsl:value-of select='RECIPIENTACCOUNTNUM/text()'/>
            <xsl:value-of select="','" />
            <xsl:value-of select='BANKNEGINSTRECIPIENTNAME/text()'/>
            <xsl:value-of select="','" />
            <xsl:choose>
              <xsl:when test='CHEQUESTATUS/text()=normalize-space("Void") or CHEQUESTATUS/text()=normalize-space("Rejected") or CHEQUESTATUS/text()=normalize-space("Cancelled")'>
                <xsl:value-of select='string("Yes")'/>
              </xsl:when>
              <xsl:when test='CHEQUESTATUS/text()=normalize-space("Payment")'>
                <xsl:value-of select='string("No")'/>
              </xsl:when>
              <xsl:otherwise>
                <xsl:value-of select='string(" ")'/>
              </xsl:otherwise>
            </xsl:choose>
            <xsl:value-of select="','" />
            <xsl:value-of select='string("Payment")'/>
            <xsl:value-of select="','" />
            <xsl:value-of select='TRANSDATE/text()'/>
            <xsl:value-of select="','" />
            <xsl:value-of select='CHEQUENUM/text()'/>
            <xsl:value-of select="','" />
            <xsl:value-of select='AMOUNTCUR/text()'/>
            <xsl:value-of select="','" />
            <xsl:value-of select='string("BOA-#1812")'/>
            <xsl:value-of select="','" />
            <xsl:choose>
              <xsl:when test='RECIPIENTTYPE/text()=normalize-space("Vend")'>
                <xsl:value-of select='VENDGROUP/text()'/>
              </xsl:when>
              <xsl:otherwise>
                <xsl:value-of select='CUSTGROUP/text()'/>
              </xsl:otherwise>
            </xsl:choose>
            <xsl:value-of select="','" />
            <xsl:value-of select='TRANSDATE/text()'/>
            <xsl:value-of select="'
    '" />
          </xsl:for-each>
        </Document>
      </xsl:template>
    </xsl:stylesheet>

## <a name="assign-the-positive-pay-format-to-a-bank-account"></a><span data-ttu-id="e23f0-138">Az ellenőrzött fizetési formátum hozzárendelése egy bankszámlához</span><span class="sxs-lookup"><span data-stu-id="e23f0-138">Assign the positive pay format to a bank account</span></span>
<span data-ttu-id="e23f0-139">Minden egyes bankszámlához, amelyhez szeretne létrehozni ellenőrzött fizetési információt, hozzá kell rendelnie az előző szakaszban megadott ellenőrzött fizetési formátumot.</span><span class="sxs-lookup"><span data-stu-id="e23f0-139">For each bank account that you want to generate positive pay information for, you must assign the positive pay format that you specified in the previous section.</span></span> <span data-ttu-id="e23f0-140">A **Bankszámlák** oldalon válassza ki azt az ellenőrzött fizetési formátumot, amely megfelel a bankszámlájának.</span><span class="sxs-lookup"><span data-stu-id="e23f0-140">On the **Bank accounts** page, select the positive pay format that corresponds to the bank account.</span></span> <span data-ttu-id="e23f0-141">Az **Ellenőrzött fizetés kezdő dátuma** mezőbe írja be az ellenőrzött fizetési fájlok létrehozásának kezdő dátumát.</span><span class="sxs-lookup"><span data-stu-id="e23f0-141">In the **Positive pay start date** field, enter the first date to generate positive pay files.</span></span> <span data-ttu-id="e23f0-142">Fontos, hogy megadjon egy dátumot ebben a mezőben.</span><span class="sxs-lookup"><span data-stu-id="e23f0-142">It's important that you enter a date in this field.</span></span> <span data-ttu-id="e23f0-143">Ellenkező esetben az első fizetési ellenőrző fájl, amit létrehoz tartalmazni fogja az összes csekket, amit valaha létrehoztak ehhez a bankszámlához.</span><span class="sxs-lookup"><span data-stu-id="e23f0-143">Otherwise, the first positive pay file that you generate will include all checks that have ever been created for this bank account.</span></span>

## <a name="assign-a-number-sequence-for-positive-pay-files"></a><span data-ttu-id="e23f0-144">Számsorozat hozzárendelése az ellenőrzött fizetési fájlokhoz</span><span class="sxs-lookup"><span data-stu-id="e23f0-144">Assign a number sequence for positive pay files</span></span>
<span data-ttu-id="e23f0-145">Minden ellenőrzött fizetési fájlnak rendelkeznie kell egy egyedi számmal.</span><span class="sxs-lookup"><span data-stu-id="e23f0-145">Each positive pay file must have a unique number.</span></span> <span data-ttu-id="e23f0-146">Használja a **Számsorozatok** lapot a **Készpénz- és bankkezelési paraméterek** oldalon, hogy számsorozatokat hozzon létre az ellenőrzött fizetési fájlokhoz.</span><span class="sxs-lookup"><span data-stu-id="e23f0-146">Use the **Number sequences** tab on the **Cash and bank management parameters** page to create a number sequence for positive pay files.</span></span>

## <a name="generate-a-positive-pay-file-for-a-single-bank-account"></a><span data-ttu-id="e23f0-147">Ellenőrzött fizetési fájl létrehozása egyetlen bankszámlához</span><span class="sxs-lookup"><span data-stu-id="e23f0-147">Generate a positive pay file for a single bank account</span></span>
<span data-ttu-id="e23f0-148">Létrehozhat egy ellenőrzött fizetési fájlt egyetlen jogi személyhez és egyetlen bankszámlához.</span><span class="sxs-lookup"><span data-stu-id="e23f0-148">You can generate a positive pay file for a single legal entity and a single bank account.</span></span> <span data-ttu-id="e23f0-149">További információért arról, hogy hogyan hozhat létre ellenőrzött fizetési fájlokat egyszerre több jogi személyhez és bankszámlához lásd a következő részt.</span><span class="sxs-lookup"><span data-stu-id="e23f0-149">For information about how to generate positive pay files for multiple legal entities and bank accounts at the same time, see the next section.</span></span> <span data-ttu-id="e23f0-150">Ellenőrzött fizetési fájl létrehozásához, egyetlen jogi személyhez és egyetlen bankszámlához, nyissa meg a **Fizetési ellenőrző fájl létrehozása** párbeszédablakot a **Bankszámlák** oldalon.</span><span class="sxs-lookup"><span data-stu-id="e23f0-150">To generate a positive pay file for a single legal entity and a single bank account, open the **Generate a positive pay file** dialog box from the **Bank accounts** page.</span></span> <span data-ttu-id="e23f0-151">A **Fordulónap dátuma** mezőben adja meg a fizetési ellenőrző fájlban használni kívánt utolsó csekk dátumát.</span><span class="sxs-lookup"><span data-stu-id="e23f0-151">In the **Cut-off date** field, enter the last check date to include in the positive pay file.</span></span> <span data-ttu-id="e23f0-152">Minden olyan csekk, amely nem került bele az ellenőrzött fizetési fájlba ezen csekkdátum végéig bekerül a fájlba.</span><span class="sxs-lookup"><span data-stu-id="e23f0-152">All checks that haven’t been included in a positive pay file by the end of this check date are included in the file.</span></span>

## <a name="generate-a-positive-pay-file-for-multiple-bank-accounts"></a><span data-ttu-id="e23f0-153">Ellenőrzött fizetési fájl létrehozása több bankszámlához</span><span class="sxs-lookup"><span data-stu-id="e23f0-153">Generate a positive pay file for multiple bank accounts</span></span>
<span data-ttu-id="e23f0-154">Ellenőrzött fizetési fájlok létrehozásához több bankszámlához használja a **Fizetési ellenőrző fájl létrehozása** ismétlődő feladatot.</span><span class="sxs-lookup"><span data-stu-id="e23f0-154">To generate a positive pay file for multiple bank accounts, use the **Generate a positive pay file** periodic task.</span></span> <span data-ttu-id="e23f0-155">Válassza ki az ellenőrzött fizetés fájlformátumát és adja meg, hogy minden jogi személyhez létrejöjjön-e a fájl, vagy csak egy kijelölt jogi személyhez.</span><span class="sxs-lookup"><span data-stu-id="e23f0-155">Select the positive pay format for the file, and specify whether to generate the file for all legal entities or for a selected legal entity.</span></span> <span data-ttu-id="e23f0-156">Létrehozhatja továbbá a fájlt minden bankszámlához, amely az adott ellenőrzött fizetési formátumot használja, vagy egy kijelölt bankszámlához.</span><span class="sxs-lookup"><span data-stu-id="e23f0-156">You can also generate the positive pay file for all bank accounts that use the specified positive pay format or for a selected bank account.</span></span> <span data-ttu-id="e23f0-157">A **Fordulónap dátuma** mezőben adja meg a fizetési ellenőrző fájlban használni kívánt utolsó csekk dátumát.</span><span class="sxs-lookup"><span data-stu-id="e23f0-157">In the **Cut-off date** field, enter the last check date to include in the positive pay file.</span></span> <span data-ttu-id="e23f0-158">Minden olyan csekk, amely nem került bele az ellenőrzött fizetési fájlba ezen csekkdátum végéig bekerül a fájlba.</span><span class="sxs-lookup"><span data-stu-id="e23f0-158">All checks that haven’t been included in a positive pay file by the end of this check date are included in the file.</span></span>

## <a name="view-the-results-of-positive-pay-file-generation"></a><span data-ttu-id="e23f0-159">Az ellenőrzött fizetési fájl létrehozásának eredményeinek megtekintése</span><span class="sxs-lookup"><span data-stu-id="e23f0-159">View the results of positive pay file generation</span></span>
<span data-ttu-id="e23f0-160">Miután a fizetési ellenőrző fájl létrejött, megtekintheti az eredmények a **Fizetési ellenőrző fájl összegzése** lapon.</span><span class="sxs-lookup"><span data-stu-id="e23f0-160">After the positive pay file is generated, you can view the results on the **Positive pay file summary** page.</span></span> <span data-ttu-id="e23f0-161">Az egyes csekkek részleteinek megtekintéséhez használja a **Fizetési ellenőrző fájl** részletes lapját.</span><span class="sxs-lookup"><span data-stu-id="e23f0-161">To view the details of the individual checks, use the **Positive pay file** details page.</span></span>

## <a name="confirm-a-positive-pay-file"></a><span data-ttu-id="e23f0-162">A fizetési ellenőrző fájl visszaigazolása</span><span class="sxs-lookup"><span data-stu-id="e23f0-162">Confirm a positive pay file</span></span>
<span data-ttu-id="e23f0-163">Miután kifizetésre kerültek a fizetési ellenőrző fájlban felsorolt csekkek, a bank visszaigazolási számot küld róla.</span><span class="sxs-lookup"><span data-stu-id="e23f0-163">After the checks that are listed in a positive pay file have been paid, you receive a confirmation number from your bank.</span></span> <span data-ttu-id="e23f0-164">Ezt követően visszaigazolhatja a fizetési ellenőrző fájlt.</span><span class="sxs-lookup"><span data-stu-id="e23f0-164">You can then confirm the positive pay file.</span></span> <span data-ttu-id="e23f0-165">A **Fizetési ellenőrző fájl összegzése** lapon, válasszon ki egy ellenőrzött fizetést, amelynek állapota **Létrehozva**, majd válassza ki a **Visszaigazolás beírása** művelet.</span><span class="sxs-lookup"><span data-stu-id="e23f0-165">On the **Positive pay file summary** page, select a positive pay file that has a status of **Created**, and then select the **Enter confirmation** action.</span></span> <span data-ttu-id="e23f0-166">Amikor visszaigazol egy ellenőrzött fizetési fájlt, akkor a banktól kapott visszaigazolási szám rögzítésre kerül.</span><span class="sxs-lookup"><span data-stu-id="e23f0-166">When you confirm a positive pay file, the confirmation number that you received from the bank is recorded.</span></span>

## <a name="recall-a-positive-pay-file"></a><span data-ttu-id="e23f0-167">Fizetési ellenőrző fájl visszahívása</span><span class="sxs-lookup"><span data-stu-id="e23f0-167">Recall a positive pay file</span></span>
<span data-ttu-id="e23f0-168">Ha módosítania kell valamit a fizetési ellenőrző fájlban, akkor vissza tudja hívni.</span><span class="sxs-lookup"><span data-stu-id="e23f0-168">If you must change a positive pay file, you can recall it.</span></span> <span data-ttu-id="e23f0-169">A **Fizetési ellenőrző fájl összegzése** lapon, válasszon ki egy ellenőrzött fizetést, amelynek állapota **Létrehozva**, majd válassza ki a **Visszahívás** művelet.</span><span class="sxs-lookup"><span data-stu-id="e23f0-169">On the **Positive pay file summary** page, select a positive pay file that has a status of **Created**, and then select the **Recall** action.</span></span> <span data-ttu-id="e23f0-170">Minden csekkhez a mező, amely a fizetési ellenőrző fájlban azt jelöli, hogy a csekk szerepel-e egy fizetési ellenőrző fájlban visszaállításra kerül.</span><span class="sxs-lookup"><span data-stu-id="e23f0-170">For each check in the positive pay file, the field that indicates whether that check has been included in a positive pay file is reset.</span></span> <span data-ttu-id="e23f0-171">Ezt követően létrehozhat egy új ellenőrzött fizetési fájlt, amely tartalmazza a visszavont csekket.</span><span class="sxs-lookup"><span data-stu-id="e23f0-171">You can then create a new positive pay file that includes the check that was recalled.</span></span>



