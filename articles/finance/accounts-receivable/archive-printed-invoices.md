---
title: Nyomtatott vevői számlák archiválása kivonatszámokkal
description: Ez a témakör bemutatja, hogyan engedélyezheti az archiválást a nyomtatott, kivonatszámokat is tartalmazó vevői számlák tárolására.
author: ilyako
ms.date: 03/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-03-05
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 841e6059f5b0d70dbd1fe12a1f8910bbb31ddc86
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018978"
---
# <a name="archive-printed-customer-invoices-with-hash-numbers"></a>Nyomtatott vevői számlák archiválása kivonatszámokkal

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Egyes országokban jogszabályi előírás a kiszámított kivonatszámok tárolása a rendszerben, bizonyos dokumentumok kinyomtatott változatával együtt. A kivonatszámok a hatóságoknak való jelentésre és a könyvvizsgálatok során használhatók.

Ez a témakör bemutatja, hogyan konfigurálhatja az archiválást a nyomtatott, kivonatszámokat is tartalmazó vevői számlák tárolására.

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

![Melléklet kivonatszáma](media/attach-hash-num.jpg)

