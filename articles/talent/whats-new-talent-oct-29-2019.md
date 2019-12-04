---
title: Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban (2019. október 29.)
description: Ez a témakör a Microsoft Dynamics 365 Talent új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 10/29/2019
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
ms.search.validFrom: 2019-10-29
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 83b4734190163ebd2dc29096632642bd45c61e8f
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/06/2019
ms.locfileid: "2773877"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-october-29-2019"></a>Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban (2019. október 29.)

[!include [banner](includes/banner.md)]

Ez a témakör a Dynamics 365 Talent új vagy módosított szolgáltatásait írja le.

## <a name="changes-in-attract"></a>Változások az Attract-ben

A kiadás a Dynamics 365 Talent: Attract apró hibáinak javításait is tartalmazza.

## <a name="changes-in-onboard"></a>Változások az Onboard alkalmazásban

A kiadás a Dynamics 365 Talent: Onboard apró hibáinak javításait is tartalmazza.

## <a name="changes-in-core-hr"></a>A Core HR módosításai

A szakaszban ismertetett módosítások a 8.1.2586-ös buildre vonatkoznak. A néhány fejlécben látható, zárójelben lévő számok az Microsoft Dynamics Lifecycle Services (LCS) támogatási számaira vonatkoznak.

### <a name="delete-parties-with-no-roles-should-be-on-by-default-371233"></a>A szerepkörökkel nem rendelkező felek törlésének alapértelmezés szerint bekapcsolt állapotban kell lennie (371233)

Ha egy új környezetet hoz létre a Talent programban, akkor a **Felek törlése, ha nem találhatók szerepkörök** alapértelmezett módon be van kapcsolva. Dolgozó törlésekor a dolgozóhoz társított fél nem kerül eltávolításra, csak akkor, ha ez a beállítás bekapcsolt állapotban van. Ez a módosítás korlátozza a globális címjegyzék ismétlődő rekordjait, amikor a dolgozókat importálni, módosítani vagy újraimportálni szeretné.

### <a name="draft-and-cancelled-leave-requests-should-be-allowed-to-be-deleted-in-common-data-service-376999"></a>A Common Data Service szolgáltatásban a tervezet állapotú és a visszavont szabadságkérelmeket tudni kell törölni (376999)

Ezzel a módosítással most már kitörölheti a **Tervezet** vagy **Visszavont** állapotú szabadságkérelmeket a Common Data Service szolgáltatásban.

### <a name="additional-list-values-in-custom-fields-arent-reflected-in-common-data-service-after-clicking-apply-on-the-custom-fields-form-379599"></a>Az egyéni mezőkben szereplő további listaelemek nem jelennek meg a Common Data Service szolgáltatásban az egyéni mezők képernyőjén az alkalmazás gombra történő kattintás után (379599)

Amikor új listaértékeket ad hozzá olyan meglévő egyéni mezőhöz, amelyet már szinkronizált a Common Data Service szolgáltatással, ezek elérhetővé válnak a a Common Data Service szolgáltatásban, miután elvégzi a módostásokat az **Egyéni mezők** űrlapon.

### <a name="apply-onboarding-checklists-across-legal-entities-when-more-than-one-employment-exists-371270"></a>Toborzási ellenőrzőlisták alkalmazása több jogi személyen, amikor több foglalkoztatás található (371270)

Az e heti kiadásban ellenőrzőlistákat alkalmazhat olyan alkalmazottakra, akik egynél több foglalkoztatással rendelkeznek a **Dolgozói űrlap > Ellenőrzőlista** pontban.

### <a name="benefits-open-enrollment-preview-feature-has-been-removed"></a>A juttatásokra való nyitott jelentkezés előzetes funkciót eltávolították

A [Stratégiai befektetések a Core HR-ben a működési kiválóság elősegítése érdekében](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/10/02/strategic-investments-in-core-hr-drive-operational-excellence) bejelentése blogbejegyzés mellett a Microsoft eltávolította a juttatásokra való nyitott jelentkezés funkciót a nyilvános előzetesből. A jövőben új funkciók lesznek kiadva. A juttatásokra való nyitott jelentkezés funkciójának működési használatát nem támogatja a rendszer.

## <a name="coming-soon"></a>Hamarosan

### <a name="print-performance-reviews"></a>Teljesítményértékelések nyomtatása

Lásd [Teljesítményértékelések nyomtatása](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) a Dynamics 365: 2019 release wave 2 tervben.

### <a name="feature-management-workspace"></a>A Funkciókezelés munkaterület

Minden kiadásban új szolgáltatások és frissítések jelennek meg. A funkció-kezelési élmény olyan munkaterületet tartalmaz, amelyen megtekintheti az egyes kiadásokban elérhetővé tett szolgáltatások listáját. Alapértelmezés szerint az új szolgáltatások ki vannak kapcsolva. A munkaterületen bekapcsolhatja a szolgáltatásokat, és megtekintheti a rájuk vonatkozó dokumentációt.

További információ a szolgáltatások kezelésével kapcsolatos változásokról: [Funkciókezelés áttekintése](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).
