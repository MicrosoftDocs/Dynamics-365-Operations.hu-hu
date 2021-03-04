---
title: Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban (2019. október 8.)
description: Ez a témakör a Microsoft Dynamics 365 Talent új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 10/08/2019
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
ms.search.validFrom: 2019-10-08
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 40898ca7f54089337180def964b8942e8653663b
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/17/2020
ms.locfileid: "4529480"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-october-8-2019"></a>Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban (2019. október 8.)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Ez a témakör a Microsoft Dynamics 365 Talent új vagy módosított szolgáltatásait írja le.

## <a name="changes-in-attract"></a>Változások az Attract-ben

A kiadás a Dynamics 365 Talent: Attract apró hibáinak javításait is tartalmazza.

## <a name="changes-in-onboard"></a>Változások az Onboard alkalmazásban

A kiadás a Dynamics 365 Talent: Onboard apró hibáinak javításait is tartalmazza.

## <a name="changes-in-core-hr"></a>A Core HR módosításai

A szakaszban ismertetett módosítások a 8.1.2542-ös buildre vonatkoznak. A néhány fejlécben látható, zárójelben lévő számok az Microsoft Dynamics Lifecycle Services (LCS) támogatási számaira vonatkoznak.

### <a name="removal-of-benefits-open-enrollment-from-public-preview"></a>A feliratkozásra nyitott juttatások eltávolítása a nyilvános előzetesből

A [Stratégiai befektetések a core HR-ben a működési kiválóság elősegítése érdekében](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/10/02/strategic-investments-in-core-hr-drive-operational-excellence/) bejelentése blogbejegyzés mellett 2019. október 18-án a Microsoft eltávolítja juttatások nyitása regisztrációra funkciót a nyilvános előzetesből. Helyette a jövőben új funkciók lesznek kiadva. A juttatások megnyitása regisztrációra funkciónak a termelési része, amely jelenleg a nyilvános előzetesben szerepel, nem lesz támogatott. 

### <a name="common-data-service-integration-is-now-turned-off-by-default-on-new-provisions-343675"></a>A Common Data Service integráció most alapértelmezésben ki van kapcsolva az új telepítéseken (343675).
 
Új környezetek létesítése esetén a Common Data Service integráció most ki van kapcsolva. További információ: [A Common Data Service integráció konfigurálása](hr-common-data-service-integration.md).

### <a name="streamlined-employee-entry-and-navigation"></a>Korszerű alkalmazotti belépés és navigálás

Az alkalmazotti bejegyzés és a navigálás funkció az összes környezetben elérhető. Ha be szeretné kapcsolni ezt a funkciót, nyissa meg a **Rendszerfelügyelet \> Hivatkozások \> Beállítások \> Rendszerparaméterek \> Előnézeti szolgáltatások** lehetőséget, és a **Továbbfejlesztett dolgozói képernyő és navigáció** lehetőséget. Ezt követően a funkció minden felhasználó számára be van kapcsolva. Ezt a beállítást bármikor ki lehet kapcsolni.

További információ: [Egyszerűsített alkalmazotti adatbevitel](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/streamlined-employee-data-entry) a Dynamics 365: 2019 2019 release wave 2 tervben.

### <a name="attract-and-onboard-create-inactive-workers-in-core-hr-380517"></a>Az Attract és az Onboard inaktív dolgozókat hoz létre a Core HR-ben (380517)

Ez a heti kiadás korrigálja azt a hibát, amikor az Attract és az Onboard inaktív dolgozókat hoznak létre e Core HR-ben.

### <a name="the-workflow-fails-when-the-manager-is-signed-in-to-another-company-while-terminating-an-employee-346852"></a>A munkafolyamat nem hajtható végre, ha a vezető be van jelentkezve egy másik vállalatba egy alkalmazott munkaviszonyának megszüntetésekor (346852).

A munkafolyamat már fog meghiúsulni azon jogi személy alapján, amelybe a vezető be van jelentkezve.

### <a name="missing-information-on-hcmonboardingworkerchecklisttaskentity-349591"></a>Hiányzó információ itt: HcmOnboardingWorkerChecklistTaskEntity (349591)

Ez a kiadás további információkat tartalmaz a **HcmOnboardingWorkerChecklistTaskEntity** entitáshoz. Íme néhány példa:

- **Csoport neve**, ha a hozzárendelt típus **csoport**
- **Alkalmazott neve**, ha a hozzárendelt típus **alkalmazott**
- **Vezető neve**, ha a hozzárendelt típus **vezető**

### <a name="entities-arent-listed-in-alphabetical-order-in-common-data-service-administration-377414"></a>Az entitások nem jelennek meg ábécé-sorrendben a Common Data Service adminisztrációjában (377414)

Az entitások immár ábécé-sorrendben jelennek meg a **CDS adminisztráció** oldalon.

### <a name="changing-the-employment-type-with-a-future-date-doesnt-allow-a-position-assignment-339958"></a>A foglalkoztatás típusának jövőbeli dátummal történő módosítása nem teszi lehetővé egy beosztás hozzárendelését (339958)

Ez a módosítás a beosztások hozzárendelését lehetővé teszi a dolgozótípusok módosításakor (például az alkalmazottról alvállalkozóra).

### <a name="updating-the-common-data-service-leave-bank-transaction-entity-creates-a-new-record-in-talent-352938"></a>A Common Data Service Szabadság tranzakcióentitásának frissítése egy új rekordot hoz létre a Talent alkalmazásban (352938)

A szabadság tranzakciója most frissül, ha frissítés történik a Common Data Service szabadságtranzakciói esetében frissítés történik.

### <a name="the-title-of-attachments-for-feedback-items-shows-the-feedback-description-343765"></a>A visszajelzési cikkek mellékleteinek címe a visszajelzés leírását jeleníti meg (343765)

A visszajelzés leírása már nem jelenik meg a melléklet címében.

### <a name="compensation-workflow-comments-field-shows-incorrect-content-339297"></a>A kompenzációs munkafolyamat megjegyzések mezője helytelen tartalmat jelenít meg (339297)

Ez a módosítás a **%HcmActionState.HcmWorkerActionComment.Comments%** mező tartalmát jeleníti meg.

### <a name="workcalendarentity-and-workcalendardayentity-arent-exposed-through-odata-376329"></a>A WorkCalendarEntity és a WorkCalendarDayEntity entitás nem jelenik meg az OData-n keresztül (376329)

Ebben a verzióban **a** WorkCalendarEntity és a **WorkCalendarDayEntity** már elérhetők az Open Data Protocol (OData) segítségével.

### <a name="hcmworkerentity-is-slow-when-odata-is-used-375221"></a>A HCMWorkerEntity lassú OData használatakor (375221)

A változtatások javítják a **HCMWorkerEntity** teljesítményét a Microsoft Excel munkafüzet-tervező használata esetén.

### <a name="manager-performance-journal-entry-shows-an-error-after-deleting-a-performance-journal-and-creating-a-new-one-336061"></a>A vezető teljesítménye naplóbejegyzés hibát jelez egy teljesítménymutató törlése és egy új létrehozása után (336061)

Ez a kiadás javítja egy problémát, amelyek egy teljesítménynapló törlése után következik be, és a rendszer azonnal létrehoz egy újat. Ez a javítás megváltoztatja a vezetői önkiszolgáló szolgáltatás működését.

## <a name="coming-soon"></a>Hamarosan

### <a name="print-performance-reviews"></a>Teljesítményértékelések nyomtatása

Lásd [Teljesítményértékelések nyomtatása](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) a Dynamics 365: 2019 release wave 2 tervben.


[!INCLUDE[footer-include](../includes/footer-banner.md)]