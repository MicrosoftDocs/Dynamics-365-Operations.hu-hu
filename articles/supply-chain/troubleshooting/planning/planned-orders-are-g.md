---
title: Az alaptervezés tervezett rendeléseket hoz létre a látszólagos termékekhez
description: Tervezett rendeléseket jönnek létre a látszólagos termékekhez a mestertervezés futtatása után.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: anderso
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: f3170bcb723e2d7483258bb0ecf786e62f2aa3d196745074c2ac554bc212ec55
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6742004"
---
# <a name="master-planning-generates-planned-orders-for-phantom-products"></a>Az alaptervezés tervezett rendeléseket hoz létre a látszólagos termékekhez

Tudásbáziscikk száma: 4614729

## <a name="symptoms"></a>Tünetek

Tervezett rendeléseket jönnek létre a látszólagos termékekhez a mestertervezés futtatása után.

## <a name="resolution"></a>Felbontás

A kiadott termékek **Látszólagos** beállításának beállítása határozza meg az anyagjegyzék alapértelmezett sortípusát. Ha a **Látszólagos** beállítás értéke *Igen*, a rendszer továbbra is létrehozza a cikk tervezett rendeléseit, de a **Közvetlenül származtatott követelmény** beállítása minden tervezett rendelésnél *Igen* lesz. Így a tervezett termelési rendelést nem lehet saját magában megerősíteni. Ehelyett a rendszer mindig automatikusan hozzáadja a rendelést a szülő termelési rendelés megerősítésekor. Továbbá a tervezett látszólagos rendelés anyagjegyzéksorai a szülő termelési rendelés anyagjegyzékében is szerepelni fognak.
