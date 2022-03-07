---
title: A szervizrendelések fokozatai
description: Szervizrendelési szakaszok definiálásával, és azok dolgozókhoz való hozzárendelésével, a szolgáltatási szervezeten belül dolgozó, különböző személyek által elvégzett feladatokon keresztül szabályozhatók a szervizrendelés folyamatai.
author: kamaybac
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAStageTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0a43cbe0cf5993a305ff500f34f0da5d3763084c
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7576328"
---
# <a name="service-order-stages"></a>A szervizrendelések fokozatai   

[!include [banner](../includes/banner.md)]


Annak érdekében, hogy meghatározza az elvégzendő feladatokat, a feladatok sorrendjét, és a feladatok elvégzéséért felelős dolgozókat, a szolgáltatási rendeléshez szakaszok beállítására van lehetőség. Szervizrendelési szakaszok definiálásával, és azok dolgozókhoz való hozzárendelésével, a szolgáltatási szervezeten belül dolgozó, különböző személyek által elvégzett feladatokon keresztül szabályozhatóvá válnak a szervizrendelés folyamatai. A szakaszok sorrendjének tartalmaznia kell a kezdő szakaszt.

Az egyes szakaszokon belül engedélyezett műveleteket is meghatározhat. Például ha az utolsó szakaszhoz tartozó jelölőnégyzetet leszámítva az összes **Feladás** jelölőnégyzet jelét törli, akkor megakadályozhatja, hogy egy szervizrendelés azelőtt feladásra kerüljön, hogy a rendelés összes szakasza feldolgozásra kerülne.

## <a name="branching-in-service-order-stages"></a>Szervizrendelési szakaszok elágaztatása

Ha egy szolgáltatási szakaszt állít be, a következő szakaszhoz több lehetőség vagy oldalág létrehozása közül választhat. A kezdeti szakasz befejezése után az összes létrehozott ág közül választhat. Állítsa be például a **Tervezés** lehetőséget kezdeti szakaszként. Hozzon létre két szakaszt **Folyamatban** és **Érvénytelenítés** névvel, majd válassza a **Tervezés** szakaszt azok szülőjének. Társítsa a **Tervezés** szakaszt az értékesítési rendeléshez. Amikor az értékesítési rendelés tervezési szakasza befejeződik, válassza a **Folyamatban** szakaszt, ha az értékesítési rendelés készen áll a munkára, vagy választhatja az **Érvénytelenítés** szakaszt, amennyiben az értékesítési rendelést érvénytelítették.

## <a name="see-also"></a>Lásd még

[Szervizrendelési fokozatok beállítása](set-up-service-order-stages.md)

[Szervizrendelés fokozatának módosítása](change-service-order-stage.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]