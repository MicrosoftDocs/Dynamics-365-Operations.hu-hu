---
title: "Elektronikus jelentéskészítési konfigurációk életciklusainak kezelése"
description: "Ez a témakör az Elektronikus jelentés (ER) konfigurációk életciklusának kezelését ismerteti a Microsoft Dynamics 365 for Operations megoldás esetén."
author: kfend
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ERDataModelDesigner, ERMappedFormatDesigner, ERModelMappingDesigner, ERModelMappingTable, ERSolutionImport, ERSolutionTable, ERVendorTable, ERWorkspace
audience: Application User, Developer, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 58801
ms.assetid: 35ad19ea-185d-4fce-b9cb-f94584b14f75
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: f4d8994f6548119789715a4879b6bc02d25598e9
ms.lasthandoff: 03/31/2017


---

# <a name="manage-the-electronic-reporting-configuration-lifecycle"></a>Elektronikus jelentéskészítési konfigurációk életciklusainak kezelése

[!include[banner](../includes/banner.md)]


Ez a témakör az Elektronikus jelentés (ER) konfigurációk életciklusának kezelését ismerteti a Microsoft Dynamics 365 for Operations megoldás esetén.

<a name="overview"></a>Áttekintés
--------

Az Elektronikus jelentés (ER) felel a jogszabályokban követelményként előírt és országspecifikus dokumentumok támogatásáért a Microsoft Dynamics 365 for Operations rendszerben. Általánosságban az ER feltételezi, hogy az alábbi feladatok elvégezhetők egyetlen elektronikus dokumentumhoz. További részletekért lásd: [Elektronikus jelentés – áttekintés](general-electronic-reporting.md).

-   Sablon tervezése elektronikus dokumentumhoz:
    -   Határozza meg a dokumentumban feltüntethető adatokhoz szükséges forrásokat:
        -   Másodlagos Dynamics 365 for Operations adatok (adattáblák, adatentitások és osztályok).
        -   Folyamat-specifikus tulajdonságok (végrehajtási dátum és idő, valamint időzóna).
        -   Felhasználó által megadott paraméterek (futásidőben, végfelhasználó által megadott).
    -   Definiálja a szükséges dokumentum elemeinek, valamint ezen elemeknek a végső dokumentum formátumának meghatározásához használt topológiát.
    -   A dokumentum elemeinek (adatforrás kötéssel a dokumentumformátum komponenséhez), valamint a folyamatvezérlő logika meghatározásához konfigurálja a kívánt adatfolyamot a kiválasztott adatforrásokból.
-   Tegyen elérhetővé egy sablont, amely ezáltal használhatóvá válik más Dynamics 365 for Operations példányokban is:
    -   Alakítson át egy, a Dynamics 365 for Operations rendszerben készült dokumentumot ER konfigurációvá. Ezt követően exportálja a jelenlegi Dynamics 365 for Operations példányból helyileg, illetve LCS rendszerben tárolható XML-csomagként.
    -   Alakítson át ER konfigurációt Dynamics 365 for Operations dokumentumsablonná.
    -   Importáljon egy helyben vagy LCS rendszerben tárolt XML csomagot a Dynamics 365 for Operations példányába.
-   Egy elektronikus dokumentum sablonjának testreszabása:
    -   Importáljon egy sablont ER-konfigurációként az aktuális Dynamics 365 for Operations példányba az LCS rendszerből.
    -   Egy ER-konfiguráció testreszabott verziójának megtervezése, hivatkozást biztosítva az alapverzióhoz.
-   Integráljon egy bizonyos üzleti folyamattal rendelkező sablont, hogy az elérhető legyen a Dynamics 365 for Operations rendszerben:
    -   Ha hivatkozik a folyamathoz kapcsolódó paraméteren belüli konfigurációra, akkor beállíthatja, hogy a Dynamics 365 for Operations rendszer elkezdje használni az ER konfigurációt. Például hivatkozzon egy ER konfigurációra egy megadott Kötelezettségek fizetése módban, hogy elektronikus fizetési üzenetet hozzon létre a feldolgozás alatt lévő számlákhoz.
-   Egy sablon használata egy meghatározott üzleti folyamatban:
    -   Futtasson ER-konfigurációt egy meghatározott üzleti folyamatban. Például hozzon létre számlafeldolgozással kapcsolatos elektronikus fizetési üzenetet, amikor egy ER-konfigurációra mutató hivatkozást használó fizetési módszer van kiválasztva

## <a name="concepts"></a>Koncepció
A következő szerepkörök és a kapcsolódó tevékenységek társítva vannak az ER-konfigurációk életciklusához.

| Szerep                                       | Tevékenységek                                                      | Leírás                                                                                                                                                                                                                  |
|--------------------------------------------|-----------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Elektronikus jelentések funkcióival foglalkozó konzulens | Hozzon létre és kezeljen egy ER komponenst (modellek és formátumok).           | Egy üzleti személy, aki az ER tartomány-specifikus adatmodelleket tervezi, fogja megfelelően hozzákötni és megtervezni az elektronikus dokumentumokhoz szükséges sablonokat.                                                                           |
| Elektronikus jelentések fejlesztője             | Adatmodell hozzárendelések létrehozása és kezelése.                          | Egy Dynamics 365 for Operations szakember, aki kiválasztja a szükséges Dynamics 365 for Operations-adatforrásokat, és hozzáköti azokat az ER tartomány-specifikus adatmodellekhez                                                                 |
| Számviteli felügyelő                      | Az ER műtermékre hivatkozó folyamathoz kapcsolódó beállítás konfigurálása. | Például egy **Számviteli felügyelő** szerepkör, ami engedélyezi, hogy az ER konfiguráció beállításai használhatóak legyenek egy megadott Kötelezettségek fizetése módban, a feldolgozás alatt lévő számlákhoz tartozó elektronikus fizetési üzenet létrehozásánál. |
| Kötelezettségkifizetési adminisztrátor            | Egy ER műtermék használata egy meghatározott üzleti folyamatban.                | Például egy **Kötelezettségkifizetési adminisztrátor** szerepkör, ami engedélyezi a megszabott fizetési módhoz konfigurált ER formátumon alapuló, feldolgozás alatt lévő számlákhoz tartozó elektronikus fizetési üzenet létrehozását.           |

## <a name="er-configuration-development-lifecycle"></a>ER konfiguráció fejlesztési életciklusa
A következő, ER rendszerrel kapcsolatos okok miatt javasolt a ER-konfigurációkat a fejlesztői környezetben megtervezni egy különálló 365 for Operations példányként:

-   Az **Elektronikus jelentések fejlesztője** vagy az **Elektronikus jelentések funkcióival foglalkozó konzulens** szerepkörrel rendelkező felhasználók szerkeszthetik a konfigurációkat is futtathatják azokat tesztelés céljából. Olyan osztályok és táblázatok módszereit hívhatja meg, amelyek esetleg károsak lehetnek az üzleti adatokra és a Dynamics 365 for Operations példány használati hatékonyságára nézve.
-   A Dynamics 365 for Operations belépési pontok és naplózott vállalati tartalmak nem korlátozzák az osztály- és táblázatmódszerek ER-konfigurációkhoz tartozó ER-adatforrásokként történő hívását. Tehát a bizalmas üzleti adatokhoz hozzáférnek az **Elektronikus jelentések fejlesztője** vagy az **Elektronikus jelentések funkcióival foglalkozó konzulens** szerepkörrel rendelkező felhasználók.

A fejlesztői környezetben megtervezett ER-konfigurációk feltölthetők a tesztkörnyezetbe a konfiguráció kiértékelése (megfelelő folyamatintegrálás, eredményhelyesség, teljesítmény), illetve a minőségbiztosítás (például szerepkörtől függő hozzáférési jogok helyessége, feladatkörök szétválasztása) céljából. Azok a funkciók használhatóak erre a célra, amelyek engedélyezik az ER konfiguráció adatcseréjét. Végül az igazoltan helyes ER-konfigurációk feltölthetők az LCS-be megosztva a szolgáltatás előfizetőivel, vagy az éles környezetbe belső használatra, a következő ábrán látható módon. ![ER-konfigurációs életciklus](./media/ger-configuration-lifecycle.png)

<a name="see-also"></a>Lásd még
--------

[Elektronikus jelentések áttekintése](general-electronic-reporting.md)




