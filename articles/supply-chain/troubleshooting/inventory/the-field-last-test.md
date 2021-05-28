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
ms.openlocfilehash: 6f796bdaa88d32b1c58dd8a4bca19f0ce4f3943d
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026586"
---
# <a name="the-last-tested-date-field-isnt-updated-when-multiple-quality-orders-are-created"></a>Több minőségi rendelés létrehozásakor nem frissül a Legutóbbi tesztelés dátuma mező

Tudásbáziscikk száma: 4612803

## <a name="symptoms"></a>Tünetek

Több minőségi rendelés létrehozásakor nem frissül a **Legutóbbi tesztelés dátuma** mező.

## <a name="resolution"></a>Felbontás

A rendszer úgy viselkedik, ahogy tervezték. A legutóbbi tesztelés dátuma nem kapcsolódik minőségi rendelésekhez. Azt a dátumot tárolja, amikor a késztermékeket először vásárolták vagy gyártották. Ez a dátum használatos az eltarthatósági idő ajánlott dátumának kiszámításához.
