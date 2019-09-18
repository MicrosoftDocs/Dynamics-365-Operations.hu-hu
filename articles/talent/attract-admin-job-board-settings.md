---
title: Broadbean integráció engedélyezése a Microsoft Dynamics 365 for Talent - Attract megoldásban
description: Ez a témakör azt mutatja be, hogyan lehet a Microsoft Dynamics 365 for Talent - Attract megoldást konfigurálni állások közzétételére külső állásportálokon, például a Broadean portálon.
author: andreabichsel
manager: AnnBe
ms.date: 07/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-07-08
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 2334c2bd0edccf3000f8d91651afafd4619ad0b8
ms.sourcegitcommit: 7c49475402632069685df714546770d30804af7f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/11/2019
ms.locfileid: "1739679"
---
# <a name="enable-broadbean-integration"></a><span data-ttu-id="20683-103">Broadbean integráció engedélyezése</span><span class="sxs-lookup"><span data-stu-id="20683-103">Enable Broadbean integration</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="20683-104">A nyitott pozíciókat elehető legjobb alkalmas jelölt számára szeretné eljuttatni.</span><span class="sxs-lookup"><span data-stu-id="20683-104">You want to get your open positions in front of as many qualified candidates as possible.</span></span> <span data-ttu-id="20683-105">A toborzási oldalak, például a Broadbean segítenek elérni ezt a célt.</span><span class="sxs-lookup"><span data-stu-id="20683-105">Recruiting sites such as Broadbean help you accomplish this goal.</span></span> <span data-ttu-id="20683-106">A Microsoft Dynamics 365 for Talent 365 Talent: Attract lehetővé teszi, hogy állásokat tegyen közzé a Broadbean oldalon, és a Microsoft folyamatosan új ajánlatokat biztosít majd ezen a területen.</span><span class="sxs-lookup"><span data-stu-id="20683-106">Microsoft Dynamics 365 for Talent: Attract now lets you post jobs to Broadbean, and Microsoft is constantly providing new offerings in this area.</span></span>

> [!NOTE]
> - <span data-ttu-id="20683-107">Állások közzétételéhez külső webhelyeken rendelkeznie kell az [Átfogó felvételi bővítménnyel](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).</span><span class="sxs-lookup"><span data-stu-id="20683-107">To post jobs to external sites, you must have the [Comprehensive hiring add-on](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).</span></span>
> - <span data-ttu-id="20683-108">Az állásoknak a Broadbean felületére az Attract szolgáltatáson keresztül történő feladásához Broadbean előfizetés szükséges.</span><span class="sxs-lookup"><span data-stu-id="20683-108">To post jobs to Broadbean through Attract, you must have a Broadbean subscription.</span></span>
> - <span data-ttu-id="20683-109">Ez a funkció jelenleg előnézetben van.</span><span class="sxs-lookup"><span data-stu-id="20683-109">This feature is currently in preview.</span></span> <span data-ttu-id="20683-110">Ha ki szeretné próbálni, akkor [be kell kapcsolnia az Attract rendszergazdai beállításai között](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).</span><span class="sxs-lookup"><span data-stu-id="20683-110">If you want to try it, you must [turn it on in the Attract admin settings](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).</span></span>

## <a name="configure-broadbean-integration"></a><span data-ttu-id="20683-111">Broadbean integráció konfigurálása</span><span class="sxs-lookup"><span data-stu-id="20683-111">Configure Broadbean integration</span></span>

1. <span data-ttu-id="20683-112">Jelentkezzen be Attract alkalmazásba rendszergazdaként</span><span class="sxs-lookup"><span data-stu-id="20683-112">Sign in to Attract as an admin.</span></span>

2. <span data-ttu-id="20683-113">Válassza ki a **Beállítások** gombot (fogaskerék-szimbólum) a lap jobb felső sarkában, majd válassza a **Felügyeleti központ** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="20683-113">Select the **Settings** button (the gear symbol) in the upper-right corner of the page, and then select **Admin center**.</span></span>

3. <span data-ttu-id="20683-114">Forduljon a Broadbean-hoz, és adja meg az adatokat a **Felhasználónév**, **Ügyfélazonosító**, **Titkosítási Token** elemekhez.</span><span class="sxs-lookup"><span data-stu-id="20683-114">Contact Broadbean, and enter your information in the **Username**, **Client ID**, and **Encryption Token** fields.</span></span>

4. <span data-ttu-id="20683-115">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="20683-115">Select **Save**.</span></span>

> [!WARNING]
> <span data-ttu-id="20683-116">A Broadbean hitelesítő adatai kényes és bizalmas természetűek.</span><span class="sxs-lookup"><span data-stu-id="20683-116">Your Broadbean credentials are sensitive and confidential.</span></span> <span data-ttu-id="20683-117">Ezért átgondoltan ossza meg azokat.</span><span class="sxs-lookup"><span data-stu-id="20683-117">Therefore, store and share them responsibly.</span></span> <span data-ttu-id="20683-118">Mindenki akinek rendszergazdai szerepköre van az Attract megoldásban megtekintheti ezeket a hitelesítő adatokat.</span><span class="sxs-lookup"><span data-stu-id="20683-118">Anyone who has an Administrator role in Attract can view these credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="20683-119">A Microsoft és Attract vesz nem részt ezen értékek létrehozásában és kezelésében.</span><span class="sxs-lookup"><span data-stu-id="20683-119">Microsoft and Attract aren't involved in creating and maintaining these values.</span></span> <span data-ttu-id="20683-120">Az Ön felelőssége naprakészen tartani azokat az Attract megoldásban, illetve az, hogy együttműködjön a Broadbeannel, hogy megoldja a hitelesítési adatokkal kapcsolatos esetleges problémákat.</span><span class="sxs-lookup"><span data-stu-id="20683-120">It's your responsibility to keep them up to date in Attract and to work with Broadbean to resolve any issues that involve your credentials.</span></span>
