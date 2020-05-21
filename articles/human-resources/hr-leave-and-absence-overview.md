---
title: Áttekintés
description: A Dynamics 365 Human Resources alkalmazásban a Szabadság és távollét munkaterület rugalmas keretrendszert biztosít az új szabadságtervek és a kérések kezelésére szolgáló munkafolyamatok létrehozásához, valamint intuitív önkiszolgáló oldalt biztosít az alkalmazottak számára a szabadságok kéréséhez.
author: andreabichsel
manager: AnnBe
ms.date: 04/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2bb123b808615ff7d770c7c6b83338a32d922be3
ms.sourcegitcommit: de217452a85429675994e9cc0e06eb4821cab3e5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/30/2020
ms.locfileid: "3325765"
---
# <a name="overview"></a>Áttekintés

A Dynamics 365 Human Resources segítségével kiváló szabadságjuttatásokat biztosíthat a dolgozók számára. A **Szabadság és távollét** munkaterület rugalmas keretrendszert biztosít az új szabadságtervek és a kérések kezelésére szolgáló munkafolyamatok létrehozásához, valamint intuitív önkiszolgáló oldalt biztosít az alkalmazottak számára a szabadságok kéréséhez. Az elemzés segítséget nyújt a szervezet számára a szabadságegyenlegek és a szabadságtervek használatának méréséhez és figyeléséhez.

## <a name="set-up-leave-and-absence"></a>Szabadság és távollét beállítása

Mielőtt létrehozza a szabadságterveket az alkalmazottak számára, végre kell hajtania néhány beállítási lépést:

- [Szabadság- és távollétparaméterek konfigurálása](hr-leave-and-absence-parameters.md)
- [Munkaidőnaptár létrehozása](hr-leave-and-absence-working-time-calendar.md)
- [Szabadságkérelem munkafolyamat létrehozása](hr-leave-and-absence-workflow.md)

## <a name="create-and-manage-leave-plans"></a>Szabadságtervek létrehozása és kezelése

Mielőtt létrehozza a szabadságterveket a dolgozók számára, létre kell hoznia a szabadság- és távolléttípusokat. Miután létrehozta a szabadságtervet, elkezdheti beléptetni a dolgozókat a tervbe. Ezenkívül futtathatja a könyvelési folyamatot, figyelmeztetéseket hozhat létre, és megtekintheti a tervekhez tartozó elemzéseket.

- [Szabadság- és távolléttípusok konfigurálása](hr-leave-and-absence-types.md)
- [Szabadság- és távolléti terv létrehozása](hr-leave-and-absence-plans.md)
- [Alkalmazottak hozzárendelése a szabadságtervhez](hr-leave-and-absence-enroll.md)
- [Szabadság- és távolléti tervek elhatárolása](hr-leave-and-absence-accrue.md)
- [A szabadság és távollét elemzésének megtekintése](hr-leave-and-absence-analytics.md)

## <a name="request-time-off-and-manage-requests"></a>Szabadság kérése és a kérelmek kezelése

Az **Alkalmazotti önkiszolgáló rendszer** munkaterületen az alkalmazottak elküldhetik a szabadságra vonatkozó kérelmeiket, Ön pedig kezelheti a kérelmeket.

- [Távollét kérelmezése](hr-employee-self-service-request-time-off.md)
- [Szabadság- és távollétkérelmek kezelése](hr-employee-self-service-manage-requests.md)

## <a name="leave-and-absence-known-issues"></a>A Szabadság és távollét ismert problémái

### <a name="rounding-precision"></a>Kerekítési pontosság

**Kerekítési típus** megadása esetén a **Kerekítési pontosság** nem állítható be. A **Kerekítési pontosságot** csak a **Szabadság és a távollét típusa** entitás használatával lehet megadni. 

1. A **Szabadság és távollét típusok** alatt válassza a **Megnyitás Excelben** lehetőséget a **Szabadság és távollét típusa** entitás megnyitásához.

2. Miután a fájl megnyílik és engedélyezve van, válassza a **Tervezés** elemet.

3. A **Szabadság és távolét típusa** táblában válassza ki a ceruza lehetőséget a szerkesztéshez.

4. Válassza ki a **RoundingPrecision** és a **RoundingType** elemeket, majd válassza a **Hozzáadás** lehetőséget a hozzáadáshoz a mezőlistához.

5. Válassza a **Frissítés** majd a **Kész** elemet.

6. Adja meg vagy válassza ki a **Kerekítési típust** minden egyes szabadságtípusnál, ha még nincsenek beállítva. 

7. Adja meg a **Kerekítési pontosságot** a megfelelő típusokhoz.

8. Válassza a **Közzététel** lehetőséget, ha a változások átküldéséhez a Human Resources alkalmazásba.

## <a name="leave-and-absence-preview-features"></a>Szabadság és távollét előzetes funkciói

A **Tesztkörnyezet** segítségével kipróbálhatja a szabadságok és távollétek új előzetes funkcióit. Az előzetes funkciók bekapcsolásával kapcsolatos információt lásd a [Szolgáltatások kezelése](hr-admin-manage-features.md) című témakörben. 

[!include [banner](includes/preview-feature.md)]

Az előzetes funkciók a következők:

- **Szabadság felfüggesztése** – Egy alkalmazottra vonatkozóan felfüggesztheti a szabadságokat és a távollétet. A szabadság felfüggesztése kiválasztott távolléti típusoknál leállítja az elhatárolást. Ha a felfüggesztés a könyvelés feldolgozását követően következik be, akkor a szabadság felfüggesztése az alkalmazott szabadságának egyenlegéhez egy arányosan korrigált kiigazítást hoz létre. Az alkalmazottak szabadságának felfüggesztése során okkódok is megadhatók. A felhasználói élmény frissítve lett a felfüggesztés jelzéséhez. 

- **Átviteli szabályok** – Megadhatja, hogy az átviteli szabadságtípust az átviteli egyenlegekhez, ahová az átviteli korrekciók át lesznek helyezve. Ha például egy alkalmazott 10 napot visz át, akkor a 10 napnál más szabadság-típust is kiválaszthat. 

- **Okkódok és megjegyzések hozzáfűzése a módosításokhoz** – Az alkalmazotti szabadság egyenlegének módosításakor egy okkódot és megjegyzést is megadhat. 

- **Átállás a szabadság és távollét paramétereire** – Mostantól csak a szabadság és a távollét paraméterei használhatók a humán erőforrások paramétereinek használata helyett. 
