---
title: Hiba történt a tanúsítvány elérési útja során a WMS frissítése vagy áttelepítése során
description: Ha az alkalmazás a WMS frissítése vagy áttelepítése során a „Nem található a tanúsítvány elérési útjának megbízhatósági kapcsolatok alapja” hiba jelenik meg, ez az oldal útmutatást ad a probléma megoldására.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 2cff41455268c43bdd99e285b9675f0c69be7de7
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476526"
---
 # <a name="trust-anchor-for-certification-path-not-found-when-updating-and-migrating-to-wms"></a>Nem található a tanúsítvány elérési útjának megbízhatósági kapcsolatok alapja a WMS-be történő frissítéskor és migráláskor

## <a name="symptoms"></a>Tünetek

Amikor a speciális raktárkezelésre (WMS) frissít vagy áttelepít, a Warehouse Management alkalmazás a következő hibaüzenetet jelenítheti meg:

> java.security.cert.certPathValidatorException: A tanúsítvány elérési útjának megbízhatósági horgonyzás nem található.

## <a name="cause"></a>Ok

Ez azért fordul elő, mert az önálló aláírású tanúsítványok nem megbízhatóak az Android 8+ rendszer használata esetén a helyszíni környezetekben.

## <a name="resolution"></a>Megoldás

Külső (nyilvános) tanúsító hatóság (CA) használata. A probléma javítása a Warehouse Management alkalmazás 1.9.0.0 verziójában érhető el. További információért a problémával és a megoldásával kapcsolatban lásd: [Nem található a tanúsítvány elérési útjának megbízhatósági kapcsolatok alapja az alkalmazáskapcsolat beállításakor](certification-path-app-connection-error.md).
