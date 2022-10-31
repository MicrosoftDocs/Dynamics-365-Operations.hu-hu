---
title: Online rendeléses és aszinkron vevői rendeléses tranzakciók szerkesztése és auditálása
description: Ez a cikk azt ismerteti, hogy miként szerkesztheti és auditálhatja az online rendeléses és aszinkron vevői rendeléses tranzakciókat a Microsoft Dynamics 365 Commerce szolgáltatásban.
author: josaw1
ms.date: 10/21/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.industry: Retail
ms.openlocfilehash: dbeeff47446c1617da44f34ae56f333717f577a1
ms.sourcegitcommit: 18b7a02c497709e8d9c7b943d82f1fcc3dafa4cd
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/21/2022
ms.locfileid: "9712108"
---
# <a name="edit-and-audit-online-order-and-asynchronous-customer-order-transactions"></a>Online rendeléses és aszinkron vevői rendeléses tranzakciók szerkesztése és auditálása

[!include [banner](../includes/banner.md)]

Ez a cikk azt ismerteti, hogy miként szerkesztheti és auditálhatja az online rendeléses és aszinkron vevői rendeléses tranzakciókat a Microsoft Dynamics 365 Commerce szolgáltatásban.

## <a name="overview"></a>Áttekintés

A 10.0.5-ös és 10.0.6-os Commerce verziók között hozzáadták a készpénzzel fizetett, azonnal átvett tranzakciók (például értékesítés és visszaküldés) és a készpénzkezelési tranzakciók (például váltópénz betétele és fizetőeszköz kivétele) szerkesztésének támogatását. A Commerce 10.0.7-es verziója az online rendeléses tranzakciók és az aszinkron vevői rendeléses tranzakciók szerkesztését is támogatja.

## <a name="edit-and-audit-order-transactions"></a>Rendelési tranzakciók szerkesztése és auditálása

A rendelési tranzakciók szerkesztéséhez és auditálásához a Commerce headquarters felületén kövesse az alábbi lépéseket.

1. Telepítse a [Microsoft Dynamics Office Add-in](https://appsource.microsoft.com/product/office/WA104379629?tab=Overview) programot.
1. A **Commerce paraméterek** lap **Vevői rendelések** lapfülén, a **Rendelés** gyorslapon adjon meg egy várakoztatási kódot a **Rendelésszinkronizálási hibák várakoztatási kódja** pont alatt.
2. Szüneteltesse a szerkesztés és audit időzítésével ütköző rendelésszinkronizálási feladatokat.
3. Nyissa meg az **Üzlet pénzügyi adatai** munkaterületet. Az **Online rendelések szinkronizálási hibái** és a **Vevői rendelések szinkronizálási hibái** csempék előre szűrt nézetet biztosítanak a kiskereskedelmi tranzakciólapról. Mindegyik azokat a tranzakciórekordokat jeleníti meg, amelyek szinkronizálása sikertelen volt a megfelelő rendeléstípus esetében.
4. Nyissa meg az **Online rendelések szinkronizálási hibái** vagy a **Vevői rendelések szinkronizálási hibái** lapot. Jelöljön ki egy rekordot a szinkronizálási hiba részleteinek megtekintéséhez. A **Szinkronizálás állapota** gyorslap a következő hibaadatokat tartalmazza:

    - Függő rendelési állapot
    - Rendelési hiba részletei
    - Módosítás dátuma és időpontja
    - Újrapróbálkozások száma

1. Ha a hiba részletei azt jelzik, hogy a rekordot ki kell javítani, válassza az **Office-bővítmény**, majd a **Kijelölt tranzakció szerkesztése** lehetőséget. Megnyílik egy Excel-fájl, amely a kijelölt tranzakció részleteit mutatja.

    - Ha a szerkesztett tranzakció online rendelési tranzakció, az Excel-fájl a következő munkalapokat tartalmazza:

        - **Tranzakció** – Ezen a munkalapon szerepelnek a tranzakció fejlécadatai.
        - **Értékesítési tranzakció** – Ezen a munkalapon szerepelnek a tranzakció soradatai.
        - **Fizetési tranzakciók** – Ez a munkalap a tranzakció fizetési sorainak részleteit tartalmazza.
        - **Engedményes tranzakciók** – Ezen a munkalapon szerepelnek a tranzakció engedménnyel kapcsolatos részletei.
        - **Adótranzakciók** – Ezen a munkalapon szerepelnek a tranzakció adókkal kapcsolatos részletei.
        - **Költségtranzakciók** – Ezen a munkalapon szerepelnek a tranzakció költségekkel kapcsolatos adatai.

    - Ha a szerkesztett tranzakció aszinkron vevői rendeléses tranzakció, az Excel-fájl a következő munkalapokat tartalmazza:

        - **Sorok** – Ezen a munkalapon szerepelnek a tranzakció fejléc- és soradatai.
        - **Fizetések** – Ez a munkalap a tranzakció fizetési sorainak részleteit tartalmazza.
        - **Engedmények** – Ezen a munkalapon szerepelnek a tranzakció engedménnyel kapcsolatos részletei.
        - **Adók** – Ezen a munkalapon szerepelnek a tranzakció adókkal kapcsolatos részletei.
        - **Költségek** – Ezen a munkalapon szerepelnek a tranzakció költségekkel kapcsolatos adatai.

1. Az Excel-fájl **Függő rendelési állapot** mezőjébe írja be a **Szerkesztés** parancsot, majd tegye közzé a módosítást. Így megakadályozhatja, hogy a kötegelt módban futó **Rendelés szinkronizálása** feladat kihagyja ezt a rekordot a feldolgozás során.
1. Az Excel-fájlban módosítsa a megfelelő mezőket, majd töltse vissza az adatokat a Commerce központi felületére a Dynamics Excel-bővítmény közzétételi funkciója segítségével. Az adatok közzététel után a módosítások a rendszerben is megjelennek. A közzététel során a rendszer nem végez ellenőrzést a felhasználó által végrehajtott módosításokra.
    > [!NOTE]
    > Ha nem találja a szerkeszteni kívánt mezőt, kövesse az alábbi lépéseket a hiányzó mező munkalaphoz való hozzáadásához.
    >   1. Válassza ki a **Tervezés** lehetőséget az Adatcsatlakozóban.
    >   1. Válassza ki a ceruza ikont amellett a tábla mellett, amelyhez hozzá szeretne adni egy mezőt.
    >   1. Jelölje ki a mezőt az **Elérhető mezők** szakaszban, majd válassza a **Hozzáadás** lehetőséget.
    >   1. Adja hozzá a kívánt számú mezőket, majd válassza a **Frissítés** lehetőséget.
    >   1. Ha a frissítés befejeződött, lehet, hogy ki kell választani a **Frissítés** lehetőséget az értékek frissítéséhez.

3. A módosítások teljeskörű auditnaplóját megtekintheti, ha kiválasztja a **Kiskereskedelmi tranzakció** fejlécben (fejlécszintű adatok esetén) vagy az adott tranzakció oldalán a megfelelő szakaszban és rekordnál az **Auditnapló megtekintése** lehetőséget. Például az értékesítési sorokhoz kapcsolódó összes változás megjelenik az **Értékesítési tranzakciók** lapon, és a kifizetésekhez kapcsolódó összes változás megjelenik a **Fizetési tranzakciók** lapon. A módosításokra vonatkozóan a következő auditadatokat tartjuk meg:

    - Módosítás dátuma és időpontja
    - Mező
    - Régi érték
    - Új érték
    - Módosította

1. A módosítások végrehajtása és közzététele után válassza a **Rendelés szinkronizálása** lehetőséget a szinkronizálási folyamat azonnali elindításához. Másik lehetőségként megvárhatja, míg a kötegelt módban futó szinkronizálási folyamat feldolgozza a tranzakciót.

Alapértelmezés szerint a rendelések a sikeres szinkronizálása után a Commerce paraméterekben meghatározott várakoztatási kód alapján várakoztatási állapotba kerülnek. A rendelések várakoztatását el kell távolítani a rendelések teljesítés vagy egyéb műveletek céljából történő további feldolgozása előtt.

## <a name="additional-resources"></a>További erőforrások

[Készpénzzel fizetett, azonnal átvett és készpénzkezelési tranzakciók szerkesztése és auditálása](edit-cash-trans.md)

[Kiskereskedelmi tranzakciók pénzügyi dimenzióinak szerkesztése](edit-financial-dim.md)

[Excel-munkafüzet létrehozása a kiskereskedelmi tranzakciók szerkesztéséhez](create-excel-edit.md)

[Mezők hozzáadása Excel-munkafüzethez a kiskereskedelmi tranzakciók szerkesztéséhez](add-fields-excel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
