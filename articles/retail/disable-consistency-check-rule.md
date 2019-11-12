---
title: Kiskereskedelmi tranzakciók konzisztencia-ellenőrzési szabályainak letiltása
description: Ebben a témakörben részletes leírást találhat a kiskereskedelmi tranzakciók konzisztencia-ellenőrzési szabályainak letiltására használatos funkcióról a Microsoft Dynamics 365 Retail szolgáltatásban.
author: josaw1
manager: AnnBe
ms.date: 10/15/2019
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
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 4bf8df2fb9f8f5c33ceb13eb012fb6879f81ec66
ms.sourcegitcommit: bdbca89bd9b328c282ebfb681f75b8f1ed96e7a8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/14/2019
ms.locfileid: "2586297"
---
# <a name="disable-rules-in-the-retail-transaction-consistency-checker"></a>Kiskereskedelmi tranzakciók konzisztencia-ellenőrzési szabályainak letiltása 

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

A kiskereskedők csak rájuk jellemző, egyedi üzleti esetekkel és folyamatokkal rendelkezhetnek. Ezért nem minden kiskereskedőre érvényes az összes szabály, amely alapértelmezés szerint szerepel a kiskereskedelmi tranzakciós konzisztencia-ellenőrzési funkciójában. A különbségeknek figyelembe vétele érdekében a Microsoft Dynamics 365 Retail szolgáltatásban rendelkezésre áll a funkció, amellyel a nem érvényes szabályok letilthatók.

Ha meg szeretné tekinteni a kiskereskedelmi tranzakciós konzisztencia-ellenőrzése funkció az Ön környezetében érvényes szabályait, valamint az egyes szabályok állapotát, lépjen a **Kiskereskedelem \> Központ beállítása \> Paraméterek \> Kiskereskedelmi paraméterek** pontra, majd válassza a **Tranzakció-ellenőrzés** lapot.

Alapértelmezés szerint az összes szabály állapota **Engedélyezve**. Ez azt jelenti, hogy a rendszer az összes szabályt alkalmazza a kiskereskedelmi tranzakciók ellenőrzésére, mielőtt kiskereskedelmi kimutatásokba lehívják őket. Ha az egyik szabályt le szeretné tiltani, módosítsa állapotát **Letiltva** értékre. A letiltott szabályokat a program nem veszi figyelembe a kiskereskedelmi tranzakciók ellenőrzésekor a kimutatásszámítási folyamat során.

Ha a teljes ellenőrzési folyamatot szeretné elkerülni az engedélyezett szabályoktól függetlenül, lépjen a **Kiskereskedelem \> Központ beállítása \> Paraméterek \> Kiskereskedelmi paraméterek** pontra, majd a **Tranzakció-ellenőrzés** lapon állítsa a **Kiskereskedelmi tranzakciók konzisztencia-ellenőrzésének letiltása** beállítást **Igen** értékre. Ha ez a lehetőség **Nem** értékre van állítva, akkor a felhasználói felületen (UI) nem állítható vissza **Igen** értékre.
