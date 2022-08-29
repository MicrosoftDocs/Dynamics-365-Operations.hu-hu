---
title: Nyomtatott vevői számlák archiválása kivonatszámokkal
description: Ez a cikk bemutatja, hogyan lehet engedélyezni az archiválást a nyomtatott, kivonatszámokat is tartalmazó vevői számlák tárolására.
author: mrolecki
ms.date: 09/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2021-03-05
ms.dyn365.ops.version: 10.0.18
ms.custom: 539093
ms.search.form: ''
ms.openlocfilehash: 4c9bd7ead1615a4e6b0e8e672e858312ba518b56
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9291669"
---
# <a name="archive-printed-customer-invoices-with-hash-numbers"></a>Nyomtatott vevői számlák archiválása kivonatszámokkal

[!include [banner](../includes/banner.md)]

Egyes országokban jogszabályi előírás a kiszámított kivonatszámok tárolása a rendszerben, bizonyos dokumentumok kinyomtatott változatával együtt. A kivonatszámok a hatóságoknak való jelentésre és a könyvvizsgálatok során használhatók.

Ez a cikk bemutatja, hogyan kell konfigurálni az archiválást a nyomtatott vevői számlák és kivonatszámok tárolására.

## <a name="prerequisites"></a>Előfeltételek

- A **Funkciókezelés** munkaterületen kapcsolja be a **Nyomtatott, kivonatszámokat is tartalmazó vevői számlák archiválása** funkciót. További tájékoztatás: [Funkciókezelés – áttekintés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
- A szükséges dokumentumok nyomtatható formátumait a **Nyomtatáskezelés** lehetőségben konfigurálhatja.

Ez a funkció a következő dokumentumokra alkalmazható.

**Kinnlevőségek**
- Vevői számla
- Vevői jóváírás
- Szabadszöveges számla
- Szabadszövegű jóváírás

**Projektvezetés és könyvelés**
- Projektszámla
- Projekt jóváírása

## <a name="configure-customer-master-data"></a>Vevők alapadatainak konfigurálása
A következő lépések szerint konfigurálhatja a vevőadatokat és bekapcsolhatja a nyomtatott számlák mellékletként való automatikus mentésének lehetőségét.

1. Ugorjon a **Kinnlevőségek** > **Minden vevő** pontra. 
2. Válasszon ki egy vevőt, és a **Számlázás és szállítás** gyorslapon az **E-SZÁMLÁZÁS** szakaszban az **e-számlamelléklet** mezőben válassza az **Igen** lehetőséget.

## <a name="print-invoices"></a>Számlák nyomtatása
Az előző eljárásban konfigurált vevő számára bármilyen szabadszöveget, vevőt, projektszámlát vagy jóváírást feladhat és nyomtathat.

Nyissa meg nyomtatott számla **Mellékletek** oldalát. A **Melléklet** gyorslap **További részletek** mezőcsoportjának a **Dokumentum kivonatszáma** mezőjében keresse meg a nyomtatott számlához kiszámított tárolt kivonatszámot.

![Melléklet kivonatszáma.](media/attach-hash-num.jpg)

