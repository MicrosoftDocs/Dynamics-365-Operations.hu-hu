---
title: A megoldások érzékenységével kapcsolatos problémák elhárítása
description: Ez a témakör olyan hibaelhárítási információkat tartalmaz, amelyek segítségével javíthatók a megoldásérzékenységgel kapcsolatos problémák.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 86dd8803f7560ea337f2452e9722fe0151466daf
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748873"
---
# <a name="troubleshoot-issues-related-to-solution-awareness"></a><span data-ttu-id="a3c5f-103">A megoldások érzékenységével kapcsolatos problémák elhárítása</span><span class="sxs-lookup"><span data-stu-id="a3c5f-103">Troubleshoot issues related to solution awareness</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



<span data-ttu-id="a3c5f-104">Ez a cikk a Finance and Operations és a Dataverse alkalmazások közötti kettős írású adatintegrációk során felmerülő hibák elhárításával kapcsolatos információkat tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="a3c5f-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Dataverse.</span></span> <span data-ttu-id="a3c5f-105">Pontosabban ez a témakör olyan információkat tartalmaz, amelyek segítségével javíthatók a megoldásérzékenységgel kapcsolatos problémák.</span><span class="sxs-lookup"><span data-stu-id="a3c5f-105">Specifically, it provides information that can help you fix issues that are related to solution awareness.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a3c5f-106">Előfordulhat, hogy az ebben a témakörben leírt problémák egy része a rendszergazda szerepkört vagy Microsoft Azure Active Directory (Azure AD) bérlői adminisztrátori hitelesítő adatait igénylik.</span><span class="sxs-lookup"><span data-stu-id="a3c5f-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="a3c5f-107">Az egyes problémákat tárgyaló szakaszok leírják, hogy szükség van-e konkrét szerepkörre vagy hitelesítő adatokra.</span><span class="sxs-lookup"><span data-stu-id="a3c5f-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="error-on-the-dual-write-page"></a><span data-ttu-id="a3c5f-108">Hiba a kettős írás oldalon</span><span class="sxs-lookup"><span data-stu-id="a3c5f-108">Error on the Dual-write page</span></span>

<span data-ttu-id="a3c5f-109">A **Kettős írás** oldalon a következő példához hasonló hibaüzenet jelenhet meg:</span><span class="sxs-lookup"><span data-stu-id="a3c5f-109">On the **Dual-write** page, you might receive an error message that resembles the following example:</span></span>

<span data-ttu-id="a3c5f-110">*Az 'msdyn\_dualwriteentitymap' nevű namemapping='Logical' entitás nem találhat itt: MetadataCache.*</span><span class="sxs-lookup"><span data-stu-id="a3c5f-110">*The entity with a name 'msdyn\_dualwriteentitymap' with namemapping='Logical' was not found in the MetadataCache.*</span></span>

<span data-ttu-id="a3c5f-111">A probléma megoldása érdekében győződjön meg arról, hogy a kettős írás alapmegoldás telepítve van-e a Dataverse szolgáltatásba.</span><span class="sxs-lookup"><span data-stu-id="a3c5f-111">To fix the issue, make sure that the dual-write core solution is installed in Dataverse.</span></span> <span data-ttu-id="a3c5f-112">A kettős írás alapmegoldás a megoldásérzékenység alapfeltétele.</span><span class="sxs-lookup"><span data-stu-id="a3c5f-112">The dual-write core solution is a prerequisite for solution awareness.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]