---
title: 'Útmutató: Igény-előrejelzés manuális módosítása'
description: Ez a témakör azt ismerteti, hogyan lehet módosítani egy cikk előrejelzését.
author: t-benebo
ms.date: 08/12/2019
ms.topic: business-process
ms.search.form: EcoResProductDetailsExtended, ForecastSales
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6275749f85c9b9d5a8b89da6340beeafbe22c2d4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8859256"
---
# <a name="guide-modify-a-demand-forecast-manually"></a>Útmutató: Igény-előrejelzés manuális módosítása

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja egy cikk előrejelzésének módosítását. Ezt az eljárást a termeléstervező használja.

## <a name="modify-the-forecast-for-a-selected-item"></a>Egy kiválasztott cikk előrejelzésének módosítása

Egy kiválasztott cikk előrejelzésének módosítása:

1. Kattintson a **Modulok \>Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.
1. Keresse meg és jelölje ki a kívánt rekordot a listán. Válassza ki azt a cikket, amelynek módosítani szeretné az előrejelzését.
1. A műveletpanelen nyissa meg a **Terv** lapot, és válassza az **Igény-előrejelzés** lehetőséget.
1. Jelöljön ki egy sort a listában. Ha nincsenek előrejelzési sorok, hozzon létre egy újat: válassza az **Új** elemet a Művelet panelen.  
1. Adjon meg egy pozitív számot az **Értékesítési mennyiség** mezőben. Ez a szám a cikk előre jelzett mennyiségét jelöli. Ha negatív számot ad meg, a rendszer hibát jelez.
1. Töltse ki a egyéb mezőket, ha szükséges.
1. A Művelet ablaktáblán válassza a **Mentés** lehetőséget.

## <a name="modify-the-forecast-for-one-or-more-items-with-microsoft-excel"></a>Egy vagy több cikk előrejelzésének módosításához a Microsoft Excel segítségével

Egy vagy több cikk előrejelzésének módosításához a Microsoft Excel segítségével:

1. Válasszon az alábbi lehetőségek közül:
    - Nyissa meg bármelyik cikk **igény-előrejelzés** lapját (nem számít, melyiket) az előző szakaszban leírtak szerint.
    - Ugorjon az **Alaptervezés \> Előrejelzés \> Manuális előrejelzési bejegyzés \> Igény-előrejelzési sorok** lehetőségre.
1. A műveletpanelen nyissa meg a **Megnyitás Microsoft Office-ban \> Igény-előrejelzési bejegyzések** lehetőséget.
1. Válassza ki a letöltés helyét, mentse, majd nyissa meg a letöltött fájlt az Excel programban.
1. Ha lát egy figyelmeztetést, válassza a **Szerkesztés engedélyezése** lehetőséget.
1. Az Excel programban a Microsoft Dynamics munkaablak használatával jelentkezzen be a Supply Chain Management alkalmazásba. Úgy kell bejelentkeznie, hogy engedélyezve van a **Bejelentkezve marad** beállítás, és meg kell bíznia az adatkapcsolati alkalmazásban.
1. Az Excel-táblázat most a vállalat aktuális igény-előrejelzési sorait jeleníti meg.  Szükség szerint hozzáadhatja, törölheti és szerkesztheti az igény-előrejelzés sorait.
1. Válassza a **Közzététel** lehetőséget a Microsoft Dynamics munkaablakban, ha vissza kell töltenie módosításait a Supply Chain Management eszközbe.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
