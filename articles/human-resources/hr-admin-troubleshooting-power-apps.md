---
title: Nem lehet környezetet létrehozni a Power Apps felügyeleti központjában
description: Ez a cikk bemutatja, hogy mi a teendő olyankor, ha a rendszergazda nem tud környezetet létrehozni a Microsoft Power Apps felügyeleti központban.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 68e6dbcbbc9811211570e968047f5faa8a2c8bd0
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4418827"
---
# <a name="cant-create-an-environment-in-the-power-apps-admin-center"></a>Nem lehet környezetet létrehozni a Power Apps felügyeleti központjában

**Kibocsátás**

- A bérlő/környezet-rendszergazda nem tud környezetet létrehozni a Microsoft Power Apps felügyeleti központban.
- Az engedélyt, amely jogot biztosít a felhasználóknak, hogy végrehajtsák a környezet-létrehozás lépését, még nem rendelték közvetlenül a felhasználóhoz, aki az adott lépést végrehajtja.

**Megoldás**

Győződjön meg arról, hogy a bérlő adminisztrátor hozzárendelt érvényes Power Apps P2-licencet közvetlenül ahhoz a felhasználóhoz, aki végrehajtja a környezet létrehozási lépését. A következő Microsoft Dynamics szolgáltatási tervek biztosítják ezt a jogot.

| Teljes termékraktározási egység (SKU)       | Power Apps P2-szolgáltatási terv  |
|------------------------------------------------|----------------------------|
| Microsoft Dynamics 365 for Operations          | Power Apps for Dynamics 365 |
| Microsoft Dynamics 365 csomag Enterprise Edition | Power Apps for Dynamics 365 |

Felhívjuk figyelmét, hogy a különböző Microsoft Office-raktározási egységek (SKU-k) szintén biztosítják a jogot az önálló Power Apps Plan 2 raktározási egységekkel. Az a fontos, hogy ezek közül a raktározási egységek közül egy legyen jelen.

1. Ugorjon ide: [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).
2. Hozzon létre környezeteket az alábbi utasítások követésével: [Human Resources környezet létesítése](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).


[!INCLUDE[footer-include](../includes/footer-banner.md)]