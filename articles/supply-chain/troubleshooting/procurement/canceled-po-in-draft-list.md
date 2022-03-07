---
title: A visszavont beszerzési rendelések megjelennek a munkaterület vázlatok listájában
description: A visszavont beszerzési rendelések megjelennek a Beszerzési rendelés előkészítő munkaterületének vázlatok listájában
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: f1dc23cd7e5b4b99cb7a9440d7d4666d8396511f
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476574"
---
# <a name="canceled-purchase-orders-appear-in-the-draft-list-in-the-workspace"></a>A visszavont beszerzési rendelések megjelennek a munkaterület vázlatok listájában

## <a name="symptoms"></a>Tünetek

Miután *Jóváhagyott* állapotú beszerzési rendeléseket vont vissza a **Beszerzési rendelések előkészítése** munkaterületen a beszerzési rendelések vázlatainak listáján továbbra is megjelennek a visszavont beszerzési rendelések.

## <a name="resolution"></a>Megoldás

Ez a probléma csak a változáskezelés hatálya alá tartozó beszerzési rendelésekhez fordulhat elő. Ennek oka az, hogy a törlést olyan módosításnak kell tekinteni, amelyet jóvá kell hagyni. A jóváhagyást a rendszer automatikusan elvégezheti. Ennek megfelelően az eljárás a megszüntetett beszerzési rendelés elküldése a jóváhagyási munkafolyamatba, hogy az *Jóváhagyott* állapotba lépjen. Ezen a ponton a **Beszerzési rendelés előkészítése** munkaterületén nem fog megjelenni a beszerzési rendelések vázlatainak listájában.
