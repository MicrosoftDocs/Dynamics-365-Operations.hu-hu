---
title: Életesemények típusának konfigurálása
description: A Microsoft Dynamics 365 Human Resources az életeseménytípusokat használja az események meghatározására a munkavállalói juttatások beiratkozásának frissítéséhez.
author: twheeloc
ms.date: 08/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitLifeEventTypes
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: df523dd4da11e24c7b601c8f34aef24ad6cb3b18
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/23/2022
ms.locfileid: "9337318"
---
# <a name="configure-life-event-types"></a>Életesemények típusának konfigurálása

Dynamics 365 Human Resources Az életesemény-típusok **segítségével** határozza meg azokat az eseményeket, amelyekben érvényes az alkalmazott juttatásban való beléptetésének frissítése, például hogy jelentkezik-e vagy van-e gyermekük. Az élettartamesemény-típus azonosítója minden esetben csak egy élettartamesemény-típushoz kapcsolható. Ha **például** **·** **létrehoz** egy "Címváltozás" nevű életesemény-azonosítót, amely az Alkalmazotti címváltozás típusú eseményhez van társítva, nem hozhat létre másik azonosítónak jelölt alkalmazotti címváltozást, **·** **és** nem társíthatja azt az alkalmazotti címváltozás típusú eseményhez. Ha egy életeseménytípus nincs tervtípushoz társítva, az életeseménytípus nem fog életeseményt indítani. További információ: [Konstrukciótípusok létrehozása](hr-benefits-setup-plan-types.md).

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

A kiválasztott Life **eseménytípushoz kapcsolt tervek listája látható**. Az élettartamesemény-típusok konstrukciótípushoz vannak hozzárendelve, a konstrukciótípusok pedig konstrukcióhoz.

1. A **Juttatások kezelése** munkaterület **Beállítás** részén válassza az **Élettartamesemény-típusok** elemet.

2. Válassza a **Műveletek** lehetőséget.

3. Válassza a **Csatolt konstrukciók** elemet.

## <a name="life-events"></a>Életesemények

Az élettartamesemény-típus létrehozásakor a következő élettartam-események közül választhat:

| Életesemény | Helyszín | Eseményindító |
| --- | --- | --- |
| **Családi állapot változása** | **Dolgozó > Profil > Személyes adatok > Családi állapot**| Családi állapot változása |
| **Foglalkoztatási állapot változása** |**A > alkalmazotti > -előzményoldal** | Ha egy dolgozónak van meglévő foglalkoztatási adata, akkor egy új, más foglalkoztatási állapotú foglalkoztatási adat létrehozása elindít egy életeseményt.  Egy meglévő, más foglalkoztatási állapotú foglalkoztatási adat frissítése is elindít egy életeseményt.  |
| **Alkalmazott címváltozása** |**Dolgozó > Profil > Címek**</li><li>**Dolgozó > Személyes adatok > Személyes kapcsolattartók > Cím**</li></ul> | Címváltozás. A címnek **elsődlegesnek** kell lennie ahhoz, hogy életeseményt váltson ki. |
| **Függő fél változása** |<br><ul><li>**A > személyes >/li> a Személyes adatok** profilhoz ><li>**Alkalmazotti önkiszolgáló rendszer**</li></ul> | Egy személyes kapcsolattartó függő félként történő megadása és az **Érvényesség kezdete** meghatározása. Egy személyes kapcsolattartó függő fél **Érvényesség vége** információjának frissítése. A személyes kapcsolattartónak gyermeknek, házastársnak, élettársnak vagy volt házastársnak kell lennie.  |
| **Szülés vagy örökbefogadás (függő fél)** |<br><ul><li>**Dolgozó > Profil > Személyes adatok > Személyes kapcsolattartók**</li><li>**Alkalmazotti önkiszolgáló szolgáltatás > Személyes adatok szerkesztése > Személyes kapcsolattartók**</li></ul>| A **Születési dátum** vagy az **Elfogadási dátum** frissítése hozzá lett adva vagy frissítve lett. A gyermek **Születési dátumának** megadása kötelező. |
| **Fedezetvesztés (házastárs/élettárs)** | Dolgozó > Profil > Személyes adatok > Személyes kapcsolattartók > Függő fél adatai > Fedezetvesztés | A **Fedezetvesztés** és az **Érvényesség dátuma** kiválasztása a személyes kapcsolattartóhoz. |
| Élettárs foglalkoztatásának változása | **Dolgozó > Profil > Személyes adatok > Személyes kapcsolattartók > Függő fél adatai > Alkalmazott** | Személyes kapcsolattartó létrehozása és az **Alkalmazott** lehetőség **Igen** értékre való állítása. Személyes kapcsolattartó frissítése és az **Alkalmazott** módosítása.  |
| **Távollét (házastárs/élettárs)** | **Dolgozó > Profil > Személyes adatok > Személyes kapcsolattartók > Függő fél adatai > Távozás** | A személyes kapcsolattartó létrehozva, és a **Távollétkérelem érvényességi dátuma** meg van adva. A személyes kapcsolattartó **Távollétkérelme** frissítve van. A személyes kapcsolattartó **Távollétkérelem érvényességi dátuma** frissítve van.  |
| **Fedezet változása (beosztás)** |<br><ul><li>**Dolgozó > Beosztás-hozzárendelés > Dolgozóhoz rendelt beosztások**</li><li>**Beosztások > Beosztások**</li></ul>| A dolgozó beosztásának változása a beosztás-hozzárendelési rekordokban. A beosztás változása a dolgozó hozzárendelésében. |
| **Fedezet változása (fizetés)** |<br><ul><li>**Dolgozó > Kompenzáció > Fix konstrukció**</li><li>**Dolgozó > Személyes adatok > Juttatások éves fizetése**</li></ul>| **Ha a juttatások kezelése > Emberi erőforrások megosztott paraméterei > Juttatások >** A juttatások éves fizetése nem engedélyezett, **akkor a Dolgozó > Kompenzáció >** Fix konstrukció beállítással életeseményt hoz létre. **Ha a juttatások kezelése > Emberi erőforrások megosztott paraméterei > Juttatások >** Juttatások éves fizetése engedélyezve van, **akkor > Személyes adatok frissítése >** Juttatások éves fizetése egy élettartam eseményt hoz létre. |
| **Egészségbiztosítási adó (alkalmazott/függő fél)** | **Dolgozó > Profil > Személyes adatok > Személyes kapcsolattartók > Függő fél adatai > Egészségbiztosítási adó érvényességi dátuma** | Személyes kapcsolattartó **Egészségbiztosítás érvényességi** dátumának hozzáadása vagy frissítése létrehozza ezt az életeseményt. |
| **Bíróság által elrendelt tartás** | **A >-profilt > személyes adatokról > Személyes kapcsolattartók > >** A Peres tanács által rendelt támogatás (QMSCO/QDRO) és az hatályba lépő dátumok alapján | Személyes kapcsolattartó létrehozása esetén egy életesemény is létrejön, ha a **Bíróság által elrendelt tartás** lehetőség **Igen** értékre van állítva. A **Bíróság által elrendelt tartás** vagy a **Bíróság által elrendelt tartás lejárati dátuma** is elindít egy életeseményt. |
| **Elhunyt** | **Dolgozó > Profil > Személyes adatok > Elhalálozás dátuma** | Egy **Elhunyt dátumot** adunk meg vagy frissítünk. |
| **Biztosítás igazolása** | **Dolgozó > Dolgozó > Verziók > Foglalkoztatási előzmények > Dátumkezelő > Juttatás részletei** | **Biztosíthatóság igazolása** lehetőség **Igen** értékre van állítva. **Biztosíthatóság igazolásának megerősítési dátuma** megadva. |
| **Kedvezményezett** | **Dolgozó > Profil > Személyes adatok > Személyes kapcsolattartók** | A személyes kapcsolat hozzáadásra kerül, és a **Kedvezményezett** és a **Hatálybalépés napja** mezők kitöltésre kerülnek. A személyes kapcsolattartó típusának a következőnek kell lennie: **Gyermek**, **Házastárs**, **Élettárs**, **Testvér**, **Családon belüli kapcsolattartó**, **Egyéb kapcsolattartó** vagy **Szülő**. |
| **Alkalmazotti egészségbiztosítási adó** | **Dolgozó > Dolgozó > Verziók > Foglalkoztatási előzmények > Dátumkezelő > Juttatás részletei** | A **Társadalombiztosításra jogosult** lehetőség **Igen** értékűre állítása. A **Társadalombiztosításra jogosultság dátuma** módosult. |
| **Születésnap** | **Juttatások kezelése > Életesemény változásának feldolgozása** | Ezek az életesemények az **Életesemény változásának feldolgozásból** vannak létrehozva. A folyamat elemzi a kiválasztott időszakot és jogi személyt, illetve megkeresi a társított dolgozókat. Kiszámítja a legutóbbi születésnapjukat, és létrehoz egy születésnapi eseményt, ha az még nincs létrehozva. |
| **Dolgozói jogosultság változása (nem USA)** |<br><ul><li>**Dolgozó > Foglalkoztatás**</li><li>**Dolgozó > Dolgozó > Verziók > Foglalkoztatási előzmények**</li></ul>| Életesemény létrehozása, ha:<br><ul><li>Új foglalkoztatást hoz létre, valamint van egy korábbi foglalkoztatás, és a dolgozó típusa megváltozik.</li><li>Új foglalkoztatási részletet hoz létre, valamint van egy korábbi foglalkoztatási részlet, és a dolgozó foglalkoztatási típusa vagy foglalkoztatási kategóriája megváltozik.</li><li>Egy foglalkoztatási rekord frissítése, és egy másik dolgozótípus van meghatározva.</li><li>Egy foglalkoztatási részletrekord frissítése, és másik foglalkoztatási típus vagy kategória meghatározása.</li></ul> |
| **Új jogosultság felülbírálása (nem USA)** | **Human Resources – Speciális > Juttatások > Konstrukciók > Juttatások > Jogosultsági szabály felülbírálása** | Élettartam-esemény feldolgozásának használata<br>Egy dolgozónál a juttatási terv alkalmazhatóságának felülbírálásának létrehozása elindítja ezt az életeseményt.<br>BenefitEligibilityRuleOverride.ValidFrom. |
| **Jogosultsági szabály felülbírálásának változása (nem USA)** | **Human Resources – Speciális > Juttatások > Konstrukciók > Juttatások > Jogosultsági szabály felülbírálása** | Ha frissíti egy juttatási terv **Érvényesség kezdete** vagy **Érvényesség vége** lehetőséget egy juttatási terv jogosultsági felülbírálásán, azzal elindítja ezt az életeseményt. |
| **Jogosultsági szabály felülbírálásának lejárata (nem USA)** | Juttatások kezelése > Életesemény változásának feldolgozása  | Ezek az életesemények az **Életesemény változásának feldolgozásból** vannak létrehozva. A folyamat elemzi a kiválasztott időszakot és jogi személyt, illetve megkeresi a juttatási terv jogosultsági felülbírálását. Életeseményeket hoz létre, ha a felülbírálások lejártak. |
| **Új juttatási konstrukció (nem USA)** | **Human Resources – Speciális > Juttatások > Tervek > Új** | Jogosultsági beállítások hozzáadása egy aktuális konstrukcióhoz. Jogosultsági beállításokat tartalmazó új konstrukció hozzáadása.</br></br>A HR munkatársainak ebben az esetben futtatniuk kell ezen a példányon az Élettartam-esemény jogosultsága feldolgozást. |
| **Jogosultsági szabály változása (nem USA)** | **Juttatások kezelése > Alkalmazhatósági szabályok** | Élettartam-esemény jogosultsága feldolgozás használata. Naplózás akkor történik, ha a **BenefitEligibilityRule** rekordokban változtak a következő értékek: **UseEmplCategory**, **UseEmplStatus** vagy **UseEmplType**. Csak azok az élettartamesemény-tranzakciók frissülnek, amelyek már léteznek a módosított szabálynál vagy jogosultsági feltételnél. |


[!INCLUDE[footer-include](../includes/footer-banner.md)]
