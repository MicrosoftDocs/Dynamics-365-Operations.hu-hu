---
title: Figyelmeztetési modul
description: Ez a témakör a figyelmeztetésmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 82138dd7f0934f732215f67a3726638eb87075d4
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785352"
---
# <a name="alert-module"></a>Figyelmeztetési modul

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Ez a témakör a figyelmeztetésmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A figyelmeztetésmodul a lapokon található belső tájékoztató üzenetek megjelenítésére szolgál. A figyelmeztetésmodulok szöveges üzenetet és egy hivatkozást támogatnak. Az e-kereskedelmi webhely összes lapján megjelenő, egész webhelyen elérhető promóciókat lehet a használatukkal megjeleníteni. 

A figyelmeztetésmodulokat a tartalomkezelő rendszer (CMS) adatai vezérlik, és bármilyen lapra elhelyezhetők.

## <a name="examples-of-alert-modules-in-e-commerce"></a>Példák az e-Commerce figyelmeztetésmoduljaira

A webhely fejlécében a figyelmeztetésmodulok a webhely egészére érvényes promóciók és üzenetek jelzésére használhatók. Íme néhány példa:

„Az éves akció 10 napon belül lejár”

„Nagy megtakarítás az iskolakezdő akcióval. Vásároljon most.”

## <a name="alert-module-properties"></a>Figyelmeztetésmodul tulajdonságai

| Tulajdonság neve  | Érték                              | Leírás |
|----------------|------------------------------------|-------------|
| Szöveg           | Szöveg                               | A figyelmeztetésmodulban megjelenő szöveges üzenet. |
| Szöveg igazítása | **Jobb**, **Bal** vagy **Közép** | Az érték, amely meghatározza a szöveg igazítását a figyelmeztetésmodulban. |
| Figyelmeztetés elutasítása  | **Igaz** vagy **Hamis**              | Ha az érték **Igaz**, akkor a vevő elvetheti a figyelmeztetést. |
| Hivatkozás           | URL-cím                                | Az opcionális hivatkozás URL-címe. |

## <a name="add-an-alert-module-to-a-page"></a>Figyelmeztetésmodul felvétele egy oldalra 

A figyelmeztetésmodulnak az oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.

1. Hozzon létre egy **figyelmeztetéssablon** nevű oldalsablont.
1. Az alapértelmezett lap **Fő** helyén adjon hozzá egy figyelmeztetésmodult.
1. Adja be a sablont és tegye közzé. 
1. A most létrehozott figyelmeztetéssablon használatával hozzon létre egy **figyelmeztetéslap** nevű lapot. 
1. Az új lap **Fő** helyén adjon hozzá egy figyelmeztetésmodult.
1. A figyelmeztetésmodul beállításaiban adja meg a figyelmeztetés szövegét. A további tulajdonságokat módosíthatja, ha a figyelmeztetésmodult tovább személyre szabására van szükség.
1. Mentse a lapot, és tekintse meg az előnézetét. A lap tetején egy olyan figyelmeztetés jelenik meg, amely az Ön által hozzáadott szöveget tartalmazza.
1. Adja be a lapot, és tegye közzé. 

## <a name="additional-resources"></a>További erőforrások

[Kezdő csomag áttekintése](starter-kit-overview.md)

[Forgótármodul](add-carousel.md)

[Tartalomgazdag blokkmodul](add-content-rich-block.md)

[Tartalomelhelyezési modul](add-content-placement-modules.md)

[Funkciómodul](add-feature-module.md)

[Főképmodul](add-hero-module.md)

[Videólejátszó modul](add-video-player.md)
