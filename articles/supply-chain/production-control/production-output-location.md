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
ms.search.scope: Core, Operations
ms.custom: 221264
ms.assetid: dde49743-1541-4353-a030-63ca3069cd7d
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: e4002bf7dddb196edf306268ecc16e1bfa5d6d1e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429699"
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