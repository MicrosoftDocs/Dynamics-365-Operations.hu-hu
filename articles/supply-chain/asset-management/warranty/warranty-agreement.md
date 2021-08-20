---
title: Garanciaszerződések
description: Ez a témakör az Eszközkezelés modulban található garanciaszerződéseket ismerteti.
author: johanhoffmann
ms.date: 08/24/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8269b9f2084ddd0f69039044c29978ce7940270d5b569456f7a0bfca0a6f1f0b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6735303"
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

5. A **Garanciasorok** gyorslapon hajtsa végre az alábbi lépéseket a garanciamegállapodásba foglalandó sorok hozzáadásához:

    1. Ha új feltételt szeretne a garanciához hozzáadni, válassza a **Sor hozzáadása** elemet. A **Sor** mezőben a sorrendben következő sorszám automatikusan bekerül.
    2. Az **Időszak** mezőben válassza ki az garancia-időszak típusát.
    3. Az **Intervallum** mezőben adjon meg egy számot. Ez a mező határozza meg, hogy hány időszakra érvényes a garancia.
    4. A **Százalék** mezőbe írja be a garanciasor fedezeti százalékát. A százalékos érték azt jelzi, hogy a vállalat mekkora részt fedez.

![Garancia lap.](media/01-warranty.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]