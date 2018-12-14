---
title: "Személyes címekhez való hozzáférés biztonsági szerepkörönként"
description: "Ez a témakör bemutatja a probléma megoldását, amikor a vevő nem fér hozzá a személyes címeket."
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: d3f974f94b6c327fd70b8098d24f9e1f1e1e8eeb
ms.openlocfilehash: c1c1c3ce1233408e73d177f9e04f1137f3171a49
ms.contentlocale: hu-hu
ms.lasthandoff: 12/04/2018

---

# <a name="access-to-private-addresses-by-security-role"></a>Személyes címekhez való hozzáférés biztonsági szerepkörönként

[!include [banner](includes/banner.md)]

**Probléma**

Miután a vevő duplikál egy biztonsági szerepkört, és az új szerepkörrel jelentkezik be, a vevő nem látja a személyesként megjelölt címeket.

**Felbontás**

A probléma megoldásához a vevőnek az alábbi lépéseket kell követnie a duplikált biztonsági szerepkör esetén.

1. Lépjen a **Szervezeti felügyelet \> Globális címjegyzék \> Globális címjegyzék paraméterei** elemre.
2. A **Saját hely biztonsága** lapon helyezze át az új biztonsági szerepkört az **Elérhető szerepkörök** listából a **Kijelölt szerepkörök** listájába.
3. Válassza a **Mentés** lehetőséget.

![Globális címjegyzék paraméterei oldal](media/GAD-parameters.png)

