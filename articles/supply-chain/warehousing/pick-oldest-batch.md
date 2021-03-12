---
title: A mobileszköz legrégebbi kötegének kitárolása
description: Ez a témakör leírja, hogyan állíthatja be és alkalmazhatja a mobileszköz legrégebbi kötegének kitárolási beállításait.
author: Mirzaab
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fdf6335bd333569e278ccd9cf3972c0ec57d4e6c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4989668"
---
# <a name="pick-oldest-batch-on-a-mobile-device"></a>A mobileszköz legrégebbi kötegének kitárolása

[!include [banner](../includes/banner.md)]

A **Legrégebbi köteg kitárolása** konfigurációjához a mobileszköz menüjén keresztül férhet hozzá, amely lehetővé teszi, hogy kötelezze vagy figyelmeztesse a raktári dolgozókat arra, hogy tárolják ki az aktuális helyük legrégebbi kötegét.  

## <a name="where-it-applies"></a>Alkalmazási kör
A Legrégebbi köteg kitárolásának konfigurációja a mobileszköz menüelemeiben történik, és a kitárolási köteg alatti elemere van hatással.

## <a name="how-to-set-up-the-configuration-for-pick-oldest-batch"></a>A Legrégebbi köteg kitárolása konfigurációjának beállítása 
Folyamatban lévő munkát használó beállítású cikkeknél a **Legrégebbi köteg kitárolása** lehetséges beállításai a **Nincs**, a **Figyelmeztetés** vagy a **Kényszerítés** a mobileszköz menüjében.

**Nincs**: A dolgozók nem kapnak üzeneteket, és bármelyik köteget kitárolhatják az aktuális helyükön.

**Figyelmeztetés** és **Kényszerítés**: Amikor a dolgozó kijelöl egy köteget, a kötegvezérlő fölött egy köteglista jelenik meg, amely a legrégebbi lejárati dátummal tartalmazó kötegeket tartalmazza. Az azonosítótáblával szabályozott a hely esetén az azonosítótábla-vezérlő fölött a legrégebbi köteget tartalmazó azonosítótáblák listája jelenik meg. 
-   **Figyelmeztetés**: Ha egy dolgozó olyan azonosítótáblát vagy köteget választ ki, amelyik nem szerepel a listán, a rendszer letiltja a vezérlőt, és egy figyelmeztetés fog megjelenni, hogy létezik egy korábbi kiválasztható köteg. Ha folytatni szeretné a munkát, a dolgozó újból kiválaszthatja ugyanazt az azonosítótáblát vagy köteget.  
-   **Kényszerítés**: A dolgozók továbbra is megkapják azt az üzenetet, hogy van egy korábbi kitárolandó köteg.
