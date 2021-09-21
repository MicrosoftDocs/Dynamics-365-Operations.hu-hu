---
title: Rendeléskeresési modul
description: Ez a témakör ismerteti rendeléskeresési modult, és bemutatja, hogyan konfigurálhatjuk a Microsoft Dynamics 365 Commerce alkalmazásban.
author: stuharg
ms.date: 09/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2021-08-15
ms.dyn365.ops.version: Release 10.0.22
ms.openlocfilehash: fa61a20ffd9a31f800c48b71832be7547952119f
ms.sourcegitcommit: d420b96d37093c26f0e99c548f036eb49a15ec30
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/03/2021
ms.locfileid: "7472619"
---
# <a name="order-lookup-module"></a>Rendeléskeresési modul

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Ez a témakör ismerteti rendeléskeresési modult, és bemutatja, hogyan konfigurálhatjuk a Microsoft Dynamics 365 Commerce alkalmazásban.

A rendeléskeresési modul egy olyan képernyőt biztosít, ahol a vevők meg tudják keresni az e-kereskedelmi webhelyen leadott rendeléseket. [A rendeléskeresés engedélyezése a vendégpénztárnál](order-lookup-guest.md) funkció részeként használatos. A rendeléskeresési modul segítségével meg lehet keresni az e-kereskedelmi webhelyen, a kiskereskedelmi pénztárban (POS) vagy egy hívásközpontban elküldött rendeléseket. A képernyő lekérheti mind a vendégfelhasználók, mind a regisztrált felhasználók által elküldött rendeléseket.

Az alábbi ábra a rendeléskeresési modul által megjelenített képernyőt mutatja be. Amikor a vevők kitöltik az űrlapot, és a **Rendelés megkeresése** lehetőséget választják, a program átirányítja őket a rendelés adatai lapra.

![Űrlap a lap rendeléskeresési modulja számára.](./media/OrderLookup_module.PNG)

## <a name="order-lookup-module-properties"></a>Rendelés keresési modul tulajdonságai

| Tulajdonság neve     | Érték     | Leírás |
|-------------------|-----------|-------------|
| Fejléc           | Szöveg      | A képernyő tetején megjelenő címsor (például „Rendelés megkeresése”). |
| Rich Text         | Rich Text | A címsor alatt megjelenő magyarázó szöveg (nem kötelező). |
| Rendelési állapot típusa | Enum      | <p>A rendelés-visszaigazolási azonosítón kívül válassza ki, hogy milyen típusú információkat kérjen a képernyő a vevőtől. Jelenleg a következő értékek támogatottak:</p><ul><li><b>E-mail</b> – A képernyőn egy mező található, ahol a vevők megadhatjak a rendelés elküldésekor használt e-mail-címet.</li><li><b>Nincs</b> – A képernyő a rendelés visszaigazolási azonosítója mellett nem kér adatokat.</li></ul> |

## <a name="add-an-order-lookup-module-to-a-page"></a>Rendeléskeresés modul felvétele egy oldalra

A rendeléskeresés modul az e-kereskedelmi webhely bármelyik oldalának törzséhez hozzáadható. Ha a rendeléskeresés modul segítségével engedélyezni szeretné a vendégpénztároknál a rendeléskeresést, mindenképpen adja hozzá egy olyan oldalhoz, amely nem igényli a felhasználó bejelentkezését. Ha meg kívánja keresni egy lap **Bejelentkezés szükséges?** beállítását a Commerce webhelykészítő fanézetében, válassza az **Alapértelmezett lap (Kötelező)** lehetőséget, és nézze meg a jobb oldali panel alsó részét.

## <a name="additional-resources"></a>További erőforrások

[Rendelés keresésének engedélyezése vendégpénztárak részére](order-lookup-guest.md)

[Modultár áttekintése](starter-kit-overview.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
