---
title: Automatikus költségek csatorna szerinti engedélyezése és konfigurálása
description: Ez a témakör azt mutatja be, hogyan lehet engedélyezni és konfigurálni az automatikus költségeket csatornánként a Microsoft Dynamics 365 Commerce alkalmazásban.
author: gvrmohanreddy
ms.date: 03/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2020-03-01
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: d905819d1e0c8223c74509bfb357b3aaa51d20305a2857061eadb0b0ff8f6b9b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6727630"
---
# <a name="enable-and-configure-auto-charges-by-channel"></a>Automatikus költségek csatorna szerinti engedélyezése és konfigurálása

Ez a témakör azt mutatja be, hogyan lehet engedélyezni és konfigurálni az automatikus költségeket (auto költségek) csatornánként a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

Előfordulhat, hogy olyan forgatókönyvei vannak amikor egy adott államban (például Kalifornia) egy vagy több üzletben értékesített termékek egy csoportjára vonatkozóan újrahasznosítási díjat vagy egyéb díjat kell alkalmazni. A **Az automatikus kötsége szűrésének engedélyezése csatornánként** funkcióval csatornánként határozhat meg automatikus költségeket (péládul egy adott fizikiai üzlet csatornához). Ez a funkció elérhető a Dynamics 365 Commerce alkalmazás 10.0.10 vagy újabb verziójában.

Az automatikus költségek csatorna szerinti engedélyezéséhez és beállításához a következő feladatokat kell elvégeznie:

- Kapcsolja be az **Automatikus kötségek szűrésének engedélyezése csatornánként** funkciót.
- Konfigurálja a szervezeti hierarchia célját.
- Automatikus költségek definiálása csatornánként.

> [!NOTE]
> Az **Automatikus kötségek szűrésének engedélyezése csatornánként** funkció csak akkor működik, ha a speciális automatikus költségek funkció is be van kapcsolva. A speciális automatikus költség funkció bekapcsolásával kapcsolatban a következő témakör tartalmaz további tájékoztatást: [Többcsatornás speciális automatikus költségek](omni-auto-charges.md).

## <a name="turn-on-the-enable-filter-auto-charges-by-channel-feature"></a>Kapcsolja be az Automatikus kötségek szűrésének engedélyezése csatornánként funkciót

A csatorna szerinti automatikus költségek engedélyezéséhez a Commerce alkalmazásban hajtsa végre az alábbi lépéseket.

1. Válassz a **Rendszerfelügyelet \> Munkaterületek \> Funkciókezelés** elemet.
1. A **Nem engedélyezett** lapon a **Szolgáltatások neve** listáján keresse meg és válassza ki az **Automatikus kötségek szűrésének engedélyezése csatornánként** lehetőséget.
1. A jobb alsó sarokban válassza az **Engedélyezés most** lehetőséget. Miután a funkció be lett kapcsolva, az **Összes** lap listájában jelenik meg.
1. Ugorjon a **Kiskereskedelem és kereskedelem \> Kiskereskedelem és kereskedelem informatika \> Elosztási ütemezés** pontra.
1. A bal oldali ablaktáblában keresse meg és válassza ki a **1110** (**Globális konfiguráció**) feladatot.
1. A Műveletek ablaktáblán válassza a **Futtatás most** parancsot a konfigurációs módosítások propagálásához.

> [!WARNING]
> Ha kikapcsolja az **Automatikus kötségek szűrésének engedélyezése csatornánként** funkciót, miután már használta azt, akkor **Kiskereskedelmi csatorna kapcsolat** mező az **Automatikus költésgek** alatt nem fog megjelenni, és minden létező konfigurációt elveszik. Ha a **Kiskereskedelmi csatorna kapcsolat** konfigurációk eltávolítása az automatikus költésgek szabályainak duplikálását okozná akkor nem fog sikerüni a funkció kikapcsolása. A funkció kikapcsolása előtt fontos, hogy minden automatikus költség-szabályt ellenőrizen, és végezze el a szükséges módosításokat.

## <a name="configure-the-organization-hierarchy-purpose"></a>Konfigurálja a szervezeti hierarchia célját

A program létrehozta a **Kiskereskedelmi automatikus költség** nevű új szervezeti hierarchiát, amely a csatorna szerinti automatikus díjak hierarchiájának kezelésére szolgál.

Ha egy alapértelmezett hierarchiát szeretné társítani egy szervezeti hierarchiához a Commerce-ben, hajtsa végre az alábbi lépéseket.
        
1. Ugrás a **Szervezet felügyelete \> Szervezetek \> Szervezeti hierarchiák céljai** menübe.
1. A bal oldali ablakban válassza ki a **Kiskereskedelmi automatikus költség** elemet.
1. A **Hozzárendelt hierarchiák** területen válassza **Hozzáadás** elemet.
1. A **Szervezeti hierarchiák** párbeszédpanelen válasszon egy szervezeti hierarchiát (például a **Kiskereskedelmi üzletek régiónként**), majd kattintson az **OK** gombra.
1. A **Hozzárendelt hierarchiák** területen válassza **Beállítás alapértelmezettként** elemet.
1. Ugorjon a **Kiskereskedelem és kereskedelem \> Kiskereskedelem és kereskedelem informatika \> Elosztási ütemezés** pontra.
1. A bal oldali ablaktáblában keresse meg és válassza ki a **1040** (**Termékek**) feladatot.
1. A Műveleti ablaktáblán kattintson a **Futtatás most** elemre.
1. A **1070** (**Csatorna-konfigurációja**) és a **1110** (**Globális konfiguráció**) feladatok futtatásához ismételje meg az előző két lépést.

![A Kiskereskedelmi automatikus költség szervezeti hierarchia céljának konfigurálása.](media/Auto-charges-org-hierarchy-purpose.png)

## <a name="define-auto-charges-by-channel"></a>Automatikus költségek definiálása csatornánként

Miután bekapcsolta az **Automatikus kötségek szűrésének engedélyezése csatornánként** funkciót, és konfigurálta a **Kiskereskedelmi automatikus költség** szervezeti hierarchia célját, a csatorna szerinti automatikus költség definiálható a rendelés fejléc szintjén vagy a rendelési sor szintjén.

A csatorna szerinti automatikus költségek definiálásához a Commerce alkalmazásban hajtsa végre az alábbi lépéseket.

1. Ugorjon a **Kinnlevőségek \> Költségek beállítása \> Automatikus költségek** pontra.
1. A bal oldali ablak **Szint** mezőjében válassza a **Fejléc** vagy **Sor** beállítást az üzleti igényektől függően.
1. A **Kiskereskedelmi csatorna kódja** mezőben válassza ki a megfelelő csatornakódot (például **Tábla** vagy **Csoport**). Ha az alapértelmezett **Minden** beállítás van használatban, akkor minden csatornára alkalmazva lesznek a költségszabályok.

    - Ha a **Csoport** lehetőséget választja, akkor győződjön meg róla, hogy kiskereskedelmi csatorna költésgcsoportja létre van hozva a **Kiskereskedelem és kereskedelem \> Csatorna beállításai \> Költésgek \> Kiskreskedelmi csatorna költségcsoportjai** menüben.
    - Ha a **Tábla** lehetőséget választja, akkor a **Kiskereskedelmi csatorna kapcsolata** mezőben kiválaszthatja a kívánt csatornát (például **San Francisco**).

1. Ugorjon a **Kiskereskedelem és kereskedelem \> Kiskereskedelem és kereskedelem informatika \> Elosztási ütemezés** pontra.
1. A bal oldali ablaktáblában keresse meg és válassza ki a **1040** (**Termékek**) feladatot.
1. A Műveleti ablaktáblán kattintson a **Futtatás most** elemre.
1. A **1070** (**Csatorna-konfigurációja**) és a **1110** (**Globális konfiguráció**) feladatok futtatásához ismételje meg az előző két lépést.
    
![Automatikus költségek csatornánként definiálva.](media/Auto-charges-line-charge-by-channel.png)

## <a name="example-scenario"></a>Példaforgatókönyv

A következő példa a termék konfigurálásához szükséges lépéseket írja le, hogy az újrafeldolgozási díjak fel legyenek számítva, amikor a terméket egy San Francisco-i fizikai üzletben értékesítik. A példa azt is bemutatja, hogy hogyan jelenjenek meg az automatikus költségek a Commerce pénztár (POS) alkalmazásában.

A szervezet definiál egy **ÚJRAHASZNOSÍTÁS** nevű költségkódot a következő ábrán látható módon.

![ÚJRAFELDOLGOZÁS költségkód.](media/Auto-charges-charge-code.png)

Az automatikus költséget a sor szintjén jön létre. Az alábbi konfiguráció jellemzi:

- A **Számlakód** mező be van állítva **Minden** értékre.
- A **Cikkkód** mező be van állítva **Tábla** értékre.
- A **Cikk- kapcsolat** mező értéke a **91001** termékazonosító.
- A **Szállítási mód** mező be van állítva **Minden** értékre.
- A **Kiskereskedelmi csatorna kódja** mező be van állítva **Tábla** értékre.
- A **Kiskereskedelmi csatorna kapcsolata** mező értéke a **San Francisco** üzletre van állítva.

Létrejön egy automatikus költség sor. Az alábbi konfiguráció jellemzi:

- A **Pénznem** mező beállítása **USD**.
- A **Költségkód** mező be van állítva **ÚJRHASZNOSÍTÁS** értékre.
- A **Kategória** mező be van állítva **Rögzített** értékre.
- A **Költésgek** mező beállítása **6,25 USD**.

![A sorszintű automatikus költségek és az automatikus költségek sorának konfigurálása.](media/Auto-charges-recyclingfee-line-fee.png)

A pénztár alkalmazásban létrejön egy értékesítési rendelés a **San Franciscó** üzlet csatornájában. A **Költségek** sor a **6,25 dolláros** újrahasznosítási díjat jeleníti meg.

Ha kiválasztja a **Tranzakcióbeállítások \> Költségék \> Költésgek kezelése** lehetőséget a POS-alkalmazásban, akkor megtekintheti az újrahasznosítási díj költségkódját és leírását.

![Újrahasznosítási díj a pénztár alkalmazásban.](media/pos-auto-charges-recyclingfee-line-fee.png)

## <a name="additional-resources"></a>További erőforrások

[Többcsatornás speciális automatikus költségek](omni-auto-charges.md)

[Fejlécköltségek arányosítása az egyező értékesítési sorokhoz](pro-rate-charges-matching-lines.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]