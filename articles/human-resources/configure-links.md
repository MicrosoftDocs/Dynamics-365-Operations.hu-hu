---
title: Hivatkozások létrehozása az Emberi erőforrások csoportból másik környezetbe
description: Ez a cikk bemutatja, hogyan lehet hivatkozást létrehozni a Microsoft Dynamics 365 Human Resources és egy másik Dynamics 365-környezet között.
author: twheeloc
ms.date: 03/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-29-11
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0c9efae1061e96c0c42d5ca6a100bb36889ce56b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8859666"
---
# <a name="create-links-from-human-resources-to-another-finance-environment"></a>Hivatkozások létrehozása az Emberi erőforrások csoportból egy másik pénzügyi környezetbe

Egy ügyfélnek két Dynamics 365 környezete lehet, amelyekben dolgoznak. Például lehet, hogy az ügyfél környezete a Dynamics 365 Human Resources pénzügyi infrastruktúra területén van, és egy másik Dynamics 365 Pénzügyi környezethez kell kapcsolódnia. 

Ez a funkció lehetővé teszi az Emberi erőforrások lapról egy másik pénzügyi környezet meghatározott lapjára mutató hivatkozásokat. A hivatkozások konfigurálásakor megadhatja, hogy a hivatkozás hol legyen elérhető az Emberi erőforrásokban, valamint a céloldalt, amely a másik környezetben fog megnyílni.

> [!Note] 
> A funkció használatához be kell kapcsolnia **az Emberi erőforrások felhasználói élmény fokozásait** **a** Funkciókezelésben.

## <a name="configure-target-systems"></a>Célrendszerek konfigurálása

Az Emberi erőforrások csoportban a rendszergazdák meghatározhatják az Emberi erőforrások lapokon elérhető **hivatkozásokat**. A konfiguráció egyes részei a pénzügy környezetek, amelyekre a hivatkozás céljaként el szeretne navigálni. 

A célrendszer konfigurálása:
1. A Hivatkozások **konfigurálása lapon** válassza a Célrendszer **konfigurálása lehetőséget**.  
2. Adja meg a célrendszer nevét, és adja meg a Pénzügyi környezet URL-címét. A célrendszerek konfigurálása után megadhatja a hivatkozásokat.

## <a name="configure-links"></a>Hivatkozások konfigurálása

Minden létrehozott hivatkozáshoz a következő információk lesznek meghatározva:
 - **Hivatkozás**: A hivatkozás neve. Csak azonosításra használatos.
 - **A hivatkozás engedélyezése**: Állítsa Igen **beállításra**, ha meg szeretné jelenni az Emberi erőforrások felhasználóira mutató hivatkozást.
 - **Megjelenített név**: Adja meg azt a nevet, amely a másodlagos környezetre mutató hivatkozásként jelenik meg. 
 - **Felületkapcsolat a képernyőn**: Válassza ki, hogy melyik oldalon szeretné megjeleníteni a hivatkozást. A hivatkozások csak az alkalmazotti **önkiszolgáló** **munkaterületen** és a Munkakör, Beosztás **,** **·** **Dolgozó és Leegyszerűsített dolgozó oldalon ásnak lapokon edznek.**
 - **Csoport**: A hivatkozásokat csoportok segítségével rendszerezheti. Válasszon ki egy meglévő csoportot, vagy hozzon létre egy újat a Csoport oszlop **segítségével**.
 - **Célrendszer**: Válassza ki a célrendszer konfigurálása **beállítással létrehozott célrendszert**. Ez lesz a hivatkozással való navigáláskor használt másodlagos környezet.
 - **A felhasználó aktuális vállalatának használata**: Válassza az Igen **lehetőséget**, ha a felhasználó aktuális vállalatát használja a Pénzügy felé való navigáláshoz. Válassza a **Nem** lehetőséget a használni kívánt vállalat kiválasztásához.
 - **Cél** menüelem: Adja meg a pénzügyi környezetből azt a menüelemet, amelyiket a hivatkozásnak használnia kell navigáláskor. Elérhetők menüelemek, amelyekhez közvetlenül el lehet navigálni. 

   A menüelem megkereséhez a következő elemek szükségesek:
   1. Menjen a Pénzügyi környezetbe, és nyissa meg azt a lapot, amely a navigáció célja. 
   2. Másolja ki a menüelemet az URL-ből. Például, ha azt szeretné, hogy a hivatkozásra kattintva az alkalmazottak listájához jusson a Finance and Operations alkalmazásban azt az értéket adja meg, amely a „&mi” után jelenik meg az URL-ben. 
   3. A menüelemet az alkalmazottak listáját tartalmazó oldal eléréshez ebben a példában: HcmWorkerListPage_Employees.

 - **Adatforrásra mutató** hivatkozás: Válassza ki azt az adatforrást, amelyre a hivatkozás hivatkozik. A leggyakoribb adatforrások, mint a **Dolgozó** és a **Beosztás** érhetők el.

### <a name="access-to-links"></a>Hivatkozások elérése

A rendszergazdák az újonnan létrehozott hivatkozásokat látni fogják a meghatározott lapokon még akkor is, ha az **Adott hivatkozás engedélyezése** beállítás értéke **Nem**. Ez a hivatkozások ellenőrzésére használható, mielőtt azok meg lennének jelenítve az alkalmazottaknak. Az összes többi szerepkör csak a konfigurált **hivatkozásokat** fogja látni, miután a hivatkozás engedélyezése beállítás Igen beállításra **van állítva**. Azon munkavállalók, akik hozzáférnek az oldalakhoz, amelyeken a hivatkozások megjelennek elérhetik a hivatkozásokat.

A felhasználóknak a másodlagos környezetben ahhoz is biztonsági jogokkal kell rendelkezikuk, hogy hozzáférjenek az adott környezet lapjaihoz. Ha nem rendelkeznek ilyennel, egy biztonsági párbeszédpanel jelenik meg a hivatkozás használata esetén.

