---
title: Üzletkiválasztó modul
description: Ez a témakör az üzletválasztó modullal foglalkozik, és bemutatja, hogy hogyan lehet azt hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 03/19/2020
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
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: ''
ms.openlocfilehash: 8efc2345ded52bfaee2d400815795906f326f4fd
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/21/2020
ms.locfileid: "3157340"
---
# <a name="store-selector-module"></a>Üzletkiválasztó modul

[!include [banner](includes/banner.md)]

Ez a témakör az üzletválasztó modullal foglalkozik, és bemutatja, hogy hogyan lehet azt hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

Egy üzletválasztó modul van használatban az „online vásárlás, átvétel az áruházban” "(BOPIS) vevői forgatókönyvhöz. Megjeleníti azoknak az üzleteknek a listáját, amelyekben a termék rendelkezésre áll felvételre, valamint az egyes üzletekhez tartozó nyitva tartást és termékkészletet.

Az üzletválasztó modulnak szükséges a termék kontextusa és egy keresési hely az üzletek megkereséséhez. A keresési hely hiányában a vevő böngészőjének alapértelmezett helye lesz használva, ha a vevő ehhez hozzájárul. A modulnak van egy beviteli doboza, amely lehetővé teszi, hogy a vevő megadjon egy helyet (irányítószámot vagy várost, illetve államot) a közelben található üzletek megtalálására.

Az áruházválasztó modul integrálva van a Bing Maps földrajzi kódolási alkalmazásprogramozási felületével (API), hogy a vevő által megadott helyszínt egy földrajzi szélességgé és hosszúsággá alakíthassa. A Bing Maps API-kulcsot kötelező megadni, és hozzá kell adni a Commerce megosztott paraméterei oldalhoz a Dynamics 365 Commerce szolgáltatásban.

Az üzletválasztó modul hozzáadható a termék részletei oldalon (PDP) található Vásárlásmező modulhoz, amelyben megtekinthetők azok az üzletek, amelyekben a termék rendelkezésre áll felvételre. A kosár modulhoz is hozzáadhatók. A kosár modulhoz való felvételkor az üzletválasztó modul minden egyes kosár sortételhez megjeleníti az átvételi beállításokat. Ezenkívül az egyéni kódolással a modul hozzáadható más oldalakhoz vagy modulokhoz a bővítményeken és a testreszabásokon keresztül.

A BOPIS szcenárió működéséhez a termékeket a „vevői átvétel” szállítási móddal kell konfigurálni. Máskülönben a modul nem fog megjelenni a megfelelő lapokon. A szállítási mód konfigurálásával kapcsolatos további tudnivalókat lásd: [Szállításimódok beállítása](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).

A következő kép a PDP-ben használt üzletválasztó modul egy példáját jeleníti meg.

![Példa egy üzletválasztó modulra](./media/BOPIS.PNG)

## <a name="store-selector-module-usage-in-e-commerce"></a>Az Üzletválasztó modul használata az e-kereskedelemben

- Az üzletválasztó modul hozzáadható a termék részletei oldalhoz (PDP) azon közeli üzletek megkereséséhez, amelyekben a termék rendelkezésre áll felvételre.
- Az üzletválasztó modul hozzáadható a kosároldalhoz azon közeli üzletek megkereséséhez, amelyekben a kosárban található termék rendelkezésre áll felvételre.

## <a name="store-selector-module-properties"></a>Az üzletkiválasztó modul tulajdonságai

| Tulajdonság neve             | Érték                 | Leírás |
|---------------------------|-----------------------|-------------|
| Keresési sugár | Szám | Az üzletek keresési sugarát határozza meg (mérföldben). Ha nincs megadva érték, akkor a program az alapértelmezett 50 mérföldes keresési sugarat használja.|
|Szolgáltatási feltételek | URL-cím    |  A Bing Térképek szolgáltatáshoz a szolgáltatási feltételek hivatkozása szükséges. |

## <a name="add-a-store-selector-module-to-a-page"></a>Üzletválasztó modul hozzáadása a laphoz

Egy üzletválasztó modulnak szüksége van egy termék környezetére, így csak a vásárlásmező és a kosár modulokban használható. Az üzletválasztó modulok nem működnek ezeken a modulokon kívül.

- Az üzletválasztó modulnak egy vásárlásmező modulhoz való hozzáadásával kapcsolatos tudnivalókat lásd: [Vásárlásmező](add-buy-box.md) modul. 
- Az üzletválasztó modulnak egy kosármodulhoz való hozzáadásával kapcsolatos tudnivalókat lásd: [Kosár modul](add-cart-module.md).

## <a name="additional-resources"></a>További erőforrások

[Kezdő csomag áttekintése](starter-kit-overview.md)

[Vásárlásmező-modul](add-buy-box.md)

[Kosármodul](add-cart-module.md)

[A PDP rövid bemutatása](quick-tour-pdp.md)

[A kosár és a pénztár rövid bemutatása](quick-tour-cart-checkout.md)

[Szállítási módok beállítása](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)
