---
title: A cikkhez nem tartozhat anyagjegyzék vagy receptúra
description: Amikor rendelést próbál megerősíteni, hibaüzenetet kap a cikk ellenőrzése során. A hibaüzenetben az áll, hogy a cikkhez nem tartozhat anyagjegyzék vagy receptúra.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPO
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 6739b8b1e4d080055a2a0501427eac1c2e8a96c5
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294092"
---
# <a name="item-cant-have-a-bom-or-formula"></a>A cikkhez nem tartozhat anyagjegyzék vagy receptúra

Hibakód: PRO2614

## <a name="symptoms"></a>Tünetek

Amikor rendelést próbál megerősíteni, a köetkező hibaüzenetet kapja a cikk ellenőrzése során:

> A cikkhez nem tartozhat anyagjegyzék vagy receptúra

## <a name="resolution"></a>Megoldás

Az anyagjegyzékkel vagy receptúrával rendelkező cikkeknek *Tervezési cikk*, *Anyagjegyzék* vagy *Receptúra* típusúnak kell lenniük. A cikkek típusa a következőképpen módosítható.

1. Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.
1. Nyissa mega releváns terméket.
1. A **Mérnöki feladatok** gyorslap **Termelés típusa** mezőjében adja meg a *Tervezési cikk*, az *Anyagjegyzék* vagy a *Receptúra* elemet.
