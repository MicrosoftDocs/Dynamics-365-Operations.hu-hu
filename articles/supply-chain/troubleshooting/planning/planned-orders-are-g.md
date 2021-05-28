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
ms.openlocfilehash: 1ea4bdb3729d163126234e02524cef331051cd48
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026582"
---
# <a name="master-planning-generates-planned-orders-for-phantom-products"></a>Az alaptervezés tervezett rendeléseket hoz létre a látszólagos termékekhez

Tudásbáziscikk száma: 4614729

## <a name="symptoms"></a>Tünetek

Tervezett rendeléseket jönnek létre a látszólagos termékekhez a mestertervezés futtatása után.

## <a name="resolution"></a>Felbontás

A kiadott termékek **Látszólagos** beállításának beállítása határozza meg az anyagjegyzék alapértelmezett sortípusát. Ha a **Látszólagos** beállítás értéke *Igen*, a rendszer továbbra is létrehozza a cikk tervezett rendeléseit, de a **Közvetlenül származtatott követelmény** beállítása minden tervezett rendelésnél *Igen* lesz. Így a tervezett termelési rendelést nem lehet saját magában megerősíteni. Ehelyett a rendszer mindig automatikusan hozzáadja a rendelést a szülő termelési rendelés megerősítésekor. Továbbá a tervezett látszólagos rendelés anyagjegyzéksorai a szülő termelési rendelés anyagjegyzékében is szerepelni fognak.
