---
title: A munka nincs zárolva
description: A munka nincs zárolva
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTable_WHSWorkUnblocking
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: d64ab282972e46e8857581b59e5705dd15667328
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924204"
---
# <a name="work-isnt-blocked"></a>A munka nincs zárolva

Hibakód: WHSUnblockNotBlockedWorkErrorMessage

## <a name="symptoms"></a>Tünetek

A rendszer a következő hibaüzenetet jeleníti meg:

> A(z) %1 azonosítóval rendelkező munka nincs zárolva.

## <a name="cause"></a>Ok

A hullám **Blokkolt hullám** beállításának értéke *Nem*. A munka zárolása nem oldható fel, mert jelenleg nincs zárolva.

## <a name="resolution"></a>Felbontás

 Csak azok a munka zárolása oldható fel, amelyekben a **Blokkolt hullám** beállítása *Igen*.
