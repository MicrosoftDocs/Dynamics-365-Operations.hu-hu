---
title: A rendszergazdák nem tudják törölni a rendelésvárakoztatásokat, mert nincsenek felhatalmazva
description: A rendszergazdák nem tudják törölni a rendelésvárakoztatásokat, mert nincsenek felhatalmazva.
author: SmithaNataraj
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: acabd6409d9b2860535335bc648bcc34304e0cb0
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026592"
---
# <a name="system-administrators-cant-clear-order-holds-because-they-arent-authorized"></a>A rendszergazdák nem tudják törölni a rendelésvárakoztatásokat, mert nincsenek felhatalmazva

Tudásbáziscikk száma: 4614642

## <a name="symptoms"></a>Tünetek

A rendszergazdák csak akkor tudják törölni az értékesítési rendelés várakoztatásokat ha a rendelésvárakoztatási kódhoz megadott konkrét szerepkörük van.

## <a name="resolution"></a>Felbontás

Egyes műveletek – például az értékesítési rendeléstartások törlése – az üzleti irányelvek beállításától függ. A rendszergazdák általában nem hajthatnak végre ilyen típusú műveleteket. 

Az egyes feladatok végrehajtásához való hozzáférést jellemzően üzleti irányelvek szabályozzák, és csak a szervezet meghatározott személyei jogosultak feladat elvégzésére. Ilyenek lehetnek például a munkafolyamat-jóváhagyások erdményeképpen létrejött jóváhagyások, illetve a munkafolyamat-konfiguráció eredményeként keletkező konkrét feladatok.

Bár nincs munkafolyamat társítva rendelések visszatartásához, az elv hasonló. A megfelelő szerep egy szervezethez kapcsolódó olyan személyek csoportját jelöli ki, akiknek joga van a rendelések visszatartásának törléséhez. Ezt a jogosultságot nem feltétlenül kell biztosítani minden rendszergazdának, mert ez a megközelítés sérti a meghatározott üzleti irányelveket.
