---
title: Áttekintés
description: A Dynamics 365 Human Resources alkalmazásban a **Szabadság és távollét** munkaterület rugalmas keretrendszert biztosít az új szabadságtervek és a kérések kezelésére szolgáló munkafolyamatok létrehozásához, valamint intuitív önkiszolgáló oldalt biztosít az alkalmazottak számára a szabadságok kéréséhez.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
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
ms.openlocfilehash: 493bc3abe82103541125914896252b2eae596b38
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/28/2020
ms.locfileid: "3091748"
---
# <a name="overview"></a>Áttekintés

A Dynamics 365 Human Resources segítségével kiváló szabadságjuttatásokat biztosíthat a dolgozók számára. A **Szabadság és távollét** munkaterület rugalmas keretrendszert biztosít az új szabadságtervek és a kérések kezelésére szolgáló munkafolyamatok létrehozásához, valamint intuitív önkiszolgáló oldalt biztosít az alkalmazottak számára a szabadságok kéréséhez. Az elemzés segítséget nyújt a szervezet számára a szabadságegyenlegek és a szabadságtervek használatának méréséhez és figyeléséhez.

## <a name="set-up-leave-and-absence"></a>Szabadság és távollét beállítása

Mielőtt létrehozná a szabadságterveket az alkalmazottak számára, végre kell hajtania néhány beállítási lépést:

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

- [Szabadság kérése](hr-employee-self-service-request-time-off.md)
- [Szabadság- és távollétkérelmek kezelése](hr-employee-self-service-manage-requests.md)

## <a name="leave-and-absence-preview-features"></a>Szabadság és távollét előzetes funkciói

A **Tesztkörnyezet** segítségével kipróbálhatja a szabadságok és távollétek új előzetes funkcióit. Az előzetes funkciók bekapcsolásával kapcsolatos információt lásd a [Szolgáltatások kezelése](hr-admin-manage-features.md) című témakörben. Az előzetes funkciók a következők:

- **Szabadság és távollét – naptár** – a szabadság és távollétre vonatkozó paraméterek az **Emberi erőforrások – paraméterek** pontból egy új képernyőre kerülnek: **Szabadság és távollét – paraméterek**. Az új képernyő tartalmaz egy új **Naptár** lapot. Ez az előnézet csak a paraméterek egy részhalmazát engedélyezi. Az új képernyőt a **Hivatkozások** lapról érheti el, amely a **Szabadság és távollét** munkaterületen található. A naptárak a következőket tartalmazzák:
  - **Vállalati naptár** – megjeleníti minden alkalmazott távolléti kérelmét. Az **Emberi erőforrás** szerepkörrel rendelkező személyek hozzáférhetnek ehhez a naptárhoz a **Hivatkozások** lapon, amely a **Szabadság és távollét** munkaterületen található.
  - **Vezetői csoport naptára** – megjeleníti az összes közvetlen jelentést a távolléti kérelmekkel kapcsolatban. A vezetők a naptárt a **Saját csapat** lapon érhetik el az alkalmazotti önkiszolgáló rendszeren, a **Szabadság és távollét** munkaterületen. 

- **Szabadság és távollét – ünnepnapokat tartalmazó naptárak** – a szabadságtípusok tartalmaznak egy új, **Ünnepnap** lehetőséget is, amely a munkaidő-naptárral együtt használatos. Az ünnepnapok és a leállások által meghatározott napok **Ünnepnap** típusúként vannak meghatározva a munkanapok létrehozásakor. Az elhatárolások feldolgozásakor megtörténik a naptárhoz hozzárendelt alkalmazottak korrekciója a munkanapra eső ünnepnapok esetén.

- **Szabadságelhatárolás ellenőrzése** – az új képernyő lehetővé teszi annak ellenőrzését az összes, illetve egyes alkalmazottak számára, hogy mikor dolgozták fel vagy törölték az elhatárolást. Ezt az új képernyőt a **Hivatkozások** lapról érheti el, amely a **Szabadság és távollét** munkaterületen található.

- **Szabadságelhatárolás törlése** – most már törölhet bizonyos szabadsági tervekre vonatkozó elhatárolási rekordokat. Ezt az új beállítást a **Hivatkozások** lapról érheti el, amely a **Szabadság és távollét** munkaterületen található. Az egyes alkalmazottak esetében ez a beállítás a **Szabadság és távollét** csoportosításban jelenik meg az alkalmazott profilján. 

- **A szabadságelhatárolás kerekítése** – a **Szabadság típusa** pont új beállításai meghatározzák a kerekítés típusát, valamint a kerekítés tizedesjegy-pontosságát az elhatárolási folyamat során. Az elhatárolások feldolgozása során a kerekítés és a pontosság az elhatárolási rekordokban is alkalmazandó. 

- **Több szabadságtípus konfigurálása egyetlen szabadságtervhez** – a szabadság típusú elhatárolási ütemezés új oszlopa lehetővé teszi a szabadságon és a távolléti tervben a különböző elhatárolási ütemezések megadását. Az előző **Szabadságtípus** mezőt eltávolították. Az alkalmazotti belépés során a szabadságtípusra vonatkozó egyenlegek ezentúl egy táblázatban jelennek meg, nem a képernyő felső részén.

  > [!IMPORTANT]
  > Ez a funkció nem kapcsolható ki, miután engedélyezte.

- **Az alkalmazott teljes munkaidő foglalkoztatással való egyenértékűség (FTE) alkalmazása az elhatároláshoz** – a szabadság elszámolási ütemezésének új oszlopa lehetővé teszi a FTE használatát az elhatároláshoz. Az elhatárolások feldolgozásakor az alkalmazás az alkalmazott elsődleges beosztását, valamint az arányosított elhatárolt összeg megállapításához meghatározott FTE-t használja.

  > [!NOTE]
  > Ez a funkció csak akkor érhető el, ha engedélyezi a **Több szabadságtípus konfigurálása egy szabadsági terven belül** opciót. 
