---
title: A rakomány súlya csak pozitív számokat tartalmazhat.
description: A helyek közötti munka feldolgozásakor hibaüzenet jelenik meg a rakomány súlyával kapcsolatban, és a frissítés érvénytelenítve lesz. A hiba javításához kövesse az alábbi lépéseket.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 8ea1f6679a521e3e8683b8e5f18f509e98044414
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476540"
---
# <a name="load-weight-error-and-update-canceled-when-processing-work-between-locations"></a>Rakomány súly hiba és frissítés megszakítva a helyszínek közötti munka feldolgozásakor

## <a name="symptoms"></a>Tünetek

Ha nyitott munka létezik a munka csomagolási helyekről előkészítési helyekre, illetve az előkészítési helyekről a dokkolóhelyekre történő feldolgozásakor, a következő hiba jelenhet meg:

> A „Rakománysúly (=-%1)” mező csak pozitív számokat tartalmazhat. A frissítés meg lett szakítva.

## <a name="resolution"></a>Megoldás

A probléma megoldásához menjen a **Rendszerfelügyelet \> Időszakos feladatok \> Adatbázis \> Konzisztencia ellenőrzése** lehetőségre, majd futtassa a **Raktári rakománysúly konzisztencia ellenőrzése** folyamatot.
