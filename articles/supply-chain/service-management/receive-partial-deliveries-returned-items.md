---
title: Visszaadott cikkek részleges szállításának bevételezése
description: A részleges szállítások visszárurendelés-sorok, nem pedig visszárurendelés-szállítmányok formájában vannak meghatározva.
author: sorenva
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6c0e27e3a5cb6be36a1d69190ce1b01ecada48a6
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/03/2022
ms.locfileid: "8677114"
---
# <a name="receive-partial-deliveries-of-returned-items"></a>Visszaadott cikkek részleges szállításának bevételezése    

[!include [banner](../includes/banner.md)]


A részleges szállítások visszárurendelés-sorok, nem pedig visszárurendelés-szállítmányok formájában vannak meghatározva.

Ez azt jelenti, hogy ha a visszárurendelés egyik sorában szereplő teljes mennyiséget visszaküldik, de Ön a többi sor mennyiségéből semmit nem kap meg, akkor a szállítás nem részleges szállítás. Ha viszont egy visszárurendelés-sorban az adott cikkből 10 kötelezően visszaküldendő egység szerepel, és ebből csak négyet kap meg, akkor ez egy részleges szállítás.

Ha egy visszáruszállítmány nem tartalmazza a visszárurendelés-sor teljes mennyiségét, akkor félreteheti a szállítmányt, és megvárhatja, amíg a visszajuttatott mennyiség maradék része is megérkezik, vagy regisztrálhatja és feladhatja a részmennyiséget.

## <a name="register-and-post-a-partial-quantity"></a>A részleges mennyiség regisztrálása és feladása

1.  Miután kiválaszt egy érkeztetendő visszárurendelést a **Beérkezés áttekintése - raktár: %1, Terület: %2, Napló neve: %3** képernyőn, kattintson az **Érkeztetés indítása** elemre egy cikkérkezési napló létrehozásához, majd kattintson a **Naplók** \> **Érkezések megjelenítése** a bevételekből elemre a **Helynapló** képernyő megnyitásához.

2.  Válassza ki azt a naplósort, amellyel dolgozni szeretne, és a **Sorok** gombra kattintva nyissa meg a **Naplósorok, helyek** képernyőt.

3.  Válassza ki azon cikkszámok sorait, amelyekből a mennyiségnek csak egy része érkezett meg, majd kattintson a **Funkciók** \> **Megosztás** parancsra a **Megosztás** képernyő megnyitásához.

4.  A **Megosztott mennyiség** mezőben írja be a beérkezett cikkek mennyiségét és teljes számát, majd kattintson az **OK** gombra.

5.  A **Naplósorok, helyek** képernyőn a beérkezett cikkmennyiség sorát, és kattintson a **Feladás** gombra. A további mennyiség sorát akkor adhatja fel, miután a cikkek megérkeznek.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]