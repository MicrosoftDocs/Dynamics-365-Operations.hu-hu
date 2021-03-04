---
title: Felvételi folyamatsablon létrehozása az Attract alkalmazásban
description: Ez a témakör információt nyújt a felvételi folyamatsablonok létrehozásáról az Attract alkalmazásban.
author: andreabichsel
manager: AnnBe
ms.date: 10/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-01
ms.dyn365.ops.version: AX 8.1
ms.openlocfilehash: 82046d43cf7366b760c140bdb8b017337b4f41da
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461443"
---
# <a name="create-a-hiring-process-template-in-attract"></a>Felvételi folyamatsablon létrehozása az Attract alkalmazásban

[!include [banner](includes/banner.md)]

A *Felvételi folyamat sablonja* egy állás felvételi folyamatának összes tevékenységet tartalmazza. Ez a témakör ismerteti az folyamatsablonnal kapcsolatos elemeket az Microsoft Dynamics 365 Talent: Attract alkalmazásban. Azt is bemutatja, hogyan lehet létrehozni egy sablont.

> [!NOTE]
> A sablon-létrehozás az Attract alkalmazás Átfogó felvételi bővítményének része.

## <a name="template-management"></a>Sablonkezelés

A szervezetek eldöntheti, hogy csak a rendszergazdák vagy a csoport tagjai is létrehozhatnak folyamatsablonokat az Attract alkalmazásban. A sablonkezelés konfigurálásához kattintson az **Adminisztrációs Központ** \> **Sablonkezelés** lehetőségre. Ahhoz, hogy a csapattagok saját sablonokat hozhassanak létre, kapcsolja be a sablonkezelést. Ha nem kapcsolja be a sablonkezelést, csak rendszergazdák hozhatnak létre sablonokat.

## <a name="default-template"></a>Alapértelmezett sablon

Csak a rendszergazdák állíthatják be az alapértelmezett sablont. Az alapértelmezett sablont használja a rendszer, ha az állás létrehozásakor nincs sablon kiválasztva. Az alapértelmezett sablon beállításához kattintson az **Adminisztrációs Központ** \> **Sablonkezelés** lehetőségre. Az alapértelmezettnek kiválasztott sablon kártyáján válassza a hármaspont gombot (**…**), majd válassza a **Beállítás alapértelmezettként** beállítást.

## <a name="create-a-process-template"></a>Folyamatsablon létrehozása

Rendszergazdák, toborzásért felelős személyek és a vezetők hozhatnak létre folyamatsablonokat. Egy folyamatsablon *fokozatokból* és *tevékenységekből* áll. A fokozatok egy vagy több tevékenységet csoportosítanak. Alapértelmezés szerint minden folyamatsablonban vannak Jelöltre, Pályázatra és Ajánlatra vonatkozó tevékenységek. Azokat a fokozatokat lehet átnevezni, amelyek tartalmazzák ezeket a tevékenységeket. Több fokozatot is hozzáadhat a **+ Új fokozat** kiválasztásával. A tevékenységeket fokozatokhoz adhatja vagy a megfelelő fokozatra húzással vagy ha a tevékenységlistában duplán kattint rájuk.

> [!NOTE]
> A fokozatok nevei a jelöltek számára láthetók a **Pályázat állapota** oldalon. Vegye figyelembe ezt, amikor elnevezi a fokozatokat.

Tevékenységekkel kapcsolatos további tudnivalókért tekintse meg a [Felvételi folyamatok tevékenységei](./activities-attract.md) részt.

Felvételi folyamatsablon létrehozásához kövesse az alábbi lépéseket:

1. Ugorjon a **Sablonok** részre.
2. Válassza az **Új** lehetőséget.
3. Adja meg a sablon nevét a **Sablon neve** mezőben, majd kattintson a **Létrehozás** lehetőségre.
4. A **Jóváhagyási folyamat kiválasztása** listában válassza ki az **Alapértelmezett** lehetőséget, hogy jóváhagyást kérjen egy álláshoz.
5. Bejelölésével engedélyezheti vagy letilthatja a jelölteket.
6. Választható: Fokozatok hozzáadása vagy eltávolítása.

    - Egy szakasz hozzáadásához jelölje ki a **+ Új szakasz** elemet.
    - Egy fokozat eltávolításához vigye a kurzort a fokozat fölé, majd válassza ki a megjelenő szemeteskuka gombot.

        > [!NOTE]
        > A Jelölt, Pályázat és Ajánlat fokozatokat nem lehet eltávolítani, de át lehet őket nevezni.

7. Választható: Tevékenységek hozzáadása vagy eltávolítása.

    - Egy tevékenység hozzáadásához húzza át azt a jobb oldalon található tevékenységek listájáról a megfelelő fokozatra. Másik lehetőségként kattintson duplán a tevékenységre, és válassza ki a szakaszt, amelyikhez hozzá szeretné adni.
    - Egy tevékenység eltávolításához bontsa ki azt, majd kattintson a tevékenység fejlécében a szemeteskuka gombra.

8. Válassza a **Mentés** lehetőséget.


[!INCLUDE[footer-include](../includes/footer-banner.md)]