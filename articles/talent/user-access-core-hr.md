---
title: Felhasználó hozzá tud férni a Core HR alkalmazáshoz, de az Onboard vagy Attract alkalmazáshoz nem
description: Ez a témakör bemutatja, hogy hogyan lehet megoldani a problémát, amikor a felhasználó hozzá tud férni a Microsoft Dynamics 365 for Talent Core HR alkalmazáshoz, de nem fér hozzá az Attract és az Onboard alkalmazásokhoz.
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 2e5d0b1bf993aec89c7d2c6d4916732f5824310d
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "304720"
---
# <a name="user-can-access-core-hr-but-not-the-onboard-or-attract-app"></a><span data-ttu-id="767e1-103">A felhasználó hozzáfér a Core HR alkalmazáshoz, de az Onboard és Attract alkalmazásokhoz nem</span><span class="sxs-lookup"><span data-stu-id="767e1-103">User can access Core HR but not the Onboard or Attract app</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="767e1-104">**Környezet részletes adatai**</span><span class="sxs-lookup"><span data-stu-id="767e1-104">**Environment details**</span></span>

- <span data-ttu-id="767e1-105">A Microsoft Dynamics Lifecycle Services (LCS) telepítését A felhasználó végezte.</span><span class="sxs-lookup"><span data-stu-id="767e1-105">The Microsoft Dynamics Lifecycle Services (LCS) deployment was done by user A.</span></span>
- <span data-ttu-id="767e1-106">Az A felhasználó hozzáadta B-t felhasználóként a Microsoft Dynamics 365 for Talent Core HR alkalmazáshoz.</span><span class="sxs-lookup"><span data-stu-id="767e1-106">User A added user B as a user to Microsoft Dynamics 365 for Talent Core HR.</span></span>

<span data-ttu-id="767e1-107">**Kibocsátás**</span><span class="sxs-lookup"><span data-stu-id="767e1-107">**Issue**</span></span>

<span data-ttu-id="767e1-108">B felhasználó hozzáfér a Core HR alkalmazáshoz, de nem fér hozzá a Talent: Attract vagy Talent: Onboard alkalmazáshoz.</span><span class="sxs-lookup"><span data-stu-id="767e1-108">User B can access Core HR, but can't access the Talent: Attract or Talent: Onboard app.</span></span> <span data-ttu-id="767e1-109">Amikor a felhasználó megpróbál a **Tapasztalat alkalmazásokba** belépni, a rendszer egy próbakörnyezetbe viszi a felhaszálót.</span><span class="sxs-lookup"><span data-stu-id="767e1-109">When the user tries to go to **Experience apps**, he or she is taken to a trial environment instead.</span></span>

<span data-ttu-id="767e1-110">**Megoldás**</span><span class="sxs-lookup"><span data-stu-id="767e1-110">**Solution**</span></span>

<span data-ttu-id="767e1-111">A B felhasználóhoz társítani kell a Microsoft PowerApps környezet megtekintési jogait, amelyeket A a telepítési folyamat során létrehozott.</span><span class="sxs-lookup"><span data-stu-id="767e1-111">User B must be assigned the rights to view the Microsoft PowerApps environment that user A created during the provisioning process.</span></span>

<span data-ttu-id="767e1-112">További információt a témában a [Talent létesítése](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/provisioning-talent) rész „Hozzáférés biztosítása a környezethez” szakaszában talál.</span><span class="sxs-lookup"><span data-stu-id="767e1-112">For information, see the "Granting access to the environment" section in [Provision Talent](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/provisioning-talent).</span></span>

<span data-ttu-id="767e1-113">**Hosszú távú megoldás**</span><span class="sxs-lookup"><span data-stu-id="767e1-113">**Long-term solution**</span></span>

<span data-ttu-id="767e1-114">A Microsoft javasolja a megfelelő jogok automatikus hozzárendelését az Onboard és az Attract alkalmazásokhoz, amikor egy felhasználót a Core HR alkalmazáshoz adják.</span><span class="sxs-lookup"><span data-stu-id="767e1-114">Microsoft is considering automatically assigning the appropriate rights to Onboard and Attract when a user is added to Core HR.</span></span>
