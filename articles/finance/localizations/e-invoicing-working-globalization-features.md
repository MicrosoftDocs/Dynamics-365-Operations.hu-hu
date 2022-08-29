---
title: A globalizációs funkció összetevői
description: Ez a témakör áttekintést nyújt a globalizációs funkció összetevőiről.
author: gionoder
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 94e2d118c332a15f41f33184f5e44b0fdaccd000
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275226"
---
# <a name="globalization-feature-components"></a>A globalizációs funkció összetevői

[!include [banner](../includes/banner.md)]

A globalizációs funkció az összetevők egy készlete, amely az elektronikus jelentéskészítés (ER) konfigurációiban az adatok átalakítására vonatkozó szabályokat határozza meg. Ezek az összetevők például az elektronikus dokumentumok feldolgozására, majd a külső csatornáknak történő küldésre, illetve fogadásra vonatkozó útmutatások. Feltételeket is tartalmaznak, amelyek meghatározzák, hogy mikor fusson a funkció a bejövő üzleti adatokkal.

Minden összetevő egymástól függ. A globalizációs funkciók segítségével egyszerűen létrehozhatja és karbantarthatja ezt a függőséget, valamint támogathatja az összetevők életciklusának kezelését és verziószámozását.

## <a name="access-electronic-invoicing-feature-components"></a>Hozzáférés az Elektronikus számlázás funkcióösszetevőkhöz 

1. Jelentkezzen be a saját RCS-fiókjába.
2. A **Globalizációs funkció** munkaterületen a **Funkciók** szakaszban válassza ki az **Elektronikus számlázás** csempét.

    A globalizációs funkcióknak számos összetevője van. Az **Elektronikus számlázás funkció** lap külön lapot tartalmaz minden egyes összetevő számára.

    - **Verzió** – ez az összetevő támogatja a funkció életciklus-kezelését. A funkció segítségével kezelheti a funkció különböző verzióinak állapotát.
    - **Konfigurációk** – ez az összetevő a feldolgozási folyamatban használt kapcsolódó ER-formátum- és formátum-hozzárendelési konfigurációk kezelésére, megtekintésére és szerkesztésére használható.
    - **Beállítások** – Ez az összetevő lehetővé teszi a globalizációs szolgáltatások – például az e-számlázási szolgáltatások – felhasználóinak a kapcsolódó szolgáltatás verziójának beállításának kezelését. Ezért támogatja a kommunikációs és a válaszadási szabályok rugalmas felépítését.
    - **Környezetek** – ez az összetevő lehetővé teszi a globalizációs szolgáltatások, például az e-számlázási szolgáltatások felhasználóinak, hogy kezelni tudja a funkciók verzióbeállítását használó környezetet. Lehetőséget ad továbbá arra is, hogy engedélyezést adjanak azok a felhasználók, akik hozzáférhetnek a funkcióverzió beállításához.
    - **Szervezetek – ez** az összetevő lehetővé teszi a felhasználók számára a funkció megosztását külső szervezetekkel.
    - **Címkék** – ez az összetevő lehetővé teszi a hivatkozás globalizációs tervezetében használható címkeszolgáltatásokat.
