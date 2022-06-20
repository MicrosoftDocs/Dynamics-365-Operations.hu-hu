---
title: Webhelyválasztó modul
description: Ez a témakör leírja a webhelyválasztó modult, és bemutatja, hogyan lehet a webhely lapjaihoz hozzáadni Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: ef7753658f878fdf76c6a6beb82ce54e9c12e212
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8884603"
---
# <a name="site-picker-module"></a>Webhelyválasztó modul

[!include [banner](includes/banner.md)]

Ez a témakör leírja a webhelyválasztó modult, és bemutatja, hogyan lehet a webhely lapjaihoz hozzáadni Microsoft Dynamics 365 Commerce.

Ha egy vállalatnak különböző webhelyei vannak a különböző piacokon, régiókban és nyelvi területeken, a felhasználóknak egyszerű lehetőséget kell kapniuk a helyek közötti váltásra, hogy kiválaszthassák a preferált vásárlási oldalt. Ennek az esetnek az alkalmazással a webhelyválasztó modul lehetővé teszi a felhasználók számára a több telephelyen keresztüli böngészést. A helyválasztót [akkor](geo-detection-redirection.md) is ajánlott használni, ha az e-commerce webhelyhez földrajzi észlelés és átirányítás is van megvalósítva, így a vevők felülbírálhatják az [ország/ régió választó](country-region-picker-module.md) modul segítségével javasolt hely által előnyben részesítést. 

A webhelyválasztó modulban konfigurálni kell azokat a helyeket (piacokat, régiókat vagy helyeket), amelyek között a felhasználók böngészni tudnak. A következő ábra egy olyan helyválasztó modulra mutat be, amely megjelenik egy olyan helyválasztó modulra, amely megjelenik a webhely oldalának fejlécében.

![Példa a webhelyválasztó modulra a webhelyoldal fejlécében.](./media/ecommerce-sitepicker.PNG)

## <a name="site-picker-module-properties"></a>Webhelyválasztó modul tulajdonságai

| Tulajdonság neve | Érték                 | Leírás |
|---------------|-----------------------|-------------|
| Címsor       | Szöveg                  | A modul címe. |
| Webhelybeállítások  | Név, kép, URL      | Ez a tulajdonság megad egy nevet, egy hivatkozást a webhely kezdőlapjára, valamint egy opcionális képet a modulban található minden oldal számára. A kép lehet egy zászó, vagy a piac, régió vagy nyelvi terület egyéb ábrázolása. |

## <a name="add-a-site-picker-module-to-a-page"></a>Webhelyválasztó modul hozzáadása egy laphoz

A webhelyválasztó modul hozzáadható **a fejlécmodul Webhelyválasztó-réséhez**[...](author-header-module.md). A helyválasztó modul hozzáadása után megadhatja a modul fejlécét és a hely beállításait. A fejlécmodul általában egy fejlécrészletben található, amely egy hely e-commerce lapjai között megosztható. 

A webhelyválasztó modul fejlécmodulhoz való hozzáadásához kövesse ezeket a lépéseket.

1. Válassza ki **a** fejlécrészlet fejlécmodulának Helyválasztó rését, és **·** **válassza ki a Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** adjon hozzá egy **Webhelyválasztó** modult, majd válassza az **OK gombra.**
1. A Webhelyválasztó **tulajdonságai** ablakban válassza a Webhely beállításainak **hozzáadása listát**. Megjelenik egy szerkeszthető **helybeállítások listája**.
1. Helybeállítások **listájának kiválasztása**. **Megjelenik a Webhely beállításai lista** párbeszédpanel.
1. Adja **meg a Hely neve** mezőben a helynév szövegét, amely a helyválasztó legördülő listájában jelenik meg.
1. A Webhely **átirányítási URL-címében** válassza a Hivatkozás **hozzáadása lehetőséget**. **Megjelenik a Hivatkozás hozzáadása** feláras ablak.
1. A Hivatkozás hozzáadása feláras ablakban válassza **az** Egyéni lap, majd a Tovább **lehetőséget**.**·**
1. Válassza ki a webhely URL-címének listából azt az URL-címet, amely a csatorna webhelyhez ad létrehozásakor létre van hozva (`www.adventure-works.com/fr-ca` például), majd válassza **az Alkalmaz lehetőséget**.
1. Válassza ki az **OK** lehetőséget.
1. Válassza a **Mentés** parancsot, majd válassza a **Szerkesztés befejezése** elemet.
1. A lap **közzétételéhez** válassza a Közzététel lehetőséget.

A következő példában a **helyválasztó** modul hozzá lett adva egy **HeaderContainer nevű fejlécrészletben szereplő fejlécmodul Webhelyválasztó-réséhez**.

![Példa a helyválasztó modulra fejlécrészletben.](./media/ecommerce-sitepicker-2.png)

## <a name="additional-resources"></a>További erőforrások

[Modultár áttekintése](starter-kit-overview.md)

[Fejlécmodul](author-header-module.md)

[Útkövetési modul](add-breadcrumb.md)

[Navigációs menü modul](nav-menu-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
