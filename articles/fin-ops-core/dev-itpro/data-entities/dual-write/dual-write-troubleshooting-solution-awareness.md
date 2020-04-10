---
title: A megoldások érzékenységével kapcsolatos problémák elhárítása
description: Ez a témakör olyan hibaelhárítási információkat tartalmaz, amelyek segítségével javíthatók a megoldásérzékenységgel kapcsolatos problémák.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 013e37269ec3df2bede15b28cffcc175967de9a3
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172621"
---
# <a name="troubleshoot-issues-related-to-solution-awareness"></a><span data-ttu-id="00d5b-103">A megoldások érzékenységével kapcsolatos problémák elhárítása</span><span class="sxs-lookup"><span data-stu-id="00d5b-103">Troubleshoot issues related to solution awareness</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="00d5b-104">Ez a cikk a Finance and Operations és a Common Data Service alkalmazások közötti kettős írású adatintegrációk során felmerülő hibák elhárításával kapcsolatos információkat tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="00d5b-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="00d5b-105">Pontosabban ez a témakör olyan információkat tartalmaz, amelyek segítségével javíthatók a megoldásérzékenységgel kapcsolatos problémák.</span><span class="sxs-lookup"><span data-stu-id="00d5b-105">Specifically, it provides information that can help you fix issues that are related to solution awareness.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="00d5b-106">Előfordulhat, hogy az ebben a témakörben leírt problémák egy része a rendszergazda szerepkört vagy Microsoft Azure Active Directory (Azure AD) bérlői adminisztrátori hitelesítő adatait igénylik.</span><span class="sxs-lookup"><span data-stu-id="00d5b-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="00d5b-107">Az egyes problémákat tárgyaló szakaszok leírják, hogy szükség van-e konkrét szerepkörre vagy hitelesítő adatokra.</span><span class="sxs-lookup"><span data-stu-id="00d5b-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="error-on-the-dual-write-page"></a><span data-ttu-id="00d5b-108">Hiba a kettős írás oldalon</span><span class="sxs-lookup"><span data-stu-id="00d5b-108">Error on the Dual-write page</span></span>

<span data-ttu-id="00d5b-109">A **Kettős írás** oldalon a következő példához hasonló hibaüzenet jelenhet meg:</span><span class="sxs-lookup"><span data-stu-id="00d5b-109">On the **Dual-write** page, you might receive an error message that resembles the following example:</span></span>

<span data-ttu-id="00d5b-110">*Az 'msdyn\_dualwriteentitymap' nevű namemapping='Logical' entitás nem találhat itt: MetadataCache.*</span><span class="sxs-lookup"><span data-stu-id="00d5b-110">*The entity with a name 'msdyn\_dualwriteentitymap' with namemapping='Logical' was not found in the MetadataCache.*</span></span>

<span data-ttu-id="00d5b-111">A probléma megoldása érdekében győződjön meg arról, hogy a kettős írás alapmegoldás telepítve van-e a Common Data Service szolgáltatásba.</span><span class="sxs-lookup"><span data-stu-id="00d5b-111">To fix the issue, make sure that the dual-write core solution is installed in Common Data Service.</span></span> <span data-ttu-id="00d5b-112">A kettős írás alapmegoldás a megoldásérzékenység alapfeltétele.</span><span class="sxs-lookup"><span data-stu-id="00d5b-112">The dual-write core solution is a prerequisite for solution awareness.</span></span>
