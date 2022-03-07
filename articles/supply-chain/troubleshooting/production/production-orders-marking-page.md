---
title: A termelési rendelések nem jelennek meg a Jelölés oldalon
description: Egyes termelési rendelések nem jelennek meg a Jelölés oldalon. Ez a témakör bemutatja azt a három termékkonfigurációt, amelyek nem érhetők el megjelölésre.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 87507e91d3feb2557e7ba771b8e34ff7ca105749
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476498"
---
# <a name="production-orders-arent-shown-on-the-marking-page"></a>A termelési rendelések nem jelennek meg a Jelölés oldalon

## <a name="symptoms"></a>Tünetek

A diszkrét gyártással való munka során egyes termelési rendelések nem jelennek meg a **Jelölés** lapon.

## <a name="resolution"></a>Megoldás

A következő konfigurációkkal rendelkező termékeket nem lehet megjelölni. Ezért ezek nem jelennek meg a **Jelölés** oldalon:

- A termékek *Tényleges súly* típusú termékekként vannak meghatározva.
- Ezek engedélyezve vannak a speciális raktári folyamatokhoz.
- Úgy vannak konfigurálva, hogy az *Elszámolóár* elve szabályozza őket.
