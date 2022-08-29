---
title: Nyilvántartási azonosítók
description: Ez a cikk a regisztrációs adatok beállításával és használatával kapcsolatban tartalmaz tájékoztatást.
author: kfend
ms.date: 11/08/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.custom: 264824
ms.search.form: DirPartTaxRegistrationSearch, LogisticsPostalAddress, TaxRegistrationLegislationTypes, TaxRegistrationType
ms.openlocfilehash: 380cb1d2b52d5d0debffdbe73183be2f5e783f21
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274551"
---
# <a name="registration-ids"></a>Nyilvántartási azonosítók

[!include [banner](../includes/banner.md)]

Ez a cikk a regisztrációs adatok beállításával és használatával kapcsolatban tartalmaz tájékoztatást.

Számos ország és régió eltérő szabályokkal és követelményekkel rendelkezik az adónyilvántartási számok és azonosítók nyilvántartására. Ez a cikk áttekintést nyújt a különböző európai országok/régiók felei számára szükséges beállításokról és a támogatott regisztrációs típusok feldolgozásról. Minden országban/régióban léteznek követelmények a különböző állami hivatalok által kiadott nyilvántartási számokkal kapcsolatos különböző ország-specifikus funkciók támogatását illetően. Nyilvántartási számok közé tartoznak a társadalombiztosítási szám (TAJ szám), az adóazonosító szám (adószám) és a közösségi adószám. Ez a szolgáltatás egységes keretet biztosít minden régióban minden ország számára, és figyelembe veszi az egyes európai országok országspecifikus követelményeit. Az alábbi szakaszok leírják a nyilvántartási azonosítók létrehozásához és feldolgozásához használt teljes információáramlást.

## <a name="registration-type-creation"></a>Nyilvántartási típus létrehozása
Nyilvántartási azonosító megadása előtt nyilvántartási típusokat kell beállítania az egyes felek által használt különböző nyilvántartási számokhoz. Lépjen a **Szervezeti adminisztráció** &gt; **Globális címjegyzék** &gt; **Nyilvántartástípusok** &gt; **Nyilvántartástípusok** lapra, ahol létrehozat és kezelhet a különböző országokban/régiókban található szállítók, vevők, dolgozók, valamint jogi személyek által használt nyilvántartási típusokat.

|Mező                 |Leírás      |
|------------------------------|----------------------------|                                                                           
| Név                | A nyilvántartási típus neve. |                                                                           
| Leírás         | A nyilvántartási típus leírása. |
| Ország/régió      | Az ország/régió egyedi azonosítója.|
| Adóhatóság       | A nyilvántartási típushoz társított adóhatóság.|
| Korlátozva       | Az adónyilvántartás-típusra vonatkozó korlátozás fajtája: Nincs, Személy, Szervezet.|
| Formátum              | Az nyilvántartástípus ellenőrzési formátuma.|
| Frissíthető      | Azt határozza meg, hogy a nyilvántartási típus nyilvántartási száma frissíthető-e, miután be lett írva.|
| Egyedi              | Azt határozza meg, hogy a nyilvántartási típus nyilvántartási száma egyedi-e. |
| Ország elsődleges címe | Ha valamelyik fél egy vagy több címhez kapcsolódik egy adott országban, és a nyilvántartási azonosító mindezen címekre érvényes, akkor az országnál ki kell jelölni egy címet elsődlegesként. Csak egyetlen azonosító rögzíthető elsődlegesként. Meghatározza, hogy a nyilvántartási számot csak az elsődleges országcímhez lehet-e megadni. |

## <a name="assign-a-registration-type-to-a-registration-category"></a>Nyilvántartási típus hozzárendelése nyilvántartási kategóriához
A nyilvántartási kategória egy olyan ország-/régióalapú nyilvántartási azonosító, amelyet jóváhagytak egy adott országban/régióban adó-, vám- és egyéb célokra. Ez a kategória határozza meg az adott nyilvántartási azonosító érvényesítési szabályait (ellenőrző számjegyeket stb.) és a nyilvántartási azonosító belefoglalását különböző jelentésekbe. Adott ország nyilvántartási típusának hozzárendeléséhez támogatott nyilvántartási kategóriához használja a **Szervezeti adminisztráció** &gt; **Globális címjegyzék** &gt; **Nyilvántartástípusok** &gt; **Nyilvántartási kategóriák** oldalt.

| Mező            | Leírás|
|-----------------------|----------------|
| Regisztráció típusa     | A nyilvántartási típus konkrét országban/régióban.|
| Korlátozva         | Az adónyilvántartás-típusra vonatkozó korlátozás fajtája: Nincs, Személy, Szervezet.|
| Nyilvántartási kategória | Az országban használatra jóváhagyott egyedi nyilvántartási azonosító. A támogatott kategóriák teljes listája ebben a cikkben később jelenik meg. |

## <a name="enter-registration-ids-for-global-address-book-records"></a>Globális címjegyzék nyilvántartási azonosítóinak megadása

A globális címjegyzék vevők, szállítók, partnerek, üzleti kapcsolatok és jogi személyek összevont címadatait tartalmazza. A további tudnivalókat lásd: [Globális címjegyzék áttekintése](../../fin-ops-core/fin-ops/organization-administration/overview-global-address-book.md). A globális címjegyzékben tárolt partnerrekordok egy vagy több címrekordot tartalmazhatnak. Ezeket a címeket különböző – például számlázási vagy szállítási – célokra használják. Nyilvántartási azonosítók beállíthatók vevők, szállítók, dolgozók és jogi személyek címadataihoz. Keresse meg a fél (jogi személy, szállító, vevő, dolgozó) rekordját, amelyhez meg kívánja adni a nyilvántartási azonosítót, majd kattintson a **Regisztrációs azonosítók** elemre a fél, jogi személy, szállító, vevő, dolgozó űrlapján a **Címek kezelése** oldal megnyitásához. Az **Adóregisztráció** lapon kattintson a **Hozzáadás** elemre, és adja meg a következő információkat a nyilvántartási azonosítóhoz.


|Mező                |Leírás                                                |
|---------------------|-----------------------------------------------------------|
| Regisztráció típusa   | A nyilvántartási típus a kiválasztott országban/régióban.     |
| Regisztrációs szám | A fél nyilvántartási azonosítója.                                |
| Leírás         | A nyilvántartási szám leírása.               |
| Szakasz             | A nyilvántartási számmal kapcsolatos további információk. |
| Kibocsátó ügynökség      | A nyilvántartási számot kiadó hatóság.        |
| Kiállítás dátuma         | A nyilvántartási szám kibocsátásának dátuma.              |
| Hatályos           | A nyilvántartási szám hatálybalépésének dátuma.           |
| Lejárat          | A nyilvántartási szám lejárati dátuma.          |

> [!NOTE]
> A jogi személy, szállító, vevő adómentességi számát a félnél megadott, az áfaazonosítóhoz kapcsolódó nyilvántartási azonosítóból lehet kiválasztani.

## <a name="search-for-records-by-registration-id"></a>Rekordok keresése nyilvántartási azonosító alapján
A felek rekordjainak keresése nyilvántartási azonosító alapján a fél, jogi személy, szállító, vevő és dolgozó adott űrlapján érhető el. Kattintson a **Regisztrációs azonosító keresése** elemre a **Regisztrációs azonosító keresési feltételei** lap megnyitásához. Adja meg a keresési feltételeket, és kattintson a **Keresés** elemre. A rendszer megjeleníti a kijelölt rekordokat a globális címjegyzékből és a fél hozzá tartozó típusú rekordjait.

## <a name="supported-registration-categories"></a>Támogatott nyilvántartási kategóriák
A következő táblázat felsorolja a támogatott regisztrációtípusokat. Ha jól ismeri a Microsoft Dynamics AX 2012-es adóregisztrációs mezőket, ez a tábla a mezőket a Dynamics 365 Pénzügy regisztrációs kategóriáihoz is leképezi.

| Finance nyilvántartási kategória         |Ország/régió  | Dynamics AX 2012 kifejezés/mező|
|---------------------------------------------------------------|---------------------|---------------------------------|
| Áfaazonosító                                                        | Az Európai Unió (EU) összes országa|  Adómentességi szám (jogszabályon alapuló típusú adóazonosító az AX 2012 R3-ban)|
| Vállalatazonosító (COID)                                          | Belgium Csehország Észtország Magyarország Lettország Litvánia Lengyelország Svájc | Vállalati szám (EnterpriseNumber) nyilvántartási szám (RegNum\_W) nyilvántartási szám (RegNum\_W) nyilvántartási szám (RegNum\_W) nyilvántartási szám (RegNum\_W) vállalati kód (EnterpriseCode) nyilvántartási szám (RegNum\_W) UID (jogszabályon alapuló típusú UID az AX 2012 R3-ban) |
| Fiókazonosító                                                     | Belgium            | Ágazati szám (BranchNumber)|
| Spisová značka (nyilvántartási szám, kiállító hivatal, szakasz) | Cseh Köztársaság     | Betétlap száma (CommercialRegisterInsetNumber) nyilvántartja a kereskedelmi cégjegyzék (CommercialRegister) kereskedelmi cégjegyzék szakasza (CommercialRegisterSection)|
| Vámhivatali vevőazonosító                                           | Finnország | Vámhivatali vevőszám (CustomsCustomerNumber\_FI)|
| Adóazonosító                                                           | Orosz Föderáció| INN (jogszabályon alapuló INN típus az AX 2012 R3-ban)|
| Regisztrációs okkód                                                           | Orosz Föderáció| RRC (jogszabályon alapuló RRC típus az AX 2012 R3-ban)|
| OKDP                                                          | Orosz Föderáció| OKDP (jogszabályon alapuló OKDP típus az AX 2012 R3-ban)|
| OKPO                                                          | Orosz Föderáció| OKPO (jogszabályon alapuló OKPO típus az AX 2012 R3-ban)|
| RCOAD                                                         | Orosz Föderáció| RCOAD (jogszabályon alapuló RCOAD típus az AX 2012 R3-ban)|
| OGRN                                                          | Orosz Föderáció| OGRN (jogszabályon alapuló OGRN típus az AX 2012 R3-ban) |
| SNILS                                                         | Orosz Föderáció| SNILS (jogszabályon alapuló SNILS típus az AX 2012 R3-ban)|
| CIFTS                                                         | Orosz Föderáció| CIFTS (jogszabályon alapuló CIFTS típus az AX 2012 R3-ban)|
| Útlevél                                                      | Spanyolország             | Útlevél|
| Hivatalos azonosító dokumentum                              | Spanyolország             | Hivatalos azonosító dokumentum|
| Tartózkodási igazolás                                         | Spanyolország             | Tartózkodási igazolás|
| Egyéb azonosító dokumentum                                 | Spanyolország             | Egyéb azonosító dokumentum|
| Nem összeírt                                                  | Spanyolország             | Nem érhető el az AX 2012 R3 esetében|


A nyilvántartási azonosítók feldolgozásával kapcsolatos további információkért, ideértve a szükséges előfeltételeket, nézze meg az áfaazonosítóhoz kapcsolódó következő feladatrögzítéseket a Lifecycle Services (LCS) szolgáltatásban:

-   Áfaazonosító beállítása
-   Szállítói áfaazonosító rögzítése
-    Fél keresése adószám használatával






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
