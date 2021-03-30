---
title: Termelések kimeneti helye
description: Ez a témakör leírja a hierarchiát, amely azonosítja a termelés kimeneti helyét.
author: johanhoffmann
manager: tfehr
ms.date: 04/04/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 221264
ms.assetid: dde49743-1541-4353-a030-63ca3069cd7d
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 8fa4f7d844c178ee603778fa2f1def6bfc33db97
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5209443"
---
# <a name="production-output-location"></a>Termelések kimeneti helye

[!include [banner](../includes/banner.md)]

Ez a témakör leírja a hierarchiát, amely azonosítja a termelés kimeneti helyét.

A termelés kimeneti helye az a hely, ahol a készterméket először tárolják az előállítását követően. Általában ez a hely közel van a termelési folyamathoz, amely előállítja a készterméket. A termelés kimeneti helyét köztes raktárként használja a rendszer az anyag számára, mielőtt az a szállítási területre, raktárba, illetve termelési bemeneti helyre kerülne egy folytatólagos termelési folyamathoz stb. 

Alapértelmezett termelési kimeneti hely van beállítva olyankor, amikor a készrermékeket jelentik egy termelési rendelésben vagy kötegrendelésben. Az alábbi hierarchia a kimeneti hely azonosítására szolgál:

1. A termelési rendelés vagy a kötegrendelés fejlécében megadott kimeneti helyet használja.
2. Ha ott nem található hely, használja azt a kimeneti helyet, amelyet annál az erőforrásnál határozott meg, amelyet az utolsó olyan művelet vett igénybe, amelyiket a termelési útvonalban határoztak meg.
3. Ha ott nem található hely, használja azt a kimeneti helyet, amelyet annál az erőforráscsoportnál határozott meg, amelyet az utolsó olyan művelet erőforrása vett igénybe, amelyiket a termelési útvonalban határoztak meg.
4. Ha ott nem található hely, használja azt a kimeneti helyet, amelyet annál a raktárnál adtak meg, amely a termelési rendelésnél lett meghatározva.

Alapértelmezett termelési kimeneti hely csak olyan termékeknél van beállítva, amelyeket speciális raktárkezelési folyamatok segítségével állítottak be. Ha ilyen típusú cikkek készként vannak jelentve, a **Késztermékek betárolása** vagy a **Társtermék és melléktermék betárolása** raktározási feladata jön létre. Az ilyen típusú munka a termelés kimeneti helyét használja kitárolási helyként. A betárolási helyet a helyutasítások határozzák meg.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]