---
title: Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban (2019. október 23.)
description: Ez a témakör a Microsoft Dynamics 365 Talent új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 10/23/2019
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
ms.search.validFrom: 2019-10-23
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 66419d9093cff68aa6109b22ab57bcb46ac6c718
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/06/2019
ms.locfileid: "2772896"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-october-23-2019"></a>Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban (2019. október 23.)

[!include [banner](includes/banner.md)]

Ez a témakör a Dynamics 365 Talent új vagy módosított szolgáltatásait írja le.

## <a name="changes-in-attract"></a>Változások az Attract-ben
A kiadás a Dynamics 365 Talent: Attract apró hibáinak javításait is tartalmazza.

## <a name="changes-in-onboard"></a>Változások az Onboard alkalmazásban
A kiadás a Dynamics 365 Talent: Onboard apró hibáinak javításait is tartalmazza.

## <a name="changes-in-core-hr"></a>A Core HR módosításai

A szakaszban ismertetett módosítások a 8.1.2569-ös buildre vonatkoznak. A néhány fejlécben látható, zárójelben lévő számok az Microsoft Dynamics Lifecycle Services (LCS) támogatási számaira vonatkoznak.

### <a name="platform-update-30-for-finance-and-operations-apps"></a>Platform update 30 a Finance and Operations alkalmazásokhoz

A további tudnivalókat lásd [Újdonságok és módosítások a Finance and Operations 30-as platformfrissítéséhez (2019. november)](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/fin-ops/get-started/whats-new-platform-update-30).

### <a name="remove-benefits-open-enrollment-preview-feature"></a>A juttatások megnyitása előzetes funkció eltávolítása

A [Stratégiai befektetések a core HR-ben a működési kiválóság elősegítése érdekében](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/10/02/strategic-investments-in-core-hr-drive-operational-excellence) bejelentése blogbejegyzés mellett 2019. október 18-án a Microsoft eltávolítja juttatások nyitása regisztrációra funkciót a nyilvános előzetesből. Helyette a jövőben új funkciók lesznek kiadva. A juttatások megnyitása regisztrációra funkciónak a termelési része, amely jelenleg a nyilvános előzetesben szerepel, nem lesz támogatott.

### <a name="error-while-selecting-the-countryregion-on-the-worker-form-a-second-time-350294"></a>Hiba történik a dolgozó országának/régiójának második alkalommal történő kijelölésekor (350294).

A heti kiadással a program korrigálja azt a problémát, ami akkor merül fel, amikor kiválaszt egy országot/régiót a **Dolgozó** űrlapján.

### <a name="financial-dimension-values-default-to-the-combination-display-field-when-do-not-allow-manual-entry-is-set-to-true-340097"></a>A pénzügyi dimenzióértékek alapértelmezetten a Kombináció kijelzőmező szerint, Ha a ne engedélyezze a manuális bevitelt értéke igaz(340097).

Ezzel a módosítással a pénzügyi dimenziók beállításakor és a manuális bevitelt tiltó beállítás használata esetén a rendszer a dimenzió értékét helyesen állítja be a **Kombinált kijelző** mezőre állítja be alapértelmezetten.

### <a name="new-relationship-types-should-be-added-to-relationship-lookup-in-the-personal-contacts-form-347691"></a>A személyes kapcsolattartók képernyőjén megjelenő kapcsolatok keresésekor új kapcsolattípusokat kell megadni (347691)

Ez a kiadás új képességeket tartalmaz a **Kapcsolattípusok** tábla új kapcsolatainak hozzáadására, valamint a személyes kapcsolattartók kapcsolatai kereséseiben bekövetkező változtatások tükrözésére.

### <a name="additional-list-values-in-custom-fields-arent-reflected-in-common-data-service-379599"></a>Az egyéni mezőkben szereplő további értéklista nem tükröződik a Common Data Service képernyőn (379599)

Az eheti kiadással, egy új értéklista hozzáadásával egy létező egyéni mezőhöz, amely már szinkronizálva van Common Data Service megoldással, az új kitárolási lista értékei immár megjelennek az entitás módosításainak alkalmazása után.

### <a name="on-the-terms-of-employment-page-all-employees-terms-of-employment-appear-after-selecting-open-in-excel-348073"></a>A Foglalkoztatási feltételek lapon az összes alkalmazott munkaviszonya megjelenik a Megnyitás Excelben lehetőség kiválasztása után (348073).

Ebben a verzióban csak a kiválasztott alkalmazottak foglalkoztatási feltételei jelennek meg az Excel programban. Minden vállalat biztonsági funkció figyelembe van véve.

### <a name="the-association-between-the-work-calendar-holiday-entity-and-the-work-calendar-entity-is-missing-in-common-data-service-324178"></a>A Munkanaptár szünnap-entitása és a Munkanaptár entitás közötti társítás hiányzik a Common Data Service megoldásban (324178).

Ez a kapcsolat már hozzá van adva a kiadással. Ez a módosítás lehetővé teszi az alkalmazottak munkanapjainak megjelenítését PowerApps megoldásban. 

### <a name="error-when-using-employee-self-service-workflows-with-configurable-hierarchies-370132"></a>Hiba történt az alkalmazotti önkiszolgáló munkafolyamatok konfigurálható hierarchiával való használatakor (370132).

Ebben a verzióban hatékonyabb üzenetküldési funkció érhető el a munkafolyamatok konfigurálható hierarchiák segítségével történő konfigurálásához. 

### <a name="system-allows-creation-of-new-positions-where-the-available-for-assignment-date-is-earlier-than-the-activation-date-340103"></a>A rendszer új beosztások létrehozását teszi lehetővé, ahol a rendelkezésre álló hozzárendelés dátuma korábbi az Aktiválás dátumánál (340103).

A módosítás egy figyelmeztetést jelenít meg, ha az **Elérhető hozzárendeléshez**  dátuma a beosztás **Aktiválási** dátuma előtt van.

## <a name="coming-soon"></a>Hamarosan

### <a name="print-performance-reviews"></a>Teljesítményértékelések nyomtatása

Lásd [Teljesítményértékelések nyomtatása](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) a Dynamics 365: 2019 release wave 2 tervben.

### <a name="feature-management-workspace"></a>A Funkciókezelés munkaterület

Minden kiadásban új szolgáltatások és frissítések jelennek meg. A funkció-kezelési élmény olyan munkaterületet tartalmaz, amelyen megtekintheti az egyes kiadásokban elérhetővé tett szolgáltatások listáját. Alapértelmezés szerint az új szolgáltatások ki vannak kapcsolva. A munkaterületen bekapcsolhatja a szolgáltatásokat, és megtekintheti a rájuk vonatkozó dokumentációt.

További információ a szolgáltatások kezelésével kapcsolatos változásokról: [Funkciókezelés áttekintése](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).
