---
title: Optimalizálási tanácsadó szabályainak létrehozása
description: Ez a témakör ismerteti az új szabályok hozzáadását az Optimalizálási tanácsadóhoz.
author: roxanadiaconu
manager: AnnBe
ms.date: 02/04/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SelfHealingWorkspace
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: roxanad
ms.search.validFrom: 2017-12-01
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: e14949b871534868c42d2b26a116e10ff9f05179
ms.sourcegitcommit: 8ff2413b6cb504d2b36fce2bb50441b2e690330e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/24/2020
ms.locfileid: "3081996"
---
# <a name="create-rules-for-optimization-advisor"></a><span data-ttu-id="0efcc-103">Optimalizálási tanácsadó szabályainak létrehozása</span><span class="sxs-lookup"><span data-stu-id="0efcc-103">Create rules for Optimization advisor</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0efcc-104">Ez a témakör elmagyarázza, hogyan hozhatók létre új szabályok az **Optimalizálási tanácsadóhoz**.</span><span class="sxs-lookup"><span data-stu-id="0efcc-104">This topic explains how to create new rules for **Optimization advisor**.</span></span> <span data-ttu-id="0efcc-105">Például létrehozhat egy új szabályt, amely azonosítja, melyik ajánlatkérési esetek címe üres.</span><span class="sxs-lookup"><span data-stu-id="0efcc-105">For example, you can create a new rule that identifies which Request for Quotations (RFQ) cases have an empty title.</span></span> <span data-ttu-id="0efcc-106">Címek az eseteken történő használata könnyen azonosíthatóvá és kereshetővé teszi őket.</span><span class="sxs-lookup"><span data-stu-id="0efcc-106">Using titles on cases makes them easily identifiable and searchable.</span></span> <span data-ttu-id="0efcc-107">Bár nagyon egyszerű, az alábbi példa bemutatja, mit lehet elérni optimalizálási szabályokkal.</span><span class="sxs-lookup"><span data-stu-id="0efcc-107">While quite simple, this example shows what can be achieved with optimization rules.</span></span> 

<span data-ttu-id="0efcc-108">A *szabály* egy ellenőrzés az alkalmazásadatokon.</span><span class="sxs-lookup"><span data-stu-id="0efcc-108">A *rule* is a check on application data.</span></span> <span data-ttu-id="0efcc-109">Ha teljesül a feltétel, amelyet a szabály értékel, lehetőség nyílik folyamatok optimalizálására vagy adatok javítására.</span><span class="sxs-lookup"><span data-stu-id="0efcc-109">If the condition that the rule evaluates is met, opportunities to optimize processes or improve data are created.</span></span> <span data-ttu-id="0efcc-110">Ezek a lehetőségek kihasználhatók, és opcionálisan mérhető az intézkedések hatása.</span><span class="sxs-lookup"><span data-stu-id="0efcc-110">The opportunities can be acted upon and, optionally, the impact of the actions can be measured.</span></span> 

<span data-ttu-id="0efcc-111">Új szabály létrehozásához az **Optimalizálási tanácsadó** részére adjon hozzá egy új osztályt, amely bővíti a **SelfHealingRule** absztrakt osztályt, implementálja az **IDiagnosticsRule** interfészt, és fel van szerelve a **DiagnosticRule** attribútummal.</span><span class="sxs-lookup"><span data-stu-id="0efcc-111">To create a new rule for the **Optimization advisor**, add a new class that extends the **SelfHealingRule** abstract class, implements the **IDiagnosticsRule** interface, and is decorated by the **DiagnosticRule** attribute.</span></span> <span data-ttu-id="0efcc-112">Az osztálynak olyan metódussal is kell rendelkeznie, amelynél megvan a **DiagnosticsRuleSubscription** attribútum.</span><span class="sxs-lookup"><span data-stu-id="0efcc-112">The class must also have a method decorated with the **DiagnosticsRuleSubscription** attribute.</span></span> <span data-ttu-id="0efcc-113">Megegyezés alapján ez az **opportunityTitle** metódus révén történik, amelyet később tárgyalunk.</span><span class="sxs-lookup"><span data-stu-id="0efcc-113">By convention, that is done on the **opportunityTitle** method, which will be discussed later.</span></span> <span data-ttu-id="0efcc-114">Ez az új osztály hozzáadható egy egyéni modellhez, amely a **SelfHealingRules** modelltől függ.</span><span class="sxs-lookup"><span data-stu-id="0efcc-114">This new class can be added to a custom model with a dependency on the **SelfHealingRules** model.</span></span> <span data-ttu-id="0efcc-115">A következő példában az implementált szabály neve **RFQTitleSelfHealingRule**.</span><span class="sxs-lookup"><span data-stu-id="0efcc-115">In the following example, the rule being implemented is called **RFQTitleSelfHealingRule**.</span></span>

```xpp
[DiagnosticsRule] 
public final class RFQTitleSelfHealingRule extends SelfHealingRule implements IDiagnosticsRule 
{ 
… 
} 
```

<span data-ttu-id="0efcc-116">A **SelfHealingRule** absztrakt osztályhoz absztrakt metódusok tartoznak amelyeket öröklő osztályokban kell implementálni.</span><span class="sxs-lookup"><span data-stu-id="0efcc-116">The **SelfHealingRule** abstract class has abstract methods that must be implemented in inheriting classes.</span></span> <span data-ttu-id="0efcc-117">Az alapvető az **evaluate** metódus, amely a szabály által azonosított lehetőségek listáját adja vissza.</span><span class="sxs-lookup"><span data-stu-id="0efcc-117">The core is the **evaluate** method, which returns a list of the opportunities identified by the rule.</span></span> <span data-ttu-id="0efcc-118">A lehetőségek lehetnek jogi személyenként vagy az egész rendszeren alkalmazhatók.</span><span class="sxs-lookup"><span data-stu-id="0efcc-118">Opportunities can be per legal entity or can apply to the whole system.</span></span>

```xpp
protected List evaluate() 
{ 
    List results = new List(Types::Record); 
    
    DataArea dataArea; 

    while select id from dataArea 
        where !dataArea.isVirtual 
    { 
        changecompany(dataArea.id) 
        { 
            container result = this.findRFQCasesWithEmptyTitle(); 

            if (conLen(result) > 0) 
            { 
                SelfHealingOpportunity opportunity = this.getOpportunityForCompany(dataArea.Id); 
                opportunity.EvaluationState = SelfHealingEvaluationState::Evaluated; 
                opportunity.Data = result; 
                opportunity.OpportunityDate = DateTimeUtil::utcNow(); 
                
                results.addEnd(opportunity); 
            } 
        } 
    } 
    
    return results; 
} 
```

<span data-ttu-id="0efcc-119">A fenti metódus ciklust hajt végre vállalatokon keresztül és kiválasztja azokat az ajánlatkérési eseteket, amelyek címei üresek a  **findRFQCasesWithEmptyTitle** metódusban.</span><span class="sxs-lookup"><span data-stu-id="0efcc-119">The method shown above loops over companies and selects RFQ cases with empty titles in the **findRFQCasesWithEmptyTitle** method.</span></span> <span data-ttu-id="0efcc-120">Ha legalább egy ilyen eset található, akkor létrejön egy vállalatfüggő lehetőség a **getOpportunityForCompany** metódussal.</span><span class="sxs-lookup"><span data-stu-id="0efcc-120">If at least one such case is found, then a company-specific opportunity is created with the **getOpportunityForCompany** method.</span></span> <span data-ttu-id="0efcc-121">Figyelje meg, hogy a **Data** mező a **SelfHealingOpportunity** táblában **Tároló** típusú, tehát az adott szabályban megadott logikával kapolatos bármilyen adatot tartalmazhat.</span><span class="sxs-lookup"><span data-stu-id="0efcc-121">Notice that the field **Data** in the **SelfHealingOpportunity** table is of type **Container**, and can therefore contain any data relevant to the logic specific to this rule.</span></span> <span data-ttu-id="0efcc-122">Az **OpportunityDate** beállítása az aktuális időbélyegzővel rögzíti a lehetőség legutóbbi értékelésének időpontját.</span><span class="sxs-lookup"><span data-stu-id="0efcc-122">Setting **OpportunityDate** with the current timestamp registers the time of the latest evaluation of the opportunity.</span></span>  

<span data-ttu-id="0efcc-123">A lehetőségek több vállalatot is érinthetnek.</span><span class="sxs-lookup"><span data-stu-id="0efcc-123">Opportunities can also be cross-company.</span></span> <span data-ttu-id="0efcc-124">Ebben az esetben nincs szükség vállalatokon keresztüli ciklusra, és a lehetőséget a **getOpportunityAcrossCompanies** metódussal kell létrehozni.</span><span class="sxs-lookup"><span data-stu-id="0efcc-124">In this case, the loop over companies is not necessary and the opportunity must be created with the **getOpportunityAcrossCompanies** method.</span></span> 

<span data-ttu-id="0efcc-125">A következő kód a **findRFQCasesWithEmptyTitle** metódust mutatja, amely az üres címekkel rendelkező ajánlatkérési esetek azonosítóját adja vissza.</span><span class="sxs-lookup"><span data-stu-id="0efcc-125">The following code shows the **findRFQCasesWithEmptyTitle** method, which returns the IDs of the RFQ cases that have empty titles.</span></span>

```xpp
private container findRFQCasesWithEmptyTitle() 
{ 
    container result; 

    PurchRFQCaseTable rfqCase; 
    while select RFQCaseId from rfqCase 
        where rfqCase.Name == '' 
    { 
        result += rfqCase.RFQCaseId; 
    } 
    
    return result; 
} 
```

<span data-ttu-id="0efcc-126">Két további módszer, amelyet implementálni kell, az **opportunityTitle** és az **opportunityDetails**.</span><span class="sxs-lookup"><span data-stu-id="0efcc-126">Two more methods that must be implemented are **opportunityTitle** and **opportunityDetails**.</span></span> <span data-ttu-id="0efcc-127">A korábbi egy a lehetőséghez tartozó rövid címet ad vissza, az utóbbi a lehetőség részletes leírását adja vissza, amely adatokat is tartalmazhat.</span><span class="sxs-lookup"><span data-stu-id="0efcc-127">The former returns a short title for the opportunity, the latter returns a detailed description of the opportunity, which can also include data.</span></span>

<span data-ttu-id="0efcc-128">A **opportunityTitle** által visszaadott cím az **Optimalizálási lehetőség** oszlopban jelenik az **Optimalizálási tanácsadó** munkaterületen.</span><span class="sxs-lookup"><span data-stu-id="0efcc-128">The title returned by **opportunityTitle** appears under the **Optimization opportunity** column in the **Optimization advisor** workspace.</span></span> <span data-ttu-id="0efcc-129">Emellett az oldalsó panel fejléceként is megjelenik, és a lehetőséggel kapcsolatos további információkat jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="0efcc-129">It also appears as the header of the side pane showing more information about the opportunity.</span></span> <span data-ttu-id="0efcc-130">Megegyezés alapján ez a metódus el van látva a **DiagnosticRuleSubscription** attribútummal, amely a következő argumentumokat veszi fel:</span><span class="sxs-lookup"><span data-stu-id="0efcc-130">By convention, this method is decorated with the **DiagnosticRuleSubscription** attribute, which takes the following arguments:</span></span> 

* <span data-ttu-id="0efcc-131">**Diagnosztikai terület** – egy **DiagnosticArea** típusú felsorolás, amely leírja, az alkalmazás mely területéhez tartozik a szabály, mint például **DiagnosticArea::SCM**.</span><span class="sxs-lookup"><span data-stu-id="0efcc-131">**Diagnostic area** – An enum of type **DiagnosticArea** that describes what area of the application the rule belongs to, such as **DiagnosticArea::SCM**.</span></span> 

* <span data-ttu-id="0efcc-132">**Szabály neve** – karakterlánc a szabály nevével.</span><span class="sxs-lookup"><span data-stu-id="0efcc-132">**Rule name** – A string with the rule name.</span></span> <span data-ttu-id="0efcc-133">Ez a **Szabály neve** oszlopban jelenik meg a **Diagnosztikai ellenőrzési szabály** képernyőn (**DiagnosticsValidationRuleMaintain**).</span><span class="sxs-lookup"><span data-stu-id="0efcc-133">This will appear under the **Rule name** column in the **Dianostics validation rule** form (**DiagnosticsValidationRuleMaintain**).</span></span> 

* <span data-ttu-id="0efcc-134">**Futtatás gyakorisága** – egy **DiagnosticRunFrequency** típusú felsorolás, amely leírja, hogy milyen gyakran fusson a szabály, például: **DiagnosticRunFrequency::Daily**.</span><span class="sxs-lookup"><span data-stu-id="0efcc-134">**Run frequency** – An enum of type **DiagnosticRunFrequency** that describes how often the rule should be run, such as **DiagnosticRunFrequency::Daily**.</span></span> 

* <span data-ttu-id="0efcc-135">**Szabály leírása** – karakterlánc a szabály részletesebb leírásával.</span><span class="sxs-lookup"><span data-stu-id="0efcc-135">**Rule description** – A string with a more detailed description of the rule.</span></span> <span data-ttu-id="0efcc-136">Ez a **Szabály leírása** oszlopban jelenik meg a **Diagnosztikai ellenőrzési szabály** képernyőn (**DiagnosticsValidationRuleMaintain**).</span><span class="sxs-lookup"><span data-stu-id="0efcc-136">This will appear under the **Rule description** column in the **Dianostics validation rule** form (**DiagnosticsValidationRuleMaintain**).</span></span> 

> [!NOTE]
> <span data-ttu-id="0efcc-137">A **DiagnosticRuleSubscription** attribútum szükséges a szabály működéséhez.</span><span class="sxs-lookup"><span data-stu-id="0efcc-137">The **DiagnosticRuleSubscription** attribute is required for the rule to work.</span></span> <span data-ttu-id="0efcc-138">Általában az **opportunityTitle** révén használatos, de az osztály bármely metódusához hozzárendelhető.</span><span class="sxs-lookup"><span data-stu-id="0efcc-138">Typically, it is used on **opportunityTitle**, but it can decorate any method of the class.</span></span>

<span data-ttu-id="0efcc-139">Egy példa az implementálásra a következő.</span><span class="sxs-lookup"><span data-stu-id="0efcc-139">The following is an example implementation.</span></span> <span data-ttu-id="0efcc-140">Az egyszerűség kedvéért nyers karakterláncokat használunk, de a megfelelő implementáláshoz címkék szükségesek.</span><span class="sxs-lookup"><span data-stu-id="0efcc-140">Raw strings are used for simplicity, but a correct implementation requires labels.</span></span> 

```xpp
[DiagnosticsRuleSubscription(DiagnosticsArea::SCM, 
                             'Assign titles to Request for Quotation cases', 
                             DiagnosticsRunFrequency::Daily,  
                             'This rule detects Requests for Quotation with empty titles.')] 
public str opportunityTitle() 
{ 
    return 'Assign titles to Request for Quotation cases'; 
} 
```

<span data-ttu-id="0efcc-141">Az **opportunityDetails** által visszaadott leírás megjelenik az oldalsó panelen, és további információkat jelenít meg a lehetőséggel kapcsolatosan.</span><span class="sxs-lookup"><span data-stu-id="0efcc-141">The description returned by **opportunityDetails** appears on the side pane showing more information about the opportunity.</span></span> <span data-ttu-id="0efcc-142">Ez a **SelfHealingOpportunity** argumentumot veszi fel, amely egy **Adatok** mező, amely használható a lehetőségre vonatkozó további információk megadásához.</span><span class="sxs-lookup"><span data-stu-id="0efcc-142">This takes the **SelfHealingOpportunity** argument, which is **Data** field that can be used to provide more details about the opportunity.</span></span> <span data-ttu-id="0efcc-143">Ebben a példában a metódus az üres címmel rendelkező ajánlatkérési esetek azonosítóját adja vissza.</span><span class="sxs-lookup"><span data-stu-id="0efcc-143">In the example, the method returns the IDs of the RFQ cases with an empty title.</span></span> 

```xpp
public str opportunityDetails(SelfHealingOpportunity _opportunity) 
{ 
    str details = ''; 
    container opportunityData = _opportunity.Data; 
    int affectedRFQCasesCount = conLen(opportunityData); 

    if (affectedRFQCasesCount != 0) 
    { 
        details = 'The following Request for Quotation cases have an empty title:\n'; 
        for (int i = 1; i <= affectedRFQCasesCount ; i++) 
        { 
            PurchRFQCaseId rfqCaseId = conPeek(opportunityData, i); 
            details += rfqCaseId + '\n'; 
        } 
    } 

    return details; 
}
```

<span data-ttu-id="0efcc-144">A fennmaradó kettő implementálandó absztrakt metódus a **provideHealingAction** és a **securityMenuItem**.</span><span class="sxs-lookup"><span data-stu-id="0efcc-144">The two remaining abstract methods to implement are **provideHealingAction** and **securityMenuItem**.</span></span> 

<span data-ttu-id="0efcc-145">A **provideHealingAction** IGAZ értéket ad vissza gyógyító művelet esetén, ellenkező esetben az eredmény HAMIS.</span><span class="sxs-lookup"><span data-stu-id="0efcc-145">**provideHealingAction** returns true if a healing action is provided, otherwise, it returns false.</span></span> <span data-ttu-id="0efcc-146">Ha az eredmény IGAZ, a **performAction** metódust kell implementálni, vagy hiba történik.</span><span class="sxs-lookup"><span data-stu-id="0efcc-146">If true is returned, the method **performAction** must be implemented, or an error will be thrown.</span></span> <span data-ttu-id="0efcc-147">A **performAction** metódus **SelfHealingOpportunity** argumentumot vesz fel, amelyben az adatok felhasználhatók a művelethez.</span><span class="sxs-lookup"><span data-stu-id="0efcc-147">The **performAction** method takes a **SelfHealingOpportunity** argument, in which the data can be used for the action.</span></span> <span data-ttu-id="0efcc-148">Ebben a példában a művelet megnyitja a **PurchRFQCaseTableListPage** elemet kézi javításhoz.</span><span class="sxs-lookup"><span data-stu-id="0efcc-148">In the example, the action opens the **PurchRFQCaseTableListPage**, for manual correction.</span></span> 

```xpp
public boolean providesHealingAction() 
{ 
    return true; 
} 

protected void performAction(SelfHealingOpportunity _opportunity) 
{ 
    new MenuFunction(menuItemDisplayStr(PurchRFQCaseTableListPage), MenuItemType::Display).run(); 
} 
```

<span data-ttu-id="0efcc-149">A szabály jellemzőitől függően lehetséges lehet automatikus műveletet végrehajtani a lehetőség adataival.</span><span class="sxs-lookup"><span data-stu-id="0efcc-149">Depending on the specifics of the rule, it might be possible to take an automatic action using the opportunity data.</span></span> <span data-ttu-id="0efcc-150">Ebben a példában a rendszer automatikusan címeket hozhatna létre az ajánlatkérési esetekhez.</span><span class="sxs-lookup"><span data-stu-id="0efcc-150">In this example, the system could generate titles for RFQ cases automatically.</span></span> 

<span data-ttu-id="0efcc-151">A **securityMenuItem** egy műveleti menüpont nevét adja vissza, úgy, hogy a szabály csak azoknak a felhasználóknak látható, akik hozzáférhetnek a műveleti menüponthoz.</span><span class="sxs-lookup"><span data-stu-id="0efcc-151">**securityMenuItem** returns the name of an action menu item such that the rule is only visible to users who can access the action menu item.</span></span> <span data-ttu-id="0efcc-152">A biztonság megkövetelheti, hogy konkrét szabályok és lehetőségek csak az engedélyezett felhasználók számára legyenek elérhetők.</span><span class="sxs-lookup"><span data-stu-id="0efcc-152">Security might require that specific rules and opportunities are accessible only to authorized users.</span></span> <span data-ttu-id="0efcc-153">Ebben a példában csak a **PurchRFQCaseTitleAction** elemhez hozzáféréssel rendelkező felhasználók tekinthetik meg a lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0efcc-153">In the example, only users with access to **PurchRFQCaseTitleAction** can view the opportunity.</span></span> <span data-ttu-id="0efcc-154">Figyelje meg, hogy ez a műveleti menüpont ehhez a példához készült, és belépési pontként lett hozzáadva a **PurchRFQCaseTableMaintain** biztonsági jogosultsághoz.</span><span class="sxs-lookup"><span data-stu-id="0efcc-154">Notice that this action menu item was created for this example, and was added as an entry point for the **PurchRFQCaseTableMaintain** security privilege.</span></span> 

> [!NOTE]
> <span data-ttu-id="0efcc-155">A menüelemnek műveleti menüelemnek kell lennie a biztonságnál a helyes működéshez.</span><span class="sxs-lookup"><span data-stu-id="0efcc-155">The menu item must be an action menu item for security to work correctly.</span></span> <span data-ttu-id="0efcc-156">Az egyéb menüelemtípusok, például a **megjelenítendő menüelemek**, nem működnek megfelelően.</span><span class="sxs-lookup"><span data-stu-id="0efcc-156">Other menu item types, such as **Display menu items** will not work correctly.</span></span>

```xpp
public MenuName securityMenuItem() 
{ 
    return menuItemActionStr(PurchRFQCaseTitleAction); 
}
```

<span data-ttu-id="0efcc-157">A szabály lefordítása után hajtsa végre a következő feladatot, hogy megjelenjen a felhasználói felületen (UI).</span><span class="sxs-lookup"><span data-stu-id="0efcc-157">After the rule has compiled, execute the following job to have it display in the user interface (UI).</span></span>

```xpp
class ScanNewRulesJob 
{         
    public static void main(Args _args) 
    {         
        SysExtensionCache::clearAllScopes(); 
        var controller = new DiagnosticsRuleController(); 
        controller.runOperation(); 
    } 
} 
```

<span data-ttu-id="0efcc-158">A szabály megjelenik a **Diagnosztikai ellenőrzési szabály** képernyőn, amely a **Rendszerfelügyelet** > **Időszakos feladatok** > **Diagnosztikai ellenőrzési szabály karbantartása** elemnél elérhető.</span><span class="sxs-lookup"><span data-stu-id="0efcc-158">The rule will display in the **Diagnostics validation rule** form, available from **System administration** > **Periodic tasks** > **Maintain diagnostics validation rule**.</span></span> <span data-ttu-id="0efcc-159">Az értékeléséhez lépjen a **Rendszerfelügyelet** > **Időszakos feladatok** > **Diagnosztikai ellenőrzési szabály ütemezése** elemre, és válassza ki a szabály gyakoriságát, például: **Napi**.</span><span class="sxs-lookup"><span data-stu-id="0efcc-159">To have it evaluated, go to **System administration** > **Periodic tasks** > **Schedule diagnostics validation rule**, select the frequency of the rule, such as **Daily**.</span></span> <span data-ttu-id="0efcc-160">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="0efcc-160">Click **OK**.</span></span> <span data-ttu-id="0efcc-161">Lépjen a **Rendszerfelügyelet** > **Optimalizálási tanácsadó** elemre az új lehetőség megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="0efcc-161">Go to **System administration** > **Optimization advisor** to view the new opportunity.</span></span> 

<span data-ttu-id="0efcc-162">A következő példa egy kódrészlet egy olyan szabály vázlatával, amely tartalmaz minden kötelező módszert és attribútumot.</span><span class="sxs-lookup"><span data-stu-id="0efcc-162">The following example is a code snippet with the skeleton of a rule including all the required methods and attributes.</span></span> <span data-ttu-id="0efcc-163">Segít a kezdő lépésekben az új szabályok elkészítése során.</span><span class="sxs-lookup"><span data-stu-id="0efcc-163">It helps you get started with writing new rules.</span></span><span data-ttu-id="0efcc-164"> A példában használt címkék és műveleti menüelemek csak bemutató célt szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="0efcc-164"> The labels and action menu items that are used in the example are only used for demonstration purpose.</span></span>

```xpp
[DiagnosticsRuleAttribute]
public final class SkeletonSelfHealingRule extends SelfHealingRule implements IDiagnosticsRule
{
    [DiagnosticsRuleSubscription(DiagnosticsArea::SCM,
                                 "@SkeletonRuleLabels:SkeletonRuleTitle", // Label with the title of the rule
                                 DiagnosticsRunFrequency::Monthly,
                                 "@SkeletonRuleLabels:SkeletonRuleDescription")] // Label with a description of the rule
    public str opportunityTitle()
    {
        // Return a label with the title of the opportunity
        return "@SkeletonRuleLabels:SkeletonOpportunityTitle";
    }

    public str opportunityDetails(SelfHealingOpportunity _opportunity)
    {
        str details = "";

        // Use _opportunity.data to provide details on the opportunity

        return details;
    }

    protected List evaluate()
    {
        List results = new List(Types::Record);

        // Write here the core logic of the rule

        // When creating an opportunity, use:
        //     * this.getOpportunityForCompany() for company specific opportunities
        //     * this.getOpportunityAcrossCompanies() for cross-company opportunities

        return results;
    }

    public boolean providesHealingAction()
    {
        return true;
    }

    protected void performAction(SelfHealingOpportunity _opportunity)
    {
        // Place here the code that performs the healing action

        // To open a form, use the following:
        // new MenuFunction(menuItemDisplayStr(SkeletonRuleDisplayMenuItem), MenuItemType::Display).run();
    }

    public MenuName securityMenuItem()
    {
        return menuItemActionStr(SkeletonRuleActionMenuItem);
    }

}
```

<span data-ttu-id="0efcc-165">További információért tekintse meg a rövid YouTube videót: [Optimalizálási tanácsadóa Dynamics 365 for Finance and Operations szolgáltatásban](https://www.youtube.com/watch?v=MRsAzgFCUSQ)</span><span class="sxs-lookup"><span data-stu-id="0efcc-165">For more information, watch the short YouTube video: [Optimization advisor in Dynamics 365 for Finance and Operations](https://www.youtube.com/watch?v=MRsAzgFCUSQ)</span></span>
