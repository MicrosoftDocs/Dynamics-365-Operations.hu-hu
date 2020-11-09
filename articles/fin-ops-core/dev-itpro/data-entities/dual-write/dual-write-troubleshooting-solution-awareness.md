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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 7f1a6e424996201ecae1b624c13cfc573745dc0a
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997278"
---
# <a name="troubleshoot-issues-related-to-solution-awareness"></a>A megoldások érzékenységével kapcsolatos problémák elhárítása

[!include [banner](../../includes/banner.md)]



Ez a cikk a Finance and Operations és a Common Data Service alkalmazások közötti kettős írású adatintegrációk során felmerülő hibák elhárításával kapcsolatos információkat tartalmaz. Pontosabban ez a témakör olyan információkat tartalmaz, amelyek segítségével javíthatók a megoldásérzékenységgel kapcsolatos problémák.

> [!IMPORTANT]
> Előfordulhat, hogy az ebben a témakörben leírt problémák egy része a rendszergazda szerepkört vagy Microsoft Azure Active Directory (Azure AD) bérlői adminisztrátori hitelesítő adatait igénylik. Az egyes problémákat tárgyaló szakaszok leírják, hogy szükség van-e konkrét szerepkörre vagy hitelesítő adatokra.

## <a name="error-on-the-dual-write-page"></a>Hiba a kettős írás oldalon

A **Kettős írás** oldalon a következő példához hasonló hibaüzenet jelenhet meg:

*Az 'msdyn\_dualwriteentitymap' nevű namemapping='Logical' entitás nem találhat itt: MetadataCache.*

A probléma megoldása érdekében győződjön meg arról, hogy a kettős írás alapmegoldás telepítve van-e a Common Data Service szolgáltatásba. A kettős írás alapmegoldás a megoldásérzékenység alapfeltétele.
