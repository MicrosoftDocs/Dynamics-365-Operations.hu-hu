---
title: A szállítólevél javítása nem feldolgozható
description: Ha a feladás után megpróbál kijavítani egy szállítólevelet, hibaüzenet jelenik meg. Ez a lap bemutatja, hogyan lehet kijavítani a WMS számára engedélyezett cikkek feladott szállítólevelét.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: bb0d827adff8abd8762bf2de844cad5574628e4b
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476578"
---
# <a name="delivery-note-correction-cant-be-processed"></a>A szállítólevél javítása nem feldolgozható

## <a name="symptoms"></a>Tünetek

Feladása után nem vonhatja vissza a szállítólevelet, mert a **Mégse** gomb nem érhető el. A szállítólevél nem helyesbíthető. Ha megkísérli, a következő hibaüzenetet kapja:

> A szállítólevél javítása nem feldolgozható. A szállítólevél csak olyan cikkeket tartalmaz, amelyekre raktárkezelési folyamatok vonatkoznak, mivel ezeket a szállítólevél javítása nem támogatja.

## <a name="resolution"></a>Megoldás

A speciális raktárkezeléshez (WMS) engedélyezett cikkek könyvelt szállítólevélének helyesbítéséhez a könyvelést a rakományból kell kiadnia, nem pedig közvetlenül a rendelésből.
