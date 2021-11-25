---
title: A megoldások érzékenységével kapcsolatos problémák elhárítása
description: Ez a témakör olyan hibaelhárítási információkat tartalmaz, amelyek segítségével javíthatók a megoldásérzékenységgel kapcsolatos problémák.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: ec5afd92a71c8b12c913de78a513abb0959df88a
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/10/2021
ms.locfileid: "7782061"
---
# <a name="troubleshoot-issues-related-to-solution-awareness"></a>A megoldások érzékenységével kapcsolatos problémák elhárítása

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



Ez a cikk a Finance and Operations és a Dataverse alkalmazások közötti kettős írású adatintegrációk során felmerülő hibák elhárításával kapcsolatos információkat tartalmaz. Pontosabban ez a témakör olyan információkat tartalmaz, amelyek segítségével javíthatók a megoldásérzékenységgel kapcsolatos problémák.

> [!IMPORTANT]
> Előfordulhat, hogy az ebben a témakörben leírt problémák egy része a rendszergazda szerepkört vagy Microsoft Azure Active Directory (Azure AD) bérlői adminisztrátori hitelesítő adatait igénylik. Az egyes problémákat tárgyaló szakaszok leírják, hogy szükség van-e konkrét szerepkörre vagy hitelesítő adatokra.

## <a name="error-on-the-dual-write-page"></a>Hiba a kettős írás oldalon

A **Kettős írás** oldalon a következő példához hasonló hibaüzenet jelenhet meg:

*Az 'msdyn\_ dualwriteentitymap' nevű namemapping='Logical' entitás nem találhat itt: MetadataCache.*

A probléma megoldása érdekében győződjön meg arról, hogy a kettős írás alapmegoldás telepítve van-e a Dataverse szolgáltatásba. A kettős írás alapmegoldás a megoldásérzékenység alapfeltétele.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]