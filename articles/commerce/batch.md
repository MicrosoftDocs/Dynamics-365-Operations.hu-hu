---
title: Kötegelt nyomkövetésű cikkek továbbfejlesztett kezelése
description: Ez a témakör azokat a fejlesztéseket mutatja be, amelyeket a kötegeknek a kötegelt nyomon követésű cikkek esetén, a kimutatások feladási folyamata során történő kezelésével kapcsolatban vezettünk be.
author: josaw1
ms.date: 11/04/2019
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-05-28
ms.dyn365.ops.version: 10
ms.openlocfilehash: 2453ed711d47e062c82d3888ff471b770b5bb2ef
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799709"
---
# <a name="improved-handling-of-batch-tracked-items"></a>Kötegelt nyomkövetésű cikkek továbbfejlesztett kezelése


[!include [banner](includes/banner.md)]


A pénztár (POS) alkalmazásban a kötegelt nyomkövetésű cikkek kötegszámai nem rögzíthetők az értékesítés pillanatában. Bizonyos konfigurációk esetén azonban amikor az értékesítéseket a központban vevői rendeléseken vagy kimutatásfeladáson keresztül adják fel, a Microsoft Dynamics-rendszer arra számít, hogy a kötegelt nyomkövetésű cikkekhez léteznek érvényes kötegszámok, és ezeket használják majd a számlázási folyamat során.

Ha a termékekhez léteznek érvényes kötegszámok, a rendszer ezeket használja a vevői rendelések számlázási folyamata és a kimutatásfeladásból származó értékesítési rendelés számlázási folyamata során. Ellenkező esetben a vevői rendelés számlázási folyamata nem képes a feladásra, és a pénztárfelhasználó számára hibaüzenet jelenik meg. A kimutatásfeladás pedig hibás állapotba kerül. Ez a hibás állapot akkor fordulhat elő, ha negatív készlet van bekapcsolva a termékekhez.

A Retail 10.0.4-es és újabb verzióiban végzett fejlesztésekkel biztosítható, hogy amikor negatív készlet van bekapcsolva a kötegelt nyomon követésű cikkekhez, a vevői rendelés és az értékesítési rendelés kimutatásfeladáson keresztül történő számlázása ne legyen zárolva az adott cikkekhez, ha a készlet 0 (nulla) vagy ha nincs elérhető kötegszám. Az új funkció alapértelmezett kötegazonosítót használ az értékesítési sorokhoz, ha nem találhatók kötegszámok.

A vevői rendelésekhez használt alapértelmezett kötegazonosító meghatározásához állítsa be az **Alapértelmezett kötegazonosító** mezőt a **Kereskedelmi paraméterek** lap **Vevői rendelések** fülének **Rendelés** gyorslapján.

Az értékesítési rendelések kimutatásfeladáson keresztül történő számlázásához használt alapértelmezett kötegazonosító meghatározásához állítsa be az **Alapértelmezett kötegazonosító** mezőt a **Kereskedelmi paraméterek** lap **Feladás** fülének **Készletfrissítés** gyorslapján.

> [!NOTE]
> Ez a funkció csak akkor áll rendelkezésre, ha a megadott tárolási raktárhoz és cikkekhez be van kapcsolva a speciális raktárkezelés. Egy későbbi kiadásban a funkció már olyan esetekben is támogatott lesz, ahol nem használják a speciális raktárkezelést.

> [!NOTE]
> A kötegelt nyomkövetésű cikkek továbbfejlesztett kezelése a nem speciális raktárkezelési esetek kimutatásfeladása során a Retail 10.0.5 verziójában bevezetett funkció.


[!INCLUDE[footer-include](../includes/footer-banner.md)]