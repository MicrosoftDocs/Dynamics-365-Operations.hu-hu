---
title: Kiskereskedelmi tranzakciók konzisztencia-ellenőrzési szabályainak letiltása
description: Ebben a témakörben részletes leírást találhat a tranzakciók konzisztencia-ellenőrzési szabályainak letiltására használatos funkcióról a Microsoft Dynamics 365 Commerce szolgáltatásban.
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
ms.openlocfilehash: 37209f1c1de19335f5f9fa6636ab55dd8b2fccc1
ms.sourcegitcommit: 02640a0f63daa9e509146641824ed623c4d69c7f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2020
ms.locfileid: "3265526"
---
# <a name="disable-rules-in-the-retail-transaction-consistency-checker"></a>Kiskereskedelmi tranzakciók konzisztencia-ellenőrzési szabályainak letiltása 

[!include [banner](../includes/banner.md)]

A kiskereskedők csak rájuk jellemző, egyedi üzleti esetekkel és folyamatokkal rendelkezhetnek. Ezért nem minden kiskereskedőre érvényes az összes szabály, amely alapértelmezés szerint szerepel a kereskedelmi tranzakciós konzisztencia-ellenőrzési funkciójában. A különbségeknek figyelembe vétele érdekében a Microsoft Dynamics 365 Commerce szolgáltatásban rendelkezésre áll a funkció, amellyel a nem érvényes szabályok letilthatók.

Ha meg szeretné tekinteni a tranzakciók konzisztencia-ellenőrzése funkció az Ön környezetében érvényes szabályait, valamint az egyes szabályok állapotát, lépjen a **Retail és Commerce \> Központ beállítása \> Paraméterek \> Commerce-paraméterek** pontra, majd válassza a **Tranzakció-ellenőrzés** lapot.

Alapértelmezés szerint az összes szabály állapota **Engedélyezve**. Ez azt jelenti, hogy a rendszer az összes szabályt alkalmazza a tranzakciók ellenőrzésére, mielőtt kereskedelmi kimutatásokba lehívják őket. Ha az egyik szabályt le szeretné tiltani, módosítsa állapotát **Letiltva** értékre. A letiltott szabályokat a program nem veszi figyelembe a tranzakciók ellenőrzésekor a kimutatásszámítási folyamat során.

Ha a teljes ellenőrzési folyamatot szeretné elkerülni az engedélyezett szabályoktól függetlenül, lépjen a **Retail és Commerce \> Központ beállítása \> Paraméterek \> Commerce-paraméterek** pontra, majd a **Tranzakció-ellenőrzés** lapon állítsa a **Commerce-tranzakciók konzisztencia-ellenőrzésének letiltása** beállítást **Igen** értékre. Ha ez a lehetőség **Nem** értékre van állítva, akkor a felhasználói felületen (UI) nem állítható vissza **Igen** értékre.
