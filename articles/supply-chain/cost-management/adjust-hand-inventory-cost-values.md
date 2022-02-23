---
title: Az aktuális készlet költségértékeinek korrekciója
description: Az Aktuális készlet korrekciója lapon beállíthatja az aktuális készlet mennyiségeinek költségértékét a készletzárási folyamat futtatása után.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventAdjInventOnHand
audience: Application User
ms.reviewer: kamaybac
ms.custom: 53231
ms.assetid: bc1fde9f-5ad9-4339-8ae8-e2839b792eb2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6a702a083d60bdb289712027fbaee5c0a72e60cb
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4963838"
---
# <a name="adjust-on-hand-inventory-cost-values"></a>Az aktuális készlet költségértékeinek korrekciója

[!include [banner](../includes/banner.md)]

Az Aktuális készlet korrekciója lapon beállíthatja az aktuális készlet mennyiségeinek költségértékét a készletzárási folyamat futtatása után.

Az **Aktuális készlet korrekciója** oldalon módosíthatja az aktuális készlet mennyiségeinek költségértékét a készletzárási folyamat futtatása után. **Megjegyzés**: az **Aktuális készlet korrekciója** oldalon a **Zárás és helyesbítés lapon** válasszon ki egy befejezett készletzárási folyamatrekordot, majd kattintson a **Korrekció** &gt; **Aktuális** elemre. **Példa:** Februárban a következő tranzakciók voltak:

-   Február 1.: pénzügyi bevételezés készletre, 2 mennyiséggel, 10,00 USD áron
-   Február 5.: pénzügyi bevételezés készletre, 1 mennyiséggel, 13,00 USD áron
-   Február 19.: pénzügyi kiadás készletről, 1 mennyiséggel, 11, 00 USD mozgóátlagon alapuló önköltségi áron

Ez a cikk az elsőként be, elsőként ki FIFO készletmodellhez van beállítva, február 28-án történik a készletzárás. A 11,00 USD értékű pénzügyi kiadási tranzakció a február 1-jei pénzügyi bevételezéssel szemben lesz kiegyenlítve, 1,00 USD lesz a korrekció. A következő készletbevételezések ekkor nyitott készletmennyiségeket tartalmaznak:

-   Febuár 1: mennyiség: 1, a költség 10,00 USD.
-   Febuár 5: mennyiség: 1, a költség 13,00 USD.

Ahhoz, hogy ennek a két cikknek az árát 15,00 USD értékre lehessen beállítani, az aktuális készlet módosítására használható funkcióval korrigálni kell a nyitott aktuális készletmennyiségeket a legutolsó készletzárási időszaknak megfelelően. **Megjegyzés:** Az aktuális készletet korrigáló tranzakció feladási dátuma a legutóbbi készletzárás dátuma lesz. Ez a dátum nem módosítható.
