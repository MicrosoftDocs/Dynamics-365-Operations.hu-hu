---
title: Elektronikus jelentéskészítési (ER) konfigurációk életciklusainak kezelése
description: Ez a témakör ismerteti az Elektronikus jelentés (ER) konfigurációk életciklusának kezelését a Microsoft Dynamics 365 Finance megoldás esetén.
author: NickSelin
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERMappedFormatDesigner, ERModelMappingDesigner, ERModelMappingTable, ERSolutionImport, ERSolutionTable, ERVendorTable, ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 58801
ms.assetid: 35ad19ea-185d-4fce-b9cb-f94584b14f75
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1a4741784103817c270c4c7f730753ba59a327d1
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682623"
---
# <a name="manage-the-electronic-reporting-er-configuration-lifecycle"></a>Elektronikus jelentéskészítési (ER) konfigurációk életciklusainak kezelése

[!include [banner](../includes/banner.md)]

Ez a témakör ismerteti az Elektronikus jelentés (ER) konfigurációk életciklusának kezelését a Microsoft Dynamics 365 Finance megoldás esetén.

## <a name="overview"></a>Áttekintés

Az Elektronikus jelentés (ER) felel a jogszabályokban követelményként előírt és országspecifikus dokumentumok támogatásáért. Általánosságban az ER feltételezi, hogy az alábbi feladatok elvégezhetők egyetlen elektronikus dokumentumhoz. További részletekért lásd: [Elektronikus jelentés (ER) – áttekintés](general-electronic-reporting.md).

- Sablon tervezése elektronikus dokumentumhoz:

    - Határozza meg a dokumentumban feltüntethető adatokhoz szükséges forrásokat:

        - Másodlagos adatok, például adattáblák, adatentitások és osztályok.
        - Folyamat-specifikus tulajdonságok (végrehajtási dátum és idő, valamint időzóna).
        - Felhasználó által megadott paraméterek (futásidőben, végfelhasználó által megadott).

    - Definiálja a szükséges dokumentum elemeinek, valamint ezen elemeknek a végső dokumentum formátumának meghatározásához használt topológiát.
    - A dokumentum elemeinek (adatforrás kötéssel a dokumentumformátum komponenséhez), valamint a folyamatvezérlő logika meghatározásához konfigurálja a kívánt adatfolyamot a kiválasztott adatforrásokból.

- Tegyen elérhetővé egy sablont, ezáltal használhatóvá válnak más példányokban:

    - Alakítson át egy, a Dynamics AX-ben készült dokumentumot ER konfigurációvá. Ezt követően exportálja a jelenlegi alkalmazáspéldányból helyileg, illetve LCS-ben tárolható XML csomagként.
    - Alakítson át ER konfigurációt alkalmazás-dokumentumsablonná.
    - Importáljon egy helyben, vagy LCS-ben tárolt XML csomagot a példányába.

- Egy elektronikus dokumentum sablonjának testreszabása:

    - Egy sablon ER-konfigurációként importálása az aktuális példányba az LCS-ből.
    - Egy ER-konfiguráció testreszabott verziójának megtervezése, hivatkozást biztosítva az alapverzióhoz.

- Integráljon egy bizonyos üzleti folyamattal rendelkező sablont, hogy az elérhető legyen az alkalmazásban:

    - Ha hivatkozik a folyamathoz kapcsolódó paraméteren belüli konfigurációra, akkor beállíthatja, hogy az alkalmazás elkezdje használni az ER-konfigurációt. Például hivatkozzon egy ER konfigurációra egy megadott Kötelezettségek fizetése módban, hogy elektronikus fizetési üzenetet hozzon létre a feldolgozás alatt lévő számlákhoz.

- Egy sablon használata egy meghatározott üzleti folyamatban:

    - Futtasson ER-konfigurációt egy meghatározott üzleti folyamatban. Például hozzon létre számlafeldolgozással kapcsolatos elektronikus fizetési üzenetet, amikor egy ER-konfigurációra mutató hivatkozást használó fizetési módszer van kiválasztva

## <a name="concepts"></a>Koncepció
A következő szerepkörök és a kapcsolódó tevékenységek társítva vannak az ER-konfigurációk életciklusához.

| Szerep                                       | Tevékenységek                                                      | Leírás |
|--------------------------------------------|-----------------------------------------------------------------|-------------|
| Elektronikus jelentések funkcióival foglalkozó konzulens | Hozzon létre és kezeljen egy ER komponenst (modellek és formátumok).           | Egy üzleti személy, aki az ER tartomány-specifikus adatmodelleket tervezi, fogja megfelelően hozzákötni és megtervezni az elektronikus dokumentumokhoz szükséges sablonokat. |
| Elektronikus jelentések fejlesztője             | Adatmodell hozzárendelések létrehozása és kezelése.                          | Egy szakember, aki kiválasztja a szükséges Finance adatforrásokat és hozzáköti azokat az ER tartomány-specifikus adatmodellekhez. |
| Számviteli felügyelő                      | Az ER műtermékre hivatkozó folyamathoz kapcsolódó beállítás konfigurálása. | Például egy **Számviteli felügyelő** szerepkör, ami engedélyezi, hogy az ER konfiguráció beállításai használhatóak legyenek egy megadott Kötelezettségek fizetése módban, a feldolgozás alatt lévő számlákhoz tartozó elektronikus fizetési üzenet létrehozásánál. |
| Kötelezettségkifizetési adminisztrátor            | Egy ER műtermék használata egy meghatározott üzleti folyamatban.                | Például egy **Kötelezettségkifizetési adminisztrátor** szerepkör, ami engedélyezi a megszabott fizetési módhoz konfigurált ER formátumon alapuló, feldolgozás alatt lévő számlákhoz tartozó elektronikus fizetési üzenet létrehozását. |

## <a name="er-configuration-development-lifecycle"></a>ER konfiguráció fejlesztési életciklusa
A következő, ER-rel kapcsolatos okok miatt javasolt a ER-konfigurációkat a fejlesztői környezetben megtervezni egy különálló Finance and Operations-példányként:

- Az **Elektronikus jelentések fejlesztője** vagy az **Elektronikus jelentések funkcióival foglalkozó konzulens** szerepkörrel rendelkező felhasználók szerkeszthetik a konfigurációkat is futtathatják azokat tesztelés céljából. Olyan osztályok és táblázatok módszereit hívhatja meg, amelyek esetleg károsak lehetnek az üzleti adatokra és a példány használati hatékonyságára nézve.
- A belépési pontok és naplózott vállalati tartalmak nem korlátozzák az osztály- és táblázatmódszerek ER-konfigurációkhoz tartozó ER-adatforrásokként történő hívását. Tehát a bizalmas üzleti adatokhoz hozzáférnek az **Elektronikus jelentések fejlesztője** vagy az **Elektronikus jelentések funkcióival foglalkozó konzulens** szerepkörrel rendelkező felhasználók.

A fejlesztői környezetben megtervezett ER-konfigurációk feltölthetők a tesztkörnyezetbe a konfiguráció kiértékelése (megfelelő folyamatintegrálás, eredményhelyesség, teljesítmény), illetve a minőségbiztosítás (például szerepkörtől függő hozzáférési jogok helyessége, feladatkörök szétválasztása) céljából. Azok a funkciók használhatóak erre a célra, amelyek engedélyezik az ER konfiguráció adatcseréjét. Végül az igazoltan helyes ER-konfigurációk feltölthetők az LCS-be megosztva a szolgáltatás előfizetőivel, vagy az éles környezetbe belső használatra, a következő ábrán látható módon.

![ER-konfigurációs életciklus](./media/ger-configuration-lifecycle.png)

## <a name="additional-resources"></a>További erőforrások

[Elektronikus jelentéskészítés (ER) áttekintése](general-electronic-reporting.md)
