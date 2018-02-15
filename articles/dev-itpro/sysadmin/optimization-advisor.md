---
title: "Optimalizálási tanácsadó szabályainak létrehozása"
description: "Ez a témakör ismerteti az új szabályok hozzáadását az Optimalizálási tanácsadóhoz."
author: roxanadiaconu
manager: AnnBe
ms.date: 01/23/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SelfHealingWorkspace
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core (Operations, Core)
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: roxanad
ms.search.validFrom: 2017-12-01
ms.dyn365.ops.version: 7.3
ms.translationtype: HT
ms.sourcegitcommit: 9cb9343028acacc387370e1cdd2202b84919185e
ms.openlocfilehash: 88739298405343a36ae5bc11f51c666c414e7157
ms.contentlocale: hu-hu
ms.lasthandoff: 01/23/2018

---

# <a name="create-rules-for-optimization-advisor"></a>Optimalizálási tanácsadó szabályainak létrehozása

[!include[banner](../includes/banner.md)]

Ez a témakör elmagyarázza, hogyan hozhatók létre új szabályok az **Optimalizálási tanácsadóhoz**. Például létrehozhat egy új szabályt, amely azonosítja, melyik ajánlatkérési esetek címe üres. Címek az eseteken történő használata könnyen azonosíthatóvá és kereshetővé teszi őket. Bár nagyon egyszerű, az alábbi példa bemutatja, mit lehet elérni optimalizálási szabályokkal. 

A *szabály* egy ellenőrzés az alkalmazásadatokon. Ha teljesül a feltétel, amelyet a szabály értékel, lehetőség nyílik folyamatok optimalizálására vagy adatok javítására. Ezek a lehetőségek kihasználhatók, és opcionálisan mérhető az intézkedések hatása. 

Új szabály létrehozásához az **Optimalizálási tanácsadó** részére adjon hozzá egy új osztályt, amely bővíti a **SelfHealingRule** absztrakt osztályt, implementálja az **IDiagnosticsRule** interfészt, és fel van szerelve a **DiagnosticRule** attribútummal. Az osztálynak olyan metódussal is kell rendelkeznie, amelynél megvan a **DiagnosticsRuleSubscription** attribútum. Megegyezés alapján ez az **opportunityTitle** metódus révén történik, amelyet később tárgyalunk. Ez az új osztály hozzáadható egy egyéni modellhez, amely a **SelfHealingRules** modelltől függ. A következő példában az implementált szabály neve **RFQTitleSelfHealingRule**.

```
[DiagnosticsRule] 
public final class RFQTitleSelfHealingRule extends SelfHealingRule implements IDiagnosticsRule 
{ 
… 
} 
```

A **SelfHealingRule** absztrakt osztályhoz absztrakt metódusok tartoznak amelyeket öröklő osztályokban kell implementálni. Az alapvető az **evaluate** metódus, amely a szabály által azonosított lehetőségek listáját adja vissza. A lehetőségek lehetnek jogi személyenként vagy az egész rendszeren alkalmazhatók.

```
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

```
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

```
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

```
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

```
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

```
public MenuName securityMenuItem() 
{ 
    return menuItemActionStr(PurchRFQCaseTitleAction); 
}
```

A szabály lefordítása után hajtsa végre a következő feladatot, hogy megjelenjen a felhasználói felületen (UI).

```
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

További információért tekintse meg a rövid YouTube-videót:

> [!Video https://www.youtube.com/embed/MRsAzgFCUSQ]
