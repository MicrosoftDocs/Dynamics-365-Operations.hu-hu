---
title: "Elektronikus jelentéskészítési konfigurációk életciklusainak kezelése"
description: "Ez a témakör leírja, hogyan elektronikus jelentési műveletek megoldás a Microsoft Dynamics 365 konfigurációi (ER) életciklusának kezelését."
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

Ez a témakör leírja, hogyan elektronikus jelentési műveletek megoldás a Microsoft Dynamics 365 konfigurációi (ER) életciklusának kezelését.

<a name="overview"></a>Áttekintés
--------

Az Elektronikus jelentés (ER) felel a jogszabályokban követelményként előírt és országspecifikus dokumentumok támogatásáért a Microsoft Dynamics 365 for Operations rendszerben. Általánosságban az ER feltételezi, hogy az alábbi feladatok elvégezhetők egyetlen elektronikus dokumentumhoz. További részletekért lásd: [elektronikus jelentése – áttekintés](general-electronic-reporting.md).

-   Sablon tervezése elektronikus dokumentumhoz:
    -   Határozza meg a dokumentumban feltüntethető adatokhoz szükséges forrásokat:
        -   Dynamics 365 fedezeti műveletek adatok, adattáblák, entitások és osztályok.
        -   Folyamat-jellemző tulajdonságok, például a végrehajtási dátum és idő és időzóna.
        -   Felhasználói bemeneti paraméterek, a felhasználó által futási időben megadott.
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
    -   Ha hivatkozik a folyamathoz kapcsolódó paraméteren belüli konfigurációra, akkor beállíthatja, hogy a Dynamics 365 for Operations rendszer elkezdje használni az ER konfigurációt. Például a számlák feldolgozására az elektronikus fizetési üzenet létrehozásához egy adott számlák fizetendő fizetési mód ER konfiguráció vonatkoznak.
-   Egy sablon használata egy meghatározott üzleti folyamatban:
    -   Az ER-konfiguráció egy adott üzleti folyamat futtatása. Például ha egy fizetési módot, az ER-konfiguráció hivatkozó számlák feldolgozása egy elektronikus fizetési üzenet létrehozásához van kijelölve.

## <a name="concepts"></a>Koncepció
Az ER-konfigurációs életciklus a következő szerepkörök és a kapcsolódó tevékenységek tartoznak.

| Szerep                                       | Tevékenységek                                                      | Leírás                                                                                                                                                                                                                  |
|--------------------------------------------|-----------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Elektronikus jelentések funkcióival foglalkozó konzulens | Hozzon létre és kezeljen egy ER komponenst (modellek és formátumok).           | Üzleti személy, aki tervez ER tartomány-specifikus adatokat modellek, tervek a szükséges elektronikus dokumentumok, sablonok, és ennek megfelelően köti őket.                                                                           |
| Elektronikus jelentések fejlesztője             | Adatmodell hozzárendelések létrehozása és kezelése.                          | A Dynamics 365 műveletek szakember, aki a szükséges Dynamics 365 adatforrások műveletek kiválasztása, és köti őket ER tartomány-specifikus adatokat modellek esetében.                                                                 |
| Számviteli felügyelő                      | Az ER műtermékre hivatkozó folyamathoz kapcsolódó beállítás konfigurálása. | Például egy **számviteli felügyelő** szerepkört, amely lehetővé teszi, hogy az ER-konfiguráció beállításainak egy adott számlák kifizetendő fizetési mód egy elektronikus fizetési üzenet feldolgozására számlák létrehozásához használható. |
| Kötelezettségkifizetési adminisztrátor            | Egy ER műtermék használata egy meghatározott üzleti folyamatban.                | Ha például egy **Kötelezettségkifizetési adminisztrátor** szerepkört, amely lehetővé teszi az üzenetek elektronikus fizetési számlák feldolgozása esetén jön létre alapján az ER-formátum, amely egy speciális fizetési mód van beállítva.           |

## <a name="er-configuration-development-lifecycle"></a>ER konfiguráció fejlesztési életciklusa
A következő, ER rendszerrel kapcsolatos okok miatt javasolt a ER-konfigurációkat a fejlesztői környezetben megtervezni egy különálló 365 for Operations példányként:

-   Az **Elektronikus jelentések fejlesztője** vagy az **Elektronikus jelentések funkcióival foglalkozó konzulens** szerepkörrel rendelkező felhasználók szerkeszthetik a konfigurációkat is futtathatják azokat tesztelés céljából. Olyan osztályok és táblázatok módszereit hívhatja meg, amelyek esetleg károsak lehetnek az üzleti adatokra és a Dynamics 365 for Operations példány használati hatékonyságára nézve.
-   A Dynamics 365 for Operations belépési pontok és naplózott vállalati tartalmak nem korlátozzák az osztály- és táblázatmódszerek ER-konfigurációkhoz tartozó ER-adatforrásokként történő hívását. Tehát a bizalmas üzleti adatokhoz hozzáférnek az **Elektronikus jelentések fejlesztője** vagy az **Elektronikus jelentések funkcióival foglalkozó konzulens** szerepkörrel rendelkező felhasználók.

ER-konfigurációk, amelyek célja a fejlesztési környezetben feltölthetők a tesztkörnyezetben, minőségbiztosítás, például a szerepkör alapú engedélyeket helyességét és szétválasztására és konfigurációs értékelésének (megfelelő integrálása, az eredmények és a teljesítmény). ER konfigurációs adatcserét lehetővé tevő szolgáltatások használható erre a célra. Végül feltölthetők az igazolt ER konfigurációk LCS, ahol azok megosztható a szolgáltatás előfizetői, vagy belső használatra, mint például az alábbi ábrán látható az éles üzemi környezettel. ![ER konfigurációs életciklus](./media/ger-configuration-lifecycle.png)

<a name="see-also"></a>Lásd még
--------

[Elektronikus jelentések áttekintése](general-electronic-reporting.md)


