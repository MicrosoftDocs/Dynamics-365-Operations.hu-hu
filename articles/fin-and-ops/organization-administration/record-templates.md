---
title: Rekordsablonok
description: Ez a cikk bevezetőként szolgál a rekordsablonok koncepciójába és bemutatja, hogyan alkalmazhatóak új, információ megosztására alkalmas rekordok létrehozására.
author: pvillads
manager: AnnBe
ms.date: 08/18/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 16101
ms.assetid: 61ada2d8-84c3-44bc-b4c5-516b1aeac3d1
ms.search.region: Global
ms.author: pvillads
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 426fd8fafec061b649cbb31109ffe8fabc24917d
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1545671"
---
# <a name="record-templates"></a>Rekordsablonok

[!include [banner](../includes/banner.md)]

Ez a cikk bevezetőként szolgál a rekordsablonok koncepciójába és bemutatja, hogyan alkalmazhatóak új, információ megosztására alkalmas rekordok létrehozására.

A rekordsablonok segítenek a rekordok gyorsabb létrehozásában a Microsoft Dynamics 365 for Finance and Operations rendszerben. Csak néhány rekordtípushoz hozhat létre rekordsablonokat a Microsoft Dynamics 365 for Finance and Operations rendszerben.

Például képzelje el, hogy bérleti információt ad meg egy San Franciscóban található autókölcsönző vállalkozáshoz. Mivel a legtöbb ügyfél valószínűleg San Franciscóból és környékéről származik majd, jó lenne automatikusan kitölteni az **Állam**, **Ország** és **Város** értékeket a bérleti képernyőn.

> [!NOTE]
> A Finance and Operations csak olyan területeihez használhat sablonokat, amelyekhez hozzáféréssel is rendelkezik. Azonban minden sabloncím látható, amikor új rekordot hoz létre, és más felhasználók számára is, ha az összes felhasználó számára rendelkezésre álló sablonokat hoz létre. Ezt mindenképpen figyelembe kell venni a sablonok elnevezésekor. Ha például bizalmasan kell kezelni, hogy a vállalat egyes alkalmazottai jutalékalapú fizetést kapnak, akkor kerülni kell az olyan elnevezéseket, amelyekben a jutalék szó szerepel.

Ha egy adott képernyőhöz egy vagy több olyan sablon áll rendelkezésre, melyekhez Ön hozzáfér, és egy új rekordot próbál létrehozni a képernyőn, akkor megjelenik az **Egy sablon kiválasztása...** oldal. Amikor kiválasztja a sablont a listából, a kiválasztott sablon alapján létrejön egy alapértelmezett adatokat tartalmazó új rekord. Ha nem szeretne sablonokat használni az új rekordok létrehozásához, akkor jelölje be a **Ne jelenjen meg többet ez a kérdés** jelölőnégyzetet az **Egy sablon kiválasztása...** képernyőn. A sablonválasztási párbeszédpanel újbóli megjelenítéséhez kattintson bármelyik rekordra a jobb gombbal, kattintson a **Rekord adatai** elemre, majd kattintson a **Sablonkiválasztás megjelenítése** lehetőségre.
