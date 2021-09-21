---
title: A mennyiség nem érvényes több azonosítótáblát is tartalmazó kitárolási munkához
description: Amikor olyan kitárolási munka van, amelyben több azonosítótábla van egy helyen, a mennyiség nem érvényes az egység ea-hoz. Ellenőrizze a következő mezők helyességét.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 5b245f71e80339fee3e42cfffa0396078a56926e
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476511"
---
# <a name="quantity-not-valid-when-theres-picking-work-with-multiple-lps-in-one-location"></a>A mennyiség nem érvényes, ha egy helyen több azonosítótáblával folyik kitárolási munka

## <a name="symptoms"></a>Tünetek

Amikor olyan kitárolási munka van, amelyben több azonosítótábla van egy helyen, a mennyiség nem érvényes az egység *ea*-hoz, és a következő hibaüzenetet kapja:

> A mennyiség nem érvényes a(z) 1% egységhez.

## <a name="resolution"></a>Megoldás

Ellenőrizze, hogy a kiadott termék vagy termék változatának **Egységszekvenciacsoport-azonosítója** és **Egységek átváltása** mezők helyesen vannak beállítva.

Ne felejtse el, hogy a 10.0.15 verzióban ki lett javítva a hibaüzenet, hogy megjelenítse a várt mennyiséget (lásd: [KB 4581627](https://fix.lcs.dynamics.com/Issue/Details/?bugId=486531)). Az új hibaüzenet:

> A mennyiség nem érvényes. Elvárt %1 %2.
