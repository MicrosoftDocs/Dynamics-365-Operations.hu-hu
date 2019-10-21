---
title: Entitásadatok megnyitása az Excel programban, és frissítésük az Excel-modul használatával
description: Ez a témakör bemutatja, hogyan lehet megnyitni az entitásadatokat a Microsoft Excel programban, és hogyan lehet megtekinteni, frissíteni és szerkeszteni az adatokat az Excel Microsoft Dynamics Office beépülő moduljának segítségével.
author: ChrisGarty
manager: AnnBe
ms.date: 04/11/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 267914
ms.assetid: 4e6c7194-a059-4057-bd62-ec0c802c36fd
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 210231bb442928674b490d83f50bf787d7bfa60c
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2181013"
---
# <a name="open-entity-data-in-excel-and-update-it-by-using-the-excel-add-in"></a>Entitásadatok megnyitása az Excel programban, és frissítésük az Excel-modul használatával

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja, hogyan lehet megnyitni az entitásadatokat a Microsoft Excel programban, és hogyan lehet megtekinteni, frissíteni és szerkeszteni az adatokat az Excel Microsoft Dynamics Office beépülő moduljának segítségével. Az entitás adatainak megnyitásához kiindulhat az Excel vagy Finance and Operations alkalmazásokból.

Az entitásadatok megnyitásával az Excel programban gyorsan és egyszerűen tekintheti meg és szerkesztheti az adatokat az Excel beépülő moduljának segítségével. A bővítményhez Microsoft Excel 2016 szükséges.

> [!NOTE]
> Ha a Microsoft Azure Active Directory (Azure AD) bérlője az Active Directory összevonási szolgáltatások (AD FS) használatára van beállítva, meg kell győződnie arról, hogy a 2016. májusi Office-frissítés telepítve van, hogy az Excel-bővítmény helyesen jelentkeztesse be.

További tudnivalókért az Excel-bővítményről, tekintse meg a rövid videót: [Excel-sablon létrehozása a fejléc- és sormintákhoz a Dynamics 365 for Finance and Operations](https://youtu.be/RTicLb-6dbI) alkalmazásban.

## <a name="open-entity-data-in-excel-when-you-start-from-finance-and-operations"></a>Nyissa meg az entitásadatokat az Excel programban a Finance and Operations indításakor
1. A Finance and Operations egyik lapján válassza a **Megnyitás a Microsoft Office** programban lehetőséget.

    Ha az oldal gyökér adatforrása (tábla) megegyezik bármelyik entitás gyökér adatforrásával, létrejönnek a lap alapértelmezett **Megnyitás az Excel programban** beállításai. A **Megnyitás az Excel programban** lehetőségek megtalálhatók a gyakran használt lapokon, például az **Összes szállító** és **Összes vevő** oldalon.
 
2. Válassza az egyik **Megnyitás az Excel programban** lehetőséget, és nyissa meg a létrejövő munkafüzetet. Ez a munkafüzet kötési információkat tartalmaz az entitásra, egy mutatót a környezetre és egy mutatót az Excel-bővítményre.
3. Az Excel programban válassza a **Szerkesztés engedélyezése** lehetőséget az Excel-bővítmény futtatásának engedélyezéséhez. Az Excel-bővítmény egy panelen fut az Excel ablak jobb oldalán.
4. Ha az Excel beépülő modult első alkalommal futtatja, válassza az **Ez a bővítmény megbízható** lehetőséget.
5. Ha a rendszer bejelentkezést kér, válassza a **Bejelentkezés** lehetőséget, majd a Finance and Operations bejelentkezéshez használt hitelesítő adatok használatával jelentkezzen be. Az Excel beépülő modul az Internet Explorer korábbi bejelentkezési kontextusát használva automatikusan bejelentkezik a rendszerbe, ha talál ilyet. Ezért ellenőrizze a felhasználónevet az Excel-bővítmény jobb felső sarkában.

Az Excel-bővítmény automatikusan beolvassa a kijelölt entitás adatait. Ne felejtse, hogy nincsenek adatok a munkafüzetben mindaddig, amíg be nem olvassa őket az Excel-bővítmény.

## <a name="open-entity-data-in-excel-when-you-start-from-excel"></a>Az entitás adatainak megnyitása az Excelben az Excel indításakor
1. Az Excel programban a **Beszúrás** lapon, a **Bővítmények** csoportban válassza az **Áruház** lehetőséget az Office Áruház megnyitásához.
2. Az Office Áruházban keressen a **Dynamics** kulcsszóra, majd válassza a **Hozzáadás** lehetőséget a **Microsoft Dynamics Office-bővítmény** (az Excel-bővítmény) mellett.
3. Ha az Excel beépülő modult első alkalommal futtatja, válassza az **Ez a bővítmény megbízható** lehetőséget az Excel-bővítmény futásának engedélyezéséhez. Az Excel-bővítmény egy panelen fut az Excel ablak jobb oldalán.
4. Válassza a **Kiszolgáló adatainak hozzáadása** lehetőséget a **Beállítások** ablak megnyitásához.
5. A böngészőben az URL-címet másolja ki a célként megadott Finance and Operations példányból, illessze be a **Kiszolgáló URL-címe** mezőben, és töröljön mindent az állomás neve után. Az eredményül kapott URL-címnek csak az állomásnévvel kell rendelkeznie.

    Ha például az URL-cím `https://xxx.dynamics.com/?cmp=usmf&amp;mi=CustTableListPage`, akkor a `https://xxx.dynamics.com` részen kívül töröljön mindent.

6. A módosítások megerősítéséhez válassza az **OK**, majd az **Igen** elemet. Az Excel-bővítmény újraindul és betölti a metaadatokat.

    Most már elérhető a **Terv** menügomb. Ha az Excel-bővítmény rendelkezik egy **Kisalkalmazások betöltése** gombbal, akkor valószínűleg nem a megfelelő felhasználóként jelentkezett be. További információért lásd a „Látszik a Kisalkalmazások betöltése gomb” részt a témakör [Hibaelhárítás](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/office-integration/use-excel-add-in#troubleshooting) című szakaszában.

7. Válassza a **Tervezés** lehetőséget. Az Excel-bővítmény lekéri az entitás metaadatait.
8. Válassza a **Táblázat beszúrása** lehetőséget. Megjelenik az entitások listája. Az entitások „Név – címke” formátumban jelennek meg.
9. Válasszon ki a listában egy entitást, például **Vevő - Vevők**, és válassza a **Tovább** elemet.
10. Mező hozzáadásához a **Választható mezők** listáról a **Kijelölt mezők** listához, válassza ki a mezőt, és kattintson a **Hozzáadás** elemre. Alternatív megoldásként kattintson duplán a mezőre a **Választható mezők** listában.
11. Miután befejezte a kívánt mezők hozzáadását a **Kijelölt mezők** listához, győződjön meg arról, hogy a kurzor a megfelelő helyen van a munkalapon (például az A1 cellán), és válassza  a **Kész** elemet. Válassza a **Kész** elemet, és lépjen ki a tervezőből.
12. Válassza a **Frissítés** elemet egy adatkészlet behúzásához.

## <a name="view-and-update-entity-data-in-excel"></a>Az entitásadatok megtekintése és frissítése az Excel programban
Miután az Excel-bővítmény beolvasta az entitásadatokat a munkafüzetbe, bármikor frissítheti az adatokat a **Frissítés** lehetőséget választva az Excel-bővítményben.

## <a name="edit-entity-data-in-excel"></a>Az Excel programban az entitás adatainak szerkesztése
Az entitásadatokat igény szerint módosíthatja, és aztán újra közzéteheti őket a **Közzététel** elemre kattintva az Excel-bővítményben. Egy rekord módosításához a munkalapon jelöljön ki egy cellát, és változtassa meg a cella értékét. Új rekord hozzáadásához hajtsa végre az alábbi lépések valamelyikét:

- Kattintson bárhová az adatforrások táblázatában, majd az **Új** lehetőségre az Excel-bővítményben.
- Kattintson az adatforrások táblázatának utolsó sorába, és nyomja le a Tab billentyűt mindaddig, amíg a kurzor ki nem lép a sor utolsó oszlopából, és új sor nem jön létre.
- Kattintson a sorra közvetlenül az adatforrások táblázata alatt, és kezdjen el adatokat beírni egy cellába. Amikor a fókuszt kimozgatja a cellából, a táblázat kiegészül az új sorral.
- A fejlécrekordok mezőkötéseihez kattintson az egyik mezőre, majd az Excel-bővítményben kattintson az **Új** lehetőségre.

Ne feledje, hogy csak akkor hozható létre új rekord, ha mind a kulcs, mind a kötelező mezők kötve vannak a munkafüzetben, illetve ha az alapértelmezett értékeket megadták a szűrőfeltétel használatával.

Rekord törléséhez hajtsa végre az alábbi lépések valamelyikét:

- Kattintson a jobb gombbal a törölendő munkalapsor melletti sorszámra, és kattintson a **Törlés** gombra.
- Kattintson a jobb gombbal a törölendő munkalapsor melletti sorszámra, és kattintson a **Törlés** &gt; **Táblázatsorok**gombra.

Ha az adatforrásokat kapcsolódóként adták meg, akkor a fejléc a sorok elé kerül. Ha más adatforrások között függőségek vannak, előfordulhat, hogy módosítania kell az alapértelmezett közzétételi sorrendet. Az Excel-bővítmény, a közzétételi sorrendjének módosítása érdekében válasszon ki a **beállítások** gomb (felszerelés szimbólumát), majd a **Data Connector** gyorslapon válassza a **Közzétételi rendelés konfigurálása** lehetőséget.

## <a name="add-or-remove-columns"></a>Oszlopok hozzáadása vagy eltávolítása
A tervező segítségével igazíthatja az oszlopokat, amelyek automatikusan adódnak hozzá a munkalaphoz.

> [!NOTE]
> Ha a **Tervező** alatt a gomb nem jelenik meg a **szűrő** gombra az Excel bővítmény, engedélyeznie kell az adatok forrásának-tervezőben. Válassza ki a **beállítások** (felszerelés szimbólumát) gombra, és jelölje be a **tervezési engedélyezése** jelölőnégyzetet.

1. Kattintson a **Tervező** lehetőségre az Excel-bővítményben. Az összes adatforrás kilistázódik.
2. Az adatforrás mellett kattintson a **Szerkesztés** gombra (ceruza jel).
3. Állítsa be a mezőlistát a **Kijelölt mezők** listában:

    - Mező hozzáadásához a **Választható mezők** listáról a **Kijelölt mezők** listához, válassza ki a mezőt, és kattintson a **Hozzáadás** elemre. Alternatív megoldásként kattintson duplán a mezőre a **Választható mezők** listában.
    - Ha el szeretne távolítani egy mezőt a **Kijelölt mezők** listából, kattintson a mezőre, majd az **Eltávolítás** parancsra. Másik lehetőségként kattintson duplán a mezőre.
    - A mezők sorrendjének módosításához kattintson a mezőre a **Kijelölt mezők** listában, és kattintson a **Fel** vagy **Le** lehetőségre.

4. A **Frissítés** lehetőségre kattintva alkalmazhatja a módosításokat az adatforrásra. Válassza a **Kész** elemet, és lépjen ki a tervezőből.
5. Ha hozzáadott egy mezőt (oszlop), kattintson a **Frissítés** lehetőségre egy frissített adatkészlet behúzásához.

## <a name="copy-environment-data"></a>Környezeti adatok másolása

Az egyik környezetből a munkafüzetbe beolvasott adatok átmásolhatók egy másik környezetbe. Nem módosíthatja azonban a kapcsolat URL-jét, mert a munkafüzetben lévő adatgyorsítótár továbbra is meglévő adatokként kezeli az adatokat. Ehelyett a Környezetvédelmi adatok másolási funkcióval kell új adatokat közzétenni az új környezetbe.

1. Válassza ki a **beállítások** gomb (felszerelés szimbólumát), majd az a **Data Connector** gyorslapon válassza **környezeti adatok másolása**. 
2. Adja meg a kiszolgáló URL-címét az új környezethez. 
3. A művelet megerősítéséhez válassza az **OK**, majd az **Igen** elemet. Az Excel-bővítmény újraindul, és csatlakozik az új környezethez. A munkafüzetben található összes létező adat új adatként kezelendő.

    Miután az Excel bővítmény újraindul, egy üzenettáblában kijelentik, hogy a munkafüzet környezeti másolási módban van.

4. Ha az adatokat az új környezetbe szeretné másolni új adatként, válassza a **Közzététel** lehetőséget. A környezet másolási művelet megszakítása, és tekintse át a meglévő adatokat, az új környezetben, jelölje be a **Frissítés** lehetőséget.

## <a name="troubleshooting"></a>Hibaelhárítás
Vannak bizonyos problémák, amelyek néhány egyszerű lépéssel megoldhatók.

- **Látszik a Kisalkalmazások betöltése gomb.** – Ha az Excel-bővítmény rendelkezik egy **Kisalkalmazások betöltése** gombbal a bejelentkezés után, akkor valószínűleg nem a megfelelő felhasználóként jelentkezett be. A probléma megoldásához ellenőrizze, hogy a helyes felhasználónév jelenik-e meg az Excel-bővítmény a jobb felső sarkában. Ha helytelen felhasználónév jelenik meg, kattintson rá, jelentkezzen ki, majd jelentkezzen be újra.
- **A „Tiltott” üzenetet kapja.** – Ha a „Tiltott” üzenetet kapja, miközben az Excel-bővítmény a metaadatok betöltését végzi, a fiók, amelyik be van jelentkezve az Excel-bővítménybe, nem rendelkezik engedéllyel a megcélzott szolgáltatás, példány vagy adatbázis használatához. A probléma megoldásához ellenőrizze, hogy a helyes felhasználónév jelenik-e meg az Excel-bővítmény a jobb felső sarkában. Ha helytelen felhasználónév jelenik meg, kattintson rá, jelentkezzen ki, majd jelentkezzen be újra.
- **Egy üres weblap jelenik meg az Excel felett.** – Ha üres weblap jelenik meg a bejelentkezési folyamat során, a fiók AD FS-t igényel, de az Excel-programnak a bővítményt futtató verziója nem elég friss a bejelentkezési párbeszédpanel betöltéséhez. A probléma megoldásához frissítse a használt Excel-verziót. Ha a vállalata a késleltetett csatornán van, az Excel verziójának frissítéséhez használja az [Office telepítési eszközt](https://technet.microsoft.com/library/jj219422.aspx) [a késleltetett csatornáról az aktuális csatornára váltáshoz](https://technet.microsoft.com/library/mt455210.aspx).
