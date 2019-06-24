---
title: Kötegelt nyomkövetésű cikkek továbbfejlesztett kezelése
description: Ez a témakör azt mutatja be, hogy milyen fejlesztéseket vezettek be a kötegek kezelésével kapcsolatban a kötegelt nyomkövetésű cikkek esetén a kiskereskedelmi kimutatások feladási folyamata során.
author: josaw1
manager: AnnBe
ms.date: 05/28/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-05-28
ms.dyn365.ops.version: 10
ms.openlocfilehash: 4456fc3d5bc4547fa8211642b11ca6df455fa187
ms.sourcegitcommit: aec1dcd44274e9b8d0770836598fde5533b7b569
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2019
ms.locfileid: "1617389"
---
# <a name="improved-handling-of-batch-tracked-items"></a>Kötegelt nyomkövetésű cikkek továbbfejlesztett kezelése

A Microsoft Dynamics 365 for Retail pénztár (POS) alkalmazásban a kötegelt nyomkövetésű cikkek kötegszámai nem rögzíthetők az értékesítés pillanatában. Bizonyos konfigurációk esetén azonban amikor az értékesítéseket a központban vevői rendeléseken vagy kimutatásfeladáson keresztül adják fel, a Microsoft Dynamics-rendszer arra számít, hogy a kötegelt nyomkövetésű cikkekhez léteznek érvényes kötegszámok, és ezeket használják majd a számlázási folyamat során.

Ha a termékekhez léteznek érvényes kötegszámok, a rendszer ezeket használja a vevői rendelések számlázási folyamata és a kimutatásfeladásból származó értékesítési rendelés számlázási folyamata során. Ellenkező esetben a vevői rendelés számlázási folyamata nem képes a feladásra, és a pénztárfelhasználó számára hibaüzenet jelenik meg. A kimutatásfeladás pedig hibás állapotba kerül. Ez a hibás állapot akkor fordulhat elő, ha negatív készlet van bekapcsolva a termékekhez.

A Microsoft Dynamics for Retail 10.0.4-es és újabb verzióiban végzett fejlesztések segítségével garantálható, hogy amikor a kötegelt nyomkövetésű cikkekhez negatív készlet van bekapcsolva, a vevői rendelés és az értékesítési rendelés kimutatásfeladáson keresztül történő számlázása nincs zárolva az adott cikkekhez, ha a készlet 0 (nulla) vagy ha nincs elérhető kötegszám. Az új funkció alapértelmezett kötegazonosítót használ az értékesítési sorokhoz, ha nem találhatók kötegszámok.

A vevői rendelésekhez használt alapértelmezett kötegazonosító meghatározásához állítsa be az **Alapértelmezett kötegazonosító** mezőt a **Kiskereskedelmi paraméterek** lap **Vevői rendelések** fülének **Rendelés** gyorslapján.

Az értékesítési rendelések kimutatásfeladáson keresztül történő számlázásához használt alapértelmezett kötegazonosító meghatározásához állítsa be az **Alapértelmezett kötegazonosító** mezőt a **Kiskereskedelmi paraméterek** lap **Feladás** fülének **Készletfrissítés** gyorslapján.

> [!NOTE]
> Ez a funkció csak akkor áll rendelkezésre, ha a megadott tárolási raktárhoz és cikkekhez be van kapcsolva a speciális raktárkezelés. Egy későbbi kiadásban a funkció már olyan esetekben is támogatott lesz, ahol nem használják a speciális raktárkezelést.
