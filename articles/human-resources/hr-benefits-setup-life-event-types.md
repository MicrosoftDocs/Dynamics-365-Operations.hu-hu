---
title: Életesemények típusának konfigurálása
description: A Microsoft Dynamics 365 Human Resources az élettartamesemény-típusok használatával határozza meg az olyan eseményeket, amikor lehetőség van az alkalmazotti juttatások beléptetéseinek frissítésére.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitLifeEventTypes
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 5286bcd940f4068531bae624876c8a35e64db4c3
ms.sourcegitcommit: 9723b5ff40c84677316d71e185cf862556b32cf9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/31/2020
ms.locfileid: "3741486"
---
# <a name="configure-life-event-types"></a>Életesemények típusának konfigurálása

A Microsoft Dynamics 365 Human Resources az élettartamesemény-típusok használatával határozza meg az olyan eseményeket, amikor lehetőség van az alkalmazotti juttatások beléptetéseinek frissítésére. Ilyen például a házasságkötés vagy a gyermek születése. Az élettartamesemény-típus azonosítója minden esetben csak egy élettartamesemény-típushoz kapcsolható. Ha például létrehoz egy élettartamesemény-azonosítót Címmódosítás néven, amelyet a az Alkalmazotti címének módosítás élettartamesemény-típushoz rendel hozzá, akkor nem hozhat létre másik azonosítót az Alkalmazott címének módosítása címkével, és nem rendelheti hozzá az Alkalmazott címének módosítás élettartamesemény-típushoz. 

Miután létrehozta az élettartamesemény-típusokat, hozzá kell rendelnie azokat a konstrukciótípusokhoz. További információ: [Konstrukciótípusok létrehozása](hr-benefits-setup-plan-types.md).

   > [!NOTE]
   > Amikor létrehozza az élettartamesemény-típusokat, hozzá kell rendelnie azokat egy konstrukciótípushoz. További információ: [Konstrukciótípusok létrehozása](hr-benefits-setup-life-event-types.md).

## <a name="create-a-life-event-type"></a>Élettartamesemény-típus létrehozása

1. A **Juttatások kezelése** munkaterület **Beállítás** részén válassza az **Élettartamesemény-típusok** elemet.

2. Válassza az **Új** lehetőséget.

3. Adjon meg értékeket a következő mezőkben:

   | Mező | Leírás |
   | --- | --- |
   | **Életesemény-típus azonosítója** | Az életesemény típusának egyedi azonosítója. |
   | **Leírás** | Az élettartamesemény-típus leírása. |
   | **Életesemény-típus** | Katalizátor az alkalmazotti juttatások regisztrálásának frissítéséhez. Az élettartam-események listáját lásd: [Élettartam-események](hr-benefits-setup-payment-frequencies.md?life-events). |

4. Válassza a **Mentés** lehetőséget.

## <a name="view-attached-plans"></a>Csatolt konstrukciók megtekintése

Megtekintheti a kiválasztott élettartamesemény-típushoz kapcsolódó konstrukciók listáját. Az élettartamesemény-típusok konstrukciótípushoz vannak hozzárendelve, a konstrukciótípusok pedig konstrukcióhoz. 

1. A **Juttatások kezelése** munkaterület **Beállítás** részén válassza az **Élettartamesemény-típusok** elemet.

2. Válassza a **Műveletek** lehetőséget.

3. Válassza a **Csatolt konstrukciók** elemet.

## <a name="life-events"></a>Életesemények

Az élettartamesemény-típus létrehozásakor a következő élettartam-események közül választhat:

| Életesemény | Helyszín | Eseményindító |
| --- | --- | --- |
| **Családi állapot változása** | Dolgozó > Profil > Személyes adatok > Családi állapot| Családi állapot változása |
| **Foglalkoztatási állapot változása** | <ul><li>Dolgozó > Foglalkoztatás</li><li>Foglalkoztatási előzmények oldal</li></ul> | Foglalkoztatási állapot változása |
| **Alkalmazott címváltozása** | <ul><li>Dolgozó > Profil > Címek </li><li>Dolgozó > Személyes adatok > Személyes kapcsolattartók > Cím</li></ul> Hozzáadott, szerkesztett vagy törölt címek |
| **Függő fél változása** | <ul><li>Dolgozó > Profil > Személyes adatok > Személyes kapcsolattartók > Függő fél hozzáadása vagy törlése</li><li>Alkalmazotti önkiszolgáló rendszer</li></ul> | Hozzáadott vagy törölt függő fél. A személyes kapcsolattartónak gyermeknek, házastársnak, élettársnak vagy volt házastársnak kell lennie. Az **Érvényesség kezdete** dátum frissítése indítja el az élettartam-eseményt. Ha nem frissíti ezt a dátumot, nem lép érvénybe az élettartam-esemény. |
| **Szülés vagy örökbefogadás (függő fél)** | <ul><li>Dolgozó > Profil > Személyes adatok > Személyes kapcsolattartók > Függő fél adatai</li><li>Alkalmazotti önkiszolgáló rendszer</li></ul> | Az **Örökbefogadás dátuma** mező kitöltése. A gyermek születési dátumának megadása kötelező. |
| **Fedezetvesztés (házastárs/élettárs)** | Dolgozó > Profil > Személyes adatok > Személyes kapcsolattartók > Függő fél adatai > Fedezetvesztés | A **Fedezetvesztés** és az **Érvényesség dátuma** kiválasztása a személyes kapcsolattartóhoz. |
| Élettárs foglalkoztatásának változása | Dolgozó > Profil > Személyes adatok > Személyes kapcsolattartók > Függő fél adatai > Alkalmazott. | <ul><li>A függő fél adatait tartalmazó rekord létrehozása és a **Személyes kapcsolattartók – alkalmazott** mező = Igen.</li><li>A **Személyes kapcsolattartó – alkalmazott** mező módosult (Igen vagy Nem).</li></ul> |
| **Távollét (házastárs/élettárs)** | Dolgozó > Profil > Személyes adatok > Személyes kapcsolattartók > Függő fél adatai > Távozás | <ul><li>A függő fél adatait tartalmazó rekord létrehozása, és az **EhrLOAEffectiveDate** mező kitöltése</li><li>A **personPrivateDetails.EhrIsLOA** mező módosult (Igen vagy Nem)</li><li>A **personPrivateDetails.EhrLOAEffectiveDate** mező módosult</li></ul> |
| **Fedezet változása (beosztás)** | <ul><li>Dolgozó > Beosztás-hozzárendelés > Dolgozóhoz rendelt beosztások</li><li>Beosztások > Beosztások</li></ul> | <ul><li>A dolgozó beosztásának változása a beosztás-hozzárendelési rekordokban</li><li>A beosztás változása a dolgozó hozzárendelésében</li></ul> |
| **Egészségbiztosítási adó (alkalmazott/függő fél)** | Dolgozó > Profil > Személyes adatok > Személyes kapcsolattartók > Függő fél adatai > Egészségbiztosítási adó érvényességi dátuma | Nem aktiválódik automatikusan, amikor a személyes kapcsolattartó beírja az érvényességi dátumot. |
| **Bíróság által elrendelt tartás** | Dolgozó > Profil > Személyes adatok > Személyes kapcsolattartók > Függő fél > Bíróság által elrendelt tartás (egészségbiztosítás/járadék és érvényességi dátumok) | Nem indítja el az automatikus frissítéseket. Nem befolyásolja a jogosultságot, rögzíti az élettartam-eseményeket. |
| **Elhunyt** | Dolgozó > Profil > Személyes adatok > Elhalálozás dátuma | Elhalálozás dátumának megadása |
| **Biztosítás igazolása** | <ul><li>Dolgozó > Dolgozó > Verziók > Foglalkoztatási előzmények > Dátumkezelő > Juttatás részletei</li><li> Dolgozó > Foglalkoztatás > Juttatás részletei > Igazolási dátum</li></ul> | <ul><li>A dolgozó beírja az igazolási dátumot</li><li>A dolgozó **Igen** értékűre állítja az EvidenceOfInsurability mezőt</li></ul> |
| **Kedvezményezett** | Dolgozó > Profil > Személyes adatok > Személyes kapcsolattartók | Személyes kapcsolattartó hozzáadása, a **Kedvezményezett** és az **Érvényesség dátuma** mező kitöltése. A személyes kapcsolattartó típusának a következőnek kell lennie: **Gyermek**, **Házastárs**, **Élettárs**, **Testvér**, **Családon belüli kapcsolattartó**, **Egyéb kapcsolattartó**, **Szülő**, **Kedvezményezett birtok**, **Kedvezményezett szervezet** vagy **Kedvezményezett alap**. |
| **Alkalmazotti egészségbiztosítási adó** | Dolgozó > Dolgozó > Verziók > Foglalkoztatási előzmények > Dátumkezelő > Juttatás részletei | <ul><li>Az **EhrMedicareEligibilityDate** módosult</li><li>A **MedicareEligibile** **Igen** értékűre állítása</li></ul> |
| **Születésnap** | Dolgozó > Profil > Személyes adatok > Személyes kapcsolattartók > Függő fél adatai > Születési dátum | Születési dátum hozzáadása vagy frissítése (nem az Élettartam-esemény módosítása feldolgozás után). Példa: Ha egy gyermek esetében a **Személyes kapcsolattartó jogosultsági beállításai** a 26 éves életkort tartalmazzák a Beállítás > Juttatások > Személyes kapcsolattartó jogosultsági beállításai között, és ha a HR munkatársai Élettartam-esemény módosítása feldolgozást indítanak, miután a függő fél betöltötte a 26. évét, akkor üzenet jelenik meg, amely jelzi, hogy a függő fél már nem jogosult a fedezetre. |
| **Dolgozói jogosultság változása (nem USA)** | <ul><li>Dolgozó > Foglalkoztatás</li><li>Dolgozó > Dolgozó > Verziók > Foglalkoztatási előzmények</li></ul> | <ul><li>Alkalmazott típusa, Foglalkoztatási kategória vagy az öt felhasználó által definiálható jogosultsági mező változása</li><li>A **HcmEmploymentDetail. EhrEmploymentType** változása (csak a *módosult* foglalkoztatási részletek rekordjainak feldolgozása, az *új* foglalkoztatási rekordok, például az újrafelvétel és a felmondás esetén nincs feldolgozás)</li></ul> |
| **Új jogosultság felülbírálása (nem USA)** | Human Resources – Speciális > Juttatások > Konstrukciók > Juttatások > Jogosultsági szabály felülbírálása | Élettartam-esemény feldolgozásának használata | EhrBenefitEligibilityRuleOverride.ValidFrom |
| **Jogosultsági szabály felülbírálásának változása (nem USA)** | Human Resources – Speciális > Juttatások > Konstrukciók > Juttatások > Jogosultsági szabály felülbírálása | Élettartam-esemény feldolgozás használata (csak a **ValidFrom** és a **ValidTo** mező módosítását figyeli a jogosultsági szabály felülbírálásakor) |
| **Jogosultsági szabály felülbírálásának lejárata (nem USA)** | Human Resources – Speciális > Juttatások > Konstrukciók > Juttatások > Jogosultsági szabály felülbírálása | Élettartam-eseményt módosító feldolgozás használata. Ha például az aktuális nap 17:00 órájára, az aktuális nap 17:00 órája utánra vagy bármelyik következő napra módosítja egy konstrukció jogosultsági szabályának felülbírálásához tartozó lejárati dátumot, majd futtatja az Életesemény-módosítás feldolgozást, akkor üzenet jelenik meg, amely jelzi, hogy a jogosultsági szabály felülírása lejárt. |
| **Új juttatási konstrukció (nem USA)** | Human Resources – Speciális > Juttatások > Tervek > Új | <ul><li>Jogosultsági beállítások hozzáadása egy aktuális konstrukcióhoz</li><li>Jogosultsági beállításokat tartalmazó új konstrukció hozzáadása</li></ul></br></br>A HR munkatársainak ebben az esetben futtatniuk kell ezen a példányon az Élettartam-esemény jogosultsága feldolgozást. |
| **Jogosultsági szabály változása (nem USA)** | Human Resources – Speciális > Juttatások > Szabályok/beállítások > Jogosultsági szabályok | Élettartam-esemény jogosultsága feldolgozás használata. Naplózás akkor történik, ha az **EhrBenefitEligibilityRule** rekordokban változtak a következő értékek: **UseEmplCategory**, **UseEmplStatus** vagy **UseEmplType**. Csak azok az élettartamesemény-tranzakciók frissülnek, amelyek már léteznek a módosított szabálynál vagy jogosultsági feltételnél. |
