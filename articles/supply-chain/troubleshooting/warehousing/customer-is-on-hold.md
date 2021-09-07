---
title: Nem erősítheti meg a szállítmányt, mert az ügyfél várakoztatott
description: Nem erősítheti meg a szállítmányt, mert az ügyfél várakoztatott.
author: GalynaFedorova
ms.date: 07/30/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 801778fc8f04b106bf168a3dcd5a89767a837740
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/13/2021
ms.locfileid: "7344264"
---
# <a name="you-cant-confirm-a-shipment-because-the-customer-is-on-hold"></a>Nem erősítheti meg a szállítmányt, mert az ügyfél várakoztatott

Hibakód: WAX:CustomerOnHoldShipmentCannotBeConfirmed

## <a name="symptoms"></a>Tünetek

Szállítmány megerősítésekor a rendszer a következő hibaüzenetet jeleníti meg:

> A(z) %1 szállítmány nem erősíthető meg, mivel a vevő várakoztatott állapotban van a következő időtartamig: %2.

Ezért nem tudja megerősíteni a szállítmányt a betöltéshez.

## <a name="cause"></a>Ok

A rakomány vagy szállítmány vevői számlája fel várakoztatott. Emiatt a vevő állapota megakadályozza a szállítás megerősítését.

## <a name="resolution"></a>Megoldás

A következő eljárás szerint oldhatja fel a vevői számla zárolását.

1. Nyissa meg a **Kinnlevőségek \> Vevők \> Minden vevő** lehetőséget.
1. Nyissa meg azt a vevői számlát, amelyre nem lehet visszaigazolni a szállítmányt.
1. A **Jóváírás és beszedések** gyorslapon állítsa a **Számlázás és szállítás felfüggesztve** mezőt *Nem* értékre.
1. Ismételje meg ezt az eljárást minden zárolt vevőnél a rakományra.
