---
title: Hozzáférés privát címekhez biztonsági szerepkörnek megfelelően
description: Ez a cikk bemutatja az olyan probléma megoldását, amikor a vevő nem fér hozzá a személyes címekhez.
author: andreabichsel
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8daee1b645836e96a4bf3057cb317d5409d4583a
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5803921"
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