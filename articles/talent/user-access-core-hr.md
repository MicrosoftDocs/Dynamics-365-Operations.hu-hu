---
title: A felhasználó hozzáfér a Human Resources alkalmazáshoz, de az Onboard és Attract alkalmazásokhoz nem
description: Ez a témakör bemutatja, hogy hogyan lehet megoldani a problémát, amikor a felhasználó hozzá tud férni a Microsoft Dynamics 365 Talent – Human Resources alkalmazáshoz, de nem fér hozzá az Attract és az Onboard alkalmazásokhoz.
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
ms.openlocfilehash: 6c384d9a7100982eabd201d910e1bea14355dc1f
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2020
ms.locfileid: "3006310"
---
# <a name="user-can-access-human-resources-but-not-onboard-or-attract"></a>A felhasználó hozzáfér a Human Resources alkalmazáshoz, de az Onboard és Attract alkalmazásokhoz nem

[!include [banner](includes/banner.md)]

**Környezet részletes adatai**

- A Microsoft Dynamics Lifecycle Services (LCS) telepítését A felhasználó végezte.
- Az A felhasználó hozzáadta B-t felhasználóként a Microsoft Dynamics 365 Human Resources alkalmazáshoz.

**Kibocsátás**

B felhasználó hozzáfér a Human Resources alkalmazáshoz, de nem fér hozzá a Talent: Attract vagy Talent: Onboard alkalmazáshoz. Amikor a felhasználó megpróbál a **Tapasztalat alkalmazásokba** belépni, a rendszer egy próbakörnyezetbe viszi a felhaszálót.

**Megoldás**

A B felhasználóhoz társítani kell a Microsoft Power Apps környezet megtekintési jogait, amelyeket A a telepítési folyamat során létrehozott.

További információt a témában a [Talent létesítése](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent) rész „Hozzáférés biztosítása a környezethez” szakaszában talál.

**Hosszú távú megoldás**

A Microsoft javasolja a megfelelő jogok automatikus hozzárendelését az Onboard és az Attract alkalmazásokhoz, amikor egy felhasználót a Human Resources alkalmazáshoz adják.
