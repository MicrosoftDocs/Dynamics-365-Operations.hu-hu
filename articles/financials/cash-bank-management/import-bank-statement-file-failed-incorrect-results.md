---
title: "Banki kivonatfájl importálása – hibaelhárítás"
description: "Fontos, hogy a banki kivonatfájl a Microsoft Dynamics 365 for Finance and Operations, Enterprise kiadás által támogatott elrendezésnek megfeleljen. Banki kivonatokra vonatkozó szigorú szabályok miatt a legtöbb Integráció megfelelően fog működni. Azonban bizonyos esetekben a fájl nem importálható, vagy helytelen eredményeket tartalmaz. Általában ezeket a problémákat a bankszámlakivonat-fájlban levő kis eltérések okozzák. Ez a cikk bemutatja, hogy hogyan javítsa ezeket az eltéréseket és hogyan oldja meg a problémákat."
author: twheeloc
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankStatementFormat
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 141273
ms.assetid: 3ee2f32b-02aa-420b-8990-e6aa5fc6bda3
ms.search.region: global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: b1f772d9c6393df97a3008f60c5c5fc2e802b853
ms.contentlocale: hu-hu
ms.lasthandoff: 01/17/2018

---

# <a name="bank-statement-file-import-troubleshooting"></a><span data-ttu-id="22de0-107">Banki kivonatfájl importálása – hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="22de0-107">Bank statement file import troubleshooting</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="22de0-108">Fontos, hogy a banki kivonatfájl a Microsoft Dynamics 365 for Finance and Operations, Enterprise kiadás által támogatott elrendezésnek megfeleljen.</span><span class="sxs-lookup"><span data-stu-id="22de0-108">It's important that the bank statement file from the bank match the layout that Microsoft Dynamics 365 for Finance and Operations, Enterprise edition supports.</span></span> <span data-ttu-id="22de0-109">Banki kivonatokra vonatkozó szigorú szabályok miatt a legtöbb Integráció megfelelően fog működni.</span><span class="sxs-lookup"><span data-stu-id="22de0-109">Because of strict standards for bank statements, most integrations will work correctly.</span></span> <span data-ttu-id="22de0-110">Azonban bizonyos esetekben a fájl nem importálható, vagy helytelen eredményeket tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="22de0-110">However, sometimes the statement file can't be imported or has incorrect results.</span></span> <span data-ttu-id="22de0-111">Általában ezeket a problémákat a bankszámlakivonat-fájlban levő kis eltérések okozzák.</span><span class="sxs-lookup"><span data-stu-id="22de0-111">Typically, these issues are caused by small differences in the bank statement file.</span></span> <span data-ttu-id="22de0-112">Ez a cikk bemutatja, hogy hogyan javítsa ezeket az eltéréseket és hogyan oldja meg a problémákat.</span><span class="sxs-lookup"><span data-stu-id="22de0-112">This article explains how to fix these differences and resolve the issues.</span></span>

<a name="what-is-the-error"></a><span data-ttu-id="22de0-113">Mi a hiba?</span><span class="sxs-lookup"><span data-stu-id="22de0-113">What is the error?</span></span>
------------------

<span data-ttu-id="22de0-114">Miután megpróbál importálni egy bankszámlakivonat fájlt, a hiba megkereséséhez ugorjon az Adatok kezelése munkaelőzményekre és a végrehajtás részleteire.</span><span class="sxs-lookup"><span data-stu-id="22de0-114">After you try to import a bank statement file, go to the Data management job history and its execution details to find the error.</span></span> <span data-ttu-id="22de0-115">A hiba a kimutatható a kivonat, egyenleg vagy kivonatsor választásával.</span><span class="sxs-lookup"><span data-stu-id="22de0-115">The error can help by pointing to the statement, balance, or statement line.</span></span> <span data-ttu-id="22de0-116">Azonban, nem valószínű, hogy segítségével azonosíthatja a mezőt vagy a problémát okozó elemet.</span><span class="sxs-lookup"><span data-stu-id="22de0-116">However, it's unlikely to provide enough information to help you identify the field or element that is causing the issue.</span></span>

## <a name="what-are-the-differences"></a><span data-ttu-id="22de0-117">Mik a különbségek?</span><span class="sxs-lookup"><span data-stu-id="22de0-117">What are the differences?</span></span>
<span data-ttu-id="22de0-118">Hasonlítsa össze a bankfájl elrendezésdefinícióját a Finance and Operations importdefiníciójával és vegye figyelembe a mezők és elemek esetleges eltéréseit.</span><span class="sxs-lookup"><span data-stu-id="22de0-118">Compare the bank file layout definition to the Finance and Operations import definition, and note any differences in the fields and elements.</span></span> <span data-ttu-id="22de0-119">Hasonlítsa össze a banki kivonatfájlt a Finance and Operations kapcsolódó mintafájljával.</span><span class="sxs-lookup"><span data-stu-id="22de0-119">Compare the bank statement file to the related sample Finance and Operations file.</span></span> <span data-ttu-id="22de0-120">A ISO20022 fájlokban az esetleges különbségeket elvileg könnyen látni lehet.</span><span class="sxs-lookup"><span data-stu-id="22de0-120">In the ISO20022 files, any differences should be easy to see.</span></span>

## <a name="transformations"></a><span data-ttu-id="22de0-121">Átalakítások</span><span class="sxs-lookup"><span data-stu-id="22de0-121">Transformations</span></span>
<span data-ttu-id="22de0-122">A változtatást általában a három átalakítás egyikében kell végezni.</span><span class="sxs-lookup"><span data-stu-id="22de0-122">Typically, the change must be made in one of three transformations.</span></span> <span data-ttu-id="22de0-123">Minden egyes átalakítás meghatározott szabványhoz van írva.</span><span class="sxs-lookup"><span data-stu-id="22de0-123">Each transformation is written for a specific standard.</span></span>

| <span data-ttu-id="22de0-124">Erőforrás neve</span><span class="sxs-lookup"><span data-stu-id="22de0-124">Resource name</span></span>                                         | <span data-ttu-id="22de0-125">Fájlnév</span><span class="sxs-lookup"><span data-stu-id="22de0-125">File name</span></span>                          |
|-------------------------------------------------------|------------------------------------|
| <span data-ttu-id="22de0-126">BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt</span><span class="sxs-lookup"><span data-stu-id="22de0-126">BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt</span></span>            | <span data-ttu-id="22de0-127">BAI2CSV-to-BAI2XML.xslt</span><span class="sxs-lookup"><span data-stu-id="22de0-127">BAI2CSV-to-BAI2XML.xslt</span></span>            |
| <span data-ttu-id="22de0-128">BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt</span><span class="sxs-lookup"><span data-stu-id="22de0-128">BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt</span></span> | <span data-ttu-id="22de0-129">ISO20022XML-to-Reconciliation.xslt</span><span class="sxs-lookup"><span data-stu-id="22de0-129">ISO20022XML-to-Reconciliation.xslt</span></span> |
| <span data-ttu-id="22de0-130">BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt</span><span class="sxs-lookup"><span data-stu-id="22de0-130">BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt</span></span>          | <span data-ttu-id="22de0-131">MT940TXT-to-MT940XML.xslt</span><span class="sxs-lookup"><span data-stu-id="22de0-131">MT940TXT-to-MT940XML.xslt</span></span>          |

## <a name="debugging-transformations"></a><span data-ttu-id="22de0-132">Hibakeresés az átalakításokban</span><span class="sxs-lookup"><span data-stu-id="22de0-132">Debugging transformations</span></span>
### <a name="adjust-the-bai2-and-mt940-files"></a><span data-ttu-id="22de0-133">Módosítsa a BAI2 és MT940 fájlokat</span><span class="sxs-lookup"><span data-stu-id="22de0-133">Adjust the BAI2 and MT940 files</span></span>

<span data-ttu-id="22de0-134">A BAI2 és MT940 fájlok szöveges fájlok, ezek módosítása szükséges a hibakeresés engedélyezéséhez a stíluslap transzformáción (XSLT).</span><span class="sxs-lookup"><span data-stu-id="22de0-134">The BAI2 and MT940 files are text-based files and require an adjustment to enable Extensible Stylesheet Language Transformations (XSLT) debugging.</span></span> <span data-ttu-id="22de0-135">A program ezt a módosítást hajtja végre egy fájl importálásakor.</span><span class="sxs-lookup"><span data-stu-id="22de0-135">The program makes this adjustment when a file is imported.</span></span>

1.  <span data-ttu-id="22de0-136">Hozzon létre XML-fájlt és másolja be a következő szöveget.</span><span class="sxs-lookup"><span data-stu-id="22de0-136">Create an XML file, and copy the following text into it.</span></span>

        <Batch><![CDATA[PASTESTATEMENTFILEHERE
        ]]></Batch>

2.  <span data-ttu-id="22de0-137">Másolja a bankszámlakivonat-fájl tartalmát és illessze be az XML-fájlba, hogy pótolja **KIVONATFÁLJ BEILLESZTÉSE**.</span><span class="sxs-lookup"><span data-stu-id="22de0-137">Copy the contents of the bank statement file, and paste them into the XML file so that they replace **PASTESTATEMENTFILEHERE**.</span></span>

### <a name="debug-the-xslt"></a><span data-ttu-id="22de0-138">Hibakeresés XSLT</span><span class="sxs-lookup"><span data-stu-id="22de0-138">Debug the XSLT</span></span>

<span data-ttu-id="22de0-139">További tudnivalókért: <https://msdn.microsoft.com/en-us/library/ms255605.aspx>.</span><span class="sxs-lookup"><span data-stu-id="22de0-139">For more information, see <https://msdn.microsoft.com/en-us/library/ms255605.aspx>.</span></span>

1.  <span data-ttu-id="22de0-140">Indítsa el a Microsoft Visual Studio alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="22de0-140">Start Microsoft Visual Studio.</span></span>
2.  <span data-ttu-id="22de0-141">Hozzon létre konzol alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="22de0-141">Create a console application.</span></span>
3.  <span data-ttu-id="22de0-142">Nyissa meg a megfelelő XSLT-fájlt.</span><span class="sxs-lookup"><span data-stu-id="22de0-142">Open the appropriate XSLT.</span></span>
4.  <span data-ttu-id="22de0-143">Kattintson az XSLT-fájlra és annak tulajdonságlapjára.</span><span class="sxs-lookup"><span data-stu-id="22de0-143">Click the XLST and its properties page.</span></span>
5.  <span data-ttu-id="22de0-144">Állítsa be a bemenetet bankszámlakivonat-fájl helyére.</span><span class="sxs-lookup"><span data-stu-id="22de0-144">Set the input to the location of the bank statement file.</span></span>
6.  <span data-ttu-id="22de0-145">Adja meg a kimenet helyét és nevét.</span><span class="sxs-lookup"><span data-stu-id="22de0-145">Define a location and file name for the output.</span></span>
7.  <span data-ttu-id="22de0-146">Állítsa be a szükséges töréspontokat.</span><span class="sxs-lookup"><span data-stu-id="22de0-146">Set the required break points.</span></span>
8.  <span data-ttu-id="22de0-147">A menüben kattintson az **XML** &gt; **XSLT-hibakeresés Indítása** elemre.</span><span class="sxs-lookup"><span data-stu-id="22de0-147">On the menu, click **XML** &gt; **Start XSLT Debugging**.</span></span>

### <a name="format-the-xslt-output"></a><span data-ttu-id="22de0-148">XSLT-kimenet formázása</span><span class="sxs-lookup"><span data-stu-id="22de0-148">Format the XSLT output</span></span>

<span data-ttu-id="22de0-149">Az átalakítás futtatásakor kimeneti fájl készül, amelyet meg lehet tekinteni a Visual Studio alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="22de0-149">When the transformation runs, it creates an output file that you can view in Visual Studio.</span></span> <span data-ttu-id="22de0-150">Használja a Ctrl + A, Ctrl + K és a Ctrl + D billentyűkombinációkat a kimeneti fájl gyors formázásához.</span><span class="sxs-lookup"><span data-stu-id="22de0-150">Use Ctrl+A, Ctrl+K, and Ctrl+D to quickly format the output file.</span></span>

### <a name="adjust-the-transformation"></a><span data-ttu-id="22de0-151">Állítsa be az átalakítást</span><span class="sxs-lookup"><span data-stu-id="22de0-151">Adjust the transformation</span></span>

<span data-ttu-id="22de0-152">Állítsa be az átalakítást, a megfelelő mező vagy elem megkereséséhez a bankszámlakivonat fájlban.</span><span class="sxs-lookup"><span data-stu-id="22de0-152">Adjust the transformation to get the appropriate field or element in the bank statement file.</span></span> <span data-ttu-id="22de0-153">Ezután rendelje hozzá azt a mezőt vagy elemet a Finance and Operations-elemhez.</span><span class="sxs-lookup"><span data-stu-id="22de0-153">Then map that field or element to the appropriate Finance and Operations element.</span></span>

### <a name="debitcredit-indicator"></a><span data-ttu-id="22de0-154">Tartozás/követelés jelzése</span><span class="sxs-lookup"><span data-stu-id="22de0-154">Debit/credit indicator</span></span>

<span data-ttu-id="22de0-155">Bizonyos esetekben kötelezettségeket kintlevőségekként lehet importálni, és kintlevőségeket kötelezettségekként lehet importálni.</span><span class="sxs-lookup"><span data-stu-id="22de0-155">Sometimes, debits might be imported as credits, and credits might be imported as debits.</span></span> <span data-ttu-id="22de0-156">A probléma megoldásához módosítania kell a megfelelő XSLT fájlt.</span><span class="sxs-lookup"><span data-stu-id="22de0-156">To resolve this issue, you must change the appropriate XSLT.</span></span> <span data-ttu-id="22de0-157">Ha a banki kivonatok több bankból származnak, ha győződjön meg róla, hogy ugyanazon tartozási/követelési módszert használják, vagy külön átalakításokat hoznak létre.</span><span class="sxs-lookup"><span data-stu-id="22de0-157">If bank statements come from multiple banks, make sure that they all use the same debit/credit approach, or create separate transformations.</span></span>

-   <span data-ttu-id="22de0-158">BAI2XML–Reconciliation.xlst GetAmountCreditDebitIndicator sablon</span><span class="sxs-lookup"><span data-stu-id="22de0-158">BAI2XML-to-Reconciliation.xlst GetAmountCreditDebitIndicator template</span></span>
-   <span data-ttu-id="22de0-159">ISO20022XML–Reconcilation.xslt GetCreditDebit sablon</span><span class="sxs-lookup"><span data-stu-id="22de0-159">ISO20022XML-to-Reconcilation.xslt GetCreditDebit template</span></span>
-   <span data-ttu-id="22de0-160">MT940XML–Reconcilation.xslt GetCreditDebitIndicator sablon</span><span class="sxs-lookup"><span data-stu-id="22de0-160">MT940XML-to-Reconcilation.xslt GetCreditDebitIndicator template</span></span>

## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a><span data-ttu-id="22de0-161">A banki kivonat formátumainak és a technikai elrendezések példái</span><span class="sxs-lookup"><span data-stu-id="22de0-161">Examples of bank statement formats and technical layouts</span></span>
<span data-ttu-id="22de0-162">A következő táblázat felsorolja a továbbfejlesztett banki egyeztetés importfájl technikai elrendezésű definicóinak példáit és a három kapcsolódó banki kivonat példafájljait találhatja.</span><span class="sxs-lookup"><span data-stu-id="22de0-162">The following table lists examples of the technical layout definitions for advanced bank reconciliation import files and three related bank statement example files.</span></span> <span data-ttu-id="22de0-163">A példafájlokat és műszaki elrendezéseket innen töltheti le: https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/exofbankstfotechlayouts</span><span class="sxs-lookup"><span data-stu-id="22de0-163">You can download the example files and technical layouts here: https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/exofbankstfotechlayouts</span></span>  


| <span data-ttu-id="22de0-164">Technikai elrendezésdefiníció</span><span class="sxs-lookup"><span data-stu-id="22de0-164">Technical layout definition</span></span>                             | <span data-ttu-id="22de0-165">Banki kivonat példafájl</span><span class="sxs-lookup"><span data-stu-id="22de0-165">Bank statement example file</span></span>          |
|---------------------------------------------------------|--------------------------------------|
| <span data-ttu-id="22de0-166">DynamicsAXMT940Layout</span><span class="sxs-lookup"><span data-stu-id="22de0-166">DynamicsAXMT940Layout</span></span>                                   | <span data-ttu-id="22de0-167">MT940StatementExample</span><span class="sxs-lookup"><span data-stu-id="22de0-167">MT940StatementExample</span></span>                |
| <span data-ttu-id="22de0-168">DynamicsAXISO20022Layout</span><span class="sxs-lookup"><span data-stu-id="22de0-168">DynamicsAXISO20022Layout</span></span>                                | <span data-ttu-id="22de0-169">ISO20022StatementExample</span><span class="sxs-lookup"><span data-stu-id="22de0-169">ISO20022StatementExample</span></span>             |
| <span data-ttu-id="22de0-170">DynamicsAXBAI2Layout</span><span class="sxs-lookup"><span data-stu-id="22de0-170">DynamicsAXBAI2Layout</span></span>                                    | <span data-ttu-id="22de0-171">BAI2StatementExample</span><span class="sxs-lookup"><span data-stu-id="22de0-171">BAI2StatementExample</span></span>                 |






