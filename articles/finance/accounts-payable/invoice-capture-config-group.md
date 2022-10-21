---
title: Számlarögzítési megoldás konfigurációs csoportjai
description: Ez a cikk a Számlarögzítés megoldás konfigurációs csoportjaival kapcsolatban tartalmaz általános tájékoztatást.
author: sunfzam
ms.date: 09/28/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: zezhangzhao
ms.search.validFrom: 2022-09-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: cfe5ae35b4f87a350d944b30a49251081766ad27
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690993"
---
# <a name="invoice-capture-solution-configuration-groups"></a>Számlarögzítési megoldás konfigurációs csoportjai

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

A felhasználók konfigurációs csoportok segítségével kezelhetik a számlamezők listáját és a jogi személyek manuális áttekintő beállításait. A felhasználók csoportonként különböző jogi személyekhez állíthatnak be számlakonfigurációkat. Az ugyanabban a konfigurációs csoportban található összes jogi személy ugyanazt a számlamezőket és a manuális áttekintő beállításokat használja.

## <a name="manage-configuration-groups"></a>Konfigurációs csoportok kezelése

Ha a konfigurációs csoportokat az alkalmazás segítségével kezelheti, használja a Telepítőt, **·** **majd válassza a Rendszerbeállítás \> megadása konfigurációs csoportok összetevőjét**.

A Konfigurációs **csoportok megadása** lapon a fő lapon a definiált konfigurációs csoportok listája látható. Az alapértelmezett konfigurációs csoportot is megjeleníti. Az egyes konfigurációs csoportoknál a következő műveletek érhetők el:

- **Konfigurációs csoport másolása** – egy meglévő csoport másolása után új konfigurációs csoportot hozhat létre. Az új csoportban ugyanazok az értékek vannak, mint az eredeti csoport **az összes mezőben, kivéve a Csoportnevet** és **a Csoport leírását**. A konfigurációs csoport másolása után válassza az **OK gombra.**
- **Konfigurációs csoportok törlése** – ha törölni szeretne egy konfigurációs csoportot, jelölje ki, majd válassza a **Törlés lehetőséget**.

    > [!NOTE]
    > Az alapértelmezett konfigurációs csoport nem törölhető.

- **Konfigurációs csoport azonosítójának szerkesztése** – konfigurációs csoport azonosítójának szerkesztéséhez jelölje be **a** Csoportazonosító mezőt, és frissítse az értéket. A csoportazonosító nem tartalmazhat szóközt vagy speciális karaktert, és nem haladhatja meg a 20 karaktert.

    > [!NOTE]
    > A Csoportazonosító **mező** értéke csak egyszer frissíthető.

- **Konfigurációs csoport leírásának szerkesztése** – konfigurációs csoport leírásának szerkesztéséhez jelölje be **a** Leírás mezőt, és frissítse az értéket.
- **A manuális ellenőrzés beállításának módosítása** – a felhasználók eldöntik, hogy manuálisan kell-e átnézni a számlákat. A manuális ellenőrzés beállításának a Módosítása a Manuális **ellenőrzés szükséges beállításával** lehetséges. Ehhez a következő lehetőségek állnak rendelkezésre:

    - **Mindig manuális ellenőrzés** – akkor válassza ezt a lehetőséget, ha a konfigurációs csoport számláit mindig manuális ellenőrzésre kell igényelni.
    - **Hibák és figyelmeztetések** esetén – akkor válassza ezt a lehetőséget, ha a hibaüzeneteket vagy figyelmeztető üzeneteket tartalmazó számlák esetében manuális ellenőrzés szükséges.
    - **Hiba esetén** – akkor válassza ezt a lehetőséget, ha a hibaüzeneteket tartalmazó számláknál manuális ellenőrzés szükséges.

- **A megbízhatósági pontszám beállításának** módosítása – a megbízhatósági pontszám metaadat, amely a számlarögzítési megoldás által a felismert számlaadatok pontosságának jelentéséhez ad tájékoztatást. Minél magasabb a pontszám, annál pontosabbak az felismert adatok. A konfiguráció lehetővé teszi a felhasználók számára a megbízhatósági pontszám alapján, hogy mikor szükséges manuális ellenőrzés. A felhasználók módosíthatják a számlákra vonatkozó megbízhatósági pontszám küszöbértékét. A megbízhatósági pontszám beállításának frissítéséhez jelölje be **a Megbízhatósági pontszám mezőt**, majd frissítse az értéket.

    A biztonsági pontszámok kétféle figyelmeztetési típust létezik:

    - **Figyelmeztetés** – helyesnek azok a számlamezők számítanak helyesnek, amelyeknél a biztonsági pontszámok túllépik a figyelmeztetési küszöbértéket. A figyelmeztetési küszöbértéknek a hibahatárnál nagyobbnak és 100-asnál kisebbnek kell lennie.
    - **Hiba** – sikertelennek azok a számlamezők számítanak, amelyeknél a hiba küszöbértéke bizalmas. Hibaüzenetek jelennek meg a felhasználó számára. A hibaküszöbnek nullánál nagyobbnak és a figyelmeztetési küszöbértéknél kisebbnek kell lennie. Figyelmeztető üzenetek jelennek meg az olyan számlamezők esetében, amelyeknél a biztonsági pontszámok a figyelmeztetési küszöbérték és a hibahatár között vannak.

- **Számlamezők kezelése** – a felhasználók kezelhetik az egymás mellett megjelenítő megjelenítő számlamezők listáját. A Számla mezőkezelés **lapon** jelölje ki a fogaskerekek szimbólumát, válassza ki a hozzáadni kívánt számlamezőket, majd válassza a Mentés **lehetőséget**. A kijelölt mezőket a program hozzáadja a listához. Ha el szeretne távolítani egy számlamezőt a listából, válassza az **Eltávolítás** lehetőséget a mezőben.

### <a name="manage-file-filters-optional"></a>Fájlszűrők kezelése (nem kötelező)

A fájlszűrők kezelése révén a felhasználók további szűrőket határozhatnak meg a bejövő számlafájlokhoz. A rendszer a szűrési **feltételeknek** nem megfelelő fájlokat fogja megkapni, és megjelennek a Beérkezett fájlok listában, de fájl-ellenőrzési hibákat fognak megjelenni. Ez a viselkedés eltér a csatornában meghatározott szűrők viselkedéstől. Ilyen szűrőknél a feltételeknek nem megfelelő fájlok egyáltalán nem fognak fogadott lenni. A felhasználók áttekinthetik a bejövő fájlokat, és eldöntik, hogy egy-egy fájl nem érvényes számla-e, elavultá válnak a fájl, vagy manuálisan belefoglalhatják őket a rögzített számlákba.

A Számlarögzítés megoldás telepítésekor meg van adva egy alapértelmezett fájlszűrő. Ez a fájlszűrő globális. Ha más szűrőbeállításokat szeretne használni, frissítheti az alapértelmezett szűrőt. Ha egy mező kötelező, válassza a Kötelező **lehetőséget**. 

### <a name="accepted-file-size"></a>Elfogadott fájlméret

Itt kiválaszthatja az elfogadott fájlméretet.

> [!NOTE]
> A 20 480 kilobájtnál (KB) nagyobb fájlok nem támogatottak.

### <a name="supported-file-types"></a>Támogatott fájltípusok

Jelenleg a következő fájltípusok támogatottak:

- PDF
- PNG
- JPG
- JPEG
- Tif
- TIFF
