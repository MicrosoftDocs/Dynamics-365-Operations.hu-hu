---
title: Új vagy módosult elemek a Dynamics 365 for Talent szolgáltatásban (2019. szeptember 10.)
description: Ez a témakör a Microsoft Dynamics 365 for Talent új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 9/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-09-10
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 14e3482f366319851bed84b6cdd6135f0bcd1e80
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897332"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-september-10-2019"></a>Új vagy módosult elemek a Dynamics 365 for Talent szolgáltatásban (2019. szeptember 10.)

Ez a témakör a Dynamics 365 for Talent új vagy módosított szolgáltatásait írja le.

## <a name="changes-in-attract"></a>Változások az Attract-ben

### <a name="candidate-e-mail-login"></a>Jelölt e-mailes bejelentkezése

A jelöltek bármilyen e-mail-címmel létrehozhatnak fiókot, és bejelentkezhetnek a Talent karrierwebhelyére, ahol állásokra jelentkezhetnek és megtekinthetik pályázatuk állapotát. Ez egy további lehetőséget biztosít amellett, hogy már közösségimédia-fiókjaik vagy szervezeti hitelesítő adataik segítségével bejelentkezhettek a Talent karrierwebhelyére.

### <a name="job-activation-and-posting"></a>Állás aktiválása és feladása

Néhány módosítást végeztünk az állásaktiválás és -feladás folyamatában. Az állásokat aktiválni kell a Talent karrierwebhelyen vagy külső álláshirdető-felületre (pl. LinkedIn vagy Broadbean) való feladás előtt.

## <a name="changes-in-onboard"></a>Változások az Onboard alkalmazásban

A kiadás a Dynamics 365 Talent: Onboard apró hibáinak javításait is tartalmazza.

## <a name="changes-in-core-hr"></a>A Core HR módosításai

A szakaszban ismertetett módosítások a 8.1.2482-ös buildre vonatkoznak. A néhány fejlécben látható, zárójelben lévő számok az Microsoft Dynamics Lifecycle Services (LCS) támogatási számaira vonatkoznak.

### <a name="you-can-enable-preview-features-in-sandbox-and-trial-environments"></a>Az előzetes funkciókat tesztkörnyezetekben és próbakörnyezetekben is engedélyezheti

Amikor új Talent-példányt hoz létre, megadhatja, hogy a példány Termelési vagy Védőfal típusú legyen-e. A Védőfal típusú példányokkal az új szolgáltatások korai tesztelése végezhető el. Ha a meglévő példányokat Védőfal típusúra szeretné frissíteni, kérje az ügyfélszolgálat segítségét.

További információ a módosítások közzétételéről: [A Talent létesítése](./provisioning-talent.md).

### <a name="platform-update-29"></a>29-as platformfrissítés

További információ a 29-es platformfrissítésről (Platform update 29): [Előzetes funkciók a Dynamics 365 for Finance and Operations platform update 29 verziójában (2019. október)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-29).

### <a name="new-job-base-entity-available-in-data-management-framework-347202"></a>Új állás alapentitás elérhető az adatkezelési keretrendszerben (347202)

Ettől a verziótól egy új Alapállás entitás érhető el az adatok importálásához és exportálásához. 

### <a name="worker-advanced-security-policy-incorrectly-displays-positions-in-position-hierarchy-354868"></a>A dolgozói speciális biztonsági irányelv helytelenül jeleníti meg a beosztásokat a Beosztáshierarchiában (354868)

Ebben a kiadásban a pozíciók nem nyitottként jelennek meg egy „üres” dolgozóval, amikor a felhasználóknak korlátozott a hozzáférésük.

### <a name="job-form-close-box-wont-close-form-in-certain-situations-342467"></a>Az állásűrlap bezárása ablak nem zárja be az űrlapot bizonyos helyzetekben (342467)

Ez a kiadás olyan módosítást tartalmaz, amely lehetővé teszi, hogy az állásűrlap minden esetben bezáródjon.

### <a name="new-case-on-employee-record-is-locked-for-human-resources-manager-role-337111"></a>Az alkalmazotti rekord új esete zárolva van az emberi erőforrás vezető szerepkör számára (337111)

Ezzel a módosítással az esetkezelési űrlap már nincs zárolva, ha a dolgozói űrlapról nyitják meg.

### <a name="employment-end-date-always-defaults-to-235959-351492"></a>A foglalkoztatás záró dátuma alapértelmezésként mindig 23:59:59 (351492)

Ezzel a módosítással a foglalkoztatási dátumot módosítani lehet másik időpontra, mint 23:59:59, amikor manuálisan zárják a foglalkoztatást.

### <a name="unable-to-set-up-expiration-date-on-an-earning-code-through-data-management-336604"></a>Nem állítható be lejárati dátum a bevételkódnál az adatkezelésen keresztül (336604)

Ebben a verzióban olyan bevételkódokat állíthat be, amelyek a **PayrollWorkerPositionEarningCodeEntity** entitáson keresztül járnak le.

### <a name="employee-development-analytic-report-doesnt-display-data-348737"></a>Az alkalmazotti fejlesztési analitikus jelentése nem jeleníti meg az adatokat (348737)

Az eheti kiadásban az alkalmazotti szakértelmek elemzése frissült, így pontos jelentéskészítést biztosít.

### <a name="terms-of-employment-datetime-dont-default-to-beginning-of-day-349101"></a>A foglalkoztatási dátum/időpont feltételei alapértelmezetten nem a nap kezdetére áll be (349101)

Ezzel a módosítással a kezdő dátum/idő alapértelmezésként a nap kezdete lesz, és a záró dátum/idő alapértelmezett értéke pedig a nap vége.

### <a name="changing-the-employment-end-date-on-worker-action-form-displays-an-error-354092"></a>A Dolgozói művelet űrlapon a foglalkoztatás záró dátumának módosítása hibaüzenetet jelenít meg (354092) 

Ez a módosítás javítja a hibát, amely a foglalkoztatás záró dátumát a dolgozói művelet részeként történő módosítás során merül fel.

### <a name="applying-onboarding-checklists-across-companies-338433"></a>Felvételi ellenőrzőlisták alkalmazása vállalatokon keresztül (338433)

Ezzel a kiadással lehetővé válik az ellenőrzőlisták alkalmazása olyan alkalmazottakra, akiket a bejelentkezett jogi személytől eltérő jogi személyben foglalkoztatnak.

## <a name="in-preview"></a>Előnézetben

### <a name="streamlined-employee-entry-and-navigation"></a>Korszerű alkalmazotti belépés és navigálás

Ez a funkció jelenleg a sandbox környezetekben érhető el. A funkció bekapcsolásához navigáljon a **Rendszer-adminisztráció > Hivatkozások > Beállítás > Rendszerparaméterek > előnézeti funkciók** ponthoz. Válassza a **Továbbfejlesztett dolgozói képernyő és navigáció** lehetőséget. Ez minden felhasználó számára engedélyezi a változtatásokat. Ezt a beállítást bármikor ki lehet kapcsolni.

További tájékoztatás: [Korszerű alkalmazotti belépés és navigálás](./streamlined-employee-entry.md).
