---
title: A tranzakcióellenőrzési folyamatban használt szabályok letiltása
description: Ebben a cikkben részletes leírást találhat a tranzakciók ellenőrzési szabályainak letiltására használatos funkcióról a Microsoft Dynamics 365 Commerce szolgáltatásban.
author: analpert
ms.date: 12/11/2021
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
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 7d566aa3b829dad281528925a341382f9637fdba
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8884876"
---
# <a name="disable-rules-used-in-the-transaction-validation-process"></a>A tranzakcióellenőrzési folyamatban használt szabályok letiltása

[!include [banner](../includes/banner.md)]

A kiskereskedők csak rájuk jellemző, egyedi üzleti esetekkel és folyamatokkal rendelkezhetnek. Ezért nem minden kiskereskedőre érvényes az összes szabály, amely szerepel a kereskedelmi tranzakció ellenőrzési funkciójában. A különbségeknek figyelembe vétele érdekében a Microsoft Dynamics 365 Commerce szolgáltatásban rendelkezésre áll a funkció, amellyel a nem vonatkozó szabályok letilthatók.

A környezetében a tranzakcióellenőrzési folyamatban elérhető szabályok listájának megtekintéséhez és az egyes szabályok állapotának megtekintéséhez menjen a **Retail és Commerce \> Központ beállítása \> Paraméretek \> Commerce Paraméterek** menüpontba, és válassza a **Tranzakcióellenőrzés** lapot. Az összes engedélyezett szabály használva van a tranzakciók ellenőrzéséhez **Üzleti tranzakciók ellenőrzése** folyamat során, és ezeknek teljesülniük kell, hogy a tranzakciók fel legyenek véve, és fel legyenek adva egy tranzakciós kimutatásban.

Alapértelmezés szerint az összes szabály állapota **Engedélyezve**. Ez azt jelenti, hogy a rendszer az összes szabályt alkalmazza a tranzakciók ellenőrzésére, mielőtt kereskedelmi kimutatásokba lehívhatók lennének. Ha az egyik szabályt le szeretné tiltani, módosítsa állapotát **Letiltva** értékre. A letiltott szabályokat a program nem veszi figyelembe a tranzakciók ellenőrzésekor az **Üzleti tranzakciók ellenőrzése** folyamat során.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
