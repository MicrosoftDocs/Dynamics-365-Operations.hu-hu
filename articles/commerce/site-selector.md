---
title: Oldalválasztó modul
description: Ez a témakör az oldalválasztó modullal foglalkozik, és bemutatja, hogy hogyan lehet azt hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 10/20/2020
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
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: b4e5f715efcac7f883df99508d282db904be0d80
ms.sourcegitcommit: 9c05d48f6e03532aa711e1d89d0b2981e9d37200
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/03/2020
ms.locfileid: "4665223"
---
# <a name="site-selector-module"></a>Oldalválasztó modul

[!include [banner](includes/banner.md)]

Ez a témakör az oldalválasztó modullal foglalkozik, és bemutatja, hogy hogyan lehet azt hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

Ha egy vállalatnak különböző webhelyei vannak a különböző piacokon, régiókban és nyelvi területeken, a felhasználóknak egyszerű lehetőséget kell kapniuk a helyek közötti váltásra, hogy kiválaszthassák a preferált vásárlási oldalt. Ennek biztosítása érdekében az oldalválasztó modul lehetővé teszi a felhasználók számára a különböző webhelyek böngészését.

Az oldalválasztó modult be kell állítani azoknak a webhelyeknek (piacoknak, régióknak vagy nyelvi területeknek) a listájára, amelyeket a webhely felhasználói megtekinthetnek.

> [!NOTE]
> Az oldalválasztó modul a Dynamics 365 Commerce 10.0.14-es verziójában érhető el.

Az alábbi ábra a webhely fejlécében található oldalválasztó modult mutatja be.

![Példa oldalválasztó modulra a webhely fejlécében](./media/ecommerce-sitepicker.PNG)

## <a name="site-selector-module-properties"></a>Az oldalválasztó modul tulajdonságai

| Tulajdonság neve | Érték                 | Leírás |
|---------------|-----------------------|-------------|
| Fejléc       | Szöveg                  | A modul címe. |
| Webhelybeállítások  | Név, kép, URL      | Ez a tulajdonság megad egy nevet, egy hivatkozást a webhely kezdőlapjára, valamint egy opcionális képet a modulban található minden oldal számára. A kép lehet egy zászó, vagy a piac, régió vagy nyelvi terület egyéb ábrázolása. |

## <a name="add-a-site-selector-module-to-a-page"></a>Oldalválasztó modul hozzáadása a laphoz

Az oldalválasztó modul az oldalválasztó helyen adható hozzá a [Fejlécmodulhoz](author-header-module.md). A hozzáadása után megadhatja a modul fejlécét és az oldal beállításait.

## <a name="additional-resources"></a>További erőforrások

[Modultár áttekintése](starter-kit-overview.md)

[Fejlécmodul](author-header-module.md)

[Útkövetési modul](add-breadcrumb.md)

[Navigációs menü modul](nav-menu-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]