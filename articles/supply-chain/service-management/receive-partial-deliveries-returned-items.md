---
title: Visszaadott cikkek részleges szállításának bevételezése
description: A részleges szállítások visszárurendelés-sorok, nem pedig visszárurendelés-szállítmányok formájában vannak meghatározva.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: da4020afc8832ed9bef88f5387533ee6cd09645b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5234801"
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