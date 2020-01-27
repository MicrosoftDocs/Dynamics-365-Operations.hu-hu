---
title: A Dynamics 365 Talent új vagy módosult elemei (2019. július 16.)
description: Ez a témakör a Microsoft Dynamics 365 Talent új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 07/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-07-16
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 6dce39bc529bf6dd6079ed900af12510c0773f9a
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/06/2019
ms.locfileid: "2899082"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-july-16-2019"></a>A Dynamics 365 Talent új vagy módosult elemei (2019. július 16.)

Ez a témakör a Microsoft Dynamics 365 Talent új vagy módosított szolgáltatásait írja le.

## <a name="changes-in-attract"></a>Változások az Attract-ben
A kiadás a Dynamics 365 Talent: Attract apró hibáinak javításait is tartalmazza.

### <a name="coming-soon-in-attract"></a>Hamarosan az Attract alkalmazásban
#### <a name="job-approvals-appear-on-the-home-page"></a>A feladatok jóváhagyása megjelenik a kezdőképernyőn

A jóváhagyások az irányítópult **Jóváhagyások** szakaszában jelennek meg. A jóváhagyók megtekinthetik a rájuk váró jóváhagyásokat az **Önhöz rendelt** részen, ahol látható a feladat azonosítója és neve, a többi jóváhagyó és a feladat hozzárendelésének dátuma. Azok a felhasználók, akik elküldenek jóváhagyásra egy feladatot, az **Ön által küldött kérések** szakaszban látják a feladatot, ahol megjelennek azok a jóváhagyók, akiknek még jóvá kell hagyniuk a feladatot.

## <a name="changes-in-onboard"></a>Változások az Onboard alkalmazásban
A kiadás a Dynamics 365 Talent: Onboard apró hibáinak javításait is tartalmazza.

## <a name="changes-in-core-hr"></a>A Core HR módosításai
A szakaszban ismertetett módosítások a 8.1.2390-ös buildre vonatkoznak.

### <a name="common-data-service-entities-that-now-support-custom-fields"></a>Common Data Service-entitások, melyek támogatják az egyéni mezőket

- BusinessProcessCalendar                     
- BusinessProcessGroupAssignment         
- BusinessProcessStage                          
- BusinessProcessTemplateHeader          
- BusinessProcessTemplateTask            
- HcmBenefitOption                              
- HcmBenefitType                                  
- HcmCompensationGrid                            
- HcmCompensationLevel                          
- HcmCompensationPayFrequency                 
- HcmCompensationReferencePointSetup        
- HcmCompensationReferencePointSetupLine 
- HcmCompensationRegion                     
- HcmCompFixedPlanTable                     
- HcmEmployment                                
- HcmEthnicOrigin                                
- HcmFixedCompensationEvent                 
- HcmJob                                           
- HcmJobFunction
- HcmJobType
- HcmLanguageCode
- HcmPayrollCalculationFrequency
- HcmPosition
- HcmPositionType
- HcmSkillType
- HcmVeteranStatus
- HcmWorkCalendarHoliday
- HcmWorkCalendarHolidayLine
- HcmWorker
- HcmWorkerPersonalDetail
- LeaveType
- OMDepartment
- OMLegalEntity
- PayCycle
- PayPeriod
- PayrollBenefitCalculationRate
- PayrollBenefitCalculationRateDetail
- PayrollEarningCode

### <a name="unable-to-see-goals-and-reviews-in-manager-self-service"></a>Nem lehet megtekinteni a célokat és a véleményeket a vezetői önkiszolgáló szolgáltatásban

Az e heti változtatások lehetővé teszik a célok megjelenítését és szerkesztését a szintet váltó vezetők részére az önkiszolgáló szolgáltatásban.

### <a name="goal-form-cannot-be-closed-after-a-user-edits-any-goal-field"></a>A célképernyőt nem lehet bezárni, miután egy felhasználó szerkeszt egy célmezőt

Ez a kiadás kijavítja azt a hibát, hogy a célképernyő nem záródik be a **Bezárás** pont kiválasztásakor.

### <a name="creating-new-goals-and-saving-displays-error"></a>Új célok létrehozása és mentése esetén hibaüzenet jelenik meg

Ez a kiadás kijavít egy hibát, amikor a célkitűzéseket mentik az alkalmazotti és a vezetői önkiszolgáló szolgáltatásban.

### <a name="unable-to-add-a-field-to-position-details"></a>Nem adható hozzá mező a beosztás részleteihez 

Ebben a verzióban az egyéni mezők most már támogatottak a beosztás részleteinél.
 
### <a name="unable-to-set-up-expiring-date-on-the-earning-code-through-data-management"></a>Nem állítható be lejárati dátum a bevételkódnál az adatkezelés során

A módosítások most lehetővé teszik a bevételkódok lejárati dátumának beállítását az adatkezelésnél.

### <a name="new-custom-fields-dont-sync-quickly-enough"></a>Az új egyéni mezők nem szinkronizálnak elég gyorsan

Az egyéni mező Common Data Service szolgáltatással való szinkronizálásának teljesítménye javult az e heti kiadással.

### <a name="entity-export-to-database-jobs-fail-with-error-message-format-of-the-initialization-string-does-not-conform-to-specification-starting-at-index-0"></a>Az entitásexportálás adatbázis-feladatainál a következő hibaüzenet jelenik meg: „Az inicializálás karakterlánc-formátuma nem egyezik meg a 0. indexben kezdődő specifikációval”.

Ez a kiadás kijavítja azt a hibát, amely miatt az kötegelt adatbázis-feladatok sikertelenek. A manuális frissítéshez:

1. Menjen az **Adatkezelés** lehetőségre.
2. Válassza az **Adatbázisba történő entitásexportálás beállítása** elemet.
3. Adja meg újra a kapcsolati karakterláncot a cél-adatbázishoz, majd válassza a **Mentés** parancsot.

### <a name="smtp-email-configuration-suddenly-fails-with-error-message-the-smtp-server-requires-a-secure-connection-or-the-client-was-not-authenticated"></a>Az SMTP-email-konfiguráció hirtelen leáll, és a következő hibaüzenet jelenik meg: „Az SMTP-kiszolgálónak biztonságos kapcsolatra van szüksége, vagy az ügyfél nem volt hitelesítve.”

Ez a kiadás kijavítja az egyik SMTP e-mail-konfigurációt, amelyik hirtelen hibát jelez. A manuális frissítéshez:

1. Lépjen a **Rendszerfelügyelet** ponthoz.
2. Válassza az **E-mail paraméterek** lehetőséget.
3. Válassza az **SMTP-beállítások** lehetőséget. 
4. Írja be újra az SMTP-kiszolgálóhoz tartozó felhasználónevet és jelszót, majd válassza a **Mentés** parancsot.

## <a name="in-preview"></a>Előnézetben

### <a name="preview-features-are-enabled-only-in-sandbox-instances"></a>Az előnézeti szolgáltatások csak a védőfalpéldányokban engedélyezettek

Amikor új Talent-példányt hoz létre, megadhatja, hogy a példány **Termelési** vagy **Védőfal** típusú legyen-e. A **Védőfal** típusú példányokkal az új szolgáltatások korai tesztelése végezhető el. Minden létező Talent példányt a **Termelési** példány típusára lesz frissítve. Ha a meglévő példányokat **Védőfal** típusúra szeretné frissíteni, kérje az [ügyfélszolgálat](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) segítségét.

További információ a módosítások közzétételéről: [A Talent létesítése](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

### <a name="restrict-leave-types-in-time-off-requests"></a>A szabadság típusának korlátozása a távolléti kérelmekben

A szervezetek számos különböző típusú szabadságot tudnak nyújtani az alkalmazottak számára. Előfordulhat azonban, hogy egyes szabadságtípusok esetében nem megfelelő megoldás, hogy az alkalmazottak küldjenek be távolléti kérelmet. Lehetséges, hogy ezeket a szabadságtípusokat a HR kezeli. Ebben a kiadásban konfigurálhatja, hogy az alkalmazottak milyen szabadságtípusokhoz küldhetnek távolléti kérelmet. 

### <a name="view-performance-information-for-direct-and-extended-reports-in-manager-self-service"></a>A közvetlen és bővített jelentések teljesítményadatainak megtekintése az önkiszolgáló kezelői rendszerben

Egy új beállítással a vezetők mind a közvetlen beosztottak, mind a közvetett beosztottak teljesítményét megtekinthetik. Jelenleg a közvetlen felettesek hozzárendelhetnek teljesítménycélokat és frissíthetik őket, illetve olyan új értékeléseket adhatnak ki. Ezenkívül a közvetlen felettesek és alkalmazottaik karbantarthatják és frissíthetik a teljesítménymutatókat, így megbizonyosodhatnak róla, hogy a teljesítmény ellenőrzési folyamata gördülékenyen megy majd. A módosítás végrehajtásakor a vezetők a közvetlen beosztottakon kívül a bővített jelentések teljesítménnyel kapcsolatos adatait is megtekinthetik és karbantartják.
