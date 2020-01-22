---
title: Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban (2019. május 6.)
description: Ez a témakör a Microsoft Dynamics 365 Talent új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 05/06/2019
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
ms.search.validFrom: 2019-05-06
ms.dyn365.ops.version: Talent
ms.openlocfilehash: f06d989ea4e927111729dfbd4bb7700745a16a54
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897511"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-may-6-2019"></a>Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban (2019. május 6.)

Ez a témakör a Dynamics 365 Talent új vagy módosított szolgáltatásait írja le.

## <a name="changes-in-attract"></a>Változások az Attract-ben

### <a name="select-optional-documents-upon-offer-creation"></a>Választható dokumentumok kiválasztása ajánlat létrehozásakor

Ha kiválaszt egy ajánlaticsomag-sablont, akkor most a program felkéri, hogy válassza ki a megfelelő, választható dokumentumokat a sablonból. Az ajánlat előkészítése közben más opcionális dokumentumokat is hozzáadhat.

## <a name="changes-in-onboard"></a>Változások az Onboard alkalmazásban

A kiadás a Dynamics 365 Talent: Onboard apró hibáinak javításait is tartalmazza.

## <a name="changes-in-core-hr"></a>A Core HR módosításai

A szakaszban ismertetett módosítások a 8.1.2282-ös buildre vonatkoznak. A néhány fejlécben látható, zárójelben lévő számok az Microsoft Dynamics Lifecycle Services (LCS) támogatási számaira vonatkoznak.

### <a name="platform-update-26-for-finance-and-operations"></a>Platform update 26 a Finance and Operations szolgáltatáshoz

További információ a Finance and Operations 26-os platformfrissítésről (Platform update 26): [Előzetes funkciók a Dynamics 365 Finance and Operations platform update 26-os verziójában (2019. május)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-26). 

### <a name="common-data-service-entity-support-for-custom-fields"></a>Common Data Service entitás-támogatás egyéni mezőkhöz

A heti kiadásban a következő entitások már támogatják az egyéni mezőket: Juttatási számítás gyakorisága, Juttatási számítási mértéke, Juttatás típusa, Munkanaptár, Munkanaptár-szünnap, Fizetési ciklus és Dolgozóazonosító típusok.

### <a name="leave-mass-enrollment-changing-the-tier-basis-to-seniority-date-doesnt-refresh-the-initial-accrual-rate-318526"></a>Tömeges felvétel elhagyása, a rangsorolás alapja "Szolgálati idő" értékre állítása nem frissíti a kezdeti elhatárolási mértéket (318526)

Az alkalmazottak tömeges felvételekor és a szintek alapjának módosításakor a kezdeti elhatárolás most a kiválasztott szintalapot tükrözi.

### <a name="workflow-showing-duplicate-place-holders-313636"></a>Ismétlődő tárolókat megjelenítő munkafolyamat (313636)

Az ebben a verzióban bekövetkező változtatások a munkafolyamatok értesítéseinek elküldésekor kiküszöbölik a helyőrzők duplikálását.

### <a name="dimension-fields-arent-updated-when-using-open-in-excel-176261"></a>A Dimenzió mezők nem frissülnek a „Megnyitás Excel alkalmazásban” használata során (176261).

Ebben a verzióban most frissítheti a pénzügyi dimenziót a **Megnyitás Excelalkalmazás** funkcióval a **Dolgozó** lapon. 

### <a name="worker-address-created-in-common-data-service-isnt-synced-to-talent-317555"></a>A dolgozó részére a Common Data Service megoldásban létrehozott cím nincs szinkronizálva a Talent alkalmazással (317555).

Ezzel a módosítással a Common Data Service megoldásban létrehozott címeket a Talent: Core HR frissíti.


## <a name="in-preview"></a>Előnézetben

### <a name="new-page-to-validate-position-hierarchy-data"></a>Új oldal a beosztás-hierarchia adatainak ellenőrzéséhez

A személyzeti osztály munkatársai (HR) és a rendszergazdák most ellenőrizni tudják a vezetői hierarchiát a véletlenül importált körkörös hivatkozások tekintetében. Ezt az új lapot a **Szervezeti adminisztráció > Hivatkozások > Beosztások > Beosztáshierarchia ellenőrzése** helyről érheti el.

### <a name="specify-reason-codes-on-leave-types"></a>Okkódok meghatározása a távollét típusaihoz

A szervezeteknek kiegészítő információkra lehet szüksége a szabadságkérelmekkel kapcsolatban. Immár megadhat okkódokat egy adott távolléttípushoz, és megengedheti az alkalmazottak számára okkód választását szabadságkérelmükhöz.

### <a name="require-reason-codes-for-specific-leave-types-on-time-off-requests"></a>Okkódok kérése adott szabadságtípusokhoz a távollétkérelmek során

Előfordulhat, hogy a szervezetek okkódok beállítását kérik, bizonyos távolléttípusokhoz, amikor a munkavállalók távolléti kérelmeket nyújtanak be. Ez a követelmény a vállalat szabályzata vagy a törvényi követelmények miatt állhat fenn. Immár meghatározhatja, mely szabadságtípusokhoz szükséges okkód, és alkalmazottaktól megkövetelheti okkód megadását a szabadságtípushoz a távollétkérelmekhez.

### <a name="provide-a-leave-and-absence-transaction-list-for-hr"></a>Egy szabadság és a távolléti tranzakciólista átadása a HR-nek

Az alkalmazotti szabadidő követésének képessége és a szabadidő kiszámításának ismerete azon túl. hogy segít a HR-nek alkalmazott kérdések megválaszolásában, pontos szabadságmegítéléseket biztosít a munkavállalóknak. HR új nézetet kap a tranzakciókhoz (támogatások, könyvelések, helyesbítések és kérelmek) így a HR munkatársai láthatják az egyenlegek okait.

## <a name="coming-soon"></a>Hamarosan

### <a name="indicate-instance-type-when-provisioning-talent"></a>Példány típusának jelzése a Talent kiépítése alkalmával

Ha egy új Talent példányt telepít akkor jelezheti, hogy a példány típusa **Termelési** vagy **Védőfal**típusú, és lehetővé teszi az új szolgáltatások korai tesztelését. Minden létező Talent példányt a termelési példány típusára lesz frissítve. Ha azt szeretné, hogy a meglévő példányok frissítve legyenek a védőfal példányra, forduljon a támogatáshoz a módosítási kérelem kezdeményezéséhez.
