---
title: Optimalizálási tanácsadó szabályainak létrehozása
description: Ez a témakör ismerteti az új szabályok hozzáadását az Optimalizálási tanácsadóhoz.
author: roxanadiaconu
ms.date: 02/04/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SelfHealingWorkspace
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: sericks
ms.search.validFrom: 2017-12-01
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: d2a0d6d2e70bfb797de919b536fa1ca62fd181a8
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746001"
---
# <a name="create-rules-for-optimization-advisor"></a>Optimalizálási tanácsadó szabályainak létrehozása

[!include [banner](../includes/banner.md)]

Ez a témakör elmagyarázza, hogyan hozhatók létre új szabályok az **Optimalizálási tanácsadóhoz**. Például létrehozhat egy új szabályt, amely azonosítja, melyik ajánlatkérési esetek címe üres. Címek az eseteken történő használata könnyen azonosíthatóvá és kereshetővé teszi őket. Bár nagyon egyszerű, az alábbi példa bemutatja, mit lehet elérni optimalizálási szabályokkal. 

A *szabály* egy ellenőrzés az alkalmazásadatokon. Ha teljesül a feltétel, amelyet a szabály értékel, lehetőség nyílik folyamatok optimalizálására vagy adatok javítására. Ezek a lehetőségek kihasználhatók, és opcionálisan mérhető az intézkedések hatása. 

Új szabály létrehozásához az **Optimalizálási tanácsadó** részére adjon hozzá egy új osztályt, amely bővíti a **SelfHealingRule** absztrakt osztályt, implementálja az **IDiagnosticsRule** interfészt, és fel van szerelve a **DiagnosticRule** attribútummal. Az osztálynak olyan metódussal is kell rendelkeznie, amelynél megvan a **DiagnosticsRuleSubscription** attribútum. Megegyezés alapján ez az **opportunityTitle** metódus révén történik, amelyet később tárgyalunk. Ez az új osztály hozzáadható egy egyéni modellhez, amely a **SelfHealingRules** modelltől függ. A következő példában az implementált szabály neve **RFQTitleSelfHealingRule**.

```xpp
[DiagnosticsRule] 
public final class RFQTitleSelfHealingRule extends SelfHealingRule implements IDiagnosticsRule 
{ 
… 
} 
```

A **SelfHealingRule** absztrakt osztályhoz absztrakt metódusok tartoznak amelyeket öröklő osztályokban kell implementálni. Az alapvető az **evaluate** metódus, amely a szabály által azonosított lehetőségek listáját adja vissza. A lehetőségek lehetnek jogi személyenként vagy az egész rendszeren alkalmazhatók.

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

A fenti metódus ciklust hajt végre vállalatokon keresztül és kiválasztja azokat az ajánlatkérési eseteket, amelyek címei üresek a  **findRFQCasesWithEmptyTitle** metódusban. Ha legalább egy ilyen eset található, akkor létrejön egy vállalatfüggő lehetőség a **getOpportunityForCompany** metódussal. Figyelje meg, hogy a **Data** mező a **SelfHealingOpportunity** táblában **Tároló** típusú, tehát az adott szabályban megadott logikával kapolatos bármilyen adatot tartalmazhat. Az **OpportunityDate** beállítása az aktuális időbélyegzővel rögzíti a lehetőség legutóbbi értékelésének időpontját.  

A lehetőségek több vállalatot is érinthetnek. Ebben az esetben nincs szükség vállalatokon keresztüli ciklusra, és a lehetőséget a **getOpportunityAcrossCompanies** metódussal kell létrehozni. 

A következő kód a **findRFQCasesWithEmptyTitle** metódust mutatja, amely az üres címekkel rendelkező ajánlatkérési esetek azonosítóját adja vissza.

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

Két további módszer, amelyet implementálni kell, az **opportunityTitle** és az **opportunityDetails**. A korábbi egy a lehetőséghez tartozó rövid címet ad vissza, az utóbbi a lehetőség részletes leírását adja vissza, amely adatokat is tartalmazhat.

A **opportunityTitle** által visszaadott cím az **Optimalizálási lehetőség** oszlopban jelenik az **Optimalizálási tanácsadó** munkaterületen. Emellett az oldalsó panel fejléceként is megjelenik, és a lehetőséggel kapcsolatos további információkat jelenít meg. Megegyezés alapján ez a metódus el van látva a **DiagnosticRuleSubscription** attribútummal, amely a következő argumentumokat veszi fel: 

* **Diagnosztikai terület** – egy **DiagnosticArea** típusú felsorolás, amely leírja, az alkalmazás mely területéhez tartozik a szabály, mint például **DiagnosticArea::SCM**. 

* **Szabály neve** – karakterlánc a szabály nevével. Ez a **Szabály neve** oszlopban jelenik meg a **Diagnosztikai ellenőrzési szabály** képernyőn (**DiagnosticsValidationRuleMaintain**). 

* **Futtatás gyakorisága** – egy **DiagnosticRunFrequency** típusú felsorolás, amely leírja, hogy milyen gyakran fusson a szabály, például: **DiagnosticRunFrequency::Daily**. 

* **Szabály leírása** – karakterlánc a szabály részletesebb leírásával. Ez a **Szabály leírása** oszlopban jelenik meg a **Diagnosztikai ellenőrzési szabály** képernyőn (**DiagnosticsValidationRuleMaintain**). 

> [!NOTE]
> A **DiagnosticRuleSubscription** attribútum szükséges a szabály működéséhez. Általában az **opportunityTitle** révén használatos, de az osztály bármely metódusához hozzárendelhető.

Egy példa az implementálásra a következő. Az egyszerűség kedvéért nyers karakterláncokat használunk, de a megfelelő implementáláshoz címkék szükségesek. 

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

Az **opportunityDetails** által visszaadott leírás megjelenik az oldalsó panelen, és további információkat jelenít meg a lehetőséggel kapcsolatosan. Ez a **SelfHealingOpportunity** argumentumot veszi fel, amely egy **Adatok** mező, amely használható a lehetőségre vonatkozó további információk megadásához. Ebben a példában a metódus az üres címmel rendelkező ajánlatkérési esetek azonosítóját adja vissza. 

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

A fennmaradó kettő implementálandó absztrakt metódus a **provideHealingAction** és a **securityMenuItem**. 

A **provideHealingAction** IGAZ értéket ad vissza gyógyító művelet esetén, ellenkező esetben az eredmény HAMIS. Ha az eredmény IGAZ, a **performAction** metódust kell implementálni, vagy hiba történik. A **performAction** metódus **SelfHealingOpportunity** argumentumot vesz fel, amelyben az adatok felhasználhatók a művelethez. Ebben a példában a művelet megnyitja a **PurchRFQCaseTableListPage** elemet kézi javításhoz. 

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

A szabály jellemzőitől függően lehetséges lehet automatikus műveletet végrehajtani a lehetőség adataival. Ebben a példában a rendszer automatikusan címeket hozhatna létre az ajánlatkérési esetekhez. 

A **securityMenuItem** egy műveleti menüpont nevét adja vissza, úgy, hogy a szabály csak azoknak a felhasználóknak látható, akik hozzáférhetnek a műveleti menüponthoz. A biztonság megkövetelheti, hogy konkrét szabályok és lehetőségek csak az engedélyezett felhasználók számára legyenek elérhetők. Ebben a példában csak a **PurchRFQCaseTitleAction** elemhez hozzáféréssel rendelkező felhasználók tekinthetik meg a lehetőséget. Figyelje meg, hogy ez a műveleti menüpont ehhez a példához készült, és belépési pontként lett hozzáadva a **PurchRFQCaseTableMaintain** biztonsági jogosultsághoz. 

> [!NOTE]
> A menüelemnek műveleti menüelemnek kell lennie a biztonságnál a helyes működéshez. Az egyéb menüelemtípusok, például a **megjelenítendő menüelemek**, nem működnek megfelelően.

```xpp
public MenuName securityMenuItem() 
{ 
    return menuItemActionStr(PurchRFQCaseTitleAction); 
}
```

A szabály lefordítása után hajtsa végre a következő feladatot, hogy megjelenjen a felhasználói felületen (UI).

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

A szabály megjelenik a **Diagnosztikai ellenőrzési szabály** képernyőn, amely a **Rendszerfelügyelet** > **Időszakos feladatok** > **Diagnosztikai ellenőrzési szabály karbantartása** elemnél elérhető. Az értékeléséhez lépjen a **Rendszerfelügyelet** > **Időszakos feladatok** > **Diagnosztikai ellenőrzési szabály ütemezése** elemre, és válassza ki a szabály gyakoriságát, például: **Napi**. Kattintson az **OK** gombra. Lépjen a **Rendszerfelügyelet** > **Optimalizálási tanácsadó** elemre az új lehetőség megtekintéséhez. 

A következő példa egy kódrészlet egy olyan szabály vázlatával, amely tartalmaz minden kötelező módszert és attribútumot. Segít a kezdő lépésekben az új szabályok elkészítése során. A példában használt címkék és műveleti menüelemek csak bemutató célt szolgálnak.

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

További információért tekintse meg a rövid YouTube videót: [Optimalizálási tanácsadóa Dynamics 365 for Finance and Operations szolgáltatásban](https://www.youtube.com/watch?v=MRsAzgFCUSQ)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]