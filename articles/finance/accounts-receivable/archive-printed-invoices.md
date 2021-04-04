---
title: Nyomtatott vevői számlák archiválása kivonatszámokkal
description: Ez a témakör bemutatja, hogyan engedélyezheti az archiválást a nyomtatott, kivonatszámokat is tartalmazó vevői számlák tárolására.
author: ilyako
manager: AnnBe
ms.date: 03/05/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: d502ec5d286573c72e207419b66f283183009c09
ms.sourcegitcommit: 08ac570bece3e4ee4a0f632f51623e328536dfcf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/08/2021
ms.locfileid: "5557480"
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

