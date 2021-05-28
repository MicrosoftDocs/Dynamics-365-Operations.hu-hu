---
title: Kiadott termékre nem lehet sablont alkalmazni
description: Kiadott termékre nem lehet sablont alkalmazni.
author: t-benebo
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: EcoResProductDetailsExtended
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 1ad6efdced9bce924fbf5bc207c92fa2c3a6c79d
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026568"
---
# <a name="you-cant-apply-a-template-to-create-a-released-product"></a>Kiadott termék létrehozásához nem lehet sablont alkalmazni

Tudásbáziscikk száma: 4612097

## <a name="symptoms"></a>Tünetek

Amikor új kiadott terméket hoz létre az **Új kiadott termék** párbeszédpanelen, ki lehet választani egy sablont. A sablonnak az új kiadott termék számos mezőjéhez alapértelmezett beállításokat kell adnia. A sablon kiválasztása után azonban néhány vagy az összes mező nem lesz beállítva.

## <a name="cause"></a>Ok

A Microsoft Dynamics 365 Supply Chain Management számos lapja lehetőséget ad olyan sablon létrehozására, amely meghatározza az ilyen lapokon megjelenő rekordok kezdeti beállításait. Egy ilyen sablont úgy hozhat létre, hogy kiválasztja a **Rekordadatok** lehetőséget a Műveleti panel **Beállítások** lapján. A kiadott termékek azonban összetettebbek, mint a legtöbb más rekordtípus. Bár a **Kiadott termékek** lapon **Rekordadatokat** választhat sablon létrehozásához, és bár a sablont ki is választhatja a kiadott termékek létrehozásakor, a sablon nem fogja tartalmazni az új kiadott termék várt mezőértékeit. Így a kiadott termékekhez nem használhatja a "rekordinformációk" sablonokat. Ehelyett külön terméksablonokat kell létrehoznia.

## <a name="resolution"></a>Felbontás

Terméksablon létrehozásához használja a Munkaablak **Termék** lapján található **Sablon** menüt, nem pedig a **Beállítások** lap **Rekordinformációk** lapját.

1. Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.
1. A Műveleti panelen a **Termék** lapon, az **Új** csoportban válassza a **Sablon** lehetőséget, majd válassza a **Személyes sablon létrehozása** vagy a **Megosztott sablon létrehozása** lehetőséget igény szerint.
