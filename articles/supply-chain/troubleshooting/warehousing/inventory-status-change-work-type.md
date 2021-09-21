---
title: Nem választható ki a készlet állapotának változása munkatípusként
description: Nem hozhat létre munkasablonsort a Készletállapot-változáshoz, mert a munkatípust csak a rendszerfolyamatok használják. Válasszon másik munkatípust.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: ad7f26f3235d15779583f9cdadeb4e6dca16242a
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476586"
---
# <a name="cant-select-inventory-status-change-in-the-work-type-column"></a>A Munkatípus oszlopban nem választható ki a készlet állapotának változása

## <a name="symptoms"></a>Tünetek

A Microsoft Dynamics 365 Supply Chain Management konfigurálásakor a következő hibaüzenet jelenhet meg:

> Nem hozhat létre munkasablonsort a Készletállapot-változáshoz, mert a munkatípus nem érvényes. Válasszon másik munkatípust.

## <a name="resolution"></a>Megoldás

Ez szándékosan van. A *Készletállapot módosítás* munkatípust csak rendszerfolyamatok használják. Ezt nem lehet konfigurálni. Mivel a munkatípusok listája számbavételként van rögzítve, a program nem tudja kiszűrni a **Munka típusa** legördülő menüből a felesleges bejegyzéseket.
