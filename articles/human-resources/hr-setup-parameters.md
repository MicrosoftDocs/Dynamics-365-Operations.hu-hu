---
title: A Human Resources paramétereinek konfigurálása
description: Ez a témakör ismerteti a vállalat-specifikus paraméterek beállítását a Dynamics 365 Human Resources alkalmazásban.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HRMParameters, HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 51941
ms.assetid: 2cfb061a-a616-4bf9-9d98-9cde00039eec
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 74bdf891ffa7a9d875e23cf46aeee1dbaf86db48
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5802407"
---
# <a name="configure-human-resources-parameters"></a><span data-ttu-id="a46a4-103">A Human Resources paramétereinek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="a46a4-103">Configure Human resources parameters</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="a46a4-104">A Human Resources egyes paramétereinek beállításait közösen használják a vállalatok, azonban vannak olyan paraméter-beállítások, amelyek vállalatonként különböznek.</span><span class="sxs-lookup"><span data-stu-id="a46a4-104">The settings of some Human resources parameters are shared across companies, while the settings of other parameters are company-specific.</span></span> <span data-ttu-id="a46a4-105">Ez a témakör ismerteti a vállalat-specifikus Human Resources paraméterek beállítását.</span><span class="sxs-lookup"><span data-stu-id="a46a4-105">This topic explains how to set up company-specific Human resources parameters.</span></span>

<span data-ttu-id="a46a4-106">A Human Resources paraméterek beállítása két oldalon történik.</span><span class="sxs-lookup"><span data-stu-id="a46a4-106">Two pages are used to set Human resources parameters.</span></span> <span data-ttu-id="a46a4-107">A vállalatok között megosztott paraméterekhez az **Emberi erőforrások megosztott paraméterei** oldal használatos.</span><span class="sxs-lookup"><span data-stu-id="a46a4-107">For parameters that are shared across companies, you use the **Human resources shared parameters** page.</span></span> <span data-ttu-id="a46a4-108">A vállalatspecifikus (más szóval, a beállítások csak egy vállalatra vonatkoznak) paraméterekhez az **Emberierőforrás-paraméterek** oldal használatos.</span><span class="sxs-lookup"><span data-stu-id="a46a4-108">For parameters that are company-specific (in other words, the settings apply to a single company), you use the **Human resource parameters** page.</span></span>

![Lépjen a Humar Resources paramétereihez](./media/hr-employee-self-service-human-resources-parameters.png)

<span data-ttu-id="a46a4-110">Az **Emberierőforrás-paraméterek** oldalon a beállítások 6 lapra vannak szétosztva.</span><span class="sxs-lookup"><span data-stu-id="a46a4-110">On the **Human resources parameters** page, the settings are divided among six tabs:</span></span>

- <span data-ttu-id="a46a4-111">**Általános**</span><span class="sxs-lookup"><span data-stu-id="a46a4-111">**General**</span></span>
- <span data-ttu-id="a46a4-112">**Toborzás** (ez a lap nem része a Dynamics 365 Human Resources rendszernek)</span><span class="sxs-lookup"><span data-stu-id="a46a4-112">**Recruitment** (this tab isn't included in Dynamics 365 Human Resources)</span></span>
- <span data-ttu-id="a46a4-113">**Kompenzáció**</span><span class="sxs-lookup"><span data-stu-id="a46a4-113">**Compensation**</span></span>
- <span data-ttu-id="a46a4-114">**Számsorozatok**</span><span class="sxs-lookup"><span data-stu-id="a46a4-114">**Number sequences**</span></span>
- <span data-ttu-id="a46a4-115">**FMLA**</span><span class="sxs-lookup"><span data-stu-id="a46a4-115">**FMLA**</span></span>
- <span data-ttu-id="a46a4-116">**Alkalmazotti önkiszolgáló rendszer**</span><span class="sxs-lookup"><span data-stu-id="a46a4-116">**Employee self service**</span></span>
- <span data-ttu-id="a46a4-117">**Vezetői önkiszolgáló rendszer**</span><span class="sxs-lookup"><span data-stu-id="a46a4-117">**Manager self service**</span></span>
- <span data-ttu-id="a46a4-118">**Juttatáskezelés**</span><span class="sxs-lookup"><span data-stu-id="a46a4-118">**Benefits management**</span></span>
- <span data-ttu-id="a46a4-119">**Szabadság és távollét**</span><span class="sxs-lookup"><span data-stu-id="a46a4-119">**Leave and absence**</span></span>
- <span data-ttu-id="a46a4-120">**Fizetési módok**</span><span class="sxs-lookup"><span data-stu-id="a46a4-120">**Payment methods**</span></span>

<span data-ttu-id="a46a4-121">Minden lap egyetlen vállalatra vonatkozóan tartalmaz információkat.</span><span class="sxs-lookup"><span data-stu-id="a46a4-121">Each tab contains information that pertains to a single company.</span></span>

## <a name="general"></a><span data-ttu-id="a46a4-122">Általános</span><span class="sxs-lookup"><span data-stu-id="a46a4-122">General</span></span>

<span data-ttu-id="a46a4-123">Az **Általános** lapon található beállítások határozzák meg a távolléttel, sérüléssel, betegséggel és új munkaerővel kapcsolatos információk megjelenését.</span><span class="sxs-lookup"><span data-stu-id="a46a4-123">The settings on the **General** tab define the appearance of information about absence, injury and illness, and new hires.</span></span> <span data-ttu-id="a46a4-124">Az ezen a lapon található beállítások meghatároznak néhány alapértelmezett tételt is, amelyek a munkavégzés során jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="a46a4-124">The settings on this tab also define some default entries that appear as you work.</span></span> <span data-ttu-id="a46a4-125">Ez a lap a következőt teszi lehetővé:</span><span class="sxs-lookup"><span data-stu-id="a46a4-125">Specifically, this tab lets you:</span></span>

- <span data-ttu-id="a46a4-126">A nyitott távolléti tranzakcióra alkalmazni kívánt szín megadása</span><span class="sxs-lookup"><span data-stu-id="a46a4-126">Select a color to apply to open absence transactions</span></span>
- <span data-ttu-id="a46a4-127">A jelentésekhez használt stíluslap megadása</span><span class="sxs-lookup"><span data-stu-id="a46a4-127">Specify the style sheet to use for reports</span></span>
- <span data-ttu-id="a46a4-128">Tanfolyamok és távolléti regisztrációk közötti integráció engedélyezése</span><span class="sxs-lookup"><span data-stu-id="a46a4-128">Enable the integration between training courses and absence registration</span></span>
- <span data-ttu-id="a46a4-129">Az integráció szabályozásához használt távolléti kód kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="a46a4-129">Select the absence code that is used to control this integration.</span></span>
- <span data-ttu-id="a46a4-130">Adja meg, mennyi ideig kell megőrizni a sérüléssel és betegséggel kapcsolatos eseményeket.</span><span class="sxs-lookup"><span data-stu-id="a46a4-130">Indicate how long to keep injury and illness case incidents.</span></span>
- <span data-ttu-id="a46a4-131">Adja meg az új dolgozó felvétele esetén megjelenő alapértelmezett azonosítószámot.</span><span class="sxs-lookup"><span data-stu-id="a46a4-131">Specify the default identification number shown when a new worker is hired.</span></span>

![Általános fül](./media/hr-setup-parameters-general.png)

## <a name="recruitment"></a><span data-ttu-id="a46a4-133">Munkaerő-felvétel</span><span class="sxs-lookup"><span data-stu-id="a46a4-133">Recruitment</span></span>

<span data-ttu-id="a46a4-134">A **Toborzás** lapon megadott beállítások határozzák meg azokat a dokumentumtípusokat, amelyek a pályázóknak automatikusan küldött levelezéshez használatosak.</span><span class="sxs-lookup"><span data-stu-id="a46a4-134">The settings on the **Recruitment** tab define the document types used for correspondence automatically sent to applicants.</span></span> <span data-ttu-id="a46a4-135">Jelezheti a kéretlen pályázatokhoz használt toborzási projektet is.</span><span class="sxs-lookup"><span data-stu-id="a46a4-135">You can also indicate the recruitment project used for unsolicited applications.</span></span>

<span data-ttu-id="a46a4-136">A toborzási projekt korosításához definiált időszak határozza meg a **Toborzás kezelése** munkaterületen található **Korosítási projektek** csempe által tartalmazott toborzási projekteket.</span><span class="sxs-lookup"><span data-stu-id="a46a4-136">The period defined for recruitment project aging determines the recruitment projects included on the **Aging projects** tile in the **Recruitment management** workspace.</span></span> <span data-ttu-id="a46a4-137">A pályázati határidőre vonatkozó figyelmeztetéshez definiált időszak használatos a **Toborzás** munkaterületen a **Közelgő jelentkezési határidő** csempében található, a pályázati határidejükhöz közelítő toborzási projektek megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="a46a4-137">The period defined for the application deadline warning is used to display recruitment projects that are approaching their application deadline on the **Application deadline approaching** tile in the **Recruitment** workspace.</span></span>

<span data-ttu-id="a46a4-138">A toborzásról a [Jelöltek toborzása](hr-personnel-recruit.md) oldalon található részletes tájékoztatás.</span><span class="sxs-lookup"><span data-stu-id="a46a4-138">For more information about recruiting, see [Recruit job candidates](hr-personnel-recruit.md).</span></span>

## <a name="compensation"></a><span data-ttu-id="a46a4-139">Kompenzáció</span><span class="sxs-lookup"><span data-stu-id="a46a4-139">Compensation</span></span>

<span data-ttu-id="a46a4-140">A Dynamics 365 Finance alkalmazásban a **Kompenzáció** lap meghatározza, hogy a felhasználóknak meg kell-e erősíteniük, hogy menteni szeretnék-e a rögzített vagy változó kompenzációs terv adatait.</span><span class="sxs-lookup"><span data-stu-id="a46a4-140">In Dynamics 365 Finance, the settings on the **Compensation** tab define whether users must confirm that they want to save information for a fixed or variable compensation plan.</span></span> <span data-ttu-id="a46a4-141">Ha bejelöli a **Mentésellenőrzés engedélyezése** lehetőséget, amikor a felhasználók bezárnak egy kompenzációval kapcsolatos oldalt, megjelenik egy üzenet, amely megkérdezi, hogy akarják-e menteni a bejegyzést.</span><span class="sxs-lookup"><span data-stu-id="a46a4-141">If you select **Enable save validation**, when users close a compensation-related page, they receive a message that asks whether they want to save the record.</span></span> <span data-ttu-id="a46a4-142">A Kompenzációkezelés egyes oldalai nem teszik lehetővé adatok törlését felhasználók számára.</span><span class="sxs-lookup"><span data-stu-id="a46a4-142">Some pages in Compensation management don't let users delete information.</span></span> <span data-ttu-id="a46a4-143">Az által, hogy megerősítést kér a felhasználóktól az adatok mentésével kapcsolatban, képes lehet korlátozni az elmentett, de a későbbiekben nem törölhető adatok mennyiségét.</span><span class="sxs-lookup"><span data-stu-id="a46a4-143">By prompting users to verify that they want to save information, you might be able to limit the amount of information that is saved but can't be deleted later.</span></span> <span data-ttu-id="a46a4-144">Ha törli a **Mentésellenőrzés engedélyezése** jelölőnégyzetet, a bejegyzések mentése azonnal megtörténik, esetleg még az előtt, hogy a felhasználó készen állna.</span><span class="sxs-lookup"><span data-stu-id="a46a4-144">If you clear **Enable save validation**, records save immediately, possibly before the user is ready.</span></span> <span data-ttu-id="a46a4-145">Ha Teljesítménymenedzsmentet alkalmaz, akkor a **Kompenzáció** lapon kiválaszthat egy osztályozási modellt, amelyet a teljesítmény osztályozáskor az alkalmazott kompenzációs konstrukciókhoz rendelt modell helyett használhat.</span><span class="sxs-lookup"><span data-stu-id="a46a4-145">If you're using Performance management, the **Compensation** tab also lets you select a rating model to use instead of the model assigned to compensation plans when rating performance.</span></span>

<span data-ttu-id="a46a4-146">A Human Resources alkalmazásban a **Kompenzáció** lapon kiválaszthatja, hogy korlátozza-e a hozzáférést a kompenzációs konstrukciókhoz, és beállít-e alapértelmezett pénznemet.</span><span class="sxs-lookup"><span data-stu-id="a46a4-146">In Human Resources, you can use the **Compensation** tab to choose to restrict access to compensation plans and to set a default currency.</span></span>

<span data-ttu-id="a46a4-147">A kompenzációval kapcsolatos további információkért lásd: [Kompenzációs konstrukciók áttekintése](hr-compensation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a46a4-147">For more information about compensation, see [Compensation plans overview](hr-compensation-overview.md).</span></span>

![Kompenzáció lap](./media/hr-setup-parameters-compensation.png)

## <a name="number-sequences"></a><span data-ttu-id="a46a4-149">Számsorozatok</span><span class="sxs-lookup"><span data-stu-id="a46a4-149">Number sequences</span></span>

<span data-ttu-id="a46a4-150">A **Számsorozat** lap beállításai határozzák meg, hogy milyen sorrendben rendeljenek automatikusan értékeket a Human Resources alkalmazásban található cikkekhez, például:</span><span class="sxs-lookup"><span data-stu-id="a46a4-150">The settings on the **Number sequence** tab determine the sequences used to automatically assign IDs to items in Human Resources, such as:</span></span>

- <span data-ttu-id="a46a4-151">Pályázatok</span><span class="sxs-lookup"><span data-stu-id="a46a4-151">Applications</span></span>
- <span data-ttu-id="a46a4-152">Távollét-regisztrációk</span><span class="sxs-lookup"><span data-stu-id="a46a4-152">Absence registrations</span></span>
- <span data-ttu-id="a46a4-153">Kompenzációs folyamat eredményei</span><span class="sxs-lookup"><span data-stu-id="a46a4-153">Compensation process results</span></span>
- <span data-ttu-id="a46a4-154">Esetszámok</span><span class="sxs-lookup"><span data-stu-id="a46a4-154">Case numbers</span></span>
- <span data-ttu-id="a46a4-155">Tanfolyamok</span><span class="sxs-lookup"><span data-stu-id="a46a4-155">Courses</span></span>
- <span data-ttu-id="a46a4-156">Tanfolyami napirendek</span><span class="sxs-lookup"><span data-stu-id="a46a4-156">Course agendas</span></span>

<span data-ttu-id="a46a4-157">A számsorozat-hivatkozások és -kódok karbantartásához használja a **Számsorozatok** listaoldalt (válassza a **Szervezet felügyelete > Számsorozatok > Számsorozatok** lehetőséget).</span><span class="sxs-lookup"><span data-stu-id="a46a4-157">To maintain number sequence references and codes, use the **Number sequences** list page (select **Organization administration > Number sequences > Number sequences**).</span></span>

<span data-ttu-id="a46a4-158">További információkért lásd: [Számsorozatok áttekintése](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/number-sequence-overview?toc=/dynamics365/human-resources/toc.json).</span><span class="sxs-lookup"><span data-stu-id="a46a4-158">For more information, see [Number sequences overview](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/number-sequence-overview?toc=/dynamics365/human-resources/toc.json).</span></span>

> [!NOTE]
> <span data-ttu-id="a46a4-159">A ledolgozott órák száma nem haladhatja meg az 1250-et, és a munkaviszony nem lehet hosszabb 12 hónapnál.</span><span class="sxs-lookup"><span data-stu-id="a46a4-159">The number of hours that are worked can't exceed 1,250, and the length of employment can't exceed 12 months.</span></span> <span data-ttu-id="a46a4-160">Ezek a maximális értékek az Egyesült Államok szövetségi törvényének megfelelőek.</span><span class="sxs-lookup"><span data-stu-id="a46a4-160">These maximum values are in accordance with federal law in the United States.</span></span>

![Számsorozatok lap](./media/hr-setup-parameters-number-sequences.png)

## <a name="fmla"></a><span data-ttu-id="a46a4-162">FMLA</span><span class="sxs-lookup"><span data-stu-id="a46a4-162">FMLA</span></span>

<span data-ttu-id="a46a4-163">Az FMLA lapon lehet beállítani az FMLA-alkalmazhatósági követelmények és az FMLA-jogosultsági órák beállítását.</span><span class="sxs-lookup"><span data-stu-id="a46a4-163">On the FMLA tab, you set FMLA eligibility requirements and FMLA entitlement hours.</span></span> <span data-ttu-id="a46a4-164">További tájékoztatás: [Szabadság és távolléti paraméterek konfigurálása](hr-leave-and-absence-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="a46a4-164">For more information, see [Configure leave and absence parameters](hr-leave-and-absence-parameters.md).</span></span>

![FMLA lap](./media/hr-setup-parameters-fmla.png)

## <a name="employee-self-service"></a><span data-ttu-id="a46a4-166">Alkalmazotti önkiszolgáló rendszer</span><span class="sxs-lookup"><span data-stu-id="a46a4-166">Employee self service</span></span>

<span data-ttu-id="a46a4-167">Az **Alkalmazotti önkiszolgáló rendszer** lap beállításai befolyásolják, hogyan jelenik meg az Alkalmazotti önkiszolgáló rendszer az alkalmazottak számára.</span><span class="sxs-lookup"><span data-stu-id="a46a4-167">The settings on the **Employee self service** tab affect how Employee self service appears to employees.</span></span> <span data-ttu-id="a46a4-168">Ezen a lapon a következő beállításokat használhatja:</span><span class="sxs-lookup"><span data-stu-id="a46a4-168">On this tab, you can:</span></span>

- <span data-ttu-id="a46a4-169">Alkalmazotti önkiszolgáló munkaterület nevének megadása</span><span class="sxs-lookup"><span data-stu-id="a46a4-169">Enter a name for the Employee self service workspace</span></span>
- <span data-ttu-id="a46a4-170">Adja meg, hogy a vezető mely adatokat adhatja meg az alkalmazottak számára</span><span class="sxs-lookup"><span data-stu-id="a46a4-170">Select which information a manager can enter for employees</span></span>
- <span data-ttu-id="a46a4-171">Hasznos hivatkozások hozzáadása az alkalmazottak számára</span><span class="sxs-lookup"><span data-stu-id="a46a4-171">Add useful links for employees</span></span>
- <span data-ttu-id="a46a4-172">Az alkalmazottak korlátozása az üzleti kapcsolattartók részleteinek hozzáadása és szerkesztése tekintetében.</span><span class="sxs-lookup"><span data-stu-id="a46a4-172">Restrict employees from adding or editing business contact details.</span></span> <span data-ttu-id="a46a4-173">A további tudnivalókat lásd: [Személyes adatok szerkesztésének korlátozása](hr-employee-self-service-restrict-editing.md).</span><span class="sxs-lookup"><span data-stu-id="a46a4-173">For more information, see [Restrict editing of personal information](hr-employee-self-service-restrict-editing.md).</span></span>

<span data-ttu-id="a46a4-174">Az Alkalmazotti önkiszolgáló rendszer beállításával kapcsolatos további tudnivalókat lásd: [Alkalmazotti és vezetői önkiszolgáló rendszer áttekintése](hr-employee-manager-self-service-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a46a4-174">For more information about setting up Employee self service, see [Employee and Manager self service overview](hr-employee-manager-self-service-overview.md).</span></span>

![Alkalmazotti önkiszolgáló rendszer lap](./media/hr-setup-parameters-employee-self-service.png)

## <a name="manager-self-service"></a><span data-ttu-id="a46a4-176">Vezetői önkiszolgáló rendszer</span><span class="sxs-lookup"><span data-stu-id="a46a4-176">Manager self service</span></span>

<span data-ttu-id="a46a4-177">A **Vezetői önkiszolgáló rendszer** lapon megadott beállítások befolyásolják, hogy mit látnak a vezetők a Vezetői önkiszolgáló rendszerében.</span><span class="sxs-lookup"><span data-stu-id="a46a4-177">The settings on the **Manager self service** tab affect what managers see in Manager self service.</span></span> <span data-ttu-id="a46a4-178">Ezen a lapon a következő beállításokat lehet beállítani:</span><span class="sxs-lookup"><span data-stu-id="a46a4-178">On this tab, you can configure the following options:</span></span>

- <span data-ttu-id="a46a4-179">A lejáró rekordok tartománya</span><span class="sxs-lookup"><span data-stu-id="a46a4-179">The range for expiring records</span></span>
- <span data-ttu-id="a46a4-180">A vezetők által a lejáró rekordokban látható információk</span><span class="sxs-lookup"><span data-stu-id="a46a4-180">Information managers can view in expiring records</span></span>
- <span data-ttu-id="a46a4-181">Azt jelzi, hogy a vezetők megtekinthetnek-e nyitott pozíciókat a kiterjesztett jelentésekhez</span><span class="sxs-lookup"><span data-stu-id="a46a4-181">Whether managers can view open positions for extended reports</span></span>
- <span data-ttu-id="a46a4-182">A kilépő dolgozók nézete</span><span class="sxs-lookup"><span data-stu-id="a46a4-182">Views of exiting workers</span></span>
- <span data-ttu-id="a46a4-183">Hasznos hivatkozások a vezetőknek</span><span class="sxs-lookup"><span data-stu-id="a46a4-183">Useful links for managers</span></span>

<span data-ttu-id="a46a4-184">A Vezetői önkiszolgáló rendszer beállításával kapcsolatos további tudnivalókat lásd: [Alkalmazotti és vezetői önkiszolgáló rendszer áttekintése](hr-employee-manager-self-service-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a46a4-184">For more information about setting up Manager self service, see [Employee and Manager self service overview](hr-employee-manager-self-service-overview.md).</span></span>

![Vezetői önkiszolgáló rendszer lap](./media/hr-setup-parameters-manager-self-service.png)

## <a name="benefits-management"></a><span data-ttu-id="a46a4-186">Juttatáskezelés</span><span class="sxs-lookup"><span data-stu-id="a46a4-186">Benefits management</span></span>

<span data-ttu-id="a46a4-187">A Juttatáskezelés lapon beállíthatja a Juttatáskezelése e-mail-beállításait.</span><span class="sxs-lookup"><span data-stu-id="a46a4-187">On the Benefits management tab, you can configure email options for Benefits management.</span></span> <span data-ttu-id="a46a4-188">A Juttatáskezelés beállításával és használatával kapcsolatos további tudnivalókért lásd: [Juttatáskezelés áttekintése](hr-benefits-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a46a4-188">For information about setting up and using Benefits management, see [Benefits management overview](hr-benefits-management-overview.md).</span></span>

![Juttatáskezelés lap](./media/hr-setup-parameters-benefits-management.png)

## <a name="leave-and-absence"></a><span data-ttu-id="a46a4-190">Szabadság és távollét</span><span class="sxs-lookup"><span data-stu-id="a46a4-190">Leave and absence</span></span>

<span data-ttu-id="a46a4-191">A Szabadság és távollét beállításával és használatával kapcsolatos további tudnivalókat lásd: [Szabadság és a távollét áttekintése](hr-leave-and-absence-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a46a4-191">For information about setting up and using Leave and absence, see [Leave and absence overview](hr-leave-and-absence-overview.md).</span></span>

## <a name="payment-methods"></a><span data-ttu-id="a46a4-192">Fizetési módok</span><span class="sxs-lookup"><span data-stu-id="a46a4-192">Payment methods</span></span>

<span data-ttu-id="a46a4-193">A **Fizetési módok** lapon kiválaszthatja a szervezet által támogatott fizetési módokat.</span><span class="sxs-lookup"><span data-stu-id="a46a4-193">On the **Payment methods** tab, you can select the payment methods supported by your organization.</span></span> <span data-ttu-id="a46a4-194">A kompenzáció konfigurálásával kapcsolatos további információkért lásd: [Kompenzációs konstrukciók áttekintése](hr-compensation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a46a4-194">For more information about configuring compensation, see [Compensation plans overview](hr-compensation-overview.md).</span></span>

![Fizetési módok lap](./media/hr-setup-parameters-payment-methods.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]