---
title: Okkódok készletszámláláshoz
description: Ez a témakör ismerteti az okkódok beállítását számlálási feladatokhoz.
author: perlynne
ms.date: 08/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventCountingReasonCodePolicy, InventCountingReasonCode
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 95f7ceb39d2afef1871f395ed562632865022b39
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/13/2021
ms.locfileid: "7345266"
---
# <a name="reason-codes-for-inventory-counting"></a>Okkódok készletszámláláshoz

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Az okkódok segítségével elemezheti a számlálási folyamat eredményeit és a folyamat során felmerülő esetleges eltéréseket. Megadhatja a számlálás okait, például hogy eltört a raklap vagy a készletmintákon alapuló készletkiigazítás történt. Ezzel egyidejűleg a korrekciós funkcióval az egyes készlethelyesbítések indoka alapján az aktuális készlethelyesbítések értékét fel lehet adni a megfelelő ellenszámlára.

## <a name="recommendation"></a>Ajánlás

Mielőtt beállítaná a rendszert, javasoljuk, hogy dolgozzon ki egy stratégiát az okokkódok kezeléséhez. Próbáljon például válaszolni a következő kérdésekre:

- Legyenek az okkódok kötelezők a raktárak számára?
- Legyenek az okkódok kötelezők vagy választhatók egyes cikkeknél?
- Hány okkódra van szükség?
- Előre ki kell választani a helyesbítésekhez okkódok korlátozott listáját?
- Hogyan kell a vonalkódolvasók felhasználóinak használniuk az ok kódokat? Legyenek az okkódok előválasztottak, kötelezőek vagy nem szerkeszthetők?
- A raktári dolgozók különböző kódviselkedést igényelnek a mobil leolvasóknál? Ha a válasz igen, akkor több menüpontot hozhat létre, és hozzárendelheti azokat különböző emberekhez.
- Az okkódok vezérlik a pénzügyi ellenszámla feladását?

## <a name="turn-on-reason-code-features-in-your-system"></a>Okkód funkció bekapcsolása a rendszerben

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

Ha nem látja a rendszerben az ebben a témakörben leírt összes szolgáltatást, akkor valószínűleg be kell kapcsolnia a *Az ellenszámlákhoz kapcsolódó kódok használatával történő készlethelyesbítések feladása* funkciót. A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához. A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:

- **Modul:** *Raktárkezelés*
- **Funkció neve:** *Az ellenszámlákhoz kapcsolódó konfigurálható okkódok használatával történő készlethelyesbítések feladása*

## <a name="set-up-reason-codes"></a>Okkódok beállítása

### <a name="set-up-reason-code-policies"></a>Okkód-szabályzatok létrehozása

Több okkód-házirend is létrehozható, amelyek okkódok számolását alkalmazását szabályozzák. Minden okkódra vonatkozó irányelv két számlálási okkódtípusból áll (*Választható* vagy *Kötelező*). A számlálási okkód szabályzatok használhatók a raktár vagy a cikkek szintjén.

Az okkódra vonatkozó házirend a következő lépések szerint hozhatók létre.

1. Nyissa meg a **Készletkezelés** \> **Beállítás** \> **Készlet** \> **Számlálási okkód szabályzatok** menüpontot.
1. A műveleti ablakpanelen válassza az **Új** lehetőséget, ha hozzá szeretne adni egy házirendet a rácshoz.
1. Az új irányelv **Név** mezőjét állítsa be.
1. A **Számlálási okkód típusa** mezőben a következők közül választhat *Kötelező* vagy *Választható* – ezzel adhatja meg, hogy az okkód kiválasztása kötelező vagy választható legyen-e a következő raktárkorrekciós folyamatokban:

    - Ciklikus leltározás (mobileszköz)
    - Eseti leltározás (mobileszköz)
    - Küszöbérték-leltározás (mobileszköz)
    - Igazítás be (mobileszköz)
    - Igazítás ki (mobileszköz)
    - Leltárnapló (funkciógazdag ügyfél)
    - Mennyiség beállítása/online leltár (rich kliens)

Az egyes raktárakhoz és termékekhez is létrehozhat okkód-szabályzatokat. Egy termék okkódbeállítása felülbírálhatja a termék raktárának beállítását.

> [!NOTE]
> Azon raktárak és cikkek esetében, ahol a **Leltározási okkód irányelve** mező értéke *Kötelező*, a leltárnapló nem fejezhető be és zárható le, amíg okkód nincs megadva. További információért tekintse át a következő szakaszt.

### <a name="assign-counting-reason-code-policies-to-warehouses"></a>A leltározás okkódjával kapcsolatos irányelv hozzárendelése raktárakhoz

A számlálási okkódok raktárhoz való hozzárendelését a következő lépések szerint hajtsa végre.

1. Ugrás a következő lehetőségre: **Készletgazdálkodás** \> **Beállítás** \> **Készlet részletezése** \> **Raktárak**.
1. A listaablakban válasszon egy raktárat.
1. A Műveleti panelen, a **Raktár** lapon a **Beállítás** csoportban válassza ki a **Leltározási okkód szabályzat** lehetőséget. Ezután a **Raktározási okkód-szabályzat hozzárendelése** legördülő párbeszédpanelen hajtsa végre a következő lépések valamelyikét:

    - Ha az egyes cikkek szabálybeállításai alapján szeretné meghatározni, hogy kötelező-e a leltárnaplók használata, ne adjon meg értéket (vagy törölje a meglévő értéket).
    - Ha a raktár leltárnaplóiban okkódot kell megadni, válassza ki azt az okkódot-szabályzatot, ahol a **Leltározási okkód típusa** mező értéke *Kötelező*.
    - Ha a raktár leltárnaplóiban okkódot opcionális válassza ki azt az okkódot-szabályzatot, ahol a **Leltározási okkód típusa** mező értéke *Opcionális*.

### <a name="assign-counting-reason-code-policies-to-products"></a>A leltározás okkódjával kapcsolatos irányelv hozzárendelése termékekhez

A leltározási okkódok termékhez való hozzárendelését a következő lépések szerint hajtsa végre.

1. Kattintson a **Termékinformációk kezelése** \> **Termékek** \> **Kiadott termékek** lehetőségre.
1. A rácsban válasszon egy terméket.
1. A Műveleti panelen, a **Termék** lapon a **Beállítás** csoportban válassza ki a **Leltározási okkód szabályzat** lehetőséget. Ezután a **Raktározási okkód-szabályzat hozzárendelése** legördülő párbeszédpanelen hajtsa végre a következő lépések valamelyikét:

    - Ha a raktár szabálybeállításai alapján szeretné meghatározni, hogy kötelező-e a leltárnaplók használata a termékhez, ne adjon meg értéket (vagy törölje a meglévő értéket).
    - Ha a leltárnaplókban okkódot kell megadni a termékhez, válassza ki azt az okkódot-szabályzatot, ahol a **Leltározási okkód típusa** mező értéke *Kötelező*. Ez a beállítás felülbírálja a raktár szintjén érvényes okkód-beállításokat.
    - Ha a leltárnaplókban az okkód opcionális válassza ki azt az okkódot-szabályzatot, ahol a **Leltározási okkód típusa** mező értéke *Opcionális*. Ez a beállítás felülbírálja a raktár szintjén érvényes okkód-beállításokat.

### <a name="set-up-counting-reason-codes"></a>Leltározási okkódok beállítása

A leltározási okkódok beállításához kövesse az alábbi lépéseket.

1. Nyissa meg a **Készletkezelés** \> **Beállítás** \> **Készlet** \> **Leltározási okkódok** menüpontot.
1. A műveleti ablakpanelen válassza ki az **Új** lehetőséget, ha hozzá szeretne adni egy sort a rácshoz.
1. Az új sorhoz állítsa be a **Leltározási okkód** és **Leírás** mezőket.
1. Ellenszámla hozzárendeléshez adjon meg vagy válasszon ki egy értéket az **Ellenszámla** mezőben.

    > [!NOTE]
    > Ha egy ellenszámla hozzá van rendelve egy leltározási okkódhoz, ha a leltárnapló feladásakor azt az okkódot használja, az érték a hozzárendelt ellenzsámlával szemben lesz feladva az alapértelmezett készletfeladási profilszámla helyett.

### <a name="set-up-counting-reason-code-groups"></a><a name="reason-groups"></a>Leltározási okkódok csoportjainak beállítása

A *Leltározási okkódcsoportok* a Warehouse Management mobilalkalmazás *Korrekció be* és *Korrekció ki* menüelemei részeként használhatók a leltározási okkódok listájának kolrátozásához. (A leltározási okkódcsoportokkal kapcsolatos további tudnivalókat lásd: [A mobileszköz-menüpont módosítása igazítás be és igazítás ki folyamathoz](#setup-adjustment-in-out) szakaszt a témakör későbbi részében.)

1. Nyissa meg a **Készletkezelés** \> **Beállítás** \> **Készlet** \> **Leltározási okkód-csoportok** menüpontot.
1. Jelölje be a Műveleti ablaktáblán az **Új** lehetőséget csoprot hozzáadásához.
1. Az új csoporthoz állítsa be a **Leltározási okcsoport** és **Csoport leírása** mezőket.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
1. Ha új sort szeretne felvenni a rácsba, a **Részletek** szakaszban válassza az eszköztár **Új** gombját. Az új sorhoz állítsa be a **Leltározási okkód** mezőt. 
1. Ha további kódokat szeretne hozzárendelni, ismételje meg az előző lépést. Ha el kell távolítania egy kódot a csoportból, jelölje ki, majd válassza az eszköztár **Törlés** parancsát.

### <a name="set-up-reason-codes-for-mobile-device-menu-items"></a>Okkódok beállítása mobileszköz menüelemeihez

Az okkódok a következő, tényleges kiigazítási típusokhoz konfigurálhatók:

- Ciklikus leltározás
- Eseti leltározás
- Küszöbérték-leltározás
- Igazítás be
- Igazítás ki

A legtöbb esetben a következő adatokat lehet meghatározni az egyes kapcsolódó mobileszköz-menüpontok számára:

- Azt, hogy az okkód megjelenik-e a mobileszközön dolgozó számára leltározás közben.
- Az alapértelmezett okkódot, amely megjelenik a mobileszköz menüpontjában.
- Azt, hogy a felhasználó szerkesztheti-e az okkódot.

#### <a name="set-up-mobile-device-menu-items-for-a-counting-process"></a>Mobileszköz beállítása leltározás folyamathoz

Mobileszköz-menüelem beállításához a leltározási folyamathoz kövesse az alábbi lépéseket.

1. Lépjen a **Raktárkezelés** \> **Beállítás** \> **Mobileszköz** \> **Mobileszköz-menüelemek** részre.
1. Válassza ki a kívánt menüelemet a listaablakban, vagy hozzon létre egy új menüelemet.
1. A Művelet ablaktáblán válassza ki a **Ciklikus leltározása** lehetőségre.
1. Az **Alapértelmezett leltározási okkód** mezőben állítsa be az alapértelmezett okkódot, amelyet rögzíteni kell a leltár készítésekor a mobileszköz-menüpont használatával.
1. A **Leltározási okkód megjelenítése** mezőben válassza a következő értékek egyikét:

    - *Sor* – az okkód megjelenítése az egyes eltérések rögzítése után.
    - *Elrejtés* – Ne jelenítse meg az okkódot.

1. Állítsa a **Leltározási okkód szerkesztése** mezőt *Igen* értékre, hogy a dolgozó szerkeszthesse az okkódot, amikor a leltár során megjelenik a mobileszközön. Állítsa *Nem* értékre, ha meg szeretné akadályozni, hogy a dolgozó szerkessze a kódot.

> [!NOTE]
> A **Ciklikus leltározás** gomb engedélyezhető bármely mobileszköz-menüpontban, ahol leltározás végezhető. Példák menüelemek eseti leltározáshoz, felhasználó által irányított munkához és a rendszer által irányított munkához.

#### <a name="set-up-mobile-device-menu-items-for-adjustment-in-and-adjustment-out"></a><a name="setup-adjustment-in-out"></a>A mobileszköz-menüelemek beállítása igazítás be és igazítás ki folyamathoz

Mobileszköz-menüelem beállításához a az igazítás be és igazítás folyamathoz kövesse az alábbi lépéseket.

1. Lépjen a **Raktárkezelés** \> **Beállítás** \> **Mobileszköz** \> **Mobileszköz-menüelemek** részre.
1. A menüelem létrehozásához a műveleti ablaktáblán válassza ki az **Új** lehetőséget.
1. Az új menüelemhez állítsa be **Mobilelem neve** és **Cím** mezőket.
1. A **Mód** mező beállítása *Munka* legyen.
1. A **Meglévő munka használata** lehetőséget állítsa *Nem* értékre.
1. A **Munkalétrehozási folyamat** mezőben válassza az *Igazítás be* vagy *Igazítás ki* lehetőséget.
1. Az **Általános** gyorslapon állítsa be a következő mezőket. (A kiválasztott mezőket a rendszer hozzáadja, ha az *Igazítás be* vagy *Igazítás ki* értéket választja a **Munkalétrehozási folyamat** mezőben.)

    - **Folyamat-útmutató használata** – ha *Igazítás ki* folyamatot létre, mindenképpen állítsa ezt *Igen* beállításra. Ha *Igazítás ki* folyamatot hoz létre, ez a beállítás mindig *Igen* értékre van állítva.
    - **Alapértelmezett leltározási okkód** – Állítsa be az alapértelmezett okkódot, amelyet rögzíteni kell a leltár készítésekor a mobileszköz-menüpont használatával.
    - **Leltározási okkód megjelenítése** – válassza a következő értékek egyikét:

        - *Sor* – az okkód megjelenítése az egyes eltérések rögzítése után.
        - *Elrejtés* – Ne jelenítse meg az okkódot.

    - **Leltározási okkód szerkesztése** – Állítsa ezt a beállítást *Igen* értékre, hogy a dolgozó szerkeszthesse az okkódot, amikor a leltár során megjelenik a mobileszközön. Állítsa *Nem* értékre, ha meg szeretné akadályozni, hogy a dolgozó szerkessze a kódot.
    - **Leltározási okkódcsoport** – Ha korlátozni szeretné a dolgozóknak megjelenő lehetőségek listáját, válasszon egy okkódcsoportot. Az okkódcsoportok beállítását a témakör korábbi, [Leltározási okkódcsoportok beállítása](#reason-groups) című szakasza tartalmazza. 

> [!NOTE]
> Amikor leltározási okkódcsoportot rendel az *Igazítás be* és *Igazítás ki* menüelemekhez, ahol a **Folyamatútmutató használata** beállítás *Igen* értékű, akkor a leltározási okkódok korlátozott listáját jelenítheti meg a feldolgozás részeként a Warehouse Management mobilalkalmazásban.
>
> A **Folyamatútmutató használata** beállítás a nagy helyesbítési mennyiségek véletlen elvégzésének megakadályozására is használható. (Például egy dolgozó mennyiségérték helyett véletlenül beolvashatja egy cikkszám vonalkódját.) Ennek a funkciónak a beállításához állítsa a **Folyamatútmutató használata** lehetőséget *Igen* beállításra minden egyes kapcsolódó menüelemhez. Ezután menjen a **Raktárkezelés \> Beállítás \> Dolgozó** menübe, és állítsa be a **Korrekció mennyiségének korlátozása** mezőt minden egyes érintett raktári dolgozóhoz, hogy meghatározza a dolgozó által regisztrálható maximális módosítási mennyiséget.

## <a name="processing-that-uses-counting-reason-codes"></a>Leltározási okkódokat használó feldolgozás

Amikor a dolgozók a Warehouse Management mobilalkalmazást használják, az okkódok rögzítésre kerülnek. Hacsak nincs megadva leltározás-jóváhagyási folyamat, a rögzített okkódokat a rendszer azonnal használja az utána következő leltárnapló-feladásakor.

### <a name="cycle-count-approvals"></a>Ciklikus leltári jóváhagyások

A leltár jóváhagyása előtt a dolgozó módosíthatja a leltárhoz társított okkódot. A leltár jóváhagyásakor az okkód bekerül a leltárnapló soraiba.

#### <a name="modify-reason-codes-for-cycle-count-approvals"></a>Ciklikus leltárjóváhagyásokhoz tartozó okkódok módosítása

Kövesse ezeket a lépéseket a ciklikus leltározási terv módosításához.

1. Nyissa meg a **Raktárkezelés** \> **Ciklikus leltározás** \> **Ciklikus leltározási munka ellenőrzése függőben** lehetőséget.
1. A rácsban válasszon egy ciklikus leltárt.
1. A Művelet panelen a **Munka** lapon válassza a **Ciklikus leltározás** menüpontot. Majd az **Okkód** mezőben válasszon egy új okkódot.

Az okkódok a *Leltárnapló* leltárnaplóknál a napló soraiba kerülnek hozzáadásra.

1. Lépjen a **Készletgazdálkodás** \> **Naplóbejegyzések** \> **Cikkleltár** \> **Leltár** menüpontba.
2. A leltárnapló sorrészleteiben, a **Leltározás okkódja** mezőben válassza ki az aktuális helyzetnek megfelelő okkódot.

### <a name="view-the-reason-codes-recorded-in-the-counting-history"></a>A leltározási előzményekben bejegyzett okkódok megtekintése

A leltározási előzményekben rögzített okkódok megtekintéséhez kövesse ezeket a lépéseket.

1. Menjen a **Készletkezelés** \> **Lekérdezések és jelentések** \> **Leltározási előzmények** lehetőségre.
1. Válasszon ki a cikkleltározási rekordot a listaablakban.
1. A **Leltározás okkódja** mezőjében megtekintheti az okkóddal rögzített leltározási előzményeket.

### <a name="use-reason-codes-for-quantity-adjustment-or-online-counting"></a>Okkódok használata mennyiségkorrekcióhoz vagy online leltározáshoz

A mennyiségkorrekciók és online leltárak okkódja a következő lépések szerint használható.

1. Menjen a **Készletkezelés \> Lekérdezések és jelentések \> Aktuális készletlista** lehetőségre.
1. Válassza a Műveleti ablaktáblán a **Mennyiségi kiigazítás** lehetőséget.
1. Válassza a **Mennyiség kiigazítása** elemet, majd a **Leltározási okkód** mezőben válasszon egy okkódot.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
