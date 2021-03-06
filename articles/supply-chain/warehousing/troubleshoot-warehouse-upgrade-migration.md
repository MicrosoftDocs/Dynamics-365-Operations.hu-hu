---
title: Speciális raktárkezelésre való frissítés és áttelepítés – hibaelhárítás
description: Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben frissíti és áttelepíti a speciális raktárkezelést.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 12dcadae2a65d71614a2eee9468ec93cac284a7b
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2021
ms.locfileid: "5907887"
---
# <a name="troubleshoot-upgrade-and-migration-to-advanced-warehouse-management"></a>Speciális raktárkezelésre való frissítés és áttelepítés – hibaelhárítás

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben frissíti és áttelepíti a speciális raktárkezelést.

## <a name="i-receive-the-following-error-message-javasecuritycertcertpathvalidatorexception-trust-anchor-for-certification-path-is-not-found"></a>A következő hibaüzenet jelenik meg: „java.security.cert.certPathValidatorException: A tanúsítvány elérési útjának megbízhatósági horgonyzás nem található.”

### <a name="issue-description"></a>Probléma leírása

Ez a hibaüzenet a Raktárkezelés mobilalkalmazásban jelenik meg, mert az önaláírt tanúsítványok nem Android megbízhatóak a helyszíni környezetekben 8+ felett.

### <a name="issue-resolution"></a>Probléma megoldása

Külső (nyilvános) tanúsító hatóság (CA) használata. A probléma javítása a raktári alkalmazás 1.9.0.0 verziójában érhető el. A problémáról és a probléma megoldásáról a [Raktárkezelés mobilalkalmazás kapcsolódási hibáinak hibaelhárítása](troubleshoot-warehouse-app-connection.md) című témakörben talál további információt.

## <a name="what-is-the-approved-process-for-moving-from-basic-warehousing-to-advanced-warehousing"></a>Mi a jóváhagyott folyamat az alapraktározásról a speciális raktározásra való áttérésre?

### <a name="issue-description"></a>Probléma leírása

Jelenleg készletkezelés alatt fut, és alapvető készletfunkciókat használ, és a mobileszközök, a hullámok és a munka előnyeinek kihasználása érdekében speciális raktározásra szeretne áthelyezni. Azonban problémákat tapasztal, amikor megpróbálja ezt a lépést. Például nem módosíthatja a termékeket úgy, hogy azok tárolási dimenziókat (hely, raktár és hely) használjanak, mert a termékek tranzakcióval rendelkeznek. Ezért meg kell tanulnia a jóváhagyott folyamat alapraktározásról a speciális raktározásra való áttérést.

### <a name="issue-resolution"></a>Probléma megoldása

Az alapraktározásról a speciális raktározásra való áttérés folyamatáról a következő blogbejegyzésekben és dokumentációban olvashat bővebben:

- [Tegye elérhetővé a meglévő cikknek és raktárnak a raktárkezelő folyamatot](https://cleverax.wordpress.com/2017/12/06/d365fo-enable-warehouse-management-process-for-existing-items-and-warehouses/)
- [A WMS áttelepítése Microsoft Dynamics AX új R3 raktárra és szállítási funkcióra](https://cloudblogs.microsoft.com/dynamics365/no-audience/2015/08/17/migration-of-microsoft-dynamics-ax-wms-to-new-r3-warehouse-and-transportation-functionality/)
- [WMSI/WMS2 cikk áttelepítése](https://cloudblogs.microsoft.com/dynamics365/no-audience/2018/05/03/wmsiwms2-item-migration/)
- [Raktárkezelés frissítése a Microsoft Dynamics AX 2012-ről a Supply Chain Management szolgáltatásra](./upgrade-migration-warehouse-management-processes.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]