---
title: Garanciaszerződések
description: Ez a témakör az Eszközkezelés modulban található garanciaszerződéseket ismerteti.
author: josaw1
manager: tfehr
ms.date: 08/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e9cbb9068101f3004179f338da18af0369190807
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3215378"
---
# <a name="warranty-agreements"></a>Garanciaszerződések

[!include [banner](../../includes/banner.md)]

 


Az Eszközkezelés modulban beállíthat garanciafeltételeket, amelyeket egy eszközhöz vagy eszköztípushoz kapcsolhat. A garanciafeltételeket meghatározott időpontra hozzák létre. A garanciát beállíthatja teljes fedezet vagy részleges fedezet biztosítására, és beállíthatja a feltételeket órákhoz, költségekhez és cikkekhez kapcsolódóan.

Első lépésként hozzon létre egy bármilyen szállítói garanciaszerződést, amely a berendezésére vonatkozik. Majd csatoljon garanciaszerződéseket eszközökhöz vagy eszköztípusokhoz. A szállítói garanciaszerződések csak tájékoztatási célokat szolgálnak. Ha egy eszközön be van állítva szállítói garancia, akkor az eszközön látható a garancia fedezeti időszaka.

## <a name="create-a-warranty-agreement"></a>Garanciaszerződés létrehozása

A garanciaszerződések több szerződéssort is tartalmazhatnak a munkaórák, költségek és cikkek garanciájának fedezésére.

1. Válassza ki az **Eszközkezelés** \> **Beállítás** \> **Eszközök** \> **Garancia** elemet.
2. Válassza az **Új** lehetőséget egy termék létrehozásához.
3. A **Garancia** mezőben adjon meg egy garanciaazonosítót.
4. A **Név** mezőbe adja meg a leírást.

    A **Garancia** gyorslapon az **Eszközök** mezőben látható azon aktív eszközök száma, amelyek a garanciaszerződést használják.

5. Az **Órákra vonatkozó garancia** és a **Cikkre vonatkozó garancia** gyorslapokon kövesse ezeket a lépéseket a sorok hozzáadásához, amelyeket szerepeltetni kíván a garanciaszerződésben, amelyek az órákhoz vagy cikkekhez tartoznak:

    1. Ha új feltételt szeretne a garanciához hozzáadni, válassza a **Sor hozzáadása** elemet. A **Sor** mezőben a sorrendben következő sorszám automatikusan bekerül.
    2. Az **Időszak** mezőben válassza ki az garancia-időszak típusát.
    3. Az **Intervallum** mezőben adjon meg egy számot. Ez a mező határozza meg, hogy hány időszakra érvényes a garancia.
    4. A **Százalék** mezőbe írja be a garanciasor fedezeti százalékát. A százalékos érték azt jelzi, hogy a vállalat mekkora részt fedez.

![Garancia lap](media/01-warranty.png)
