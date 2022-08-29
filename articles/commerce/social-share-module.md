---
title: Közösségi megosztási modul
description: Ez a témakör a közösségi megosztási modulokat ismerteti, és bemutatja, hogyan lehet hozzáadni azokat a webhelyoldalakhoz Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.14
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.openlocfilehash: 88bc5469e3072b625836cc942efbd2206f6dd6ba
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9284684"
---
# <a name="social-share-module"></a>Közösségi megosztási modul

[!include [banner](includes/banner.md)]

Ez a témakör a közösségi megosztási modulokat ismerteti, és bemutatja, hogyan lehet hozzáadni azokat a webhelyoldalakhoz Microsoft Dynamics 365 Commerce.

A Közösségi megosztás modulok lehetővé teszik a felhasználók számára, hogy megosszanak e-kereskedelmi oldal URL-címeket közösségi felületeken, mint a Facebook, a Twitter, a Pinterest és a LinkedIn. A webhely URL-címeit e-mailen keresztül is meg lehet osztani. A Közösségi megosztási modulokat gyakran használják a termékek részletező oldalain (PDP-k), hogy segítsenek a felhasználóknak megosztani a termék adatait.

Minden közösségi megosztási modul egy tároló a közösségi megosztás elemmodulokhoz. Minden közösségi megosztási modul beállítható úgy, hogy egy adott közösségi webhelyre mutasson. Alaphelyzetben a Facebook, Twitter, Pinterest, LinkedIn és az e-mail támogatott. Amikor a webhely felhasználója kiválasztja egy közösségi felület szimbólumát, egy HTML iframe-t indít el a megfelelő közösségi oldalra. Az iFrame-en belül a felhasználó bejelentkezhet, és közzéteheti az éppen megtekintett tartalmat.

Minden közösségimédia-platform nyomon követhet a sütiket, így ez a modul megköveteli, hogy a webhely felhasználó elfogadja a cookie-beleegyezés értesítő üzenetet. Ha nem fogadja el a cookie-hozzájárulást, akkor a modul el lesz rejtve a lapon. További információ:- [Cookie-k megfelelősége](cookie-compliance.md).

A következő ábra bemutatja a termék részletei oldalon használt közösségi megosztási modul egy példáját.

![Példa egy közösségi megosztási modulra.](./media/ecommerce-socialshare.png)

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
1. A buyboxban **(kötelező)** válassza ki a három pontból (**...**), **majd válassza a Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **a Social Share modult**, majd kattintson az **OK gombra**.
1. A Social **Share-pontnál** válassza ki a három pontból (**...**), majd válassza a Modul **hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza a **SocialShare** modult, majd kattintson az **OK gombra**.
1. A **SocialShare** modul tulajdonságok ablaktáblájában , a **Tájolás** területen válassza a **Vízszintes** elemet. Szükség szerint adjon meg egy feliratot.
1. A SocialShare **slotban válassza ki a három pontból (**...**), majd válassza a Modul** hozzáadása lehetőséget **.**
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **a SocialShareItem** modult, majd kattintson az **OK gombra**.
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
