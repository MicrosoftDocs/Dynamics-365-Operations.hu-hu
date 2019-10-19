---
title: A felhasználó hozzáfér a Core HR alkalmazáshoz, de az Onboard és Attract alkalmazásokhoz nem
description: Ez a témakör bemutatja, hogy hogyan lehet megoldani a problémát, amikor a felhasználó hozzá tud férni a Microsoft Dynamics 365 Talent – Core HR alkalmazáshoz, de nem fér hozzá az Attract és az Onboard alkalmazásokhoz.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 80b1f8aeabfd033f393463f4be5a61447377f2d9
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/23/2019
ms.locfileid: "2009306"
---
# <a name="user-can-access-core-hr-but-not-onboard-or-attract"></a>A felhasználó hozzáfér a Core HR alkalmazáshoz, de az Onboard és Attract alkalmazásokhoz nem

[!include [banner](includes/banner.md)]

**Környezet részletes adatai**

- A Microsoft Dynamics Lifecycle Services (LCS) telepítését A felhasználó végezte.
- Az A felhasználó hozzáadta B-t felhasználóként a Microsoft Dynamics 365 Talent: Core HR alkalmazáshoz.

**Kibocsátás**

B felhasználó hozzáfér a Core HR alkalmazáshoz, de nem fér hozzá a Talent: Attract vagy Talent: Onboard alkalmazáshoz. Amikor a felhasználó megpróbál a **Tapasztalat alkalmazásokba** belépni, a rendszer egy próbakörnyezetbe viszi a felhaszálót.

**Megoldás**

A B felhasználóhoz társítani kell a Microsoft PowerApps környezet megtekintési jogait, amelyeket A a telepítési folyamat során létrehozott.

További információt a témában a [Talent létesítése](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent) rész „Hozzáférés biztosítása a környezethez” szakaszában talál.

**Hosszú távú megoldás**

A Microsoft javasolja a megfelelő jogok automatikus hozzárendelését az Onboard és az Attract alkalmazásokhoz, amikor egy felhasználót a Core HR alkalmazáshoz adják.
