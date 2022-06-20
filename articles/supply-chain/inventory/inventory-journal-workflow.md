---
title: Készletnapló-jóváhagyási munkafolyamatok
description: Ez a témakör azt ismerteti, hogyan lehet beállítani és használni a készletnapló-jóváhagyási munkafolyamatokat a tényleges készlettranzakciók különböző típusaihoz. A készletnapló-munkafolyamatok segítségével biztosítható, hogy csak a jóváhagyott készletnaplókat tegyék közzé a tranzakciókhoz.
author: yufeihuang
ms.date: 07/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalTableWorkflowDropDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2020-07-21
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: ebb12562a9f06f2efc3b5a373d7ad0f98bc3505e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873985"
---
# <a name="inventory-journal-approval-workflows"></a>Készletnapló-jóváhagyási munkafolyamatok

[!include [banner](../includes/banner.md)]

Ez a témakör leírja, hogyan lehet beállítani és használni a készletnapló-jóváhagyási munkafolyamatokat a különböző típusú tényleges készlettranzakciókra, például a cikkekre és a bevételezésre, a készletmozgásokra, az anyagjegyzékre és a tényleges készlet egyeztetésére. A készletnapló-munkafolyamatok segítségével biztosítható, hogy csak a jóváhagyott készletnaplókat tegyék közzé a tranzakciókhoz.

> [!NOTE]
> A készletnapló-jóváhagyási munkafolyamatok csak a Készletkezelési modul használatával rögzített tranzakciókra vonatkoznak. Nem működnek a Raktárkezelési modulból indított készletnaplókkal.

## <a name="turn-on-the-inventory-journal-approval-workflows-feature"></a>Készletnaplók jóváhagyási munkafolyamatai funkció aktiválása

Az Ellátásilánc-kezelés 10.0.21-es verziója szerint ez a funkció alapértelmezés szerint be van kapcsolva. A rendszergazdák a Szolgáltatáskezelés [lapon ellenőrizhetik](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) a funkció állapotát, és szükség esetén engedélyezhetik vagy letilthatják azt. Itt a funkció a következőként szerepel:

- **Modul:** *Készlet- és raktárkezelés*
- **Funkció neve:** *Készletnapló jóváhagyási munkafolyamata*

## <a name="create-your-inventory-journal-approval-workflows"></a>Hozza létre a saját készletnapló-jóváhagyási munkafolyamatait

Ennek a funkciónak a beállításához létre kell hoznia egy munkafolyamatot minden olyan készletnapló-típushoz, amelyet vezérelni szeretne. Mivel a különböző készletnapló-típusokhoz különböző jóváhagyási hierarchiák és munkafolyamat-lépések tartozhatnak, mindegyik készletnapló-típushoz külön konfigurálhatja az egyes munkafolyamatokat.

A munkafolyamatok támogatják a verzióvezérlést, illetve mindegyikhez tartozik egy munkafolyamat-azonosító és egy aktív verzió. Kiválaszthatja, hogy a létrehozáskor vagy az inaktívként hagyáskor minden új munkafolyamat-verzió azonnal aktiválható legyen. Ha ugyanannak a naplótípusnak különböző munkafolyamatokra van szüksége, akkor több munkafolyamatot is létre kell hoznia az adott naplótípushoz. Majd ezeket olyan eltérő naplónevekhez kell hozzárendelnie, amelyek ugyanazt a típust használják.

A saját készletnapló-jóváhagyási munkafolyamatai létrehozásához:

1. Menjen a **Készletkezelés \> Beállítás\> Készletkezelési munkafolyamatok** lehetőségre.
1. A Művelet panelen válassza az **Új** lehetőséget.
1. Válassza ki azt a készletnapló-típust, amelyhez be szeretné állítani a munkafolyamatot:
    - l **Készlet címkeszámlálási naplója**
    - **Készlet tulajdonosváltozási naplója**
    - **Készletmozgási napló**
    - **Készletátviteli napló**
    - **Készletszámlálási napló**
    - **Készlet anyagjegyzék-napló**
    - **Készlethelyesbítési napló**

    ![A Munkafolyamat létrehozása párbeszédpanel.](media/journal-workflow-create-workflow.png "A Munkafolyamat létrehozása párbeszédpanel")

1. A munkafolyamat-szerkesztő alkalmazás elindul a gépén. (Előfordulhat, hogy a művelet jóváhagyását kérik.) Használja a munkafolyamat igény szerinti tervezéséhez. A munkafolyamat-szerkesztő használatáról a következő témakörben talál további tájékoztatást: [Munkafolyamat rendszer – áttekintés](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md).
1. A munkafolyamat-szerkesztő alkalmazás mentését és bezárását követően ki kell választania, hogy aktiválja-e ezt a munkafolyamat-verziót, vagy inaktívan szeretné tartani.

> [!NOTE]
> A munkafolyamatok verzió-ellenőrzést biztosítanak, ami azt jelenti, hogy a létrehozott verziók listáját megtekintheti, és kiválaszthatja, hogy melyik legyen aktív. Ha meg szeretné tekinteni a rendelkezésre álló verziók listáját, és meg szeretné adni, hogy melyik legyen aktív, akkor válasszon ki egy munkafolyamatot a **Készletkezelési munkafolyamatok** listából. A Művelet ablakban nyissa meg a **Munkafolyamat** lapot, és válassza a **Verziók** elemet. Minden munkafolyamat-azonosítónál egyszerre csak egy verzió lehet aktív.

## <a name="assign-approval-workflows-to-inventory-journal-names"></a>Jóváhagyási munkafolyamatok hozzárendelése a készletnapló-nevekhez

A következő lépés a készletnapló-munkafolyamat minden készletnapló-névhez való hozzárendeléséhez. Minden készletnapló-típushoz több készletnapló-nevet is beállíthat.

Készletnapló-munkafolyamat hozzárendelése a készletnapló nevéhez:

1. Ugorjon a **Készletkezelés \> Beállítás \> Naplónevek \> Készlet** pontra.
1. A Beállítások oldal megnyitásához válassza ki a napló nevét a lista oszlopból .
1. Az **Általános** gyorslapon állítsa a **Jóváhagyási munkafolyamat** lehetőséget **Igen** értékre. Kattintson az **Igen** gombra, ha a rendszer a művelet jóváhagyását kéri.

    ![Munkafolyamat hozzárendelése egy napló nevéhez.](media/journal-workflow-journal-name.png "Munkafolyamat hozzárendelése egy napló nevéhez")

1. Nyissa meg a **Munkafolyamat** legördülő listát és jelölje ki a megfelelő munkafolyamatot. Ez a lista minden olyan aktív munkafolyamatot megjelenít, amelyet a munkafolyamat-szerkesztő alkalmazással hozott létre.

## <a name="create-an-inventory-journal-and-send-it-for-approval"></a>Készletnapló létrehozása és elküldése jóváhagyásra

Miután társította a készletnapló nevét a megfelelő készletnapló-jóváhagyási munkafolyamattal, létrehozhat olyan új készletnaplókat, amelyek ezt a nevet használják. Majd ezeket a naplókat elküldheti jóváhagyásra a munkafolyamat használatával. Addig nem fogja tudni feladni a készletnaplót, amíg nincs jóváhagyva a munkafolyamatban konfigurált jóváhagyók által.

1. A navigációs ablakban bontsa ki a **Készletkezelés \> Naplóbejegyzések \> Elemek** lehetőségben, majd válassza ki a készletnapló típusát.
1. Válassza ki az **Új** lehetőséget a kiválasztott típusú új napló létrehozásához.
1. Megjelenik a **Készletnapló létrehozása** párbeszédpanel. Szükség szerint töltse ki az űrlapot, majd kattintson az **OK** gombra a napló mentéséhez.
1. Szükség szerint töltse ki a naplót.
1. Amikor egy jóváhagyási munkafolyamattal társított készletnaplót hoz létre vagy nyit meg, akkor a **Munkafolyamat** gomb aktívvá válik a Művelet ablakban. Amikor készen áll, hogy elküldje a naplót jóváhagyásra, válassza ki a **Munkafolyamat** gombot a legördülő párbeszédpanel megnyitásához, majd válassza a **Küldés** lehetőséget. A jóváhagyási kérelem ezután a megfelelő jóváhagyóhoz fog menni, aki figyelmeztetést kap a munkafolyamathoz beállított értesítési módszerrel.

    ![Napló küldése jóváhagyásra.](media/journal-workflow-inventory-journal.png "Napló küldése jóváhagyásra")

Egy jóváhagyási kérelem visszahívásához nyissa meg a megfelelő naplót, válassza ki a **Munkafolyamat**, majd a **Visszahívás** lehetőséget. Ezzel alaphelyzetbe állítja a munkafolyamatot.

Amikor a naplót jóváhagyták, feladhatja. A napló feladásához válassza a **Feladás** lehetőséget a Művelet ablakban. Ha **Feladás** gomb nem aktív, akkor a napló még nincs jóváhagyva.

## <a name="respond-to-an-inventory-journal-approval-request"></a>A készletnapló-jóváhagyási kérelem megválaszolása

Ha Ön jóváhagyó, akkor minden alkalommal üzenetet kell kapnia, amikor a jóváhagyásra van szükség (az adott munkafolyamatban konfiguráltaknak megfelelően). Ezután a következő módon hagyhatja jóvá vagy utasíthatja el a naplójóváhagyási kérelmet:

1. A navigációs ablakban bontsa ki a **Készletkezelés \> Naplóbejegyzések \> Elemek** lehetőségben, majd válassza ki a készletnapló típusát.
1. Nyissa meg az adott naplót, és tekintse át.
1. Válassza ki a **Munkafolyamat** gombot a Művelet ablakban a legördülő párbeszédpanel megnyitásához. Válasszon a következők közül:
    - **Jóváhagyás** – A kérés jóváhagyásához.
    - **Elutasítás** – A kérelem elutasításához.
    - **További \> kérelem-változtatás** – Üzenet küldése a kérelmezőnek, hogy változtasson meg egy bizonyos dolgot, majd küldje újra a kérelmet.
    - **További \> delegálás** – Jóváhagyás delegálása egy másik felhasználónak.
    - **További \> visszahívás** – A jóváhagyási kérelem visszahívása (a munkafolyamat alaphelyzetbe állítása).
    - **További \> Munkafolyamat-előzmények** – A jóváhagyási munkafolyamat eddigi előzményeinek megtekintése.

## <a name="review-the-approval-history"></a>A jóváhagyási előzmények áttekintése

Más típusú munkafolyamatokhoz ugyanúgy használhatja a **Munkafolyamat-előzmények** oldalt, amelyen megtekintheti a naplók jóváhagyási munkafolyamat-előzményeit.

A napló munkafolyamat-előzményeinek áttekintése:

1. A navigációs ablakban bontsa ki a **Készletkezelés \> Naplóbejegyzések \> Elemek** lehetőségben, majd válassza ki a készletnapló típusát.
1. Az adott napló megnyitása.
1. Válassza ki a **Munkafolyamat** gombot a Művelet ablakban a legördülő párbeszédpanel megnyitásához. Válassza a **Munkafolyamat-előzmények** lehetőséget. További információ: [Munkafolyamat-előzmények megtekintése](../../fin-ops-core/fin-ops/organization-administration/tasks/view-workflow-history.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]