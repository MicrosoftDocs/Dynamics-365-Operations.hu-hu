---
title: Banki kivonatfájl importálása – hibaelhárítás
description: Fontos, hogy a bankszámlakivonat-fájl a Microsoft Dynamics 365 Finance által támogatott elrendezésnek megfeleljen. Banki kivonatokra vonatkozó szigorú szabályok miatt a legtöbb Integráció megfelelően fog működni. Azonban bizonyos esetekben a fájl nem importálható, vagy helytelen eredményeket tartalmaz. Általában ezeket a problémákat a bankszámlakivonat-fájlban levő kis eltérések okozzák. Ez a cikk bemutatja, hogy hogyan javítsa ezeket az eltéréseket és hogyan oldja meg a problémákat.
author: panolte
ms.date: 03/29/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: f0e01881a6b68526479d27014d49a718069cffc9
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815884"
---
# <a name="bank-statement-file-import-troubleshooting"></a><span data-ttu-id="9e84f-107">Banki kivonatfájl importálása – hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="9e84f-107">Bank statement file import troubleshooting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9e84f-108">Fontos, hogy a bankszámlakivonat-fájl a Microsoft Dynamics 365 Finance által támogatott elrendezésnek megfeleljen.</span><span class="sxs-lookup"><span data-stu-id="9e84f-108">It's important that the bank statement file from the bank matches the layout that Microsoft Dynamics 365 Finance supports.</span></span> <span data-ttu-id="9e84f-109">Banki kivonatokra vonatkozó szigorú szabályok miatt a legtöbb Integráció megfelelően fog működni.</span><span class="sxs-lookup"><span data-stu-id="9e84f-109">Because of strict standards for bank statements, most integrations will work correctly.</span></span> <span data-ttu-id="9e84f-110">Azonban bizonyos esetekben a fájl nem importálható, vagy helytelen eredményeket tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="9e84f-110">However, sometimes the statement file can't be imported or has incorrect results.</span></span> <span data-ttu-id="9e84f-111">Általában ezeket a problémákat a bankszámlakivonat-fájlban levő kis eltérések okozzák.</span><span class="sxs-lookup"><span data-stu-id="9e84f-111">Typically, these issues are caused by small differences in the bank statement file.</span></span> <span data-ttu-id="9e84f-112">Ez a cikk bemutatja, hogy hogyan javítsa ezeket az eltéréseket és hogyan oldja meg a problémákat.</span><span class="sxs-lookup"><span data-stu-id="9e84f-112">This article explains how to fix these differences and resolve the issues.</span></span>

<a name="what-is-the-error"></a><span data-ttu-id="9e84f-113">Mi a hiba?</span><span class="sxs-lookup"><span data-stu-id="9e84f-113">What is the error?</span></span>
------------------

<span data-ttu-id="9e84f-114">Miután megpróbál importálni egy bankszámlakivonat fájlt, a hiba megkereséséhez ugorjon az Adatok kezelése munkaelőzményekre és a végrehajtás részleteire.</span><span class="sxs-lookup"><span data-stu-id="9e84f-114">After you try to import a bank statement file, go to the Data management job history and its execution details to find the error.</span></span> <span data-ttu-id="9e84f-115">A hiba a kimutatható a kivonat, egyenleg vagy kivonatsor választásával.</span><span class="sxs-lookup"><span data-stu-id="9e84f-115">The error can help by pointing to the statement, balance, or statement line.</span></span> <span data-ttu-id="9e84f-116">Azonban, nem valószínű, hogy segítségével azonosíthatja a mezőt vagy a problémát okozó elemet.</span><span class="sxs-lookup"><span data-stu-id="9e84f-116">However, it's unlikely to provide enough information to help you identify the field or element that is causing the issue.</span></span>

> [!NOTE]
> <span data-ttu-id="9e84f-117">Az importált banki kivonatok csak egy időpontban fedhetik át egymást.</span><span class="sxs-lookup"><span data-stu-id="9e84f-117">Imported bank statements can overlap only for single a point in time.</span></span>  <span data-ttu-id="9e84f-118">Ha például a kivonat 2021. január 1-jén 12:00 órakor ér véget, akkor a következő kivonat kezdő dátuma lehet de. 12:00 óra, 2021. de. 12:00:00 időpontban.</span><span class="sxs-lookup"><span data-stu-id="9e84f-118">For example, if a statement ends at 12:00 AM on January 1, 2021, then beginning date for the next statement can be 12:00 AM on Jarnuary 1, 2021 12:00:00 AM.</span></span>

## <a name="what-are-the-differences"></a><span data-ttu-id="9e84f-119">Mik a különbségek?</span><span class="sxs-lookup"><span data-stu-id="9e84f-119">What are the differences?</span></span>
<span data-ttu-id="9e84f-120">Hasonlítsa össze a bankfájl elrendezésdefinícióját a Finance importdefiníciójával és vegye figyelembe a mezők és elemek esetleges eltéréseit.</span><span class="sxs-lookup"><span data-stu-id="9e84f-120">Compare the bank file layout definition to the Finance import definition, and note any differences in the fields and elements.</span></span> <span data-ttu-id="9e84f-121">Hasonlítsa össze a banki kivonatfájlt a Finance kapcsolódó mintafájljával.</span><span class="sxs-lookup"><span data-stu-id="9e84f-121">Compare the bank statement file to the related sample Finance file.</span></span> <span data-ttu-id="9e84f-122">A ISO20022 fájlokban az esetleges különbségeket elvileg könnyen látni lehet.</span><span class="sxs-lookup"><span data-stu-id="9e84f-122">In the ISO20022 files, any differences should be easy to see.</span></span>

## <a name="time-zone-differences-on-imported-bank-statements"></a><span data-ttu-id="9e84f-123">Az importált banki kivonatok időzónabeli eltérései</span><span class="sxs-lookup"><span data-stu-id="9e84f-123">Time zone differences on imported bank statements</span></span>
<span data-ttu-id="9e84f-124">Az importfájl dátum- és időértékei eltérhetnek a Finance and Operations modulban megjelenített dátum-idő értéktől.</span><span class="sxs-lookup"><span data-stu-id="9e84f-124">The date-time values in the import file can differ from the date-time values that are shown in Finance and Operations.</span></span> <span data-ttu-id="9e84f-125">Ha meg szeretné akadályozni ezt az eltérést, adja meg az időzóna-beállítást az **Adatforrások konfigurálása** lapon.</span><span class="sxs-lookup"><span data-stu-id="9e84f-125">To prevent this discrepancy, enter a time zone preference on the **Configure data sources** page.</span></span> <span data-ttu-id="9e84f-126">Az [Továbbfejlesztett banki egyeztetés importálási folyamata](set-up-advanced-bank-reconciliation-import-process.md) rész további tudnivalókat nyújt az időzóna-beállítások megadásához.</span><span class="sxs-lookup"><span data-stu-id="9e84f-126">For more information about entering a time zone preference, see [Set up the advanced bank reconciliation import process](set-up-advanced-bank-reconciliation-import-process.md).</span></span>

## <a name="transformations"></a><span data-ttu-id="9e84f-127">Átalakítások</span><span class="sxs-lookup"><span data-stu-id="9e84f-127">Transformations</span></span>
<span data-ttu-id="9e84f-128">A változtatást általában a három átalakítás egyikében kell végezni.</span><span class="sxs-lookup"><span data-stu-id="9e84f-128">Typically, the change must be made in one of three transformations.</span></span> <span data-ttu-id="9e84f-129">Minden egyes átalakítás meghatározott szabványhoz van írva.</span><span class="sxs-lookup"><span data-stu-id="9e84f-129">Each transformation is written for a specific standard.</span></span>

| <span data-ttu-id="9e84f-130">Erőforrás neve</span><span class="sxs-lookup"><span data-stu-id="9e84f-130">Resource name</span></span>                                         | <span data-ttu-id="9e84f-131">Fájlnév</span><span class="sxs-lookup"><span data-stu-id="9e84f-131">File name</span></span>                          |
|-------------------------------------------------------|------------------------------------|
| <span data-ttu-id="9e84f-132">BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt</span><span class="sxs-lookup"><span data-stu-id="9e84f-132">BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt</span></span>            | <span data-ttu-id="9e84f-133">BAI2CSV-to-BAI2XML.xslt</span><span class="sxs-lookup"><span data-stu-id="9e84f-133">BAI2CSV-to-BAI2XML.xslt</span></span>            |
| <span data-ttu-id="9e84f-134">BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt</span><span class="sxs-lookup"><span data-stu-id="9e84f-134">BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt</span></span> | <span data-ttu-id="9e84f-135">ISO20022XML-to-Reconciliation.xslt</span><span class="sxs-lookup"><span data-stu-id="9e84f-135">ISO20022XML-to-Reconciliation.xslt</span></span> |
| <span data-ttu-id="9e84f-136">BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt</span><span class="sxs-lookup"><span data-stu-id="9e84f-136">BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt</span></span>          | <span data-ttu-id="9e84f-137">MT940TXT-to-MT940XML.xslt</span><span class="sxs-lookup"><span data-stu-id="9e84f-137">MT940TXT-to-MT940XML.xslt</span></span>          |

## <a name="debugging-transformations"></a><span data-ttu-id="9e84f-138">Hibakeresés az átalakításokban</span><span class="sxs-lookup"><span data-stu-id="9e84f-138">Debugging transformations</span></span>
### <a name="adjust-the-bai2-and-mt940-files"></a><span data-ttu-id="9e84f-139">Módosítsa a BAI2 és MT940 fájlokat</span><span class="sxs-lookup"><span data-stu-id="9e84f-139">Adjust the BAI2 and MT940 files</span></span>

<span data-ttu-id="9e84f-140">A BAI2 és MT940 fájlok szöveges fájlok, ezek módosítása szükséges a hibakeresés engedélyezéséhez a stíluslap transzformáción (XSLT).</span><span class="sxs-lookup"><span data-stu-id="9e84f-140">The BAI2 and MT940 files are text-based files and require an adjustment to enable Extensible Stylesheet Language Transformations (XSLT) debugging.</span></span> <span data-ttu-id="9e84f-141">A program ezt a módosítást hajtja végre egy fájl importálásakor.</span><span class="sxs-lookup"><span data-stu-id="9e84f-141">The program makes this adjustment when a file is imported.</span></span>

1.  <span data-ttu-id="9e84f-142">Hozzon létre XML-fájlt és másolja be a következő szöveget.</span><span class="sxs-lookup"><span data-stu-id="9e84f-142">Create an XML file, and copy the following text into it.</span></span>

    ```xml
    <Batch><![CDATA[PASTESTATEMENTFILEHERE
        ]]></Batch>
    ```
    
2.  <span data-ttu-id="9e84f-143">Másolja a bankszámlakivonat-fájl tartalmát és illessze be az XML-fájlba, hogy pótolja **KIVONATFÁLJ BEILLESZTÉSE**.</span><span class="sxs-lookup"><span data-stu-id="9e84f-143">Copy the contents of the bank statement file, and paste them into the XML file so that they replace **PASTESTATEMENTFILEHERE**.</span></span>

### <a name="debug-the-xslt"></a><span data-ttu-id="9e84f-144">Hibakeresés XSLT</span><span class="sxs-lookup"><span data-stu-id="9e84f-144">Debug the XSLT</span></span>

<span data-ttu-id="9e84f-145">További tájékoztatást a következő témakörben talál: <https://msdn.microsoft.com/library/ms255605.aspx>.</span><span class="sxs-lookup"><span data-stu-id="9e84f-145">For more information, see <https://msdn.microsoft.com/library/ms255605.aspx>.</span></span>

1.  <span data-ttu-id="9e84f-146">Indítsa el a Microsoft Visual Studio programot.</span><span class="sxs-lookup"><span data-stu-id="9e84f-146">Start Microsoft Visual Studio.</span></span>
2.  <span data-ttu-id="9e84f-147">Hozzon létre konzol alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="9e84f-147">Create a console application.</span></span>
3.  <span data-ttu-id="9e84f-148">Nyissa meg a megfelelő XSLT-fájlt.</span><span class="sxs-lookup"><span data-stu-id="9e84f-148">Open the appropriate XSLT.</span></span>
4.  <span data-ttu-id="9e84f-149">Kattintson az XSLT-fájlra és annak tulajdonságlapjára.</span><span class="sxs-lookup"><span data-stu-id="9e84f-149">Click the XLST and its properties page.</span></span>
5.  <span data-ttu-id="9e84f-150">Állítsa be a bemenetet bankszámlakivonat-fájl helyére.</span><span class="sxs-lookup"><span data-stu-id="9e84f-150">Set the input to the location of the bank statement file.</span></span>
6.  <span data-ttu-id="9e84f-151">Adja meg a kimenet helyét és nevét.</span><span class="sxs-lookup"><span data-stu-id="9e84f-151">Define a location and file name for the output.</span></span>
7.  <span data-ttu-id="9e84f-152">Állítsa be a szükséges töréspontokat.</span><span class="sxs-lookup"><span data-stu-id="9e84f-152">Set the required break points.</span></span>
8.  <span data-ttu-id="9e84f-153">A menüben kattintson az **XML** &gt; **XSLT-hibakeresés Indítása** elemre.</span><span class="sxs-lookup"><span data-stu-id="9e84f-153">On the menu, click **XML** &gt; **Start XSLT Debugging**.</span></span>

### <a name="format-the-xslt-output"></a><span data-ttu-id="9e84f-154">XSLT-kimenet formázása</span><span class="sxs-lookup"><span data-stu-id="9e84f-154">Format the XSLT output</span></span>

<span data-ttu-id="9e84f-155">Az átalakítás futtatásakor kimeneti fájl készül, amelyet meg lehet tekinteni a Visual Studio alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="9e84f-155">When the transformation runs, it creates an output file that you can view in Visual Studio.</span></span> <span data-ttu-id="9e84f-156">Használja a Ctrl + A, Ctrl + K és a Ctrl + D billentyűkombinációkat a kimeneti fájl gyors formázásához.</span><span class="sxs-lookup"><span data-stu-id="9e84f-156">Use Ctrl+A, Ctrl+K, and Ctrl+D to quickly format the output file.</span></span>

### <a name="adjust-the-transformation"></a><span data-ttu-id="9e84f-157">Állítsa be az átalakítást</span><span class="sxs-lookup"><span data-stu-id="9e84f-157">Adjust the transformation</span></span>

<span data-ttu-id="9e84f-158">Állítsa be az átalakítást, a megfelelő mező vagy elem megkereséséhez a bankszámlakivonat fájlban.</span><span class="sxs-lookup"><span data-stu-id="9e84f-158">Adjust the transformation to get the appropriate field or element in the bank statement file.</span></span> <span data-ttu-id="9e84f-159">Ezután rendelje hozzá azt a mezőt vagy elemet a Finance elemhez.</span><span class="sxs-lookup"><span data-stu-id="9e84f-159">Then map that field or element to the appropriate Finance element.</span></span>

### <a name="debitcredit-indicator"></a><span data-ttu-id="9e84f-160">Tartozás/követelés jelzése</span><span class="sxs-lookup"><span data-stu-id="9e84f-160">Debit/credit indicator</span></span>

<span data-ttu-id="9e84f-161">Bizonyos esetekben kötelezettségeket kintlevőségekként lehet importálni, és kintlevőségeket kötelezettségekként lehet importálni.</span><span class="sxs-lookup"><span data-stu-id="9e84f-161">Sometimes, debits might be imported as credits, and credits might be imported as debits.</span></span> <span data-ttu-id="9e84f-162">A probléma megoldásához módosítania kell a megfelelő XSLT fájlt.</span><span class="sxs-lookup"><span data-stu-id="9e84f-162">To resolve this issue, you must change the appropriate XSLT.</span></span> <span data-ttu-id="9e84f-163">Ha a banki kivonatok több bankból származnak, ha győződjön meg róla, hogy ugyanazon tartozási/követelési módszert használják, vagy külön átalakításokat hoznak létre.</span><span class="sxs-lookup"><span data-stu-id="9e84f-163">If bank statements come from multiple banks, make sure that they all use the same debit/credit approach, or create separate transformations.</span></span>

-   <span data-ttu-id="9e84f-164">BAI2XML–Reconciliation.xlst GetAmountCreditDebitIndicator sablon</span><span class="sxs-lookup"><span data-stu-id="9e84f-164">BAI2XML-to-Reconciliation.xlst GetAmountCreditDebitIndicator template</span></span>
-   <span data-ttu-id="9e84f-165">ISO20022XML–Reconcilation.xslt GetCreditDebit sablon</span><span class="sxs-lookup"><span data-stu-id="9e84f-165">ISO20022XML-to-Reconcilation.xslt GetCreditDebit template</span></span>
-   <span data-ttu-id="9e84f-166">MT940XML–Reconcilation.xslt GetCreditDebitIndicator sablon</span><span class="sxs-lookup"><span data-stu-id="9e84f-166">MT940XML-to-Reconcilation.xslt GetCreditDebitIndicator template</span></span>

## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a><span data-ttu-id="9e84f-167">A banki kivonat formátumainak és a technikai elrendezések példái</span><span class="sxs-lookup"><span data-stu-id="9e84f-167">Examples of bank statement formats and technical layouts</span></span>
<span data-ttu-id="9e84f-168">A következő táblázat felsorolja a továbbfejlesztett banki egyeztetés importfájl technikai elrendezésű definicóinak példáit és a három kapcsolódó banki kivonat példafájljait találhatja.</span><span class="sxs-lookup"><span data-stu-id="9e84f-168">The following table lists examples of the technical layout definitions for advanced bank reconciliation import files and three related bank statement example files.</span></span> <span data-ttu-id="9e84f-169">A példa fájlokat és műszaki elrendezéseket itt töltheti le: [Importfájl-példák](//download.microsoft.com/download/8/e/c/8ec8d2d0-eb8c-41fb-ad8c-f01a4d670a44/Dynamics365FinanceAdvancedBankStatementLayouts.xlsx)</span><span class="sxs-lookup"><span data-stu-id="9e84f-169">You can download the example files and technical layouts here: [Import file examples](//download.microsoft.com/download/8/e/c/8ec8d2d0-eb8c-41fb-ad8c-f01a4d670a44/Dynamics365FinanceAdvancedBankStatementLayouts.xlsx)</span></span>  

| <span data-ttu-id="9e84f-170">Technikai elrendezésdefiníció</span><span class="sxs-lookup"><span data-stu-id="9e84f-170">Technical layout definition</span></span>                             | <span data-ttu-id="9e84f-171">Banki kivonat példafájl</span><span class="sxs-lookup"><span data-stu-id="9e84f-171">Bank statement example file</span></span>          |
|---------------------------------------------------------|--------------------------------------|
| <span data-ttu-id="9e84f-172">DynamicsAXMT940Layout</span><span class="sxs-lookup"><span data-stu-id="9e84f-172">DynamicsAXMT940Layout</span></span>                                   | [<span data-ttu-id="9e84f-173">MT940StatementExample</span><span class="sxs-lookup"><span data-stu-id="9e84f-173">MT940StatementExample</span></span>](//download.microsoft.com/download/2/d/c/2dcc4e55-ddc8-4a74-b79c-250fae201c3c/mt940StatementExample.txt)                |
| <span data-ttu-id="9e84f-174">DynamicsAXISO20022Layout</span><span class="sxs-lookup"><span data-stu-id="9e84f-174">DynamicsAXISO20022Layout</span></span>                                | [<span data-ttu-id="9e84f-175">ISO20022StatementExample</span><span class="sxs-lookup"><span data-stu-id="9e84f-175">ISO20022StatementExample</span></span>](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdownload.microsoft.com%2Fdownload%2F1%2F5%2F5%2F155d84ed-c250-48f3-b0b1-c5a431e7855b%2FISO20022-MultipleStatements.xml&data=04%7C01%7CRobert.Schlomann%40microsoft.com%7C30d0c233cb6546547d0a08d8f4965edc%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637528273956712775%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&sdata=3VzvLZK%2BO8PjuI7XVdC6rD2j3nUJfteo7zFp%2B1s9BwM%3D&reserved=0)             |
| <span data-ttu-id="9e84f-176">DynamicsAXBAI2Layout</span><span class="sxs-lookup"><span data-stu-id="9e84f-176">DynamicsAXBAI2Layout</span></span>                                    | [<span data-ttu-id="9e84f-177">BAI2StatementExample</span><span class="sxs-lookup"><span data-stu-id="9e84f-177">BAI2StatementExample</span></span>](//download.microsoft.com/download/1/1/6/11693f57-bfc1-4993-a274-5fb978be70fa/BAI2StatementExample.txt)                 |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
