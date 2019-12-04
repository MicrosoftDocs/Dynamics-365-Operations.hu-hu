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
ms.openlocfilehash: 1a86936d756d8375761ce50c9d9bf33dc638dfad
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/06/2019
ms.locfileid: "2772919"
---
# <a name="user-can-access-core-hr-but-not-onboard-or-attract"></a><span data-ttu-id="1d44c-103">A felhasználó hozzáfér a Core HR alkalmazáshoz, de az Onboard és Attract alkalmazásokhoz nem</span><span class="sxs-lookup"><span data-stu-id="1d44c-103">User can access Core HR but not Onboard or Attract</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="1d44c-104">**Környezet részletes adatai**</span><span class="sxs-lookup"><span data-stu-id="1d44c-104">**Environment details**</span></span>

- <span data-ttu-id="1d44c-105">A Microsoft Dynamics Lifecycle Services (LCS) telepítését A felhasználó végezte.</span><span class="sxs-lookup"><span data-stu-id="1d44c-105">The Microsoft Dynamics Lifecycle Services (LCS) deployment was done by user A.</span></span>
- <span data-ttu-id="1d44c-106">Az A felhasználó hozzáadta B-t felhasználóként a Microsoft Dynamics 365 Talent: Core HR alkalmazáshoz.</span><span class="sxs-lookup"><span data-stu-id="1d44c-106">User A added user B as a user to Microsoft Dynamics 365 Talent: Core HR.</span></span>

<span data-ttu-id="1d44c-107">**Kibocsátás**</span><span class="sxs-lookup"><span data-stu-id="1d44c-107">**Issue**</span></span>

<span data-ttu-id="1d44c-108">B felhasználó hozzáfér a Core HR alkalmazáshoz, de nem fér hozzá a Talent: Attract vagy Talent: Onboard alkalmazáshoz.</span><span class="sxs-lookup"><span data-stu-id="1d44c-108">User B can access Core HR, but can't access the Talent: Attract or Talent: Onboard app.</span></span> <span data-ttu-id="1d44c-109">Amikor a felhasználó megpróbál a **Tapasztalat alkalmazásokba** belépni, a rendszer egy próbakörnyezetbe viszi a felhaszálót.</span><span class="sxs-lookup"><span data-stu-id="1d44c-109">When the user tries to go to **Experience apps**, he or she is taken to a trial environment instead.</span></span>

<span data-ttu-id="1d44c-110">**Megoldás**</span><span class="sxs-lookup"><span data-stu-id="1d44c-110">**Solution**</span></span>

<span data-ttu-id="1d44c-111">A B felhasználóhoz társítani kell a Microsoft Power Apps környezet megtekintési jogait, amelyeket A a telepítési folyamat során létrehozott.</span><span class="sxs-lookup"><span data-stu-id="1d44c-111">User B must be assigned the rights to view the Microsoft Power Apps environment that user A created during the provisioning process.</span></span>

<span data-ttu-id="1d44c-112">További információt a témában a [Talent létesítése](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent) rész „Hozzáférés biztosítása a környezethez” szakaszában talál.</span><span class="sxs-lookup"><span data-stu-id="1d44c-112">For information, see the "Granting access to the environment" section in [Provision Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span></span>

<span data-ttu-id="1d44c-113">**Hosszú távú megoldás**</span><span class="sxs-lookup"><span data-stu-id="1d44c-113">**Long-term solution**</span></span>

<span data-ttu-id="1d44c-114">A Microsoft javasolja a megfelelő jogok automatikus hozzárendelését az Onboard és az Attract alkalmazásokhoz, amikor egy felhasználót a Core HR alkalmazáshoz adják.</span><span class="sxs-lookup"><span data-stu-id="1d44c-114">Microsoft is considering automatically assigning the appropriate rights to Onboard and Attract when a user is added to Core HR.</span></span>
