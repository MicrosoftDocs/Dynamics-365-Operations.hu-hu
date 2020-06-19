---
title: Áttekintés
description: A Dynamics 365 Human Resources alkalmazásban a Szabadság és távollét munkaterület rugalmas keretrendszert biztosít az új szabadságtervek és a kérések kezelésére szolgáló munkafolyamatok létrehozásához, valamint intuitív önkiszolgáló oldalt biztosít az alkalmazottak számára a szabadságok kéréséhez.
author: andreabichsel
manager: AnnBe
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ec72d2d741f7f8428a7daa97bb982e9fc00b8c3f
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/04/2020
ms.locfileid: "3428967"
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

- **Szabadságelhatárolás vállalat vagy a terv szerint** – Az elhatárolási folyamatot akár minden vállalatnál, akár egyetlen vállalatnál is futtathatja. Egy adott vállalatra vonatkozóan is futtathatja az elhatárolási folyamatot egy adott szabadság- és távolléti terv esetében. 

- **Szabadság vásárlása** – Az alkalmazottak számára engedélyezheti és létrehozhatja a szabadságvásárlási irányelveket, hogy elküldjék a vételi kérelmüket. Az alkalmazottak elküldhetik a vásárlási kérelmeket, és automatikusan frissülnek az egyenlegek, hogy tükrözzék a kérelmeket.  

- **Mellékletek hozzáadása a jóváhagyott szabadságkérelmekhez** – A már jóváhagyott szabadságkérelemhez csatolhat egy mellékletet. 

