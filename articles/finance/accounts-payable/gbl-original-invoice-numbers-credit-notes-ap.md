---
title: Hivatkozás az eredeti számlákra a jóváírásokban (szállítói számlák)
description: Ez a témakör azt ismerteti, hogyan lehet jóváírás létrehozásakor egy eredeti számlára hivatkozni.
author: AdamTrukawka
ms.date: 09/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: atrukawk
ms.search.validFrom: 2021-09-23
ms.dyn365.ops.version: 10.0.20
ms.search.form: ''
ms.openlocfilehash: ed07ae9784da3ca721fcb25a9c5a14c4f75f2e59
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277370"
---
# <a name="reference-original-invoices-in-credit-notes-vendor-invoices"></a>Hivatkozás az eredeti számlákra a jóváírásokban (szállítói számlák)

[!include [banner](../includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet jóváírás létrehozásakor egy eredeti számlára hivatkozni.

## <a name="prerequisites"></a>Előfeltételek

A **Szolgáltatáskezelés** munkaterületen engedélyezze a **Jóváírás-számlázás engedélyezése a szállítói számlákhoz** funkciót. További tájékoztatás: [Funkciókezelés – áttekintés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Az ebben a cikkben ismertetett funkciók a következő üzleti dokumentumokra vonatkoznak.

**Kötelezettségek:**

- Beszerzési rendelés
- Számlanapló
- Számlajegyzék

**Főkönyv:**

- Általános napló

## <a name="define-a-reference-to-an-original-invoice"></a>Eredeti számlára mutató hivatkozás meghatározása

A következő eljárásnak megfelelően a meghatározott dokumentumtípus alapján meghatározhatja az eredeti számlára történő hivatkozást.

### <a name="vendor-credit-note-purchase-order"></a>Szállítói jóváírás (beszerzési rendelés)

1. Nyissa meg a következőt: **Kötelezettségek** \> **Beszerzési rendelések** \> **Minden beszerzési rendelés**.
2. Hozzon létre egy új beszerzési rendelést, vagy használja a meglévőt jóváírás létrehozásához.
3. A Műveleti ablaktábla **Számla** lapján a **Bevezetés** csoportban válassza a **Jóváírás számlázása** lehetőséget.
4. Írja be a javítás okát és a hivatkozást az eredeti számlára.

### <a name="vendor-credit-note-ledger-journals"></a>Szállítói jóváírás (főkönyvi naplók)

1. Tegye a következők egyikét:

    - Ugorjon a **Kötelezettségek** \> **Számlanaplók** pontra.
    - Ugorjon a **Kötelezettségek** \> **Számlajegyzék** pontra.
    - Ugorjon a **Főkönyv** \> **Naplóbejegyzések** \> **Általános naplók** menüpontra.

2. Új napló és naplósorok létrehozása.
3. A műveleti panelen válassza a **Funkciók** \> **Jóváírás számlázása** lehetőséget.
4. Írja be a javítás okát és a hivatkozást az eredeti számlára.

> [!NOTE]
> A **Jóváírás számlázása** parancs az általános naplóbizonylaton látható, ha a **Számlatípus** mezőben a **Szállító** érték van beállítva.
