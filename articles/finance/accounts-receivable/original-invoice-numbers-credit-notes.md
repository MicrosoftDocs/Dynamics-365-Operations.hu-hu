---
title: Hivatkozások eredeti számlákra a jóváírásokban
description: Ez a témakör bemutatja az eredeti számlaszámok beállítását és nyomtatását a kapcsolódó jóváírásokban.
author: ilkond
manager: AnnBe
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 673288f04b33aa2a578f9e2e7913dbe7ac309644
ms.sourcegitcommit: 7cdec5469ff0da145ac4e01caf3287d0627ae2dc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2021
ms.locfileid: "5100002"
---
# <a name="references-to-original-invoices-in-credit-notes"></a>Hivatkozások eredeti számlákra a jóváírásokban

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Egyes országokban és régiókban jogi előírás, hogy a nyomtatott jóváírások hivatkozást tartalmazzanak az eredeti számlákra. Ez a témakör bemutatja az eredeti számlaszámok beállítását és nyomtatását a kapcsolódó jóváírásokban.

## <a name="prerequisites"></a>Előfeltételek

- A **Funkciókezelés** munkaterületen kapcsolja be az **Értékesítési és projektszámla-jelentések jóváírás-számlázási elrendezése** funkciót. További tájékoztatás: [Funkciókezelés – áttekintés](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).
- A szükséges dokumentumok nyomtatható formátumait a Nyomtatáskezelésben kell konfigurálni.

Az ebben a témakörben leírt funkciók a következő dokumentumokra vonatkoznak:

**Kinnlevőségek**

- Szabadszövegű jóváírás
- Vevői jóváírás

**Projektvezetés és könyvelés**

- Projekt jóváírása

## <a name="configure-accounts-receivable-parameters"></a>A Kinnlevőségek paraméterei konfigurálása

A következő lépések segítségével beállíthatja azt a paramétert, amely meghatározza, hogy az eredeti számlákra vonatkozó hivatkozások ki vannak-e nyomtatva a kapcsolódó jóváírásokban.

1. Lépjen a **Kinnlevőségek** \> **Beállítások** \> **Kinnlevőségek paraméterei** pontra.
2. A **Számla** gyorslap **Frissítések** lapján állítsa a **Jóváírás-számlázási elrendezés alkalmazása értékesítési és projektszámla-jelentésekre** lehetőséget **Igen** értékre.

![A Kinnlevőségek paraméterei konfigurálása](media/original-invoice-number-in-credit-note.jpg)

## <a name="define-references-to-original-invoices"></a>Eredeti számlákra mutató hivatkozások meghatározása

A következő eljárásnak megfelelően a dokumentumtípus alapján meghatározhatja az eredeti számlákra történő hivatkozásokat.

### <a name="free-text-credit-note"></a>Szabadszövegű jóváírás

1. Válassza a következőt **Kinnlevőségek** \> **Számlák** \> **Kizárólag szabadszöveges számlák**.
2. Hozzon létre új jóváírást vagy válasszon ki egy meglévőt.
3. Nyissa meg a számlát.
4. A Műveleti ablaktábla **Számla** lapján a **Függvények** csoportban válassza a **Jóváírás számlázása** lehetőséget.
5. Írja be az eredeti számlára való hivatkozást, és válassza ki a javítás okát.

![Szabadszöveges számla hivatkozásának meghatározása](media/reference-original-invoice-FTI.jpg)

### <a name="customer-credit-note"></a>Vevői jóváírás

1. Lépjen a **Kinnlevőségek** \> **Rendelések** \> **Minden értékesítési rendelés** pontra.
2. Válassza ki és nyissa meg a javítandó leszámlázott értékesítési rendelést.
3. A Műveleti ablaktábla **Értékesítés** lapján a **Jóváírás** csoportban válassza a **Jóváírás** lehetőséget.
4. Adja meg a javítás okát. Az eredeti számlára való hivatkozás automatikusan létrejön.

![Értékesítési rendelés hivatkozásának meghatározása](media/reference-original-invoice-SO.jpg)

### <a name="project-credit-note"></a>Projekt jóváírása

1. Lépjen a **Projektvezetés és könyvelés** \> **Projektszámlák** \> **Projektszámlák** menüpontba.
2. Válassza ki és nyissa meg a javítandó projektszámlát.
3. A Műveleti ablaktábla **Projektszámla** lapján a **Függvények** csoportban válassza a **Kijelölés jóváíráshoz** lehetőséget.
4. Válassza a **Jóváírás számlázása** lehetőséget.
5. Adja meg a javítás okát. Az eredeti számlára való hivatkozás automatikusan létrejön.

![Projektszámla hivatkozásának meghatározása](media/reference-original-invoice-project.jpg)

## <a name="printing-credit-notes"></a>Jóváírások nyomtatása

Szabadszöveges, vevői és projektjóváírások nyomtatása esetén a jóváírások az eredeti számlára való hivatkozást és a javítás okát is tartalmazzák.

![Kinyomtatott jóváírás](media/credit-note-FTI.jpg)

> [!NOTE]
> Győződjön meg arról, hogy a dokumentumok nyomtatható formátumai helyesen legyenek konfigurálva, feltételezve, hogy az eredeti számlákra mutató hivatkozásokat ki fogják nyomtatni.
