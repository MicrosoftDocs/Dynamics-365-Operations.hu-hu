---
title: A készletnaplója zárolva van, és a munkafolyamat kötegelt feladata nem működik
description: Valamelyik készletnaplót valamilyen művelet zárolta, ezért nem lesz kiadva
author: sherry-zheng
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 8b21ec2e2b3b8546dcb138422c5540053392c179
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476525"
---
# <a name="your-inventory-journal-is-locked-and-the-workflow-batch-job-doesnt-work"></a>A készletnaplója zárolva van, és a munkafolyamat kötegelt feladata nem működik

## <a name="symptoms"></a>Tünetek

Valamelyik készletnaplót valamilyen művelet zárolta, ezért nem lesz kiadva. Ha például a feladás során (amely rendszerzárolási művelet) ismeretlen hiba történik, a napló zárolt állapotú maradhat a rendszerben. Ebben az esetben a munkafolyamat munkatétel-kezelője hibát jelez, miközben zárolja az ellenőrzést.

## <a name="resolution"></a>Megoldás

Jelentkezzen be a Supply Chain Management SQL Server példányába, és ellenőrizze, hogy az **InventJournalTable.SystemBlocked** beállítása *1*-e. Ha igen, győződjön meg róla, hogy a napló nem lehet zárolt állapotú, majd állítsa vissza az **InventJournalTable.SystemBlocked** értékét *0*-ra.
