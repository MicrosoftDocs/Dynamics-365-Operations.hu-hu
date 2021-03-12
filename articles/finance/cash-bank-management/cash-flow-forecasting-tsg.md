---
title: A pénzforgalmi előrejelzés beállításaival kapcsolatos hibák elhárítása
description: Ez a témakör olyan kérdésekre ad választ, amelyek a pénzforgalmi előrejelzés konfigurálásakor merülhetnek fel. Tartalmazza a pénzforgalmi beállításokra, a pénzforgalom frissítésére és a Power BI pénzforgalomra vonatkozó gyakran feltett kérdéseket (GYIK) is.
author: panolte
manager: AnnBe
ms.date: 12/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerCovParameters
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2020-12-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 89eb2f1bcfc73a6a7171a275532b2356e858e87c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985287"
---
# <a name="troubleshoot-cash-flow-forecasting-setup"></a>A pénzforgalmi előrejelzés beállításaival kapcsolatos hibák elhárítása

[!include [banner](../includes/banner.md)]

Ez a témakör olyan kérdésekre ad választ, amelyek a pénzforgalmi előrejelzés konfigurálásakor merülhetnek fel. Tartalmazza a pénzforgalmi beállításokra, a pénzforgalom frissítésére és a Power BI pénzforgalomra vonatkozó gyakran feltett kérdéseket (GYIK) is.

## <a name="why-is-cash-flow-shown-for-only-one-legal-entity"></a>Miért jelenik meg a pénzforgalom csak egyetlen jogi személynél?

A pénzforgalmi előrejelzés konfigurálása és számítása jogi személyenként történik. A Power BI-jelentések és a pénzforgalmi előrejelzések képesség a Finance Insights alkalmazásban megjelenítik az eredményeket.

A pénzforgalmi előrejelzést minden egyes jogi személyhez be kell állítani, amelyikhez előrejelzést szeretne látni. Ellenőrizze a pénzforgalmi előrejelzés konfigurációját minden jogi személye esetében. Alternatív lehetőségként tekintse át az összes jogi személy konfigurációját a pénzforgalmi előrejelzésre vonatkozóan, és győződjön meg arról, hogy a szándéknak megfelelően legyenek beállítva.

## <a name="why-doesnt-power-bi-show-all-the-cash-flow-data"></a>Miért nem jeleníti meg a Power BI az összes pénzforgalmi adatot?

Több lépést kell végrehajtani ahhoz, hogy a pénzforgalmi előrejelzések megjelenjenek a Power BI-nézetekben. Tekintse át az alábbi ellenőrző listát, és győződjön meg arról, hogy minden lépést elvégzett:

- Pénzforgalom beállítása minden egyes jogi személyhez.
- A Főkönyvi paraméterek pontban állítsa be a rendszer pénznemét és a rendszer árfolyamtípusát.
- Állítsa be a főkönyvi könyvelési pénznemet és az árfolyam típusát.
- Írja be a tranzakció pénzneme és a könyvelési pénznem közötti átváltási árfolyamot.
- Írja be a könyvelési pénznem és a rendszer pénzneme közötti átváltási árfolyamot.
- Írja be a könyvelési pénznem és az egyes bankok pénzneme közötti átváltási árfolyamot.

## <a name="why-did-cash-flow-power-bi-work-in-previous-versions-but-is-now-blank"></a>Miért működött a Power BI pénzforgalom a korábbi verziókban, de most üres?

Ellenőrizze, hogy az Entitástár Pénzforgalmi mérő V2 és LedgerCovLiquidityMeasurement mértékei konfigurálva vannak-e. Az Entitástárban található adatokkal való munkáról lásd: [Power BI-integrációja az Entitástárral](../../fin-ops-core/dev-itpro/analytics/power-bi-integration-entity-store.md) Ellenőrizze, hogy a Power BI-tartalom megtekintéséhez szükséges összes lépést elvégezte-e. További információkért lásd: [Készpénz áttekintés - Power BI tartalom](Cash-Overview-Power-BI-content.md).

## <a name="have-the-entity-store-entities-been-refreshed"></a>Frissültek-e az Entitástár entitásai?

Rendszeresen frissítenie kell az entitásokat, hogy az adatok pontosak és aktuálisak legyenek. Egy adott entitás manuális frissítéséhez lépjen a **Rendszerfelügyelet \> Beállítás \> Entitástár** pontra, jelölje ki az entitást, majd válassza a **Frissítés** lehetőséget. Az adatok automatikusan is frissíthetők. Az **Entitástár** lapon állítsa az **Automatikus frissítés engedélyezve** lehetőséget **Igen** értékre.
