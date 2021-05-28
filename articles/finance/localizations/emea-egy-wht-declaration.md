---
title: Adóelőleg-bevallás Egyiptom számára
description: Ez a témakör bemutatja, hogyan kell konfigurálni és létrehozni az adóelőleg-bevallásokat Egyiptom számára.
author: sndray
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: ''
ms.search.region: Global
ms.author: tfehr
ms.search.validFrom: 2017-06-20
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 8c9aaa3868167806ce3189d724621991ec7e53eb
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022811"
---
#  <a name="withholding-tax-declaration-for-egypt-eg-00005"></a><span data-ttu-id="16a03-103">Adóelőleg-bevallás Egyiptom számára (EG-00005)</span><span class="sxs-lookup"><span data-stu-id="16a03-103">Withholding tax declaration for Egypt (EG-00005)</span></span>

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/preview-banner.md)]

## <a name="overview"></a><span data-ttu-id="16a03-104">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="16a03-104">Overview</span></span>
<span data-ttu-id="16a03-105">Ez a témakör bemutatja az adóelőleg-bevallás beállítását és létrehozását, valamint az egyiptomi jogi személyek adóelőleg-bevallásainak 41-es és 11-es űrlapjait.</span><span class="sxs-lookup"><span data-stu-id="16a03-105">This topic explains how to set up and generate the withholding tax declaration and the withholding tax declaration forms 41 and 11 for legal entities in Egypt</span></span> 

<span data-ttu-id="16a03-106">Minden egyiptomi entitásnak elő kell készítenie a 41-es űrlapot, amely összegzi a helyi szállítóktól és szolgáltatóktól visszatartott adókat.</span><span class="sxs-lookup"><span data-stu-id="16a03-106">All Egyptian entities must prepare the form  41 which summarizes all taxes that are retained from local suppliers and service providers.</span></span> <span data-ttu-id="16a03-107">A 41-es űrlapon kívül a 11-es űrlapot is létre kell hozni, amelyen a külföldi szolgáltatóktól származó visszatartott adót kell részletezni.</span><span class="sxs-lookup"><span data-stu-id="16a03-107">In addition to form 41, form 11 must be generated to detail all of the retained taxed from foreign providers.</span></span> 

<span data-ttu-id="16a03-108">Az **Adóelőleg-bevallás** a Dynamics 365 Finance rendszerben a következő jelentéseket tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="16a03-108">The **Withholding tax declaration** report in Dynamics 365 Finance includes the following reports:</span></span>

- <span data-ttu-id="16a03-109">Bevallás űrlapja, szám:</span><span class="sxs-lookup"><span data-stu-id="16a03-109">Declaration form No.</span></span> <span data-ttu-id="16a03-110">41</span><span class="sxs-lookup"><span data-stu-id="16a03-110">41</span></span>
- <span data-ttu-id="16a03-111">Bevallás űrlapja, szám:</span><span class="sxs-lookup"><span data-stu-id="16a03-111">Declaration form No.</span></span> <span data-ttu-id="16a03-112">11</span><span class="sxs-lookup"><span data-stu-id="16a03-112">11</span></span>
    
    
## <a name="prerequisites"></a><span data-ttu-id="16a03-113">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="16a03-113">Prerequisites</span></span>
<span data-ttu-id="16a03-114">A jogi személy elsődleges címének Egyiptomban kell lennie.</span><span class="sxs-lookup"><span data-stu-id="16a03-114">The primary address of the legal entity must be in Egypt.</span></span>
<span data-ttu-id="16a03-115">Be kell kapcsolni a következő funkciókat a **Funkció kezelése** munkaterületen:</span><span class="sxs-lookup"><span data-stu-id="16a03-115">In the **Feature management** workspace, the following feature must be enabled:</span></span>

   - <span data-ttu-id="16a03-116">**Globális adóelőleg**</span><span class="sxs-lookup"><span data-stu-id="16a03-116">**Global withholding tax**</span></span>

<span data-ttu-id="16a03-117">A funkciók engedélyezésével kapcsolatos további tudnivalókat lásd: [Funkciókezelés áttekintése](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="16a03-117">For more information about how to enable features, see [Feature management overview.](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)</span></span>

1. <span data-ttu-id="16a03-118">Lépjen az **Adó** > **Beállítás** > **Paraméterek** > **Főkönyvi paraméterek** pontra, majd az **Adóelőleg** lapon állítsa a **Globális adóelőleg engedélyezése** beállítást **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="16a03-118">Go to **Tax** > **Setup** > **Parameters** > **General ledger parameters**, and on the **Withholding tax** tab, set **Enable global withholding tax** to **Yes**.</span></span>
2. <span data-ttu-id="16a03-119">Az **Elektronikus jelentéskészítés** munkaterületen importálja az adattárból a következő elektronikus jelentési formátumokat:</span><span class="sxs-lookup"><span data-stu-id="16a03-119">In the **Electronic reporting** workspace, import the following Electronic reporting formats from the repository:</span></span>

    - <span data-ttu-id="16a03-120">WHT bevallás Excel (EG)</span><span class="sxs-lookup"><span data-stu-id="16a03-120">WHT Declaration Excel (EG)</span></span>

    > [!NOTE]
    > <span data-ttu-id="16a03-121">A fenti formátum az **Adóbevallás modellen** alapul, és az **Adóbevallási modell-leképezését** használja.</span><span class="sxs-lookup"><span data-stu-id="16a03-121">The format above is based on the **Tax declaration model** and uses the **Tax declaration model mapping**.</span></span> <span data-ttu-id="16a03-122">Ezt a további konfigurációt a program automatikusan importálja.</span><span class="sxs-lookup"><span data-stu-id="16a03-122">This additional configuration is automatically imported.</span></span>

<span data-ttu-id="16a03-123">További információért azzal kapcsolatosan, hogyan importálhat le Elektronikus jelentéstételi konfigurációkat, lásd: [Az elektronikus jelentéskészítési konfigurációk letöltése a Lifecycle Services rendszerből](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span><span class="sxs-lookup"><span data-stu-id="16a03-123">For more information about how to import Electronic reporting configurations, see [Download Electronic reporting configurations from Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span></span>

## <a name="download-electronic-reporting-configurations"></a><span data-ttu-id="16a03-124">Elektronikus jelentéskészítési konfigurációk letöltése</span><span class="sxs-lookup"><span data-stu-id="16a03-124">Download Electronic reporting configurations</span></span>

<span data-ttu-id="16a03-125">Az Egyiptomra vonatkozó WHT bevallás űrlapjainak végrehajtása az elektronikus jelentéskészítési (ER) konfigurációkon alapul.</span><span class="sxs-lookup"><span data-stu-id="16a03-125">The implementation of the WHT declaration forms for Egypt is based on Electronic reporting (ER) configurations.</span></span> <span data-ttu-id="16a03-126">A konfigurálható jelentésekkel kapcsolatos funkciókról és fogalmakról további információkat itt talál: [Elektronikus jelentéskészítés](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="16a03-126">For more information about the capabilities and concepts of configurable reporting, see [Electronic reporting](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).</span></span>

<span data-ttu-id="16a03-127">A termelési és a felhasználói elfogadási tesztelési (UAT) környezetekkel kapcsolatban kövesse [Az elektronikus jelentéskészítési konfigurációk letöltése a Lifecycle Services rendszerből](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md) témakör utasításait.</span><span class="sxs-lookup"><span data-stu-id="16a03-127">For production and user acceptance testing (UAT) environments, follow the instructions in the topic, [Download Electronic reporting configurations from Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span></span>

<span data-ttu-id="16a03-128">Az adóelőleg-bevallás egyiptomi jogi személynél való létrehozásához fel kell töltenie a következő konfigurációkat:</span><span class="sxs-lookup"><span data-stu-id="16a03-128">To generate the Withholding declarations in an Egyptian legal entity, you need to upload the following configurations:</span></span>

- <span data-ttu-id="16a03-129">Adóbevallás modell.verzió.82.xml vagy újabb verzió</span><span class="sxs-lookup"><span data-stu-id="16a03-129">Tax declaration model.version.82.xml or later version</span></span>
- <span data-ttu-id="16a03-130">Adóbevallás modell-leképezés.verzió.82.xml vagy újabb verzió</span><span class="sxs-lookup"><span data-stu-id="16a03-130">Tax declaration model mapping.version.82.133.xml or a later version</span></span>
- <span data-ttu-id="16a03-131">WHT bevallás Excel (EG).verzió.82.21 vagy újabb verzió</span><span class="sxs-lookup"><span data-stu-id="16a03-131">WHT Declaration Excel (EG).version.82.21  or a later version</span></span>

<span data-ttu-id="16a03-132">Miután befejezte az ER-konfigurációk letöltését a Lifecycle Services (LCS) szolgáltatásból vagy a globális adattárból, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="16a03-132">After you finish downloading the ER configurations from Lifecycle Services (LCS) or the global repository, complete the following steps.</span></span>

1. <span data-ttu-id="16a03-133">Az **Elektronikus jelentéskészítés** munkaterületen válassza ki a **Jelentéskészítési konfiguráció** csempét.</span><span class="sxs-lookup"><span data-stu-id="16a03-133">Go to the **Electronic reporting** workspace and select the **Reporting configurations** tile.</span></span>
1. <span data-ttu-id="16a03-134">A **Konfigurációk** lapon a műveleti ablaktáblában válassza az **Átváltás > Betöltés XML-fájlból** elemet.</span><span class="sxs-lookup"><span data-stu-id="16a03-134">On the **Configurations** page, on the Action Pane, select **Exchange > Load from XML file**.</span></span>
1. <span data-ttu-id="16a03-135">Töltse fel az összes fájlt abban a sorrendben, amelyben az előző felsorolásban szerepelnek.</span><span class="sxs-lookup"><span data-stu-id="16a03-135">Upload all the files in the order in which they are listed in the previous bullets.</span></span> <span data-ttu-id="16a03-136">Miután minden konfigurációt feltöltött, a konfigurációs fának jelen kell lennie a Finance rendszerben.</span><span class="sxs-lookup"><span data-stu-id="16a03-136">After all of the configurations are uploaded, the configuration tree should be present in Finance.</span></span>

## <a name="set-up-application-specific-parameters"></a><span data-ttu-id="16a03-137">Alkalmazásfüggő paraméterek beállítása</span><span class="sxs-lookup"><span data-stu-id="16a03-137">Set up application-specific parameters</span></span>

<span data-ttu-id="16a03-138">Az alkalmazásspecifikus paraméterek beállítással a felhasználók megszahatják, hogyan történjen az adótranzakciók osztályozása és kiszámítása a létrehozott jelentés egyes soraiban az **adóelőleg cikkcsoportjának** vagy a keresés definíciójában meghatározott egyéb feltételeknek megfelelően.</span><span class="sxs-lookup"><span data-stu-id="16a03-138">The application-specific parameters option lets users establish the criteria of how the tax transactions will be classified and calculated in each line of a generated report depending on the configuration of **withholding tax item group** or other criteria established in the definition of lookup.</span></span>

<span data-ttu-id="16a03-139">A 41-es adóelőleg-bevallás egy konkrét oszlopot tartalmaz, amelyben az adóelőleg-tranzakciót az adóhatóság **Engedmény kódjának típusa** nevű osztályozásának megfelelően kell osztályozni.</span><span class="sxs-lookup"><span data-stu-id="16a03-139">Withholding declaration form 41 includes a specific column where the withholding tax transaction must be classified in accordance with the tax authority classification named **Discount code type**.</span></span> <span data-ttu-id="16a03-140">Ahelyett, hogy ezeket az új osztályozásokat új bejegyzési adatként határoznák meg a tranzakciók feladása során, az osztályozásokat a **Konfigurációk** > **Alkalmazásspecifikus paraméterek** > **Beállítás** pontban bevezetett különböző keresések alapján határozzák meg az egyiptomi adóelőleg-jelentésekkel szemben támasztott követelményeknek való megfelelés érdekében.</span><span class="sxs-lookup"><span data-stu-id="16a03-140">Instead of including these new classifications as new entry data when the transactions are posted, the classifications will be determined based on the different lookups introduced in **Configurations** > **Set up application-specific parameters** > **Setup** to meet the requirements of withholding reports for Egypt.</span></span> 

<span data-ttu-id="16a03-141">Az Adóelőleg-bevallás 41-es űrlapján a következő konfiguráció használatos a tranzakciók osztályozására:</span><span class="sxs-lookup"><span data-stu-id="16a03-141">The following configuration is used to classify the transactions in the Withholding declaration form 41 report:</span></span>

- <span data-ttu-id="16a03-142">**DiscountTaxTypeLookup**-> 18. oszlop</span><span class="sxs-lookup"><span data-stu-id="16a03-142">**DiscountTaxTypeLookup**-> Column No 18</span></span> 

<span data-ttu-id="16a03-143">A következő lépések alapján beállíthatja a WHT bevallást és vonatkozó könyvekkel kapcsolatos jelentéseket generáló különféle kereséseket.</span><span class="sxs-lookup"><span data-stu-id="16a03-143">Complete the following steps to set up the different lookups used to generate the WHT declaration and related books reports.</span></span> 

1. <span data-ttu-id="16a03-144">Az **Elektronikus jelentéskészítés** munkaterületen a **Konfiguráció** > **Beállítás** kiválasztásával adja meg, hogy milyen szabályok szerint történjen a tranzakciók a WHT bevallási jelentésben való osztályozása.</span><span class="sxs-lookup"><span data-stu-id="16a03-144">In the **Electronic reporting** workspace, select **Configurations** > **Setup** to set up the rules to identify how transactions are classified in the WHT declaration report.</span></span> 
2. <span data-ttu-id="16a03-145">Válassza ki az aktuális verziót, és a **Keresések** gyorslapon válassza ki a keresési nevet.</span><span class="sxs-lookup"><span data-stu-id="16a03-145">Select the current version, and on the **Lookups** FastTab, select the lookup name.</span></span> <span data-ttu-id="16a03-146">Például: **DiscountTaxTypeLookup**.</span><span class="sxs-lookup"><span data-stu-id="16a03-146">For example, **DiscountTaxTypeLookup**.</span></span> <span data-ttu-id="16a03-147">Ez a keresés azonosítja az adóhatóság által előírt engedménytípusok listáját.</span><span class="sxs-lookup"><span data-stu-id="16a03-147">This lookup identifies the list of discount types required by the tax authority.</span></span>
3. <span data-ttu-id="16a03-148">Válassza ki a **Feltételek** gyorslapon a **Hozzáadás** lehetőséget, és a **Keresés eredménye** oszlopban az új sorban válassza ki azt a kapcsolódó sort, amely a **18. oszlopban** található osztályozásnak felel meg.</span><span class="sxs-lookup"><span data-stu-id="16a03-148">On the **Conditions** FastTab, select **Add** and in the new line in the **Lookup result** column, select the related line that represents the classification in the **Column 18**.</span></span>
4. <span data-ttu-id="16a03-149">Az **Adóelőleg – cikkcsoport** oszlopban válassza ki az osztályozás azonosításához használt kódot.</span><span class="sxs-lookup"><span data-stu-id="16a03-149">In the **Withholding tax item group** column, select the related code that's used to identify the classification.</span></span> <span data-ttu-id="16a03-150">Például: **Megengedett engedmény**.</span><span class="sxs-lookup"><span data-stu-id="16a03-150">For example, **Allowed discount**.</span></span>  
5. <span data-ttu-id="16a03-151">Ismételje meg a 3–4. lépést az összes elérhető kereséssel.</span><span class="sxs-lookup"><span data-stu-id="16a03-151">Repeat steps 3 and 4 for all available lookups.</span></span>
6. <span data-ttu-id="16a03-152">Válassza újra a **Hozzáadás** lehetőséget a végső rekordsor beemeléséhez, és a **Keresés eredménye** oszlopban válassza a **Nem alkalmazható** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="16a03-152">Select **Add** again to include the final record line, and in the **Lookup result** column, select **Not applicable**.</span></span> 
7. <span data-ttu-id="16a03-153">A többi oszlopban válassza a **Nem üres** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="16a03-153">In the remaining columns, select **Not blank**.</span></span> 

> [!NOTE]

## <a name="set-up-general-ledger-parameters"></a><span data-ttu-id="16a03-154">Főkönyvi paraméterek beállítása</span><span class="sxs-lookup"><span data-stu-id="16a03-154">Set up General ledger parameters</span></span>

<span data-ttu-id="16a03-155">A WHT bevallás jelentéseinek Microsoft Excel alkalmazásban való létrehozásához definiáljon ER-formátumot a **Főkönyvi paraméterek** oldalon.</span><span class="sxs-lookup"><span data-stu-id="16a03-155">To generate the WHT declaration form reports in Microsoft Excel, define an ER format on the **General ledger parameters** page.</span></span>

1. <span data-ttu-id="16a03-156">Lépjen az **Adó** > **Beállítás** > **Főkönyvi paraméterek** pontra.</span><span class="sxs-lookup"><span data-stu-id="16a03-156">Go to **Tax** > **Setup** > **General ledger parameters**.</span></span>
2. <span data-ttu-id="16a03-157">Az **Adóelőleg** lapon a **WHT bevallás formátum-hozzárendelése** mezőben válassza a **WHT bevallás Excel (EG)** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="16a03-157">On the **Withholding tax** tab, in the **WHT declaration format mapping** field, select **WHT Declaration Excel (EG)**.</span></span> <span data-ttu-id="16a03-158">Ha üresen hagyja ezt a mezőt, a normál áfajelentés SSRS-formátumban jön létre.</span><span class="sxs-lookup"><span data-stu-id="16a03-158">If you leave the field blank, the standard sales tax report will be generated in SSRS format.</span></span>


![Bevallás űrlapja](media/egypt-wht-declaration-setup1.png)

## <a name="generate-the-withholding-declaration-forms"></a><span data-ttu-id="16a03-160">Adóelőleg-bevallás űrlapjainak létrehozása</span><span class="sxs-lookup"><span data-stu-id="16a03-160">Generate the Withholding declaration forms</span></span>
<span data-ttu-id="16a03-161">Az adóelőleg-bevallás egy adott időszakra történő elkészítésének és benyújtásának folyamata a kiegyenlítési és kifizetési feladási adóügyi feladat során feladott adóelőleg-tranzakcióin alapul.</span><span class="sxs-lookup"><span data-stu-id="16a03-161">The process of preparing and submitting a Withholding declaration form for a specific period is based on the withholding tax transactions posted during the settle and post payment tax job.</span></span> <span data-ttu-id="16a03-162">A globális adóelőleggel kapcsolatos további tudnivalókat lásd: [Globális adóelőleg](../general-ledger/global-withholding-tax-overview.md).</span><span class="sxs-lookup"><span data-stu-id="16a03-162">For more information about global withholding tax, see [Global withholding tax](../general-ledger/global-withholding-tax-overview.md).</span></span>

<span data-ttu-id="16a03-163">Az áfabevallási jelentés létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="16a03-163">Complete the following steps to generate the tax declaration report.</span></span>

1. <span data-ttu-id="16a03-164">Lépjen ide: **Adó** > **Bevallások** > **Adóelőleg** > \**Adóelőleg kifizetése*.</span><span class="sxs-lookup"><span data-stu-id="16a03-164">Go to **Tax** > **Declarations** > **Withholding tax** > \**Withholding tax payment*.</span></span>
2. <span data-ttu-id="16a03-165">Válassza ki a kiegyenlítési időszakot, majd válassza ki a jelentés dátumát.</span><span class="sxs-lookup"><span data-stu-id="16a03-165">Select the settlement period and then select the from date for the report.</span></span> 
3. <span data-ttu-id="16a03-166">Írja be a tranzakció dátumát, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="16a03-166">Enter the transaction date and then select **OK**.</span></span>
4. <span data-ttu-id="16a03-167">A megjelenő párbeszédpanelen válasszon ki egy vagy több űrlaptípust **41-es űrlap**, **11-es űrlap** vagy **Nincs**.</span><span class="sxs-lookup"><span data-stu-id="16a03-167">In the dialog box that opens, select one or more of the form types \*\*Form No 41 \*\*, **Form No 11**, or **None**.</span></span> <span data-ttu-id="16a03-168">Ha a **Nincs** lehetőséget választja, a normál jelentés jön létre.</span><span class="sxs-lookup"><span data-stu-id="16a03-168">If you select **None**, the standard report is generated.</span></span> 
5. <span data-ttu-id="16a03-169">Válassza ki a nyelvet.</span><span class="sxs-lookup"><span data-stu-id="16a03-169">Select the language.</span></span> <span data-ttu-id="16a03-170">Minden jelentés fordítása **en-us** és **ar-eg**.</span><span class="sxs-lookup"><span data-stu-id="16a03-170">All reports are translated in **en-us** and **ar-eg**.</span></span>
6. <span data-ttu-id="16a03-171">Írja be azon fiók és bank nevét, ahol az adóbefizetés megtörténik.</span><span class="sxs-lookup"><span data-stu-id="16a03-171">Enter the branch and name of the bank where the tax payment will be paid.</span></span>
7. <span data-ttu-id="16a03-172">Válassza ki az üzlettípust, majd adja meg a csekk- és dokumentumszámokat.</span><span class="sxs-lookup"><span data-stu-id="16a03-172">Select the business type and then enter the check and document numbers.</span></span> 
8. <span data-ttu-id="16a03-173">Írja be az entitás típusát.</span><span class="sxs-lookup"><span data-stu-id="16a03-173">Enter the entity type.</span></span> 
9. <span data-ttu-id="16a03-174">Adja meg az árlap hozzárendeléséhez regisztrált személy nevét, és a jelentés generálásának megerősítéséhez kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="16a03-174">Enter the name of person registered to assign the form and select **OK** to confirm the report generation.</span></span> 

 
[!INCLUDE[footer-include](../../includes/footer-banner.md)]
