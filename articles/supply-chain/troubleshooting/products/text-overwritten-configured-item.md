---
title: Szöveg felülírva, amikor egy cikket konfigurálnak egy értékesítési rendeléssorban
description: Ha egy termék egy értékesítésirendelés-sorban van konfigurálva, a módosított szöveget felülírja a szokásos szöveg. A szöveget a sor konfigurálása után kell módosítania, nem korábban.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 20239b9b0eecb355274e909a8b8b39450e468c7e
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476506"
---
# <a name="item-text-is-overwritten-when-a-product-is-configured-on-a-sales-order-line"></a>A cikk szövege felülíródik, amikor egy terméket konfigurálnak egy értékesítési rendeléssorban

## <a name="symptoms"></a>Tünetek

Ez a probléma akkor fordul elő, ha egy konfigurálható cikkhez értékesítési rendeléssort hoz létre, majd módosítja a cikk szövegét. Amikor konfigurálja az elemet, majd az **OK** lehetőséget választja, a program felülírja a szöveget a szabványos szöveggel.

## <a name="resolution"></a>Megoldás

Ez a viselkedés várható. A szövegmező tartalmazza a változat nevét, amelyet csak a sor konfigurálása után tölt ki a program. Ezért a szöveget a sor konfigurálása után kell módosítania, nem korábban.
