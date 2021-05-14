---
title: Nem erősítheti meg szállítmányt, mert probléma van a naptárral
description: Nem erősítheti meg szállítmányt, mert probléma van a naptárral
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f1fccd10d8867252f32b37c77f9a3bad54157bdd
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938485"
---
# <a name="you-cant-confirm-a-shipment-because-of-an-issue-with-the-calendar"></a>Nem erősítheti meg szállítmányt, mert probléma van a naptárral

Hibakód: TRX2716

## <a name="symptoms"></a>Tünetek

Szállítmány megerősítésekor a rendszer a következő hibaüzenetet jeleníti meg:

> A naptártípus (%1) megköveteli a találkozón (%2) történő be- és kijelentkezést.

Ezért nem tudja megerősíteni a szállítmányt a betöltéshez.

## <a name="cause"></a>Ok

Léteznek aktív találkozók a meglévő rakományhoz. Van például egy olyan szabály, amely megköveteli a járművezető bejelentkezését. Emiatt a rakomány jelenleg olyan állapotban van, amelyben a szállítmány megerősítése sikertelen.

## <a name="resolution"></a>Felbontás

A rakományhoz kapcsolódó aktív találkozókon megvizsgálhatja és kijavíthatja az esetleges problémákat.

1. Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.
1. Válassza ki azt a rakományt, amelynél a szállítmányt nem lehet megerősíteni.
1. A Művelet ablaktábla **Szállítás** fülén, a **Találkozók** csoportban válassza a **Találkozók ütemezése** elemet.
1. Tegye a következők egyikét:

    - Győződjön meg arról, hogy a gépjárművezető találkozóval kapcsolatos be- és kijelentkezése befejeződött.
    - A találkozó befejezése vagy visszavonása.
    - A **Gépjárművezető bejelentkezéséhez szükséges** beállítás letiltása a kapcsolódó találkozószabályhoz.
