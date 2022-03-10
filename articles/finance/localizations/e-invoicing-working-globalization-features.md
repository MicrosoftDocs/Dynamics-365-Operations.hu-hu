---
title: A globalizációs funkció összetevői
description: Ez a témakör áttekintést nyújt a globalizációs funkció összetevőiről.
author: dkalyuzh
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 87d7dd231b9ccda7761c91f129659c18039f3299
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/02/2022
ms.locfileid: "8371903"
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
