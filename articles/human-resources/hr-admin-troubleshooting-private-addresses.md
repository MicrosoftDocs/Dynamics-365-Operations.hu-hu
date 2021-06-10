---
title: Hozzáférés privát címekhez biztonsági szerepkörnek megfelelően
description: Ez a cikk bemutatja az olyan probléma megoldását, amikor a vevő nem fér hozzá a személyes címekhez.
author: andreabichsel
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2edcef338f0ff8fcf231d4314fc972284397d000
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053323"
---
# <a name="access-to-private-addresses-by-security-role"></a>Személyes címekhez való hozzáférés biztonsági szerepkörönként

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Probléma**

Miután a vevő duplikál egy biztonsági szerepkört, és az új szerepkörrel jelentkezik be, a vevő nem látja a személyesként megjelölt címeket.

**Felbontás**

A probléma megoldásához a vevőnek az alábbi lépéseket kell követnie a duplikált biztonsági szerepkör esetén.

1. Lépjen a **Szervezeti felügyelet \> Globális címjegyzék \> Globális címjegyzék paraméterei** elemre.
2. A **Saját hely biztonsága** lapon helyezze át az új biztonsági szerepkört az **Elérhető szerepkörök** listából a **Kijelölt szerepkörök** listájába.
3. Válassza a **Mentés** lehetőséget.

![Globális címjegyzék paraméterei oldal](media/GAD-parameters.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]