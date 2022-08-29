---
title: A megoldások érzékenységével kapcsolatos problémák elhárítása
description: Ez a cikk olyan hibaelhárítási információkat tartalmaz, amelyek segítséget nyújtnak a megoldással kapcsolatos problémák kijavítása során.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: c70287cb8ec29fb622f3aefff971b884339e4205
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289424"
---
# <a name="troubleshoot-issues-related-to-solution-awareness"></a>A megoldások érzékenységével kapcsolatos problémák elhárítása

[!include [banner](../../includes/banner.md)]





Ez a témakör hibaelhárítási információkat tartalmaz a pénzügyek és a műveletalkalmazások, valamint a Dataverse. Pontosabban ez a témakör olyan információkat tartalmaz, amelyek segítségével javíthatók a megoldásérzékenységgel kapcsolatos problémák.

> [!IMPORTANT]
> Az ebben a témakörben említett problémák egy része a rendszergazdai szerepkörhöz vagy a Microsoft Azure Active Directory (Azure AD) bérlői rendszergazdai hitelesítő adatokhoz lehet szükséges. Az egyes problémákat tárgyaló szakaszok leírják, hogy szükség van-e konkrét szerepkörre vagy hitelesítő adatokra.

## <a name="error-on-the-dual-write-page"></a>Hiba a kettős írás oldalon

A **Kettős írás** oldalon a következő példához hasonló hibaüzenet jelenhet meg:

*Az 'msdyn\_dualwriteentitymap' nevű namemapping='Logical' entitás nem találhat itt: MetadataCache.*

A probléma megoldása érdekében győződjön meg arról, hogy a kettős írás alapmegoldás telepítve van-e a Dataverse szolgáltatásba. A kettős írás alapmegoldás a megoldásérzékenység alapfeltétele.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
