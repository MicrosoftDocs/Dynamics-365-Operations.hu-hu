---
title: "Költségkezelés konfigurálása"
description: "Ez a cikk ismerteti azokat a szempontokat, amelyeket a tervezési folyamat során – a Költséggazdálkodás Microsoft Dynamics 365 for Finance and Operations Enterprise edition rendszerben történő konfigurálása előtt – figyelembe kell venni, valamint az ekkor meghozandó döntéseket."
author: KimANelson
manager: AnnBe
ms.date: 08/29/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: GlobalCategory, ProjCategory, TrvLocations, TrvParameters, TrvPaymethod, TrvPerDiems
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 23001
ms.assetid: aa3fd14d-7e94-4603-985f-ca26d6f860ea
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 4fad62c5da11e88e07f4e9d4343c4ac1a487bdd8
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="configure-expense-management"></a><span data-ttu-id="4408d-103">Költségkezelés konfigurálása</span><span class="sxs-lookup"><span data-stu-id="4408d-103">Configure expense management</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="4408d-104">Ez a témakör ismerteti azokat a szempontokat, amelyeket a tervezési folyamat során – a Költséggazdálkodás Microsoft Dynamics 365 for Finance and Operations Enterprise edition rendszerben történő konfigurálása előtt – figyelembe kell venni, valamint az ekkor meghozandó döntéseket.</span><span class="sxs-lookup"><span data-stu-id="4408d-104">This topic describes the considerations and the decisions that you must make during the planning process before you configure Expense management in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span></span> <span data-ttu-id="4408d-105">A Költséggazdálkodás területén többek között fizetési módokkal, utazásigénylésekkel, költségjelentésekkel, irányelvekkel stb. kapcsolatos információkat tárolhat.</span><span class="sxs-lookup"><span data-stu-id="4408d-105">In Expense management, you can store information about payment methods, travel requisitions, expense reports, policies, and so on.</span></span>

<span data-ttu-id="4408d-106">Mivel a Költséggazdálkodási konfiguráció tervezése során meghozott számos döntés az Ön szervezetének hierarchiáján, illetve annak pénzügyi struktúráján alapszik, így szükséges átolvasnia ezen területek tervezési dokumentumait is.</span><span class="sxs-lookup"><span data-stu-id="4408d-106">Because many of the decisions that you make when you plan your configuration for Expense management are based on your organization’s hierarchy and financial structure, you must refer to the planning documents for those areas.</span></span>

## <a name="intercompany-expenses"></a><span data-ttu-id="4408d-107">Vállalatközi költségek</span><span class="sxs-lookup"><span data-stu-id="4408d-107">Intercompany expenses</span></span>

<span data-ttu-id="4408d-108">Ha engedélyezi a vállalatközi költségeket, úgy azt teszi lehetővé, hogy a jogi személyek és az alkalmazottak költségeket szenvedjenek el, illetve kifizetéseket vegyenek kézhez más, az Ön szervezetén belüli alkalmazó jogi személyektől.</span><span class="sxs-lookup"><span data-stu-id="4408d-108">When you enable intercompany expenses, you allow legal entities and employees to incur expenses on behalf of another legal entity, and collect payment from the legal entity of employment within your organization.</span></span> <span data-ttu-id="4408d-109">Például az A jogi személynél egy alkalmazott elvégez egy projektet a B jogi személy számára, és a projekt során utazással kapcsolatos költségek merülnek fel.</span><span class="sxs-lookup"><span data-stu-id="4408d-109">For example, an employee in legal entity A completes a project for legal entity B, and the project incurs travel related expenses.</span></span> <span data-ttu-id="4408d-110">Ha engedélyezve vannak a vállalatközi költségek, akkor az alkalmazott benyújthat egy olyan költségjelentést, amely a költséget a B jogi személyhez adja fel, és a költséget az A jogi személynek kell kifizetnie. Ha az Ön szervezetéhez csak egy jogi személy tartozik, akkor nem szükséges engedélyeznie a vállalatközi költségeket.</span><span class="sxs-lookup"><span data-stu-id="4408d-110">If intercompany expenses are enabled, the employee can then file an expense report that will post the expense to legal entity B, and the expense must then be paid by legal entity A. If your organization doesn’t have multiple legal entities, you don’t have to enable intercompany expenses.</span></span>

<span data-ttu-id="4408d-111">**Döntés:** Szeretné engedélyezni a vállalatközi költségeket?</span><span class="sxs-lookup"><span data-stu-id="4408d-111">**Decision:** Do you want to enable intercompany expenses?</span></span>

## <a name="financial-management"></a><span data-ttu-id="4408d-112">Pénzgazdálkodás</span><span class="sxs-lookup"><span data-stu-id="4408d-112">Financial management</span></span>

<span data-ttu-id="4408d-113">A költséggazdálkodás szorosan kapcsolódik szervezete pénzgazdálkodásához.</span><span class="sxs-lookup"><span data-stu-id="4408d-113">Expense management is tightly integrated with the financial management of your organization.</span></span> <span data-ttu-id="4408d-114">A költséggazdálkodásra vonatkozó konfigurációk jelentős része a szervezete pénzügyei kapcsán már korábban meghozott döntéseken alapul.</span><span class="sxs-lookup"><span data-stu-id="4408d-114">Lots of your configuration for Expense management will be based on the decisions that you’ve made about your organization’s finances.</span></span> <span data-ttu-id="4408d-115">Az alábbi szakaszok azokat a különféle területeket mutatják be, melyek tervezést és döntéshozatalt igényelnek, a szervezete pénzügyi döntései, illetve a vezető testület útmutatása alapján.</span><span class="sxs-lookup"><span data-stu-id="4408d-115">The following sections describe the various areas that require planning and decisions, based on your organization’s financial decisions and guidance from your leadership team.</span></span>

### <a name="per-diems"></a><span data-ttu-id="4408d-116">Napidíjak</span><span class="sxs-lookup"><span data-stu-id="4408d-116">Per diems</span></span>

<span data-ttu-id="4408d-117">Meg kell adnia a szervezete által biztosított alkalmazotti napidíjakat.</span><span class="sxs-lookup"><span data-stu-id="4408d-117">You must define the employee per diems that your organization provides.</span></span> <span data-ttu-id="4408d-118">Mivel a napidíjak jellemzően olyan költségek fedezésére szolgálnak, mint az étkezés, a szállás és más járulékos költségek, tud létrehozni a szervezete által térített napidíjakra vonatkozó szabályokat.</span><span class="sxs-lookup"><span data-stu-id="4408d-118">Because per diems are typically used to cover expenses such as meals, lodging, and other incidental expenses, you can create rules for the per diem allowances that your organization offers.</span></span> <span data-ttu-id="4408d-119">A napidíj alapja a dátum, az utazási helyszín, vagy a kettő kombinációja lehet.</span><span class="sxs-lookup"><span data-stu-id="4408d-119">per diem rates can be based on the time of year, the travel location, or both.</span></span> <span data-ttu-id="4408d-120">Napidíjszabályt létrehozásakor be tudja állítani, hogy a napidíj egy részét visszatartsa a rendszer, ha a dolgozó ingyenes étkezésben vagy egyéb szolgáltatásban részesül.</span><span class="sxs-lookup"><span data-stu-id="4408d-120">When you define a per diem rule, you can specify that a percentage of the per diem rate will be withheld if a worker receives complimentary meals or services.</span></span> <span data-ttu-id="4408d-121">Emellett tud megadni napidíjszinteket is, melyek a dolgozó útjára alkalmazható napidíjjal érintett órák minimális és maximális számát szabályozzák.</span><span class="sxs-lookup"><span data-stu-id="4408d-121">You can also define per diem rate tiers to set the minimum and maximum number of hours that the per diem rate can be applied to a worker’s travel.</span></span>

<span data-ttu-id="4408d-122">**Döntések:**</span><span class="sxs-lookup"><span data-stu-id="4408d-122">**Decisions:**</span></span>

- <span data-ttu-id="4408d-123">Az első és utolsó napra érvényes alapértelmezett napidíjszabályok:</span><span class="sxs-lookup"><span data-stu-id="4408d-123">Default per diem rules for the first and last days:</span></span>

    - <span data-ttu-id="4408d-124">Mi az az alkalmazott által benyújtott minimális napi óraszám, amelyre már jár a napidíj?</span><span class="sxs-lookup"><span data-stu-id="4408d-124">What is the minimum number of hours that an employee can claim for a day and still receive a per diem?</span></span>
    - <span data-ttu-id="4408d-125">Vonatkozik-e bármilyen levonás az első napra és utolsó napra járó étkezési díj összegére?</span><span class="sxs-lookup"><span data-stu-id="4408d-125">Is there a reduction in the amount that is offered for meals for the first day and last day?</span></span> <span data-ttu-id="4408d-126">Ha van levonás, mekkora a levonás százaléka?</span><span class="sxs-lookup"><span data-stu-id="4408d-126">If there is a reduction, what is the percentage of the reduction?</span></span>
    - <span data-ttu-id="4408d-127">Vonatkozik-e bármilyen levonás az első és utolsó napra járó szállásdíj összegére?</span><span class="sxs-lookup"><span data-stu-id="4408d-127">Is there a reduction in the amount that is offered for a hotel for the first day and last day?</span></span> <span data-ttu-id="4408d-128">Ha van levonás, mekkora a levonás százaléka?</span><span class="sxs-lookup"><span data-stu-id="4408d-128">If there is a reduction, what is the percentage of the reduction?</span></span>
    - <span data-ttu-id="4408d-129">Vonatkozik-e bármilyen levonás az első napra és utolsó napra járó egyéb költségtérítés összegére?</span><span class="sxs-lookup"><span data-stu-id="4408d-129">Is there a reduction in the amount that is offered for other expenses that are incurred on the first day and last day?</span></span> <span data-ttu-id="4408d-130">Ha van levonás, mekkora a levonás százaléka?</span><span class="sxs-lookup"><span data-stu-id="4408d-130">If there is a reduction, what is the percentage of the reduction?</span></span>

- <span data-ttu-id="4408d-131">Alapértelmezett napidíjszabályok:</span><span class="sxs-lookup"><span data-stu-id="4408d-131">Default per diem rules:</span></span>

    - <span data-ttu-id="4408d-132">Vonatkozik-e bármilyen, az egyes étkezésekre vonatkozó százalékos levonás, például ingyenes étkezések esetén?</span><span class="sxs-lookup"><span data-stu-id="4408d-132">Is there a percentage reduction in the per diem allowance for each meal if, for example, the meal is complimentary?</span></span> <span data-ttu-id="4408d-133">Ha van levonás, mekkora a levonás százaléka az egyes étkezéseknél?</span><span class="sxs-lookup"><span data-stu-id="4408d-133">If there is a reduction, what is the reduction percentage for each meal?</span></span>
    - <span data-ttu-id="4408d-134">Az étkezési levonás kiszámítása naponta, utanként vagy a napi étkezések darabszáma alapján történjen-e?</span><span class="sxs-lookup"><span data-stu-id="4408d-134">Is the meal reduction calculated per day, per trip, or by the number of meals per day?</span></span>
    - <span data-ttu-id="4408d-135">A napidíj-összegeket a szokásos módon vagy felfelé kell kerekíteni?</span><span class="sxs-lookup"><span data-stu-id="4408d-135">Should per diem amounts be rounded in the regular manner or rounded up?</span></span>
    - <span data-ttu-id="4408d-136">A napidíjak kiszámítása 24 órás időszak, vagy naptári napok alapján történjen-e?</span><span class="sxs-lookup"><span data-stu-id="4408d-136">Are per diems calculated on a 24-hour period or on a calendar day?</span></span>

- <span data-ttu-id="4408d-137">Helyszínfüggő napidíjszabályok:</span><span class="sxs-lookup"><span data-stu-id="4408d-137">Per diem rules that are based on location:</span></span>

    - <span data-ttu-id="4408d-138">A napidíjösszegek hely szerint változnak?</span><span class="sxs-lookup"><span data-stu-id="4408d-138">Do per diem rates vary according to location?</span></span> <span data-ttu-id="4408d-139">Milyen helyeket foglal ez magában?</span><span class="sxs-lookup"><span data-stu-id="4408d-139">What locations are included?</span></span>
    - <span data-ttu-id="4408d-140">Ha napidíjösszegek hely szerint változnak, minden egyes hely esetén milyen százalékérték tartozik a következő típusú költségekhez:</span><span class="sxs-lookup"><span data-stu-id="4408d-140">If per diem rates vary according to location, for each location, what percentage amount is provided for the following types of expenses:</span></span>

        - <span data-ttu-id="4408d-141">Étkezés</span><span class="sxs-lookup"><span data-stu-id="4408d-141">Meals</span></span>
        - <span data-ttu-id="4408d-142">Szálloda</span><span class="sxs-lookup"><span data-stu-id="4408d-142">Hotel</span></span>
        - <span data-ttu-id="4408d-143">Egyéb költségek</span><span class="sxs-lookup"><span data-stu-id="4408d-143">Other expenses</span></span>

### <a name="expense-management-journals-and-accounts"></a><span data-ttu-id="4408d-144">Költséggazdálkodási naplók és számlák</span><span class="sxs-lookup"><span data-stu-id="4408d-144">Expense management journals and accounts</span></span>

<span data-ttu-id="4408d-145">A költséggazdálkodás több napló és számla használatát teszi szükségessé.</span><span class="sxs-lookup"><span data-stu-id="4408d-145">Expense management requires that you use multiple journals and accounts.</span></span> <span data-ttu-id="4408d-146">El kell például döntenie, hogy ugyanazt a számlát használja-e a készpénzelőlegekhez, illetve a vitatott hitelkártya tételekhez?</span><span class="sxs-lookup"><span data-stu-id="4408d-146">You must decide, for example, whether the same account is used for cash advances and credit card disputes.</span></span>

<span data-ttu-id="4408d-147">**Döntések:**</span><span class="sxs-lookup"><span data-stu-id="4408d-147">**Decisions:**</span></span>

- <span data-ttu-id="4408d-148">Melyik főkönyvi naplóba történik a jóváhagyott költségjelentések feladása?</span><span class="sxs-lookup"><span data-stu-id="4408d-148">Which ledger journal are approved expense reports posted to?</span></span>
- <span data-ttu-id="4408d-149">Melyik számlát használja a készpénzelőlegekhez?</span><span class="sxs-lookup"><span data-stu-id="4408d-149">Which account is used for cash advances?</span></span>
- <span data-ttu-id="4408d-150">Azonnal sor kerül-e a készpénzelőlegek feladására?</span><span class="sxs-lookup"><span data-stu-id="4408d-150">Should cash advances be posted immediately?</span></span>

### <a name="payment-methods"></a><span data-ttu-id="4408d-151">Kifizetési módok</span><span class="sxs-lookup"><span data-stu-id="4408d-151">Payment methods</span></span>

<span data-ttu-id="4408d-152">Ha engedélyezi az alkalmazottak részére a vállalati költségek kiegyenlítését, úgy meg kell adnia, hogy melyek az alkalmazottak részére engedélyezett fizetési módok.</span><span class="sxs-lookup"><span data-stu-id="4408d-152">When you allow employees to incur expenses on behalf of your business, you must define the payment methods that employees are allowed to use.</span></span> <span data-ttu-id="4408d-153">Lehetővé teheti például az alkalmazottak részére a készpénz vagy a vállalati hitelkártya használatát.</span><span class="sxs-lookup"><span data-stu-id="4408d-153">For example, you might allow employees to use cash or a corporate credit card.</span></span> <span data-ttu-id="4408d-154">De engedélyezheti az alkalmazottak személyes hitelkártyáinak használatát, illetve az összeg utólagos megtérítését is.</span><span class="sxs-lookup"><span data-stu-id="4408d-154">You might also allow employees to use personal credit cards, and then reimburse the employees.</span></span> <span data-ttu-id="4408d-155">Minden engedélyezett fizetési mód kapcsán el kell döntenie az alábbiakat.</span><span class="sxs-lookup"><span data-stu-id="4408d-155">You must make the following decisions for each payment method that you allow.</span></span>

<span data-ttu-id="4408d-156">**Döntések:**</span><span class="sxs-lookup"><span data-stu-id="4408d-156">**Decisions:**</span></span>

- <span data-ttu-id="4408d-157">Melyek az engedélyezett fizetési módok?</span><span class="sxs-lookup"><span data-stu-id="4408d-157">What payment methods are allowed?</span></span>
- <span data-ttu-id="4408d-158">Ki viseli a fizetési módhoz kapcsolódó költségeket?</span><span class="sxs-lookup"><span data-stu-id="4408d-158">Who owns the payment method expenses?</span></span>
- <span data-ttu-id="4408d-159">Van-e ellenszámlatípus?</span><span class="sxs-lookup"><span data-stu-id="4408d-159">Is there an offset account type?</span></span> <span data-ttu-id="4408d-160">Ha van ellenszámlatípus, melyik az?</span><span class="sxs-lookup"><span data-stu-id="4408d-160">If there is an offset account type, what is it?</span></span>
- <span data-ttu-id="4408d-161">Ha van ellenszámla, melyik az?</span><span class="sxs-lookup"><span data-stu-id="4408d-161">If there is an offset account, what is the account?</span></span>
- <span data-ttu-id="4408d-162">Hitelkártyás fizetési mód esetén ez a fizetési mód csak importált tranzakciók esetén legyen alkalmazható?</span><span class="sxs-lookup"><span data-stu-id="4408d-162">If the payment method is a credit card, should the payment method be used only with imported transactions?</span></span>

### <a name="expense-categories-and-shared-categories"></a><span data-ttu-id="4408d-163">Költség- és megosztott kategóriák</span><span class="sxs-lookup"><span data-stu-id="4408d-163">Expense categories and shared categories</span></span>

<span data-ttu-id="4408d-164">Amikor egy alkalmazott költségjelentést hoz létre, minden abban rögzített költséget társítani kell egy költségkategóriával.</span><span class="sxs-lookup"><span data-stu-id="4408d-164">When employees create an expense report, each expense that they record must be associated with an expense category.</span></span> <span data-ttu-id="4408d-165">A költségkategóriákat a rendszer a szervezetén belül működő jogi személyek által használt megosztott kategóriákból eredezteti.</span><span class="sxs-lookup"><span data-stu-id="4408d-165">Expense categories are derived from shared categories that can be shared across the legal entities in your organization.</span></span> <span data-ttu-id="4408d-166">Ezek a kategóriák, a szervezeti beállítások függvényében, a Projektvezetés és könyvelés modullal is megoszthatók.</span><span class="sxs-lookup"><span data-stu-id="4408d-166">These categories can also be shared in Project management and accounting, depending on the way that your organization is defined.</span></span> <span data-ttu-id="4408d-167">Határozza meg a szervezeti beállításai, illetve a végrehajtásért felelős csapat útmutatása alapján, hogy költséggazdálkodásban meghatározott kategóriákat csak a költségkezelés kapcsán, vagy a Projektvezetés és könyvelés és a Költségkezelés között megosztva kívánja-e használni.</span><span class="sxs-lookup"><span data-stu-id="4408d-167">Based on the definition of your organization and guidance from the implementation team, determine whether the categories that are used in Expense management will be used only in Expense management, or whether they should be shared between Project management and accounting and Expense management.</span></span> <span data-ttu-id="4408d-168">Kérjük, vegye figyelembe, hogy ezek a kategóriák a Projekt és a Költség, illetőleg a Projekt és a Termelés modul között oszthatók meg, de a Költség és a Termelés modul között nem.</span><span class="sxs-lookup"><span data-stu-id="4408d-168">Note that these categories can be shared between Project and Expense or Project and Production, but not between Expense and Production.</span></span> <span data-ttu-id="4408d-169">Az egyes költségkategóriák kapcsán az alábbi döntéseket kell meghoznia.</span><span class="sxs-lookup"><span data-stu-id="4408d-169">You must make the following decisions for each expense category.</span></span>

<span data-ttu-id="4408d-170">**Döntések:**</span><span class="sxs-lookup"><span data-stu-id="4408d-170">**Decisions:**</span></span>

- <span data-ttu-id="4408d-171">Mi a költségkategória?</span><span class="sxs-lookup"><span data-stu-id="4408d-171">What is the expense category?</span></span> <span data-ttu-id="4408d-172">Példák: légi közlekedési, szállodai vagy útiköltség kategóriák.</span><span class="sxs-lookup"><span data-stu-id="4408d-172">Examples include categories for flights, hotel, or mileage.</span></span>
- <span data-ttu-id="4408d-173">A költségkategória használható a Projektvezetés és könyvelési modulban is?</span><span class="sxs-lookup"><span data-stu-id="4408d-173">Can the expense category also be used in Project management and accounting?</span></span>
- <span data-ttu-id="4408d-174">Mi a költségkategória?</span><span class="sxs-lookup"><span data-stu-id="4408d-174">What is the expense type?</span></span>
- <span data-ttu-id="4408d-175">Mi a költségkategóriára érvényes alapértelmezett fizetési mód?</span><span class="sxs-lookup"><span data-stu-id="4408d-175">What is the default payment method for the expense category?</span></span>
- <span data-ttu-id="4408d-176">A költségkategória-kiadásokat részletezve kell feltüntetni?</span><span class="sxs-lookup"><span data-stu-id="4408d-176">Do expenses in the expense category have to be itemized?</span></span>
- <span data-ttu-id="4408d-177">Mi a költségkategóriára érvényes fő alapértelmezett számla?</span><span class="sxs-lookup"><span data-stu-id="4408d-177">What is the main default account for the expense category?</span></span>
- <span data-ttu-id="4408d-178">Mi a költségcsoportra érvényes alapértelmezett cikkáfacsoportot?</span><span class="sxs-lookup"><span data-stu-id="4408d-178">What is the default item sales tax group for the expense category?</span></span>
- <span data-ttu-id="4408d-179">Engedélyezett-e további fizetési mód ebben a költségkategóriában?</span><span class="sxs-lookup"><span data-stu-id="4408d-179">Are additional payment methods allowed for the expense category?</span></span> <span data-ttu-id="4408d-180">Ha engedélyezve vannak további fizetési módok, melyek ezek?</span><span class="sxs-lookup"><span data-stu-id="4408d-180">If additional payment methods are allowed, what are they?</span></span>
- <span data-ttu-id="4408d-181">Ebben a költségkategóriában vannak-e alkategóriák?</span><span class="sxs-lookup"><span data-stu-id="4408d-181">Are there subcategories in this expense category?</span></span> <span data-ttu-id="4408d-182">Ha vannak alkategóriák, a következő döntéseket kell meghozni:</span><span class="sxs-lookup"><span data-stu-id="4408d-182">If there are subcategories, you must also make the following decisions:</span></span>

    - <span data-ttu-id="4408d-183">Vannak-e adó-visszaigénylésre nem jogosító alkategóriák?</span><span class="sxs-lookup"><span data-stu-id="4408d-183">Are any of the subcategories excluded from tax recovery?</span></span>
    - <span data-ttu-id="4408d-184">Mi az alkategóriák cikkáfacsoportja?</span><span class="sxs-lookup"><span data-stu-id="4408d-184">What is the item sales tax group of the subcategories?</span></span>

<span data-ttu-id="4408d-185">Válaszoljon az alábbi kérdésekre, ha a költségkategória a Projektvezetés és könyvelés modulban is felhasználásra kerül.</span><span class="sxs-lookup"><span data-stu-id="4408d-185">If the expense category is also used in Project management and accounting, answer the remaining questions.</span></span> <span data-ttu-id="4408d-186">Ellenkező esetben lépjen a következő szakaszra.</span><span class="sxs-lookup"><span data-stu-id="4408d-186">Otherwise, move on to the next section.</span></span>

- <span data-ttu-id="4408d-187">Melyik költségszámla használandó az alábbi költségek kapcsán?</span><span class="sxs-lookup"><span data-stu-id="4408d-187">Which cost accounts will be used for the following expenses?</span></span>

    - <span data-ttu-id="4408d-188">Költség</span><span class="sxs-lookup"><span data-stu-id="4408d-188">Cost</span></span>
    - <span data-ttu-id="4408d-189">Bérfoglalás</span><span class="sxs-lookup"><span data-stu-id="4408d-189">Payroll allocation</span></span>
    - <span data-ttu-id="4408d-190">Folyamatban lévő munka - költségérték</span><span class="sxs-lookup"><span data-stu-id="4408d-190">WIP-cost value</span></span>
    - <span data-ttu-id="4408d-191">Költség-cikk</span><span class="sxs-lookup"><span data-stu-id="4408d-191">Cost-item</span></span>
    - <span data-ttu-id="4408d-192">Folyamatban lévő munka - költségérték - cikk</span><span class="sxs-lookup"><span data-stu-id="4408d-192">WIP-cost value-item</span></span>
    - <span data-ttu-id="4408d-193">Elhatárolt veszteség</span><span class="sxs-lookup"><span data-stu-id="4408d-193">Accrued loss</span></span>
    - <span data-ttu-id="4408d-194">Folyamatban lévő munka-elhatárolt veszteség</span><span class="sxs-lookup"><span data-stu-id="4408d-194">WIP-accrued loss</span></span>

- <span data-ttu-id="4408d-195">Melyik bevételszámla használandó az alábbiak kapcsán?</span><span class="sxs-lookup"><span data-stu-id="4408d-195">Which revenue accounts will be used for the following?</span></span>

    - <span data-ttu-id="4408d-196">Számlázott bevétel</span><span class="sxs-lookup"><span data-stu-id="4408d-196">Invoiced revenue</span></span>
    - <span data-ttu-id="4408d-197">Elhatárolt bevétel-értékesítési érték</span><span class="sxs-lookup"><span data-stu-id="4408d-197">Accrued revenue-sales value</span></span>
    - <span data-ttu-id="4408d-198">Folyamatban lévő munka-értékesítési érték</span><span class="sxs-lookup"><span data-stu-id="4408d-198">WIP-sales value</span></span>
    - <span data-ttu-id="4408d-199">Elhatárolt bevétel-termelés</span><span class="sxs-lookup"><span data-stu-id="4408d-199">Accrued revenue-production</span></span>
    - <span data-ttu-id="4408d-200">Folyamatban lévő munka-termelés</span><span class="sxs-lookup"><span data-stu-id="4408d-200">WIP-production</span></span>
    - <span data-ttu-id="4408d-201">Elhatárolt bevétel-nyereség</span><span class="sxs-lookup"><span data-stu-id="4408d-201">Accrued revenue-profit</span></span>
    - <span data-ttu-id="4408d-202">Folyamatban lévő munka-nyereség</span><span class="sxs-lookup"><span data-stu-id="4408d-202">WIP-profit</span></span>
    - <span data-ttu-id="4408d-203">Elhatárolt bevétel-előfizetés</span><span class="sxs-lookup"><span data-stu-id="4408d-203">Accrued revenue-subscription</span></span>
    - <span data-ttu-id="4408d-204">Folyamatban lévő munka-előfizetés</span><span class="sxs-lookup"><span data-stu-id="4408d-204">WIP-subscription</span></span>

### <a name="taxes"></a><span data-ttu-id="4408d-205">Adók</span><span class="sxs-lookup"><span data-stu-id="4408d-205">Taxes</span></span>

<span data-ttu-id="4408d-206">A költségekhez kapcsolódó adók kapcsán meg kell adnia, hogy mit ad hozzá, illetve mit engedélyez a költségjelentésekben.</span><span class="sxs-lookup"><span data-stu-id="4408d-206">For expense-related taxes, you must determine what is included or enabled on expense reports.</span></span>

<span data-ttu-id="4408d-207">**Döntések:**</span><span class="sxs-lookup"><span data-stu-id="4408d-207">**Decisions:**</span></span>

- <span data-ttu-id="4408d-208">A költségösszegek tartalmazzák az áfát?</span><span class="sxs-lookup"><span data-stu-id="4408d-208">Is sales tax included in the expense amounts?</span></span>
- <span data-ttu-id="4408d-209">Engedélyezett a költség kapcsán az adó-visszaigénylés?</span><span class="sxs-lookup"><span data-stu-id="4408d-209">Should tax recovery be enabled on expenses?</span></span>

    > [!NOTE]
    > <span data-ttu-id="4408d-210">A főkönyv tervezésénél, ha szeretné alkalmazni az egyesült államokbeli áfa- és importadó-szabályokat, a költségeknél az adó-visszaigénylés nem engedélyezhető.</span><span class="sxs-lookup"><span data-stu-id="4408d-210">When you were planning the general ledger, if you decided to apply U.S. sales tax and use tax rules, you can’t enable tax recovery on expenses.</span></span> <span data-ttu-id="4408d-211">(USA-beli áfa- és importadó-szabályok használata esetén, állítsa az **Áfára vonatkozó adózási szabályok alkalmazása** paramétert **Igen** értékre.)</span><span class="sxs-lookup"><span data-stu-id="4408d-211">(To apply U.S. sales tax and use tax rules, set the **Apply sales tax taxations rules** option to **Yes**.)</span></span>

## <a name="policies"></a><span data-ttu-id="4408d-212">Irányelvek</span><span class="sxs-lookup"><span data-stu-id="4408d-212">Policies</span></span>

<span data-ttu-id="4408d-213">Költségjelentési irányelvek létrehozásával segíthet a szervezetnek időt és pénzt megtakarítani, amikor az alkalmazottaknál vállalati költségek merülnek fel.</span><span class="sxs-lookup"><span data-stu-id="4408d-213">By creating expense report policies, you can help your organization save time and money when employees incur expenses on its behalf.</span></span> <span data-ttu-id="4408d-214">Az irányelvek segítenek biztosítani, hogy az alkalmazottak betartsák a költségkertet, hogy megadjanak minden szükséges információt, illetve hogy csak a szükséges mértékű összeget költsék el.</span><span class="sxs-lookup"><span data-stu-id="4408d-214">Policies help guarantee that employees stay in budget, provide all required information, and spend money only as they require it.</span></span> <span data-ttu-id="4408d-215">Az alábbi döntéseket kell meghoznia minden egyes, Ön által létrehozott költségjelentés irányelv és költségjelentés jóváhagyási irányelv kapcsán.</span><span class="sxs-lookup"><span data-stu-id="4408d-215">You must make the following decisions for each expense report policy and each expense report approval policy that you create.</span></span>

<span data-ttu-id="4408d-216">**Döntések:**</span><span class="sxs-lookup"><span data-stu-id="4408d-216">**Decisions:**</span></span>

- <span data-ttu-id="4408d-217">Mi az irányelv neve?</span><span class="sxs-lookup"><span data-stu-id="4408d-217">What is the name of the policy?</span></span>
- <span data-ttu-id="4408d-218">Mi a költségirányelv célja?</span><span class="sxs-lookup"><span data-stu-id="4408d-218">What is the expense policy for?</span></span>
- <span data-ttu-id="4408d-219">Ha korábban engedélyezte a vállalatközi költségeket, úgy az irányelv a szervezet mely vállalataira vonatkozik?</span><span class="sxs-lookup"><span data-stu-id="4408d-219">If you previously decided to enable intercompany expenses, which companies in your organization will this policy apply to?</span></span>
- <span data-ttu-id="4408d-220">Mikor lép életbe az irányelv?</span><span class="sxs-lookup"><span data-stu-id="4408d-220">When does the policy become effective?</span></span>
- <span data-ttu-id="4408d-221">Mikor jár le az irányelv?</span><span class="sxs-lookup"><span data-stu-id="4408d-221">When does the policy expire?</span></span>
- <span data-ttu-id="4408d-222">Mi az irányelvszabály?</span><span class="sxs-lookup"><span data-stu-id="4408d-222">What is the policy rule?</span></span>
- <span data-ttu-id="4408d-223">Mi az irányelvszabály eredménye?</span><span class="sxs-lookup"><span data-stu-id="4408d-223">What is the outcome of the policy rule?</span></span>

