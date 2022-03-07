---
title: Több minőségi rendelés létrehozásakor nem frissül a Legutóbbi tesztelés dátuma mező
description: Több minőségi rendelés létrehozásakor nem frissül a Legutóbbi tesztelés dátuma mező.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventBatch
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 46523c55f4fd42b0985397752f0c62a3e1a55e177f2308e20b7064e339758269
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6742028"
---
# <a name="the-last-tested-date-field-isnt-updated-when-multiple-quality-orders-are-created"></a>Több minőségi rendelés létrehozásakor nem frissül a Legutóbbi tesztelés dátuma mező

Tudásbáziscikk száma: 4612803

## <a name="symptoms"></a>Tünetek

Több minőségi rendelés létrehozásakor nem frissül a **Legutóbbi tesztelés dátuma** mező.

## <a name="resolution"></a>Felbontás

A rendszer úgy viselkedik, ahogy tervezték. A legutóbbi tesztelés dátuma nem kapcsolódik minőségi rendelésekhez. Azt a dátumot tárolja, amikor a késztermékeket először vásárolták vagy gyártották. Ez a dátum használatos az eltarthatósági idő ajánlott dátumának kiszámításához.
