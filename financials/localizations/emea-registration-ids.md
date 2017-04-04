---
title: "Nyilvántartási azonosítók"
description: "Ez a témakör arról szól, beállításával és használatával a regisztrációs azonosítót."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: DirPartTaxRegistrationSearch, LogisticsPostalAddress, TaxRegistrationLegislationTypes, TaxRegistrationType
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 264824
ms.assetid: e86f0a35-be58-4ef5-b5ab-bcfc495eaa13
ms.search.region: Global
ms.author: vlru
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 32cd09975861083b8940368ed53ae16e89bcd748
ms.lasthandoff: 03/31/2017


---

# <a name="registration-ids"></a>Nyilvántartási azonosítók

Ez a témakör arról szól, beállításával és használatával a regisztrációs azonosítót.

Sok országok és régiók eltérő szabályozás és a nyilvántartási számokat vagy azonosítók rögzítésére vonatkozó követelmények rendelkezik. Ez a témakör a szükséges beállításokat és feldolgozása támogatott regisztráció-típusok áttekintése a felek különböző európai országokban/régiókban. Minden országban/régióban van kapcsolódó nyilvántartási számok különböző állami hivatalok által nyújtott különböző ország-specifikus funkciók támogatásához szükséges követelményeknek. Nyilvántartási számok közé, adóazonosító szám (TIN), Európai Áfa azonosítója az EU áfa és a társadalombiztosítási szám (SSN). Ez a szolgáltatás egységes keretet biztosít minden ország minden területen az egyes európai országok ország-specifikus követelmények figyelembevételével. Az alábbi szakaszok ismertetik az általános információáramlást használt beállítása és feldolgozása a regisztrációs azonosítót.

## <a name="registration-type-creation"></a>Regisztráció-típus létrehozása
Mielőtt a regisztrációs Azonosítót adhat meg, be kell állítania a nyilvántartási számokat, amelyek minden fél hatálya alá tartoznak a különböző típusaihoz. Ugrás a **szervezet felügyelete**&gt;**globális címjegyzék**&gt;**típusaihoz**&gt;**típusaihoz** lapon hozhatja létre és kezelheti a típusaihoz szállítók, vevők, dolgozók, valamint a jogi személyek különböző országokban/régiókban.

|Mező                 |Leírás      |
|------------------------------|----------------------------|                                                                           
| Név                | A regisztráció típusának neve. |                                                                           
| Leírás         | A regisztrációtípus leírása. |
| Ország/régió      | Az ország/régió egyedi azonosítója.|
| Adóhatóság       | Az adóhatóság a Regisztrációtípus társított.|
| Korlátozva       | Milyen típusú korlátozást, amely vonatkozik az adószám: nincs, személy, szervezet.|
| Formátum              | A Regisztrációtípus ellenőrzési formátuma.|
| Frissíthető      | Meghatározza, hogy a nyilvántartási számot, a regisztrációs típus frissíthető, miután be lett írva.|
| Egyedi              | Ha a nyilvántartási számot, a regisztrációs típus egyedi határozza meg. |
| Ország elsődleges címe | Ha valamelyik fél kapcsolódik egy vagy több címet különösen ország és a regisztrációs azonosító érvényes ezekre a címekre, ki kell jelölnie egy cím ország elsődleges. Rögzítheti egy azonosító csak elsődlegesként. Meghatározza, hogy a nyilvántartási számot csak elsődleges ország cím megadható. |

## <a name="assign-a-registration-type-to-a-registration-category"></a>A regisztráció a regisztráció típusa kategorizálás
Regisztrálás kategória ország regisztrációs azonosító használata különösen ország adó-, vám- és egyéb célokra engedélyezett érték. Ez a kategória érvényesítési szabályok különösen regisztrációs (beleértve az ellenőrző számjegy stb.) és a felvételt regisztrációs azonosító különböző jelentések határozza meg. Ezen a lapon **szervezet felügyelete**&gt;**globális címjegyzék**&gt;**típusaihoz**&gt;**nyilvántartási kategóriák** adott ország regisztrációs típusának hozzárendelése támogatott regisztrálás kategória.

| Mező            | Leírás|
|-----------------------|----------------|
| Regisztráció típusa     | A regisztráció különösen ország adja.|
| Korlátozva         | Milyen típusú korlátozás vonatkozik az adószám: nincs, személy, szervezet.|
| Nyilvántartási kategória | Az ország a jóváhagyott egyedi regisztrációs azonosítója. A teljes listát a támogatott AX7.1 a kategóriák alatt van. |

## <a name="enter-registration-ids-for-global-address-book-records"></a>Adja meg a regisztrációs azonosítót globális cím könyv rekordok
A Microsoft Dynamics 365 műveletekhez a globális címjegyzékben (GAB) vevők, szállítók, partnerek, üzleti kapcsolatok és jogi személyek konszolidált cím adatait tartalmazza. A további tudnivalókat lásd [globális cím könyv áttekintés](/dynamics365/operations/organization-administration/overview-global-address-book). A fél rekordok a globális címjegyzékben tárolt egy vagy több címet bejegyzést tartalmazhat. Ezeket a címeket különböző – például számlázási vagy szállítási – célokra használják. Beállíthatja a vevők, szállítók, a munkavállalók és a jogi személyek címadatainak azonosítók regisztrációja. (Jogi személy, szállító, vevő, dolgozó) fél rögzíteni, amelynek Azonosítóját adja meg, és kattintson a kívánt keresési **regisztrációs azonosítók** fél, jogi személy, szállító, vevő, a munkavállaló számára, hogy nyissa meg a kapcsolódó űrlap a **címek kezelése** oldalon. A a **regisztrációs adó** fülre, kattintson a **hozzáadása**, és adja meg a következő információkat talál a regisztrációs azonosítót.

|Mező                |Leírás                                                |
|---------------------|-----------------------------------------------------------|
| Regisztráció típusa   | A regisztráció mezőbe írja be a kijelölt országhoz/területhez.     |
| Regisztrációs szám | A fél regisztrációs azonosítót.                                |
| Leírás         | A nyilvántartási számot leírása.               |
| Szakasz             | A további információt a regisztrációs számot. |
| Kibocsátó ügynökség      | A hatóság a kibocsátó a regisztrációs szám.        |
| Kiállítás dátuma         | A kiállítás dátuma, nyilvántartási számára.              |
| Hatályos           | A nyilvántartási számot érvényességi dátuma.           |
| Lejárat          | A nyilvántartási szám lejárati dátuma.          |

> [!NOTE]
> Jogi személy, szállító, vevő adómentességi száma a regisztrációs lehet kiválasztani az adó azonosítók azonosítójához kapcsolódó, és a fél adott.

## <a name="search-for-records-by-registration-id"></a>Regisztrációs azonosító rekordok keresése
Fél bejegyzéseket a regisztrációs azonosító alapján kereshet a fél, jogi személy, szállítói, vevői és dolgozói kapcsolódó űrlapok érhető el. Kattintson a **regisztrációs Számot keresési** megnyitása a **regisztrációs Számot keresési feltételek** lap. Adja meg a keresési feltételeket, és kattintson a **található**. A rendszer a kijelölt rekordok a globális címjegyzékben és a hozzá tartozó típusú címjegyzékrekord jeleníti meg.

## <a name="supported-registration-categories"></a>Támogatott regisztrációs kategóriák
Az alábbi táblázat a támogatott típusaihoz Dynamics 365 műveletekhez. Megismerkedtünk a Microsoft Dynamics AX 2012 regisztrációs azonosító mezőket, ha ezt a táblát is rendeli ezeket a mezőket a Dynamics 365 műveletek regisztrációs kategóriák.

| 365 Dynamics műveletek regisztrációs kategória         |Ország/régió  | A Dynamics AX 2012 kifejezés/mező|
|---------------------------------------------------------------|---------------------|---------------------------------|
| Áfaazonosító                                                        | Minden ország az Európai Unió (EU)|  Adómentességi szám (az AX2012 R3 Adóazonosító jogalkotási típus)|
| Vállalatazonosító (COID)                                          | Belgium, Cseh Köztársaság Észtország Magyarország Lettország Litvánia Lengyelország Svájc | Vállalati szám (EnterpriseNumber) nyilvántartási szám (RegNum\_W) nyilvántartási szám (RegNum\_W) nyilvántartási szám (RegNum\_W) nyilvántartási szám (RegNum\_W) vállalati kód (EnterpriseCode) nyilvántartási szám (RegNum\_W) UID (UID AX2012 R3 a jogalkotási típus) |
| Fiókazonosító                                                     | Belgium            | Ágazati szám (BranchNumber)|
| Spisová značka (regisztrációs szám a kiállító hivatal szakasz) | Cseh Köztársaság     | Szám (CommercialRegisterInsetNumber) Kept szövegbe beszúrt kereskedelmi cégjegyzék (CommercialRegisterSection) (CommercialRegister) szakasza regisztrálása|
| Vámhivatali vevőazonosító                                           | Finnország | Vámhivatali vevőszám (CustomsCustomerNumber\_FI)|
| Adóazonosító                                                           | Orosz Föderáció| INN (az AX2012 R3 INN jogalkotási típus)|
| Regisztrációs okkód                                                           | Orosz Föderáció| Regisztrációs OKKÓD (jogszabályi AX2012 R3 a regisztrációs Okkódja. típus)|
| OKDP                                                          | Orosz Föderáció| OKDP (az AX2012 R3 OKDP jogalkotási típus)|
| OKPO                                                          | Orosz Föderáció| OKPO (az AX2012 R3 OKPO jogalkotási típus)|
| RCOAD                                                         | Orosz Föderáció| RCOAD (RCOAD AX2012 R3 a jogalkotási típus)|
| OGRN                                                          | Orosz Föderáció| OGRN (OGRN a AX2012 R3 jogalkotási típus) |
| SNILS                                                         | Orosz Föderáció| SNILS (SNILS a AX2012 R3 jogalkotási típus)|
| CIFTS                                                         | Orosz Föderáció| CIFTS (CIFTS a AX2012 R3 jogalkotási típus)|

Feldolgozás, beleértve a szükséges előfeltételek regisztrációs azonosítók további információt talál a következő feladat felvétel áfa Azonosítót életciklus-szolgáltatások (LCS):

-   Áfaazonosító beállítása
-   Szállító áfa Azonosítót regisztráció
-    Fél keresése adószám használatával



