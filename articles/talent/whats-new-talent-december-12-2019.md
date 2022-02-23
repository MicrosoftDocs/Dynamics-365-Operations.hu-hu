---
title: Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban (2019. december 10.)
description: Ez a cikk a Microsoft Dynamics 365 Talent új vagy módosított funkcióit írja le.
author: Darinkramer
manager: AnnBe
ms.date: 12/10/2019
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
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 18f86f5d87b780d5d4ffc83330d389077987dda6
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528171"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-december-10-2019"></a>Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban (2019. december 10.)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Ez a témakör a Dynamics 365 Talent új vagy módosított szolgáltatásait írja le.

## <a name="changes-in-attract"></a>Változások az Attract-ben

A kiadás a Dynamics 365 Talent: Attract apró hibáinak javításait is tartalmazza.

## <a name="changes-in-onboard"></a>Változások az Onboard alkalmazásban

A kiadás a Dynamics 365 Talent: Onboard apró hibáinak javításait is tartalmazza.

## <a name="changes-in-core-hr"></a>A Core HR módosításai

A szakaszban ismertetett módosítások a 8.1.2660-ös buildre vonatkoznak. A néhány fejlécben látható, zárójelben lévő számok az Microsoft Dynamics Lifecycle Services (LCS) támogatási számaira vonatkoznak.

### <a name="feature-management-workspace"></a>A Funkciókezelés munkaterület

A **Funkció-kezelés** munkaterülete az egyes kiadásokban kiadott funkciók listáját tartalmazza. Alapértelmezés szerint az új szolgáltatások ki vannak kapcsolva. A munkaterületen bekapcsolhatja a szolgáltatásokat, és megtekintheti a rájuk vonatkozó dokumentációt. A funkciókezeléssel kapcsolatos további tudnivalókat lásd [Funkciókezelés áttekintése](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).

Minden új funkció megmarad előzetes verzióban legalább 30 napig, és általában 30-60 napig. A főbb funkciók általában az előzetes időszakot követően minden év októberében és áprilisában érhetők el. Amint az új funkciókat a **Funkciókezelés** munkaterületen látja, be lehet kapcsolni őket. Előfordulhat, hogy egyes funkciók alapértelmezés szerint be vannak kapcsolva.
 
Időnként egy szerves funkció alapértelmezésben be van kapcsolva, de nem kapcsolható ki (például a **Funkciókezelési** munkaterület).
 
Ha egy szolgáltatás általában elérhető, előfordulhat, hogy a működési környezetben be van kapcsolva vagy ki van kapcsolva. A **funkciókezelés** munkaterület jelzi, hogy egy előzetes funkció mikor válik kötelezővé. Ez a dátum általában október 1. vagy április 1., hogy a féléves kiadási tervekkel összehangolják. Nem kapcsolhatja ki a kötelező funkciókat. Amíg nem válik kötelezővé, bármely környezetben ki- és bekapcsolhatja a funkciót.

### <a name="streamlined-worker-form-has-moved-to-the-feature-management-workspace-390583"></a>A korszerű dolgozó űrlap a Szolgáltatáskezelés munkaterületre került át (390583)

Ezzel a változtatással a korszerű dolgozó űrlap most már engedélyezett a **Szolgáltatáskezelés** munkaterületen. Ez a szolgáltatás a **Rendszerfelügyelet** **Rendszerparaméterek** képernyőjéről áthelyezésre került.

### <a name="prevent-hcmworkerpayrollinfo-records-from-being-written-without-a-worker-value-394526"></a>A HcmWorkerPayrollInfo rekordok dolgozó érték nélküli írásának megakadályozása (394526)

Ebban a kiadásban a **HcmWorkerPayrollInfo** rekordok már nem a hozhatók létre ebben a példahelyzetben a dolgozói hivatkozás nélkül. 

### <a name="message-log-associated-to-the-action-isnt-populated-when-the-action-fails-to-complete-374007"></a>A művelethez kapcsolódó Üzenetnapló nem lesz kitöltve, ha a művelet meghiúsul (374007)

Ez a kiadás tartalmaz egy olyan változást, amely bizonyos helyzetekben a tevékenység meghiúsulása esetén kitölti a tevékenység üzenetnaplót. 

### <a name="common-data-service-integration-batch-job-creation-388030"></a>Common data service integráció kötegelt feladatának létrehozása (388030)

Ezzel a változtatással az Common Data Service integráció kötegelt feladatai a szolgáltatás engedélyezésekor lesznek létrehozva.

### <a name="additional-pick-list-values-to-custom-fields-arent-reflected-in-common-data-service-after-clicking-apply-on-the-custom-fields-form-379599"></a>Az egyéni mezőkben szereplő további kitárolásilista-elemek nem jelennek meg a Common Data Service szolgáltatásban az egyéni mezők képernyőjén az alkalmazás gombra történő kattintás után (379599)

Ezzel a változtatásokkal a Talent alkalmazásban beírt új kitárolásilista-értékek szinkronizálódnak a Common Data Service alkalmazással a változtatások alkalmazásakor.

### <a name="update-to-common-data-service-for-then-leave-bank-transaction-entity-turns-into-an-insert-on-talent-side-352938"></a>Frissítés Common Data Service szolgáltatásra, amikor a Szabadság tranzakcióentitás beillesztéssé változik a Talent oldalán (352938)

Ez a változtatás kijavítja azt a hibát, amikor a szabadság banki tranzakciója új rekordot hoz létre a Talent alkalmazásban.

## <a name="in-preview"></a>Előnézetben

Az előnézeti szolgáltatások csak **tesztkörnyezetekben** érhetők el.

### <a name="print-performance-reviews"></a>Teljesítményértékelések nyomtatása

Lásd [Teljesítményértékelések nyomtatása](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) a Dynamics 365: 2019 release wave 2 tervben.

