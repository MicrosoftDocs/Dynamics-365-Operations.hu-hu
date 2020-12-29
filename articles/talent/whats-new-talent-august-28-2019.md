---
title: Új vagy módosult elemek a Dynamics 365 for Talent szolgáltatásban (2019. augusztus 27.)
description: Ez a témakör a Microsoft Dynamics 365 for Talent új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 8/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: andreabichsel
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-08-27
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 8965636e539345be5ef0ad591f7017938efd322d
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/17/2020
ms.locfileid: "4529804"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-august-27-2019"></a>Új vagy módosult elemek a Dynamics 365 for Talent szolgáltatásban (2019. augusztus 27.)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Ez a témakör a Dynamics 365 for Talent új vagy módosított szolgáltatásait írja le.

## <a name="changes-in-attract"></a>Változások az Attract-ben

A kiadás a Dynamics 365 Talent: Attract apró hibáinak javításait is tartalmazza.

## <a name="changes-in-onboard"></a>Változások az Onboard alkalmazásban

A kiadás a Dynamics 365 Talent: Onboard apró hibáinak javításait is tartalmazza.

## <a name="changes-in-core-hr"></a>A Core HR módosításai

A szakaszban ismertetett módosítások a 8.1.2447-ös buildre vonatkoznak. A néhány fejlécben látható, zárójelben lévő számok az Microsoft Dynamics Lifecycle Services (LCS) támogatási számaira vonatkoznak.

### <a name="preview-features-are-enabled-only-in-sandbox-instances"></a>Az előnézeti szolgáltatások csak a védőfalpéldányokban engedélyezettek

Amikor új Talent-példányt hoz létre, megadhatja, hogy a példány Termelési vagy Védőfal típusú legyen-e. A Védőfal típusú példányokkal az új szolgáltatások korai tesztelése végezhető el. Minden létező Talent példányt a Termelési példány típusára lesz frissítve. Ha a meglévő példányokat Védőfal típusúra szeretné frissíteni, kérje az ügyfélszolgálat segítségét.

További információ a módosítások közzétételéről: [A Talent létesítése](./provisioning-talent.md).

### <a name="view-extended-information-for-performance-in-manager-self-service"></a>Részletes teljesítményadatok megtekintése az önkiszolgáló kezelői rendszerben

Egy új beállítással a vezetők mind a közvetlen beosztottak, mind a közvetett beosztottak teljesítményét megtekinthetik. Jelenleg a közvetlen felettesek hozzárendelhetnek teljesítménycélokat és frissíthetik őket, illetve olyan új értékeléseket adhatnak ki. Ezenkívül a közvetlen felettesek és alkalmazottaik karbantarthatják és frissíthetik a teljesítménymutatókat, így megbizonyosodhatnak róla, hogy a teljesítmény ellenőrzési folyamata gördülékenyen megy majd. A módosítás végrehajtásakor a vezetők a közvetlen beosztottakon kívül a bővített jelentések teljesítménnyel kapcsolatos adatait is megtekinthetik és karbantartják.

### <a name="deleting-legal-entities-isnt-allowed-if-employees-exist-within-the-company-339849"></a>A jogi személyek törlése nem megengedett, ha az alkalmazottak léteznek a vállalaton belül (339849).

Ezzel a módosítással nem távolíthatja el vagy törölheti a vállalatokat, ha alkalmazottak vagy a jogi személyhez kapcsolódó egyéb adatok léteznek.

### <a name="compensation-management-business-intelligence-analytics-dont-match-on-the-compensation-workspace-322493"></a>A kompenzációkezelés üzletiintelligencia-analitikái nem egyeznek a kompenzációs munkaterületen (322493).

Ebben a verzióban a kompenzációs analitikákat korrigáltuk az alkalmazottakhoz rendelt tervek pontos tükrözése érdekében.

### <a name="workflow-placeholder-company-displays-dat-when-hiring-employees-through-workflow-343905"></a>A %company% munkafolyamat-helyőrző a DAT értéket jeleníti meg az alkalmazottak munkafolyamaton keresztül történő felvételekor (343905)

Ebben a kiadásban a vállalat helyőrzője az új alkalmazott munkaviszonyához társított jogi személyt jeleníti meg.

### <a name="the-cdsjobposition-entity-displays-an-error-when-valid-to-date-is-set-349387"></a>A CDSJobPosition entitás hibát jelez, ha be van állítva a záró dátum (349387).

Ebben a verzióban a **Beosztás részletei** és a **Beosztás időtartama** elemek adatforrásai lehetővé teszik a Common Data Service szolgáltatásból származó **CDSJobPosition** entitások számára az **Érvényessgi dátum** mezők módosítástát. 

### <a name="for-employee-termination-the-last-day-worked-is-populated-on-assignment-end-date-332496"></a>Az alkalmazott elbocsátása esetében a program az utolsó munkanapot tölti ki a hozzárendelés záró dátumaként (332496).

Ez a változtatás most alapértelmezés szerint a **Megbízás záró dátuma** értékét adja a **Munkaviszony záró dátuma** értékéhez. Ezeket az alapértelmezéseket módosíthatja az adatok megadásakor.

### <a name="legal-entities-arent-limited-with-hire-338871"></a>A jogi személyek nem korlátozottak felvételkor (338871)
 
Ez a módosítás korlátozza a felvételi folyamatot, és csak azokat a jogi személyeket jeleníti meg, amelyekhez a felhasználó hozzáférhet.  

## <a name="in-preview"></a>Előnézetben

### <a name="streamlined-employee-entry-and-navigation"></a>Korszerű alkalmazotti belépés és navigálás

Ez a funkció jelenleg a sandbox és a próbakörnyezetekben érhető el. A funkció bekapcsolásához navigáljon a **Rendszer-adminisztráció > Hivatkozások > Beállítás > Rendszerparaméterek > előnézeti funkciók** ponthoz. Válassza a **Továbbfejlesztett dolgozói képernyő és navigáció** lehetőséget. Ez minden felhasználó számára engedélyezi ezeket a változtatásokat. Ezt a beállítást bármikor ki lehet kapcsolni.

További tájékoztatás: [Korszerű alkalmazotti belépés és navigálás](./streamlined-employee-entry.md).

## <a name="coming-soon"></a>Hamarosan

### <a name="platform-update-29"></a>29-as platformfrissítés

További információ a 29-es platformfrissítésről (Platform update 29): [Előzetes funkciók a Dynamics 365 for Finance and Operations platform update 29 verziójában (2019. október)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-29).
