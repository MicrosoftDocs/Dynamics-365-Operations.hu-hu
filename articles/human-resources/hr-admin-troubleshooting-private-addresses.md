---
title: Hozzáférés privát címekhez biztonsági szerepkörnek megfelelően
description: Ez a témakör leírja, hogyan lehet megoldani, ha egy vevő nem fér hozzá a privát címekhez.
author: twheeloc
ms.date: 09/13/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7c1db052937b03817f22b37c50b9f1b319579cb2
ms.sourcegitcommit: 27ce4fc706100b626b81c3a1023238acd872e76c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/20/2022
ms.locfileid: "9702103"
---
# <a name="access-to-private-addresses-by-security-role"></a>Hozzáférés privát címekhez biztonsági szerepkörnek megfelelően


[!INCLUDE [PEAP](../includes/peap-2.md)]

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
