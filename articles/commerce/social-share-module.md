---
title: Közösségi megosztás modul
description: Ez a témakör a közösségi megosztás modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
ms.date: 09/15/2020
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
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: c34410a8c817de9fed350bf2cd2dd918a37c230f
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795357"
---
# <a name="social-share-module"></a>Közösségi megosztási modul

[!include [banner](includes/banner.md)]

Ez a témakör a közösségi megosztás modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.

A Közösségi megosztás modulok lehetővé teszik a felhasználók számára, hogy megosszanak e-kereskedelmi oldal URL-címeket közösségi felületeken, mint a Facebook, a Twitter, a Pinterest és a LinkedIn. A webhely URL-címeit e-mailen keresztül is meg lehet osztani. A Közösségi megosztási modulokat gyakran használják a termékek részletező oldalain (PDP-k), hogy segítsenek a felhasználóknak megosztani a termék adatait.

Minden közösségi megosztási modul egy tároló a közösségi megosztás elemmodulokhoz. Minden közösségi megosztási modul beállítható úgy, hogy egy adott közösségi webhelyre mutasson. Alaphelyzetben a Facebook, Twitter, Pinterest, LinkedIn és az e-mail támogatott. Amikor a webhely felhasználója kiválasztja egy közösségi felület szimbólumát, egy HTML iframe-t indít el a megfelelő közösségi oldalra. Az iFrame-en belül a felhasználó bejelentkezhet, és közzéteheti az éppen megtekintett tartalmat.

Minden közösségimédia-platform nyomon követhet a sütiket, így ez a modul megköveteli, hogy a webhely felhasználó elfogadja a cookie-beleegyezés értesítő üzenetet. Ha nem fogadja el a cookie-hozzájárulást, akkor a modul el lesz rejtve a lapon. További információ:- [Cookie-k megfelelősége](cookie-compliance.md).

A következő ábra bemutatja a termék részletei oldalon használt közösségi megosztási modul egy példáját.

![Példa egy közösségi megosztási modulra](./media/ecommerce-socialshare.png)

## <a name="social-share-module-properties"></a>Közösségi megosztási modul tulajdonságai

| Tulajdonság neve             | Érték                 | Leírás |
|---------------------------|-----------------------|-------------|
| Felirat                  | Szöveg | Ez a tulajdonság adja meg a modul feliratát. |
| Tájolás | **Vízszintes** vagy **Függőleges**  | Ez a tulajdonság határozza meg a közösségimédia-elemek tájolását. |

## <a name="social-share-item-module-properties"></a>Közösségi megosztási elem modultulajdonságai
| Tulajdonság neve             | Érték                 | Leírás |
|---------------------------|-----------------------|-------------|
| Közösségi média              | **Facebook**, **Twitter**, **Pinterest**, **LinkedIn**, **E-mail** | Egy legördülő menü a közösségimédia-platformok listájával. |
| Ikon |Kép    | Ez lesz a megfelelő közösségi médiához megjelenített kép. Gyakorlati tanácsként a közösségi média-felület SDK-ját tekintse meg az egyes platformokhoz javasolt képekért. |

## <a name="add-a-social-share-module-to-a-buy-box-module"></a>Közösségimédia-modul hozzáadása egy vásárlásmező-modulhoz

Közösségimédia-modul hozzáadásához egy vásárlásmező-modulhoz kövesse az alábbi lépéseket.

1. A Fabrikam webhelyén válassza ki az **Oldalak** lehetőséget, majd válassza ki a **DefaultPDP** a termékrészletek oldal megnyitásához. 
1. A **Vásárlásmező (kötelező)** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki az **Közösségi megosztás** modult, majd kattintson az **OK** gombra.
1. Az **Közösségi megosztás** helyben válassza a három pont (**…**) gombot, majd válassza a **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki a **SocialShare** modult, majd kattintson az **OK** gombra.
1. A **SocialShare** modul tulajdonságok ablaktáblájában , a **Tájolás** területen válassza a **Vízszintes** elemet. Szükség szerint adjon meg egy feliratot.
1. Az **SocialShare** helyben válassza a három pont (**…**) gombot, majd válassza a **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki a **SocialShareItem** modult, majd kattintson az **OK** gombra.
1. A **SocialShareItem** modulban, a **Közösségi média** alatt válassza a **Facebook** lehetőséget.
1. A **SocialShareItem** modulban az **Ikon** alatt válassza a **+ Kép hozzáadása** lehetőséget.
1. A **Médiaválasztó** párbeszédpanelen válassza ki a Facebook logó képét, majd kattintson az **OK** gombra. Ha nincs Facebook logókép, válassza az **Új médiaelem feltöltése** lehetőséget, hogy feltöltsön egyet.
1. Szükség esetén konfiguráljon és adjon hozzá további **SocialShareItem** modulokat.
1. Válassza a **Mentés** lehetőséget, majd az oldal előnézetének megtekintéséhez az **Előnézet** elemet. A lap a közösségi megosztás modult jeleníti meg.
1. Válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

## <a name="additional-resources"></a>További erőforrások

[Modulkönyvtár – áttekintés](starter-kit-overview.md)

[Vásárlásmező-modul](add-buy-box.md)

[Cookie-k megfelelősége](cookie-compliance.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]