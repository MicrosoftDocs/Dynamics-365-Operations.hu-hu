---
title: A Finance szolgáltatással való integráció konfigurálása
description: Ez a cikk a Dynamics 365 Human Resources Dynamics 365 Pénzügy és az integrációt írja le.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8be7cbf92c11036d334516116f0895c426380954
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8875858"
---
# <a name="configure-integration-with-finance"></a>A Finance szolgáltatással való integráció konfigurálása


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Ha integrálni Dynamics 365 Human Resources kell a Dynamics 365 Pénzügyet, az Adatintegrátor Emberi erőforrások – Pénzügy [sablont használhatja](/powerapps/administrator/data-integrator). A Human Resources to Finance sablon lehetővé teszi a feladatok, beosztások és dolgozók adatáramlását. A sablon lehetővé teszi, hogy az adatok a Human Resources alkalmazásból a Finance alkalmazásba áramoljanak de nem teszik lehetővé a Finance alkalmazásból a Human Resources alkalmazásba az áramlást.

![A Human Resources to Finance integrációs folyamata.](./media/hr-admin-integration-finance-flow.png)

A Human Resources to Finance megoldás a következő adatszinkronizálási típusokat tartalmazza:

- Feladatok karbantartása a Human Resources alkalmazásban, illetve azok szinkronizálása a Human Resources alkalmazásból a Finance alkalmazásba
- Beosztások és beosztás-hozzárendelések karbantartása a Human Resources alkalmazásban, illetve azok szinkronizálása a Human Resources alkalmazásból a Finance alkalmazásba
- Foglalkoztatások karbantartása a Human Resources alkalmazásban, illetve azok szinkronizálása a Human Resources alkalmazásból a Finance alkalmazásba
- A dolgozók és a dolgozók címeinek karbantartása a Human Resources alkalmazásban, illetve azok szinkronizálása a Human Resources alkalmazásból a Finance alkalmazásba

## <a name="system-requirements-for-human-resources"></a>A Human Resources rendszerkövetelményei

A Human Resources és a Finance következő verziói szükségesek az integrációs megoldáshoz: 

- Dynamics 365 Human Resources, helye: Dataverse
- Dynamics 365 Pénzügy - 7.2-es és újabb verzió

## <a name="template-and-tasks"></a>Sablon és feladatok

A Human Resources – Finance sablon elérése.

1. A [Power Apps Admin Center](https://admin.powerapps.com/)megnyitása. 

2. Válassza ki a **Projektek** lehetőséget, majd válassza az **Új projekt** lehetőséget jobb felső sarokban. Minden olyan jogi személyhez hozzon létre egy új projektet, amelyet integrálni kíván a Finance alkalmazásba.

3. Válassza ki a **Human Resources (Human Resources – Dataverse – Finance)** a rekordok szinkronizálásához a Human Resources irányából a Finance irányába.

A sablon a következő mögöttes tevékenységek használatával szinkronizál a Human Resources-rekordokat a Finance alkalmazásba.

- **A beosztás funkciójától a kompenzációs beosztási funkciókig**
- **Részlegek az üzemi egységhez**
- **Feladattípusok a kompenzációs feladattípushoz**
- **Feladatok a feladatokhoz**
- **Feladatok a Feladat részleteihez**
- **Beosztási típusok a Beosztási típushoz**
- **Feladatbeosztások az Alapbeosztásokhoz**
- **Feladatbeosztások a Beosztásrészletekhez**
- **Feladatbeosztások a Beosztásidőtartamokhoz**
- **Feladatbeosztások a Beosztási hierarchiákhoz**
- **Dolgozók a Dolgozóhoz**
- **Foglalkoztatások a Foglalkoztatáshoz**
- **Foglalkoztatások a Foglalkoztatás részleteihez**
- **Dolgozó beosztáshoz való hozzárendelése a Dolgozó beosztáshoz való hozzárendeléseihez**
- **Dolgozói címek a Dolgozó postai címéhez V2**

## <a name="template-mappings"></a>Sablonmegfeleltetések

A következő sablon-hozzárendelési táblákban a feladat neve tartalmazza az egyes alkalmazásokban használt entitásokat. A forrás (Human Resources) a bal oldalon van, a cél (Finance) pedig a jobb oldalon.

### <a name="job-functions-to-compensation-job-function"></a>A beosztás funkciójától a kompenzációs beosztási funkciókig

| Dataverse-tábla (forrás) | Finance-entitás (cél) |
|-------------------------------------|---------------------------------------------|
| cdm_name (cdm_Job   funkció neve)  | JOBFUNCTIONID   (JOBFUNCTIONID)            |
| cdm_description   (cdm_description) | LEÍRÁS   (LEÍRÁS)                 |

### <a name="departments-to-operating-unit"></a>Részlegek az üzemi egységhez

| Dataverse-tábla (forrás)           | Finance-entitás (cél) |
|-----------------------------------------------|---------------------------------------------|
| cdm_name (cdm_name)                           | NÉV (NÉV)                                 |
| cdm_departmentnumber   (cdm_departmentnumber) | OPERATINGUNITNUMBER   (OPERATINGUNITNUMBER) |
|                                               | OPERATINGUNITTYPE   (OPERATINGUNITTYPE)     |
| cdm_description   (cdm_description)           | NAMEALIAS   (NAMEALIAS)                     |

### <a name="job-types-to-compensation-job-type"></a>Feladattípusok a kompenzációs feladattípushoz

| Dataverse-tábla (forrás)   | Finance-entitás (cél) |
|---------------------------------------|---------------------------------------------|
| cdm_name (cdm_name)                   | JOBTYPEID   (JOBTYPEID)                     |
| cdm_description   (cdm_description)   | LEÍRÁS   (LEÍRÁS)                 |
| cdm_exemptstatus   (cdm_exemptstatus) | EXEMPTSTATUS   (EXEMPTSTATUS)               |

### <a name="jobs-to-jobs"></a>Feladatok a feladatokhoz

| Dataverse-tábla (forrás)                           | Finance-entitás (cél)           |
|---------------------------------------------------------------|-------------------------------------------------------|
| cdm_name (cdm_name)                                           | JOBID (JOBID)                                         |
| cdm_maximumnumberofpositions   (cdm_maximumnumberofpositions) | MAXIMUMNUMBEROFPOSITIONS   (MAXIMUMNUMBEROFPOSITIONS) |
| cdm_allowedunlimitedpositions   (cdm_allowunlimitedpositions) | ALLOWUNLIMITEDPOSITIONS   (ALLOWUNLIMITEDPOSITIONS)   |
| cdm_description   (cdm_description)                           | LEÍRÁS   (LEÍRÁS)                           |
| cdm_jobdescription   (cdm_jobdescription)                     | JOBDESCRIPTION   (JOBDESCRIPTIONS)                    |

### <a name="jobs-to-job-detail"></a>Feladatok a Feladat részleteihez

| Dataverse-tábla (forrás)                             | Finance-entitás (cél) |
|-----------------------------------------------------------------|---------------------------------------------|
| cdm_name (cdm_name)                                             | JOBID (JOBID)                               |
| cdm_jobtypeid. cdm_name   (Feladattípus (feladattípus neve))             | JOBTYPEID   (JOBTYPEID)                     |
| cdm_jobfunctionid. cdm_name   (Beosztás funkciója (beosztásfunkció neve)) | FUNCTIONID   (FUCNTIONID)                   |
| cdm_validfrom   (Érvényesség kezdete)                                    | VALIDFROM   (VALIDFROM)                     |
| cdm_validto (Érvényesség vége)                                        | VALIDTO (VALIDTO)                           |
| cdm_defaultfulltimeequivalent   (Alapértelmezett teljes munkaidős egyenérték)   | FULLTIMEEQUIVALENT   (FULLTIMEEQUIVALENT)   |

### <a name="position-types-to-position-type"></a>Beosztási típusok a Beosztási típushoz

| Dataverse-tábla (forrás)       | Finance-entitás (cél) |
|-------------------------------------------|---------------------------------------------|
| cdm_name (cdm_name)                       | POSITIONTYPEID   (POSITIONTYPEID)           |
| cdm_description   (cdm_description)       | LEÍRÁS   (LEÍRÁS)                 |
| cdm_classification   (cdm_classification) | OSZTÁLYOZÁS   (OSZTÁLYOZÁS)           |

### <a name="job-positions-to-base-position"></a>Feladatbeosztások az Alapbeosztásokhoz

| Dataverse-tábla (forrás)           | Finance-entitás (cél) |
|-----------------------------------------------|---------------------------------------------|
| cdm_jobpositionnumber   (Feladatbeosztás száma) | POSITIONID (POSITIONID)                      |

### <a name="job-positions-to-position-details"></a>Feladatbeosztások a Beosztásrészletekhez

| Dataverse-tábla (forrás)              | Finance-entitás (cél)       |
|--------------------------------------------------------------------------|---------------------------------------------------|
| cdm_jobpositionnumber  (Feladatbeosztás száma)                            | POSITIONID (POSITIONID)                             |
| cdm_jobid.cdm_name   (Feladat neve)                                        | JOBID (JOBID)                                    |
| cdm_description   (cdm_description)                                        | LEÍRÁS   (LEÍRÁS)                       |
| cdm_departmentid.cdm_departmentnumber   (Részleg (Részleg száma)) | DEPARTMENTNUMBER   (DEPARTMENTNUMBER)             |
| cdm_positiontypeid.cdm_name   (Beosztás típusa (név))                     | POSITIONTYPEID   (POSITIONTYPEID)                 |
| cdm_avaialableforassignment   (Elérhető hozzárendeléshez)                 | AVAILABLEFORASSIGNMENT   (AVAILABLEFORASSIGNMENT) |
| cdm_validfrom   (Érvényesség kezdete)                                            | VALIDFROM   (VALIDFROM)                           |
| cdm_validto (Érvényesség vége)                                                 | VALIDTO (VALIDTO)                               |
| cdm_fulltimeequivalent   (Teljes munkaidős egyenérték)                           | FULLTIMEEQUIVALENT   (FULLTIMEEQUIVALENT)         |

### <a name="job-positions-to-position-durations"></a>Feladatbeosztások a Beosztásidőtartamokhoz

| Dataverse-tábla (forrás)             | Finance-entitás (cél) |
|-------------------------------------------------|---------------------------------------------|
| cdm_jobpositionnumber   (Feladatbeosztás száma)   | POSITIONID (POSITIONID)                      |
| Számított   aktiválás (számított aktiválás) | VALIDFROM (VALIDFROM)                        |
| Számított   megszüntetés (számított megszüntetés) | VALIDTO (VALIDTO)                         |

### <a name="job-positions-to-position-hierarchies"></a>Feladatbeosztások a Beosztási hierarchiákhoz

| Dataverse-tábla (forrás)        | Finance-entitás (cél) |
|-----------------------------------------------------------------------------------------------|---------------------------------------------|
| cdm_jobpositionnumber   (Feladatbeosztás száma)                                                 | POSITIONID(POSITIONID)                      |
| cdm_parentjobpositionid.cdmjobpositionnumber   (cdm_parentjobpositionid.cdmjobpositionnumber) | PARENTPOSITIONID (PARENTPOSITIONID)         |
| cdm_validfrom   (Érvényesség kezdete)                                                                  | VALIDFROM   (VALIDFROM)                     |
| cdm_validto (Érvényesség   vége)                                                                      | VALIDTO (VALIDTO)                           |
| HIERARCHYTYPENAME   (HIERARCHYTYPENAME)                                                       | HIERARCHYTYPENAME   (HIERARCHYTYPENAME)     |


### <a name="workers-to-worker"></a>Dolgozók a Dolgozóhoz
| Dataverse-tábla (forrás)           | Finance-entitás (cél)       |
|-----------------------------------------------|---------------------------------------------------|
| cdm_birthdate   (cdm_birthdate)               | SZÜLETÉSI DÁTUM   (SZÜLETÉSI DÁTUM)                           |
| cdm_gender   (cdm_gender)                     | NEM (NEM)                                   |
| cdm_primaryaddress   (cdm_primaryaddress)     | PRIMARYCONTACTEMAIL   (PRIMARYCONTACTEMAIL )      |
| cdm_primarytelephone   (cdm_primarytelephone) | PRIMARYCONTACTPHONE   (PRIMARYCONTACTPHONE)       |
| cdm_facebookidentity   (cdm_facebookidentity) | PRIMARYCONTACTFACEBOOK   (PRIMARYCONTACTFACEBOOK) |
| cdm_twitteridentity   (cdm_twitteridentity)   | PRIMARYCONTACTTWITTER   (PRIMARYCONTACTTWITTER)   |
| cdm_linkedinIdentity   (cdm_linkedinIdentity) | PRIMARYCONTACTLINKEDIN   (PRIMARYCONTACTLINKEDIN) |
| cdm_websiteurl   (cdm_websiteurl)             | PRIMARYCONTACTURL   (PRIMARYCONTACTURL)           |
| cdm_firstname   (cdm_firstname)               | UTÓNÉV   (UTÓNÉV)                           |
| cdm_middlename   (cdm_middlename)             | MÁSODIK UTÓNÉV   (MÁSODIK UTÓNÉV)                         |
| cdm_lastname   (cdm_lastname)                 | VEZETÉKNÉV (VEZETÉKNÉV)                               |
| cdm_workernumber   (cdm_workernumber)         | PERSONNELNUMBER   (PERSONNELNUMBER)               |
| cdm_type (cdm_type)                           | DOLGOZÓ TÍPUSA (DOLGOZÓ TÍPUSA)                         |
| cdm_state   (cdm_state)                       | MUNKA ÁLLAPOTA   (MUNKA ÁLLAPOTA)                       |

### <a name="employments-to-employment"></a>Foglalkoztatások a Foglalkoztatáshoz

| Dataverse-tábla (forrás)                             | Finance-entitás (cél) |
|-----------------------------------------------------------------|---------------------------------------------|
| cdm_employmentstartdate   (cdm_employmentstartdate)             | FOGLALKOZTATÁS KEZDŐ DÁTUMA   (FOGLALKOZTATÁS KEZDŐ DÁTUMA) |
| cdm_employmentenddate   (cdm_employmentenddate)                 | FOGLALKOZTATÁS BEFEJEZŐ DÁTUMA   (FOGLALKOZTATÁS BEFEJEZŐ DÁTUMA)     |
| cdm_workertype   (cdm_workertype)                               | DOLGOZÓ TÍPUSA   (DOLGOZÓ TÍPUSA)                   |
| cdm_workerid.cdm_workernumber   (cdm_workerid.cdm_workernumber) | SZEMÉLYZETI SZÁM   (SZEMÉLYZETI SZÁM)         |
| cdm_companyid.cdm_companycode   (cdm_companyid.cdm_companycode) | JOGI SZEMÉLY AZONOSÍTÓJA   (JOGI SZEMÉLY AZONOSÍTÓJA)             |

### <a name="employments-to-employment-detail"></a>Foglalkoztatások a Foglalkoztatás részleteihez

| Dataverse-tábla (forrás)                             | Finance-entitás (cél)   |
|-----------------------------------------------------------------|-----------------------------------------------|
| cdm_employmentstartdate   (cdm_employmentstartdate)             | FOGLALKOZTATÁS KEZDŐ DÁTUMA   (FOGLALKOZTATÁS KEZDŐ DÁTUMA)   |
| cdm_employmentenddate   (cdm_employmentenddate)                 | FOGLALKOZTATÁS BEFEJEZŐ DÁTUMA   (FOGLALKOZTATÁS BEFEJEZŐ DÁTUMA)       |
| cdm_validfrom   (Érvényesség kezdete)                                    | ÉRVÉNYESSÉG KEZDETE   (ÉRVÉNYESSÉG KEZDETE)                       |
| cdm_validto (Érvényesség   vége)                                        | ÉRVÉNYESSÉG VÉGE (ÉRVÉNYESSÉG VÉGE)                             |
| cdm_workerstartdate   (cdm_workerstartdate)                     | DOLGOZÓ KEZDÉSI DÁTUMA   (DOLGOZÓ KEZDÉSI DÁTUMA)           |
| cdm_lastdateworked   (cdm_lastdateworked)                       | UTOLSÓ MUNKÁBAN TÖLTÖTT NAP   (UTOLSÓ MUNKÁBAN TÖLTÖTT NAP)             |
| cdm_transitiondate   (cdm_transitiondate)                       | ÁTTÉRÉS DÁTUMA   (ÁTTÉRÉS DÁTUMA)             |
| cdm_employerunitofnotice   (cdm_employerunitofnotice)           | ÉRTESÍTÉSHEZ TARTOZÓ MUNKÁLTATÓI EGYSÉG   (ÉRTESÍTÉSHEZ TARTOZÓ MUNKÁLTATÓI EGYSÉG) |
| cdm_workerunitofnotice   (cdm_workerunitofnotice)               | ÉRTESÍTÉSHEZ TARTOZÓ DOLGOZÓI EGYSÉG   (ÉRTESÍTÉSHEZ TARTOZÓ DOLGOZÓI EGYSÉG)     |
| cdm_workerid.cdm_workernumber   (cdm_workerid.cdm_workernumber) | SZEMÉLYZETI SZÁM   (SZEMÉLYZETI SZÁM)           |
| cdm_companyid.cdm_companycode   (cdm_companyid.cdm_companycode) | JOGI SZEMÉLY AZONOSÍTÓJA   (JOGI SZEMÉLY AZONOSÍTÓJA)               |
| cdm_employernoticeamount   (cdm_employernoticeamount)           | FELMONDÁSI ÖSSZEGHEZ TARTOZÓ MUNKÁLTATÓI EGYSÉG   (FELMONDÁSI ÖSSZEGHEZ TARTOZÓ MUNKÁLTATÓI EGYSÉG) |
| cdm_workernoticeamount   (cdm_workernoticeamount )              | DOLGOZÓNAK JÁRÓ FELMONDÁSI ÖSSZEG   (DOLGOZÓNAK JÁRÓ FELMONDÁSI ÖSSZEG)     |

### <a name="position-worker-assignment-to-position-worker-assignments"></a>Dolgozó beosztáshoz való hozzárendelése a Dolgozó beosztáshoz való hozzárendeléseihez

| Dataverse-tábla (forrás)                             | Finance-entitás (cél)   |
|-----------------------------------------------------------------|-----------------------------------------------|
| cdm_workerid.cdm_workernumber   (cdm_workerid.cdm_workernumber) | SZEMÉLYZETI SZÁM   (SZEMÉLYZETI SZÁM)           |
| cdm_jobpositionnumber   (Feladatbeosztás száma)                   | BEOSZTÁSAZONOSÍTÓ(BEOSZTÁSAZONOSÍTÓ)                        |
| cdm_validfrom   (Érvényesség kezdete)                                    | ÉRVÉNYESSÉG KEZDETE   (ÉRVÉNYESSÉG KEZDETE)                       |
| cdm_validto (Érvényesség vége)                                        | VALIDTO (VALIDTO)                             |

### <a name="worker-addresses-to-worker-postal-address-v2"></a>Dolgozói címek a Dolgozó postai címéhez V2

| Dataverse-tábla (forrás)                             | Finance-entitás (cél)   |
|-----------------------------------------------------------------|-----------------------------------------------|
| cdm_workerid.cdm_workernumber   (cdm_workerid.cdm_workernumber) | SZEMÉLYZETI SZÁM   (SZEMÉLYZETI SZÁM)           |
| cdm_addresstype   (cdm_addresstype)                             | CÍM-HELYSZEREPKÖRÖK   (CÍM-HELYSZEREPKÖRÖK) |
| cdm_line1   (cdm_line1)                                         | UTCA (UTCA)               |
| cdm_city (cdm_city)                                             | VÁROS   (VÁROS)                   |
| cdm_stateorprovince   (cdm_stateorprovince)                     | ÁLLAM   (ÁLLAM)                 |
| cdm_postalcode   (cdm_postalcode)                               | IRÁNYÍTÓSZÁM(IRÁNYÍTÓSZÁM)                |
| cdm_countryregion   (cdm_countryregion)                         | RÉGIÓAZONOSÍTÓ(RÉGIÓAZONOSÍTÓ)    |
| cdm_addressnumber   (cdm_addressnumber)                         | CÍM-HELYSZEREPKÖRÖK(CÍM-HELYSZEREPKÖRÖK)          |
| cdm_ispreferred   (cdm_ispreferred)                             | ISPRIMARY   (ISPRIMARY)                       |
| cdm_county   (cdm_county)                                       | MEGYEAZONOSÍTÓ(MEGYEAZONOSÍTÓ)              |
| cdm_addresstype   (cdm_addresstype)                             | CÍMLEÍRÁS(CÍMLEÍRÁS)        |

## <a name="integration-considerations"></a>Az integrációval kapcsolatos szempontok

A Human Resources és a Finance közötti integráció megkísérli a rekordok egyeztetését az azonosító alapján. Ha a rekordok egyeznek az Adatintegrátor a Human Resources alkalmazás értékeivel felülírja a Finance-adatokat. Probléma merülhet fel azonban, ha logikusan ezek különböző rekordok, és a program ugyanazt az azonosítót vagy a Human Resources alkalmazásban vagy a Finance alkalmazásban, a megfelelő számsorozat alapján generálta.

Probléma merülhet fel olyan **Dolgozó** esetén, amely a **Személyzeti szám** használatával hozza létre az egyezést, illetve a **Beosztásokat**. A feladatok nem használnak számsorozatokat. Emiatt ha ugyanaz a feladatazonosító létezik az Emberi erőforrások és a Pénzügy csoportban is, akkor az emberi erőforrások adatai felülírják a Dynamics 365 Pénzügyi adatokat. 

Ha meg szeretné akadályozni az ismétlődő azonosítókkal kapcsolatos problémákat, adjon hozzá egy előtagot a [számsorozathoz](/dynamics365/unified-operations/fin-and-ops/organization-administration/number-sequence-overview?toc=%2fdynamics365%2funified-operations%2ftalent%2ftoc.json), vagy állítson be egy kezdő számot a számsorozathoz, amely túllépi a másik rendszer tartományát. 

A dolgozó címében használt helyazonosító nem része számsorozatnak. A dolgozói cím Human Resources alkalmazásból a Finance alkalmazásba való integrálása során ha a dolgozói cím már létezik a Finance modulban, akkor ismétlődő címrekord jön létre. 

Az alábbi ábrán látható egy példa az Adatintegrátorban való sablonleképezésre. 

![Sablon-hozzárendelés.](./media/IntegrationMapping.png)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
