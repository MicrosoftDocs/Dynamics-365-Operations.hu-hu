---
title: Készletállapotok
description: A cikk leírja hogyan alkalmazza a készletállapotokat a készlet nyomon követésének és kategorizálásának érdekében.
author: MarkusFogelberg
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, WHSInventStatus, WHSWarehouseStatusChange
audience: Application User
ms.reviewer: kamaybac
ms.custom: 21331
ms.assetid: b35f495f-de4f-48a0-9d09-4d06781d7650
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e3c8b467f29037bbb869189e3607e11f40aad2c2
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829860"
---
# <a name="inventory-statuses"></a>Készletállapotok

[!include [banner](../includes/banner.md)]

A cikk leírja hogyan alkalmazza a készletállapotokat a készlet nyomon követésének és kategorizálásának érdekében.

## <a name="set-up-and-use-inventory-statuses"></a>Készletállapotok beállítása és használata

A készletállapotok a készlet csoportosítására használhatók. Ezután a elindíthatja a szükséges műveleteket, például a feltöltést vagy betárolási munkát.

Íme néhány példa készletállapotok használatára:

- Készletállapotok létrehozása aktuális készlethez, bejövő és kimenő tranzakciókhoz.
- Adjon meg egy alapértelmezett készletállapot a raktár tranzakciókhoz.
- Cikkek készletállapotának módosítása érkezés előtt, érkezés során, vagy a cikkek készletmozgással történő betárolása során.
- Használhat készletállapotot a visszárucikkek árképzéséhez, illetve a cikkfedezet megtervezéséhez az alaptervezés folyamatában.

A készletállapot a tárolásidimenzió-csoport dimenziói közé tartozik. Készletállapotok kategóriája lehet elérhető vagy nem elérhető, és használhatja a **Készletzárolás** paramétert a nem elérhető állapotú cikkek blokkolására. A zárolt állapotú cikkek tényleges készletnek tekinthetők, és nem használhatók termelési rendelésben, értékesítési rendelésben, átmozgatási rendelésben vagy kimenő tranzakcióban.

Bejövő munkához elérhető vagy nem elérhető készletállapotú cikkeket is használhat. Például létrehozhat egy elérhető állapotot, amely neve *Kész*, nem elérhető állapotot, amely neve *Sérült*, és zárolt állapotot, amely neve *Zárolva*. Bevételezett, vagy visszaküldött cikkek beszerzési rendelésének létrehozásakor, ha a cikkek megsérültek vagy eltörtek, a készlet állapotát módosíthatja *Sérült* értékre a beszerzési rendelésen. A cikkek bevételezése után, az állapot értéke automatikusan *Zárolva*. Ha mobileszköz használatával olvas be a sérült cikkeket, a Supply Chain Management használhat helyutasításokat és munkasablonokat, hogy mutassa a megfelelő helyet és helytartományokat, ahova be lehet tárolni azokat a cikkeket. Visszaküldött cikkekhez *Foglalás* kiadástpus jön létre a **Készlettranzakciók** oldalon.

Megadhatja, hogy mely készletállapotok zároló állapotok, a **Készletzárolás** jelölőnégyzetek használatával, a **Készletállapotok** oldalon. Készletállapotok nem használhatók zároló állapotokként értékesítési rendelések, átmozgatási rendelések vagy projektintegráció esetén.

Kimenő munka esetén különböző, nem zároló készletállapotokkal lehet szabályozni, hogy melyik készletre kell foglalni. Ha *Zároló* állapotú cikkekkel futtat alaptervezést, a rendszer hiányzónak fogja tekinteni őket, és automatikusan feltölti a készletet. Ezenkívül a kimenő munkához kapcsolódó minőségi rendeléseknél a minőségi rendelés részeként nem frissítheti a **Készletállapot** elemet.

> [!NOTE]
> Nem módosíthatja a készlet állapotát olyan helyeken, ahol nyitott munka található. Ha például beszerzési bevételezést végzett egy cikknél, de nem végezte el a betárolási lépést, akkor nyitott munka létezne a betárolási helyhez, és hiba jelenne meg, ha a készlet állapotát megpróbálná módosítani az adott helyen. A kapcsolódó munka befejezése vagy megszakítása lehetővé teszi az állapot változtatását.
>
> A nyitott raktári munkához kapcsolódó aktuális készlet állapotát általában csak a Raktárkezelés mobilalkalmazást használó dolgozók változtathatják meg, például a mozgatási folyamat végrehajtása közben.

Készletállapotok létrehozása után beállíthatja, hogy ez legyen az alapértelmezett készletállapot egy adott telephelyre, cikkre vagy raktárra vonatkozóan. Értékesítéshez, átadáshoz és beszerzési rendeléshez is létrehozhat alapértelmezett állapotot. Az értékesítési rendelések és a kimenő átmozgatási rendelések esetén a **Készletzárolás** alapértelmezett állapota nem lehet *Igen*. A raktár, cikk, beszerzési rendelés, átmozgatási rendelés vagy értékesítési rendelés alapértelmezett beállításaiból örökölt készletállapotot a mobileszköz, beszerzési rendelés, értékesítési rendelés, vagy átmozgatási rendelés sor segítségével lehet módosítani.

Rendelkezésre álló készlet állapotú cikkek fedezeti tervének elkészítéséhez jelölje be a **Fedezeti terv dimenziónként** lehetőséget tárolási dimenziónak, a **Tárolási dimenziócsoportok** oldalon. A **Cikkfedezet** varázsló megnyitásakor, az elérhető állapotú cikkek jelenjenek meg az **Állapot** oldalon. A cikkekre vonatkozó fedezeti beállítások létrehozásához válassza ki a készletállapot azonosítóját a rendelkezésre álló készletállapotok közül. A fedezeti beállítások alapján számíthatja ki a cikkszükségletet és jelezheti előre az elérhető cikkekre vonatkozó kínálatot és kereslete az alaptervezés során. Zárolt készletállapottal nem lehet cikkfedezeti beállítás létrehozni. A cikkfedezeti paraméterek létrehozásához vagy módosításához használhatja az **Cikk fedezete** képernyőt is.

## <a name="change-inventory-statuses"></a>Készletállapotok módosítása

A készletállapotokat módosíthatja az **Aktuális készlet hely szerint** oldal vagy a *Készletállapot módosítása* időszakos feladat használatával.

- Ha a *Készletállapot módosítása* időszakos feladatot használja, kiválaszthatja, hogy mely rekordokat kívánja felvenni, és beállíthatja a kívánt időközönként kötegben futtatni kívánt feladatot.
- A készlet állapotának ad hoc folyamatként történő módosításához nyissa meg **Aktuális készlet hely szerint** oldalt, válassza ki a megfelelő rekordokat, majd válassza a **Készlet állapotváltozása** gombot.

> [!NOTE]
> A *Nyomonkövetési dimenziók által ellenőrzött cikkek készletállapotának módosítása* funkció lehetővé teszi a nyomonkövetési dimenziók által ellenőrzött cikkek készletállapotának módosítását, beleértve a csak a kiválasztott rekordok frissítését is. A [szolgáltatáskezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) segítségével szükség szerint engedélyezheti a szolgáltatást. Ha a funkció engedélyezve van, a következőket teheti:
>
> - Az **Aktuális készlet hely szerint** oldalon a megjelenített dimenziók alapján csoportosíthatja a sorokat a **Megjelenítési dimenziók** gombbal, és módosíthatja a kijelölt sorok állapotát.
> - Az **Aktuális készlet hely szerint** oldalon több rekordot is kijelölhet, majd a **Készletállapot módosítása** gombbal egyszerre módosíthatja az összeset.
> - A **Készletállapot módosítása** időszakos feladattal szűrhet a nyomon követési dimenziókkal.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
