---
title: Hozzáférés privát címekhez biztonsági szerepkörnek megfelelően
description: Ez a téma elmagyarázza, hogyan oldható meg, ha egy ügyfél nem tud hozzáférni a privát címekhez.
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
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0b96733946e4ef79de244730d0c442b9900426c1
ms.sourcegitcommit: 7e32e5e39e762a4b1606161cb603a450d13b5251
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/23/2021
ms.locfileid: "7413339"
---
# <a name="access-to-private-addresses-by-security-role"></a>Hozzáférés privát címekhez biztonsági szerepkörnek megfelelően

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Probléma**

Miután a vevő duplikál egy biztonsági szerepkört, és az új szerepkörrel jelentkezik be, a vevő nem látja a személyesként megjelölt címeket.

**Felbontás**

A probléma megoldásához a vevőnek az alábbi lépéseket kell követnie a duplikált biztonsági szerepkör esetén.

1. Lépjen a **Szervezeti felügyelet \> Globális címjegyzék \> Globális címjegyzék paraméterei** elemre.
2. A **Saját hely biztonsága** lapon helyezze át az új biztonsági szerepkört az **Elérhető szerepkörök** listából a **Kijelölt szerepkörök** listájába.
3. Válassza a **Mentés** lehetőséget.

![Globális címjegyzék paraméterei oldal.](media/GAD-parameters.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
