---
title: Nem lehet környezetet létrehozni a Power Apps felügyeleti központjában
description: Ez a témakör bemutatja, mi a teendő, ha a rendszergazda nem tud környezetet létrehozni a Microsoft Power Apps felügyeleti központban.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 50a5aac71ec8ed850cfad32bdb1b8d589eb2885a
ms.sourcegitcommit: 7e32e5e39e762a4b1606161cb603a450d13b5251
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/23/2021
ms.locfileid: "7413561"
---
# <a name="cant-create-an-environment-in-the-power-apps-admin-center"></a>Nem lehet környezetet létrehozni a Power Apps felügyeleti központjában

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Kibocsátás**

- A bérlő/környezet-rendszergazda nem tud környezetet létrehozni a Microsoft Power Apps felügyeleti központban.
- A felhasználónak nincs olyan licence, amely lehetővé teszi környezetek létrehozását.

**Megoldás**

Győződjön meg arról, hogy a bérlői rendszergazda érvényes Power Apps P2-licencet rendelt a környezetet létrehozó felhasználóhoz. A következő Microsoft Dynamics szolgáltatási tervek nyújtanak engedélyeket környezetek létrehozásához:

| Teljes termékraktározási egység (SKU)       | Power Apps P2-szolgáltatási terv  |
|------------------------------------------------|----------------------------|
| Microsoft Dynamics 365 for Operations          | Power Apps for Dynamics 365 |
| Microsoft Dynamics 365 csomag Enterprise Edition | Power Apps for Dynamics 365 |

Felhívjuk figyelmét, hogy a különböző Microsoft Office-raktározási egységek (SKU-k) szintén biztosítják a jogot az önálló Power Apps Plan 2 raktározási egységekkel. Az a fontos, hogy ezek közül a raktározási egységek közül egy legyen jelen.

1. Ugorjon ide: [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).
2. Hozzon létre környezeteket az alábbi utasítások követésével: [Human Resources környezet létesítése](/dynamics365/unified-operations/talent/provisioning-talent).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
