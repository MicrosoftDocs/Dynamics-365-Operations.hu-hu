---
title: A pénzforgalmi előrejelzés beállításaival kapcsolatos hibák elhárítása
description: Ez a cikk olyan kérdésekre ad választ, amelyek a pénzforgalmi előrejelzés konfigurálásakor merültek fel. Tartalmazza a pénzforgalmi beállításokra, a pénzforgalom frissítésére és a Power BI pénzforgalomra vonatkozó gyakran feltett kérdéseket (GYIK) is.
author: angelad116
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerCovParameters
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2020-12-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 807a1da1906bdefec38954cea02ed29b0157d69e
ms.sourcegitcommit: 0b7a034e644f4d93fe55c7baca5a3f89dbe56898
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/14/2022
ms.locfileid: "9151401"
---
# <a name="troubleshoot-cash-flow-forecasting-setup"></a>A pénzforgalmi előrejelzés beállításaival kapcsolatos hibák elhárítása

[!include [banner](../includes/banner.md)]

Ez a cikk olyan kérdésekre ad választ, amelyek a pénzforgalmi előrejelzés konfigurálásakor merültek fel. Tartalmazza a pénzforgalmi beállításokra, a pénzforgalom frissítésére és a Power BI pénzforgalomra vonatkozó gyakran feltett kérdéseket (GYIK) is.

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

Ellenőrizze, hogy az Entitástár Pénzforgalmi mérő V2 és LedgerCovLiquidityMeasurement mértékei konfigurálva vannak-e. Ha további információt szeretne az entitástár adataival való munkáról, lásd: [Power BI-integráció az entitástárral](../../fin-ops-core/dev-itpro/analytics/power-bi-integration-entity-store.md). Ellenőrizze, hogy a Power BI-tartalom megtekintéséhez szükséges összes lépés el lett-e végezve. További információkért lásd: [Készpénz áttekintés - Power BI tartalom](Cash-Overview-Power-BI-content.md).

## <a name="have-the-entity-store-entities-been-refreshed"></a>Frissültek-e az Entitástár entitásai?

Rendszeresen frissítenie kell az entitásokat, hogy az adatok pontosak és aktuálisak legyenek. Egy adott entitás manuális frissítéséhez lépjen a **Rendszerfelügyelet \> Beállítás \> Entitástár** pontra, jelölje ki az entitást, majd válassza a **Frissítés** lehetőséget. Az adatok automatikusan is frissíthetők. Az **Entitástár** lapon állítsa az **Automatikus frissítés engedélyezve** lehetőséget **Igen** értékre.

## <a name="which-calculation-method-should-be-used-when-calculating-cash-flow-forecasts"></a>Milyen számítási módszert kell alkalmazni a pénzforgalmi előrejelzések kiszámításakor?

A Pénzforgalmi előrejelzés számítási módszer két fontos választási lehetőséggel rendelkezik. Az **Új** beállítás kiszámítja az új dokumentumok és az utolsó kötegelt feldolgozás futtatása óta megváltozott dokumentumok pénzforgalmi előrejelzéseit. Ez a beállítás általában gyorsabban fut, mert a dokumentumok kisebb részhalmazát dolgozza fel. A **Teljes** beállítás újraszámítja a rendszer minden dokumentumára vonatkozó pénzforgalmi előrejelzéseket. Ez a beállítás több időt vesz igénybe, mert több munkát kell befejeznie.

### <a name="how-do-i-improve-the-performance-of-the-cash-flow-forecasting-recurring-batch-job"></a>Hogyan javíthatom a pénzforgalmi előrejelzés ismétlődő kötegelt feldolgozás teljesítményét?

Javasoljuk, hogy az **Új** számítási módszerrel naponta egyszer futtasa a pénzforgalmi előrejelzést a csúcsidőn kívül. Javasoljuk, hogy ezt a megközelítést heti hat nap használja. Ezután futtasson egy pénzforgalmi előrejelzést hetente egyszer a **Teljes** számítási módszerrel azon a napon, ahol a legkevesebb tevékenység van.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

