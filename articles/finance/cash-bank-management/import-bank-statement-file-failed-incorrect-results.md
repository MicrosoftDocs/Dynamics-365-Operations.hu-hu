---
title: Banki kivonatfájl importálása – hibaelhárítás
description: Fontos, hogy a bankszámlakivonat-fájl a Microsoft Dynamics 365 Finance által támogatott elrendezésnek megfeleljen. Banki kivonatokra vonatkozó szigorú szabályok miatt a legtöbb Integráció megfelelően fog működni. Azonban bizonyos esetekben a fájl nem importálható, vagy helytelen eredményeket tartalmaz. Általában ezeket a problémákat a bankszámlakivonat-fájlban levő kis eltérések okozzák. Ez a cikk bemutatja, hogy hogyan javítsa ezeket az eltéréseket és hogyan oldja meg a problémákat.
author: panolte
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankStatementFormat
audience: Application User
ms.reviewer: roschlom
ms.custom: 141273
ms.assetid: 3ee2f32b-02aa-420b-8990-e6aa5fc6bda3
ms.search.region: global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: adea87b6341860a9aa1625811270274e02a88b26
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4978939"
---
# <a name="bank-statement-file-import-troubleshooting"></a><span data-ttu-id="4ffa0-107">Banki kivonatfájl importálása – hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="4ffa0-107">Bank statement file import troubleshooting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4ffa0-108">Fontos, hogy a bankszámlakivonat-fájl a Microsoft Dynamics 365 Finance által támogatott elrendezésnek megfeleljen.</span><span class="sxs-lookup"><span data-stu-id="4ffa0-108">It's important that the bank statement file from the bank match the layout that Microsoft Dynamics 365 Finance supports.</span></span> <span data-ttu-id="4ffa0-109">Banki kivonatokra vonatkozó szigorú szabályok miatt a legtöbb Integráció megfelelően fog működni.</span><span class="sxs-lookup"><span data-stu-id="4ffa0-109">Because of strict standards for bank statements, most integrations will work correctly.</span></span> <span data-ttu-id="4ffa0-110">Azonban bizonyos esetekben a fájl nem importálható, vagy helytelen eredményeket tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="4ffa0-110">However, sometimes the statement file can't be imported or has incorrect results.</span></span> <span data-ttu-id="4ffa0-111">Általában ezeket a problémákat a bankszámlakivonat-fájlban levő kis eltérések okozzák.</span><span class="sxs-lookup"><span data-stu-id="4ffa0-111">Typically, these issues are caused by small differences in the bank statement file.</span></span> <span data-ttu-id="4ffa0-112">Ez a cikk bemutatja, hogy hogyan javítsa ezeket az eltéréseket és hogyan oldja meg a problémákat.</span><span class="sxs-lookup"><span data-stu-id="4ffa0-112">This article explains how to fix these differences and resolve the issues.</span></span>

<a name="what-is-the-error"></a><span data-ttu-id="4ffa0-113">Mi a hiba?</span><span class="sxs-lookup"><span data-stu-id="4ffa0-113">What is the error?</span></span>
------------------

<span data-ttu-id="4ffa0-114">Miután megpróbál importálni egy bankszámlakivonat fájlt, a hiba megkereséséhez ugorjon az Adatok kezelése munkaelőzményekre és a végrehajtás részleteire.</span><span class="sxs-lookup"><span data-stu-id="4ffa0-114">After you try to import a bank statement file, go to the Data management job history and its execution details to find the error.</span></span> <span data-ttu-id="4ffa0-115">A hiba a kimutatható a kivonat, egyenleg vagy kivonatsor választásával.</span><span class="sxs-lookup"><span data-stu-id="4ffa0-115">The error can help by pointing to the statement, balance, or statement line.</span></span> <span data-ttu-id="4ffa0-116">Azonban, nem valószínű, hogy segítségével azonosíthatja a mezőt vagy a problémát okozó elemet.</span><span class="sxs-lookup"><span data-stu-id="4ffa0-116">However, it's unlikely to provide enough information to help you identify the field or element that is causing the issue.</span></span>

## <a name="what-are-the-differences"></a><span data-ttu-id="4ffa0-117">Mik a különbségek?</span><span class="sxs-lookup"><span data-stu-id="4ffa0-117">What are the differences?</span></span>
<span data-ttu-id="4ffa0-118">Hasonlítsa össze a bankfájl elrendezésdefinícióját a Finance importdefiníciójával és vegye figyelembe a mezők és elemek esetleges eltéréseit.</span><span class="sxs-lookup"><span data-stu-id="4ffa0-118">Compare the bank file layout definition to the Finance import definition, and note any differences in the fields and elements.</span></span> <span data-ttu-id="4ffa0-119">Hasonlítsa össze a banki kivonatfájlt a Finance kapcsolódó mintafájljával.</span><span class="sxs-lookup"><span data-stu-id="4ffa0-119">Compare the bank statement file to the related sample Finance file.</span></span> <span data-ttu-id="4ffa0-120">A ISO20022 fájlokban az esetleges különbségeket elvileg könnyen látni lehet.</span><span class="sxs-lookup"><span data-stu-id="4ffa0-120">In the ISO20022 files, any differences should be easy to see.</span></span>

## <a name="time-zone-differences-on-imported-bank-statements"></a><span data-ttu-id="4ffa0-121">Az importált banki kivonatok időzónabeli eltérései</span><span class="sxs-lookup"><span data-stu-id="4ffa0-121">Time zone differences on imported bank statements</span></span>
<span data-ttu-id="4ffa0-122">Az importfájl dátum- és időértékei eltérhetnek a Finance and Operations modulban megjelenített dátum-idő értéktől.</span><span class="sxs-lookup"><span data-stu-id="4ffa0-122">The date-time values in the import file can differ from the date-time values that are shown in Finance and Operations.</span></span> <span data-ttu-id="4ffa0-123">Ha meg szeretné akadályozni ezt az eltérést, adja meg az időzóna-beállítást az **Adatforrások konfigurálása** lapon.</span><span class="sxs-lookup"><span data-stu-id="4ffa0-123">To prevent this discrepancy, enter a time zone preference on the **Configure data sources** page.</span></span> <span data-ttu-id="4ffa0-124">Az [Továbbfejlesztett banki egyeztetés importálási folyamata](set-up-advanced-bank-reconciliation-import-process.md) további tudnivalókat nyújt az időzóna-beállítások megadásához.</span><span class="sxs-lookup"><span data-stu-id="4ffa0-124">See [Set up the advanced bank reconciliation import process](set-up-advanced-bank-reconciliation-import-process.md) for more information about entering a time zone preference.</span></span>

## <a name="transformations"></a><span data-ttu-id="4ffa0-125">Átalakítások</span><span class="sxs-lookup"><span data-stu-id="4ffa0-125">Transformations</span></span>
<span data-ttu-id="4ffa0-126">A változtatást általában a három átalakítás egyikében kell végezni.</span><span class="sxs-lookup"><span data-stu-id="4ffa0-126">Typically, the change must be made in one of three transformations.</span></span> <span data-ttu-id="4ffa0-127">Minden egyes átalakítás meghatározott szabványhoz van írva.</span><span class="sxs-lookup"><span data-stu-id="4ffa0-127">Each transformation is written for a specific standard.</span></span>

| <span data-ttu-id="4ffa0-128">Erőforrás neve</span><span class="sxs-lookup"><span data-stu-id="4ffa0-128">Resource name</span></span>                                         | <span data-ttu-id="4ffa0-129">Fájlnév</span><span class="sxs-lookup"><span data-stu-id="4ffa0-129">File name</span></span>                          |
|-------------------------------------------------------|------------------------------------|
| <span data-ttu-id="4ffa0-130">BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt</span><span class="sxs-lookup"><span data-stu-id="4ffa0-130">BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt</span></span>            | <span data-ttu-id="4ffa0-131">BAI2CSV-to-BAI2XML.xslt</span><span class="sxs-lookup"><span data-stu-id="4ffa0-131">BAI2CSV-to-BAI2XML.xslt</span></span>            |
| <span data-ttu-id="4ffa0-132">BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt</span><span class="sxs-lookup"><span data-stu-id="4ffa0-132">BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt</span></span> | <span data-ttu-id="4ffa0-133">ISO20022XML-to-Reconciliation.xslt</span><span class="sxs-lookup"><span data-stu-id="4ffa0-133">ISO20022XML-to-Reconciliation.xslt</span></span> |
| <span data-ttu-id="4ffa0-134">BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt</span><span class="sxs-lookup"><span data-stu-id="4ffa0-134">BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt</span></span>          | <span data-ttu-id="4ffa0-135">MT940TXT-to-MT940XML.xslt</span><span class="sxs-lookup"><span data-stu-id="4ffa0-135">MT940TXT-to-MT940XML.xslt</span></span>          |

## <a name="debugging-transformations"></a><span data-ttu-id="4ffa0-136">Hibakeresés az átalakításokban</span><span class="sxs-lookup"><span data-stu-id="4ffa0-136">Debugging transformations</span></span>
### <a name="adjust-the-bai2-and-mt940-files"></a><span data-ttu-id="4ffa0-137">Módosítsa a BAI2 és MT940 fájlokat</span><span class="sxs-lookup"><span data-stu-id="4ffa0-137">Adjust the BAI2 and MT940 files</span></span>

<span data-ttu-id="4ffa0-138">A BAI2 és MT940 fájlok szöveges fájlok, ezek módosítása szükséges a hibakeresés engedélyezéséhez a stíluslap transzformáción (XSLT).</span><span class="sxs-lookup"><span data-stu-id="4ffa0-138">The BAI2 and MT940 files are text-based files and require an adjustment to enable Extensible Stylesheet Language Transformations (XSLT) debugging.</span></span> <span data-ttu-id="4ffa0-139">A program ezt a módosítást hajtja végre egy fájl importálásakor.</span><span class="sxs-lookup"><span data-stu-id="4ffa0-139">The program makes this adjustment when a file is imported.</span></span>

1.  <span data-ttu-id="4ffa0-140">Hozzon létre XML-fájlt és másolja be a következő szöveget.</span><span class="sxs-lookup"><span data-stu-id="4ffa0-140">Create an XML file, and copy the following text into it.</span></span>

    ```xml
    <Batch><![CDATA[PASTESTATEMENTFILEHERE
        ]]></Batch>
    ```
    
2.  <span data-ttu-id="4ffa0-141">Másolja a bankszámlakivonat-fájl tartalmát és illessze be az XML-fájlba, hogy pótolja **KIVONATFÁLJ BEILLESZTÉSE**.</span><span class="sxs-lookup"><span data-stu-id="4ffa0-141">Copy the contents of the bank statement file, and paste them into the XML file so that they replace **PASTESTATEMENTFILEHERE**.</span></span>

### <a name="debug-the-xslt"></a><span data-ttu-id="4ffa0-142">Hibakeresés XSLT</span><span class="sxs-lookup"><span data-stu-id="4ffa0-142">Debug the XSLT</span></span>

<span data-ttu-id="4ffa0-143">További tájékoztatást a következő témakörben talál: <https://msdn.microsoft.com/library/ms255605.aspx>.</span><span class="sxs-lookup"><span data-stu-id="4ffa0-143">For more information, see <https://msdn.microsoft.com/library/ms255605.aspx>.</span></span>

1.  <span data-ttu-id="4ffa0-144">Indítsa el a Microsoft Visual Studio programot.</span><span class="sxs-lookup"><span data-stu-id="4ffa0-144">Start Microsoft Visual Studio.</span></span>
2.  <span data-ttu-id="4ffa0-145">Hozzon létre konzol alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="4ffa0-145">Create a console application.</span></span>
3.  <span data-ttu-id="4ffa0-146">Nyissa meg a megfelelő XSLT-fájlt.</span><span class="sxs-lookup"><span data-stu-id="4ffa0-146">Open the appropriate XSLT.</span></span>
4.  <span data-ttu-id="4ffa0-147">Kattintson az XSLT-fájlra és annak tulajdonságlapjára.</span><span class="sxs-lookup"><span data-stu-id="4ffa0-147">Click the XLST and its properties page.</span></span>
5.  <span data-ttu-id="4ffa0-148">Állítsa be a bemenetet bankszámlakivonat-fájl helyére.</span><span class="sxs-lookup"><span data-stu-id="4ffa0-148">Set the input to the location of the bank statement file.</span></span>
6.  <span data-ttu-id="4ffa0-149">Adja meg a kimenet helyét és nevét.</span><span class="sxs-lookup"><span data-stu-id="4ffa0-149">Define a location and file name for the output.</span></span>
7.  <span data-ttu-id="4ffa0-150">Állítsa be a szükséges töréspontokat.</span><span class="sxs-lookup"><span data-stu-id="4ffa0-150">Set the required break points.</span></span>
8.  <span data-ttu-id="4ffa0-151">A menüben kattintson az **XML** &gt; **XSLT-hibakeresés Indítása** elemre.</span><span class="sxs-lookup"><span data-stu-id="4ffa0-151">On the menu, click **XML** &gt; **Start XSLT Debugging**.</span></span>

### <a name="format-the-xslt-output"></a><span data-ttu-id="4ffa0-152">XSLT-kimenet formázása</span><span class="sxs-lookup"><span data-stu-id="4ffa0-152">Format the XSLT output</span></span>

<span data-ttu-id="4ffa0-153">Az átalakítás futtatásakor kimeneti fájl készül, amelyet meg lehet tekinteni a Visual Studio alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="4ffa0-153">When the transformation runs, it creates an output file that you can view in Visual Studio.</span></span> <span data-ttu-id="4ffa0-154">Használja a Ctrl + A, Ctrl + K és a Ctrl + D billentyűkombinációkat a kimeneti fájl gyors formázásához.</span><span class="sxs-lookup"><span data-stu-id="4ffa0-154">Use Ctrl+A, Ctrl+K, and Ctrl+D to quickly format the output file.</span></span>

### <a name="adjust-the-transformation"></a><span data-ttu-id="4ffa0-155">Állítsa be az átalakítást</span><span class="sxs-lookup"><span data-stu-id="4ffa0-155">Adjust the transformation</span></span>

<span data-ttu-id="4ffa0-156">Állítsa be az átalakítást, a megfelelő mező vagy elem megkereséséhez a bankszámlakivonat fájlban.</span><span class="sxs-lookup"><span data-stu-id="4ffa0-156">Adjust the transformation to get the appropriate field or element in the bank statement file.</span></span> <span data-ttu-id="4ffa0-157">Ezután rendelje hozzá azt a mezőt vagy elemet a Finance elemhez.</span><span class="sxs-lookup"><span data-stu-id="4ffa0-157">Then map that field or element to the appropriate Finance element.</span></span>

### <a name="debitcredit-indicator"></a><span data-ttu-id="4ffa0-158">Tartozás/követelés jelzése</span><span class="sxs-lookup"><span data-stu-id="4ffa0-158">Debit/credit indicator</span></span>

<span data-ttu-id="4ffa0-159">Bizonyos esetekben kötelezettségeket kintlevőségekként lehet importálni, és kintlevőségeket kötelezettségekként lehet importálni.</span><span class="sxs-lookup"><span data-stu-id="4ffa0-159">Sometimes, debits might be imported as credits, and credits might be imported as debits.</span></span> <span data-ttu-id="4ffa0-160">A probléma megoldásához módosítania kell a megfelelő XSLT fájlt.</span><span class="sxs-lookup"><span data-stu-id="4ffa0-160">To resolve this issue, you must change the appropriate XSLT.</span></span> <span data-ttu-id="4ffa0-161">Ha a banki kivonatok több bankból származnak, ha győződjön meg róla, hogy ugyanazon tartozási/követelési módszert használják, vagy külön átalakításokat hoznak létre.</span><span class="sxs-lookup"><span data-stu-id="4ffa0-161">If bank statements come from multiple banks, make sure that they all use the same debit/credit approach, or create separate transformations.</span></span>

-   <span data-ttu-id="4ffa0-162">BAI2XML–Reconciliation.xlst GetAmountCreditDebitIndicator sablon</span><span class="sxs-lookup"><span data-stu-id="4ffa0-162">BAI2XML-to-Reconciliation.xlst GetAmountCreditDebitIndicator template</span></span>
-   <span data-ttu-id="4ffa0-163">ISO20022XML–Reconcilation.xslt GetCreditDebit sablon</span><span class="sxs-lookup"><span data-stu-id="4ffa0-163">ISO20022XML-to-Reconcilation.xslt GetCreditDebit template</span></span>
-   <span data-ttu-id="4ffa0-164">MT940XML–Reconcilation.xslt GetCreditDebitIndicator sablon</span><span class="sxs-lookup"><span data-stu-id="4ffa0-164">MT940XML-to-Reconcilation.xslt GetCreditDebitIndicator template</span></span>

## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a><span data-ttu-id="4ffa0-165">A banki kivonat formátumainak és a technikai elrendezések példái</span><span class="sxs-lookup"><span data-stu-id="4ffa0-165">Examples of bank statement formats and technical layouts</span></span>
<span data-ttu-id="4ffa0-166">A következő táblázat felsorolja a továbbfejlesztett banki egyeztetés importfájl technikai elrendezésű definicóinak példáit és a három kapcsolódó banki kivonat példafájljait találhatja.</span><span class="sxs-lookup"><span data-stu-id="4ffa0-166">The following table lists examples of the technical layout definitions for advanced bank reconciliation import files and three related bank statement example files.</span></span> <span data-ttu-id="4ffa0-167">A példa fájlokat és műszaki elrendezéseket itt töltheti le: https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/exofbankstfotechlayouts</span><span class="sxs-lookup"><span data-stu-id="4ffa0-167">You can download the example files and technical layouts here: https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/exofbankstfotechlayouts</span></span>  


| <span data-ttu-id="4ffa0-168">Technikai elrendezésdefiníció</span><span class="sxs-lookup"><span data-stu-id="4ffa0-168">Technical layout definition</span></span>                             | <span data-ttu-id="4ffa0-169">Banki kivonat példafájl</span><span class="sxs-lookup"><span data-stu-id="4ffa0-169">Bank statement example file</span></span>          |
|---------------------------------------------------------|--------------------------------------|
| <span data-ttu-id="4ffa0-170">DynamicsAXMT940Layout</span><span class="sxs-lookup"><span data-stu-id="4ffa0-170">DynamicsAXMT940Layout</span></span>                                   | <span data-ttu-id="4ffa0-171">MT940StatementExample</span><span class="sxs-lookup"><span data-stu-id="4ffa0-171">MT940StatementExample</span></span>                |
| <span data-ttu-id="4ffa0-172">DynamicsAXISO20022Layout</span><span class="sxs-lookup"><span data-stu-id="4ffa0-172">DynamicsAXISO20022Layout</span></span>                                | <span data-ttu-id="4ffa0-173">ISO20022StatementExample</span><span class="sxs-lookup"><span data-stu-id="4ffa0-173">ISO20022StatementExample</span></span>             |
| <span data-ttu-id="4ffa0-174">DynamicsAXBAI2Layout</span><span class="sxs-lookup"><span data-stu-id="4ffa0-174">DynamicsAXBAI2Layout</span></span>                                    | <span data-ttu-id="4ffa0-175">BAI2StatementExample</span><span class="sxs-lookup"><span data-stu-id="4ffa0-175">BAI2StatementExample</span></span>                 |





