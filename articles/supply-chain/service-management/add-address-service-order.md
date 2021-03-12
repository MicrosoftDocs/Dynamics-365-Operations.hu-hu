---
title: Cím hozzáadása szolgáltatási rendeléshez
description: Ez a témakör bemutatja, hogyan lehet hozzáadni egy vevő címét a szervizrendeléshez.
author: ShylaThompson
manager: tfehr
ms.date: 05/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d6c8f00eb1a1fe2ef3aea22da20ce218d7568f64
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4966055"
---
# <a name="add-an-address-to-a-service-order"></a>Cím hozzáadása szolgáltatási rendeléshez    

[!include [banner](../includes/banner.md)]


Ez a témakör bemutatja, hogyan lehet hozzáadni egy vevő címét a szervizrendeléshez. A szervizrendelések létrehozásakor abból a projektből veszi át a program a címadatokat, amelyhez a szervizrendelés csatolva van. Azonban kiválaszthat egy másodlagos helyet azon címek közül, amelyek már szerepelnek a Microsoft Dynamics AX rendszerben vevők, szállítók, helyek, raktár, szolgáltatási rendelések és projektek esetén.

Létre is hozhat új címeket. Alapértelmezés szerint az új cím átkerül a projekthez. Azonban megadhatja, hogy az új címnek csak a szolgáltatás jelenlegi példánya esetén van jelentősége. Ebben az esetben az új cím nem kerül át a projekthez.

## <a name="create-a-customer-address-for-a-service-order"></a>Vevő cím létrehozása egy szervizrendeléshez

Egy cím hozzáadásához a szervizrendeléshez, tegye a következőket:

1.  Kattintson a következőkre: **Szolgáltatáskezelés** \> **Közös** \> **Szervizrendelések** \> **Szervizrendelések**.

2.  Nyissa meg azt a szervizrendelést, amelyhez címet szeretne létrehozni.

3.  Kattintson a **Műveleti ablaktáblában** lévő **Szerkesztés** lehetőségre, majd válassza a **Fejlécnézet** lehetőséget.

4.  A **Cím** gyorslapon kattintson a **Cím hozzáadása** lehetőségre.

5.  Az **Új cím** képernyőn adjon meg egy egyedi nevet a cím számára, majd töltse ki a többi mezőt. 
    

    > [!WARNING]
    > <P>Ha egy létező cím nevével megegyező nevet ad meg, akkor a többi mezőbe beírt adatok felülírják a már meglévő címhez tartozó adatokat.</P>


6.  Kattintson az **OK** gombra az új címnek a szervizrendeléshez másolásához.

## <a name="specify-an-alternative-address-on-a-service-order"></a>Másodlagos cím megadása egy szervizrendelésen

Egy másodlagos cím hozzáadásához a szervizrendeléshez, tegye a következőket:

1.  Kattintson a következőkre: **Szolgáltatáskezelés** \> **Közös** \> **Szervizrendelések** \> **Szervizrendelések**.

2.  Nyissa meg azt a szervizrendelést, amelyhez másodlagos címet szeretne megadni.

3.  Kattintson a **Műveleti ablaktáblában** lévő **Szerkesztés** lehetőségre, majd válassza a **Fejlécnézet** lehetőséget.

4.  A **Cím** gyorslapon kattintson az **Egyéb cím** lehetőségre.

5.  A **Cím kiválasztása** űrlapon, a **Bejegyzéstípus** mezőben válassza ki a **Szervizrendelések** lehetőséget.

6.  Válasszon ki egy címet, majd kattintson az **OK** gombra a szervizrendeléshez való másoláshoz.


  


