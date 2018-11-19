---
title: "Biztonság és szerepkörök kezelése az Attract alkalmazásban"
description: "Ez a témakör a Microsoft Dynamics 365 for Talent - Attract szerepkör szerinti biztonságáról ad tájékoztatást."
author: josaw1
manager: AnnBe
ms.date: 10/18/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: josaw1
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.translationtype: HT
ms.sourcegitcommit: 0450326dce0ba6be99aede4ebc871dc58c8039ab
ms.openlocfilehash: 9eb12bd6b9fc1aa66002908e5989b3ac504ab673
ms.contentlocale: hu-hu
ms.lasthandoff: 11/01/2018

---

# <a name="security-and-role-management-in-attract"></a>Biztonság és szerepkörök kezelése az Attract alkalmazásban

[!include[banner](../includes/banner.md)]

Microsoft Dynamics 365 for Talent: Attract szerepköralapú biztonságot használ. Más szóval a hozzáférést nem egyéni felhasználókhoz rendeli, hanem biztonsági szerepkörökhöz, amelyekhez a felhasználók hozzá vannak rendelve. Biztonsági szerepkörhöz hozzárendelt felhasználó hozzáfér a szerepkörhöz társított jogosultságok csoportjához.

Az Attract öt alapvető felhasználói szerepkört nyújt:

- Rendszergazda
- Felvételi vezető
- Toborzó
- Interjúkészítő
- Csak olvasható

A rendszergazdai szerepkörnek van csak engedélye, hogy más felhasználókat hozzáadjon, illetve módosítsa az engedélyeiket.

- **Hozzáadás** – A felügyeleti központban meg a **Felhasználói jogosultságok** lapon jelölje be a **Szerepkörök hozzárendelése** lehetőséget, keresse meg a hozzáadandó felhasználót, majd ezután rendelhet engedélyeket a felhasználóhoz.
- **Szerkesztés** – Keressen a felhasználóra, vagy keresse meg felhasználót a listában, és válassza ki a **Szerkesztés** lehetőséget az engedélyek módosításához.
- **Törlés** – Ha törli a felhasználó engedélyeit, azzal a felhasználót nem eltávolítja a rendszerből. Azonban a felhasználó hozzáférését korlátozza az Attract jogosultságaihoz. Például a humánerőforrás-vezető szerepkörhöz van rendelve Hilda, és felvételi vezetőként van egy feladathoz hozzáadva. Ha Hildát a humánerőforrás-vezető szerepkörből később eltávolítják, felvételi vezető marad, és feladathoz továbbra is hozzáférhet. Azonban nem hozhat létre más feladatokat.

A következő szakaszok ismertetik az egyes szerepkörök részletes leírását. A témakör későbbi szakaszában található táblázatok részletesebb tájékoztatást adnak.

> [!NOTE]
> Bizonyos funkciók csak az Átfogó felvételi bővítménnyel érhetők el az Attractben.

## <a name="administrator"></a>Rendszergazda

A rendszergazda szerepkörhöz rendelt felhasználók elérhetik és módosíthatják és az összes adatot Attract programban. Rendszergazdák létrehozhatnak, olvashatnak, frissíthetnek, és törölhetnek adatokat. Hozzáférhetnek a Felügyeleti központhoz is ahol konfigurálhatják az Attract alkalmazást, és beállíthatnak felhasználói információkat. Azt ajánljuk, hogy legalább egy személy legyen a Rendszergazda szerepkörhöz rendelve. Alapértelmezés szerint a Microsoft PowerApps a környezeti rendszergazdája Attract-rendszergazdaként van beállítva. Mennyiben az Attract próbaverziójára regisztrált, a rendszergazda szerepkört automatikusan Önhöz van rendelve. Jelenleg a feladatok létrehozásához, a rendszergazdai szerepkörrel rendelkező felhasználóknak rendelkezniük kell Toborzó vagy Felvételi vezető szerepkörrel is.

## <a name="hiring-manager"></a>Felvételi vezető

A Felvételi vezető szerepkörhöz hozzárendelt felhasználók feladatok létrehozhatják és frissíthetik a feladatokat, amelyeket korábban létrehoztak. A Felvételi vezetők csak korlátozott műveleteket végezhetnek el egy feladaton és a feladathoz kapcsolódó alkalmazásokban. Csak a Felvételi vezető szerepkörhöz rendelt felhasználók adhatók egy toborzócsapathoz felvételi vezetőként.

## <a name="recruiter-role"></a>Toborzó szerepkör

A toborzó szerepkörhöz hozzárendelt felhasználók rendelkeznek-e teljes olvasási, létrehozási, frissítési és törlési jogosultságokkal az általuk létrehozott feladatokkal kapcsolatosan. Mindemellett teljes létrehozási, olvasási, frissítési és törlési jogosultságaik vannak azon feladatokhoz kapcsolódó alkalmazásokban, amelyeket a tulajdonosai. Csak a Toborzó szerepkörhöz rendelt felhasználók adhatók egy toborzócsapathoz toborzóként.

## <a name="interviewer"></a>Interjúkészítő

Bármely felhasználó, aki Microsoft Azure Active Directory (Azure AD) fiókkal rendelkezik a szervezeteben hozzáadható a toborzócsoporthoz interjúkészítőként Az interjúkészítő szerepkörhöz hozzárendelt felhasználók feladat részleteit és a pályázók adatait azon feladatokhoz, amelyekre vonatkozóan a toborzócsapat tagjai. Azokn feladatok esetében az interjúkészítők felvételi ajánlásokat adhatnak és a pályázókkal kapcsolatban is adhatnak visszajelzést. Azonban nem frissíthetik a pályázók adatait és a feladat részleteit.

## <a name="read-only"></a>Csak olvasható

A Csak olvasható szerepkörhöz hozzárendelt felhasználók csak olvasási hozzáféréssel rendelkeznek minden adathoz az Attract környezetben. Azonban nem hozhatnak létre és szerkeszthetnek adatokat.

## <a name="delegated-roles"></a>Delegált szerepkörök

A toborzók és felvételi vezetők minden egyes feladathoz, ahol a toborzócsapat tagjai egy vagy több delegáltat jelölhetnek ki saját maguk helyett. Azonban a felvételi csapat más tagjaihoz nem jelölhetnek ki delegáltakat.

Delegáltak jogosultságai megegyeznek azzal a személyével, aki a kijelölt őket. Például, ha egy Felvételi vezető egy delegáltat jelöl ki maga helyett egy feladathoz, a delegált a felvételi vezetőével megegyező jogosultságokat kap a feladathoz. Delegáltak nem törölhetnek más delegáltakat a toborzócsoportból Illetve nem távolíthatják ez azokat az embereket, akik delegáltnak jelölték ki őket.

## <a name="job-details-and-actions"></a>Feladat részletei, és műveletek

A Toborzó vagy Humánerőforrás-vezető szerepkörrel rendelkező felhasználók hozhatnak létre feladatokat. A következő jogosultságok feladat részletes adataira, és a feladaton végrehajtott műveletekre vonatkoznak.

| Adat vagy művelet    | Toborzó | Felvételi vezető | Interjúkészítő |
|-------------------|-----------|----------------|-------------|
| Feladat részletei       | Létrehozás, olvasás, frissítés és törlés azon feladatokkal kapcsolatban, ahol a felhasználó a toborzócsoport tagja | Létrehozás, olvasás, frissítés és törlés azon feladatokkal kapcsolatban, ahol a felhasználó a toborzócsoport tagja | Csak olvasható |
| Toborzó csapat       | Létrehozás, olvasás, frissítés és törlés azon feladatokkal kapcsolatban, ahol a felhasználó a toborzócsoport tagja | Létrehozás, olvasás, frissítés és törlés azon feladatokkal kapcsolatban, ahol a felhasználó a toborzócsoport tagja | Csak olvasható |
| Álláshirdetés       | Létrehozás, olvasás, frissítés és törlés azon feladatokkal kapcsolatban, ahol a felhasználó a toborzócsoport tagja | Csak olvasható | Csak olvasható |
| Feldolgozás           | Létrehozás, olvasás, frissítés és törlés azon feladatokkal kapcsolatban, ahol a felhasználó a toborzócsoport tagja | Létrehozás, olvasás, frissítés és törlés azon feladatokkal kapcsolatban, ahol a felhasználó a toborzócsoport tagja | Csak olvasható |
| Pályázók hozzáadása    | Pályázók hozzáadása azon feladatokhoz, amelyek esetében a felhasználó a toborzócsoport tagja | Pályázók hozzáadása azon feladatokhoz, amelyek esetében a felhasználó a toborzócsoport tagja | Nem engedélyezett |
| Jelöltek hozzáadása     | Jelöltek hozzáadása azon feladatokhoz, amelyek esetében a felhasználó a toborzócsoport tagja | Egy konfigurációs beállítással a [jelölttel kapcsolatos tevékenység beállítása](./activities-attract.md#prospect-activity) helyen kezelheti hogy az interjúkészítők hozzáadhatnak vagy megtekinthetnek-e jelölteket. | Nem engedélyezett |
| Feladat aktiválása      | Azon feladatok aktiválása, amelyek esetében a felhasználó a toborzócsoport tagja | Azon feladatok aktiválása, amelyek esetében a felhasználó a toborzócsoport tagja | Nem engedélyezett |
| Állás bezárása         | Azon feladatok lezárása, amelyek esetében a felhasználó a toborzócsoport tagja | Nem engedélyezett | Nem engedélyezett |
| Feladat törlése        | Azon feladatok törlése, amelyek esetében a felhasználó a toborzócsoport tagja | Csak akkor, ha nem lettek pályázók hozzáadva a feladathoz | Nem engedélyezett |
| Pályázók törlése | Pályázók törlése, ha a felhasználó a toborzócsoport tagja | Nem engedélyezett | Nem engedélyezett |

## <a name="application-details-and-actions"></a>Pályázók részletei, és műveletek

A következő jogosultságok a pályázókra vonatkozó feladatspecifikus adatokra vonatkoznak, és a pályázaton végrehajtott műveletekre vonatkoznak.

| Adat vagy művelet          | Toborzó | Felvételi vezető | Interjúkészítő |
|-------------------------|-----------|----------------|-------------|
| Pályázati dokumentumok   | Létrehozás, olvasás, frissítés és törlés azon feladatokkal kapcsolatban, ahol a felhasználó a toborzócsoport tagja | Létrehozás, olvasás, frissítés és törlés azon feladatokkal kapcsolatban, ahol a felhasználó a toborzócsoport tagja | Csak olvasható |
| Pályázati jegyzetek       | Létrehozás, olvasás, frissítés és törlés azon feladatokkal kapcsolatban, ahol a felhasználó a toborzócsoport tagja | Létrehozás, olvasás, frissítés és törlés azon feladatokkal kapcsolatban, ahol a felhasználó a toborzócsoport tagja | Létrehozás |
| Pályázat aktivitása    | Megtekintés, ha a felhasználó a toborzócsoport tagja | Megtekintés, ha a felhasználó a toborzócsoport tagja | Csak olvasható |
| Pályázati visszajelzés    | Visszajelzések adása és megtekintése, ha a felhasználó a toborzócsapat tagja | Visszajelzések adása és megtekintése, ha a felhasználó a toborzócsapat tagja | Visszajelzést adhat hozzá.\*\* |
| Pályázat elutasítása      | Elutasíthat, ha a felhasználó a toborzócsoport tagja | Nem engedélyezett | Nem engedélyezett |
| Szakasz előreléptetése           | Elutasíthat, ha a felhasználó a toborzócsoport tagja | Előreléptethet, ha a felhasználó a toborzócsoport tagja | Nem engedélyezett |
| Ajánlatkezelés indítása | Elindíthatja ajánlatkezelést | Tartozik egy konfigurációslehetőség az ajánlat tevékenységhez. | Nem engedélyezett |

\*\* Egy konfigurációs beállítás a [visszajelzés tevékenység beállítása](./activities-attract.md#feedback-activity) helyen szabályozza, hogy az interjúkészítők láthatják-e egymás a visszajelzéseit.

## <a name="process-templates"></a>Folyamatsablonok

A következő jogosultságok a toborzásifolyamat-sablonokra érvényesek. Az, hogy a csapatagok létrehozhatnak és szerkeszthetnek-e sablonokat a **Sablonkezelés** helyen szabályozható a Felügyeleti központban. Ha a sablonkezelés engedélyezve van, a toborzók és felvételi vezetők létrehozhatják és szerkeszthetik saját folyamatsablonjaikat. Ha a sablonkezelés ki van kapcsolva, csak a rendszergazdák hozhatnak létre és szerkeszthetnek folyamatsablonokat. Az alábbi táblázat azt feltételezi, hogy a sablonkezelés be van kapcsolva.

| Adat              | Toborzó                                           | Felvételi vezető                                      | Interjúkészítő |
|-------------------|-----------------------------------------------------|-----------------------------------------------------|-------------|
| Folyamatsablonok | Teljes jogosultságok a felhasználó által létrehozott sablonokhoz | Teljes jogosultságok a felhasználó által létrehozott sablonokhoz | Nincs hozzáférés   |

## <a name="email-and-email-templates"></a>E-mail és e-mail-sablonok

A következő jogosultságok az e-mail sablonokra, és az e-maileken végrehajtott műveletekre vonatkoznak. Csak a rendszergazdák hozhatnak létre és szerkeszthetnek e-mail-sablonokat.

| Adat vagy művelet     | Toborzó          | Felvételi vezető     | Interjúkészítő |
|--------------------|--------------------|--------------------|-------------|
| E-mail-sablonok    | Csak olvasási hozzáférés   | Csak olvasható hozzáférés   | Nincs hozzáférés   |
| E-mail küldése         | Küldés tevékenységenként  | Küldés tevékenységenként  | Nincs hozzáférés   |
| E-mail-tartalom szerkesztése | E-mail-tartalom szerkesztése | E-mail-tartalom szerkesztése | Nincs hozzáférés   |

## <a name="talent-pools"></a>Tehetségállományok

A következő jogosultságok a tehetségállományokra vonatkoznak. A tehetségállományok csak azon csak az személy számra láthatók, aki létrehozta őket, kivéve, ha az adott személy úgy dönt, hogy megosztja azokat. A jelöltkereső azon jelöltek keresésére használható, akik még nem lettek hozzáadva egy névvel ellátott állományhoz.

| Adat vagy művelet   | Toborzó                                       | Felvételi vezető                                  | Interjúkészítő |
|------------------|-------------------------------------------------|-------------------------------------------------|-------------|
| Elnevezett állomány       | Teljes jogosultságok a felhasználó által létrehozott állományokhoz | Teljes jogosultságok a felhasználó által létrehozott állományokhoz | Nincs hozzáférés   |
| Állomány megosztása       | Csak a felhasználó által létrehozott állományok                | Csak a felhasználó által létrehozott állományok                | Nincs hozzáférés   |
| Jelöltkereső | Teljes keresési funkcionalitás                        | Teljes keresési funkcionalitás                        | Nincs hozzáférés   |

## <a name="candidates"></a>Pályázók

A jelöltek azok a személyek akik hozzá lettek adva a tehetségállományhoz, de nem lettek társítva egy feladathoz.

| Adat                        | Toborzó                        | Felvételi vezető                   | Interjúkészítő |
|-----------------------------|----------------------------------|----------------------------------|-------------|
| Profil – jelöltek adatai | Létrehozás, olvasás, frissítés és törlés | Létrehozás, olvasás, frissítés és törlés | Nincs hozzáférés   |
| Bizonylatok                   | Létrehozás, olvasás, frissítés és törlés | Létrehozás, olvasás, frissítés és törlés | Nincs hozzáférés   |

