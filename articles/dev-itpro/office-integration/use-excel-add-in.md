---
title: "Az Excel-bővítmény használata"
description: "Ez a témakör bemutatja, hogyan lehet megnyitni az entitásadatokat a Microsoft Excel programban, és hogyan lehet megtekinteni, frissíteni és szerkeszteni az adatokat az Excel Microsoft Dynamics Office beépülő moduljának segítségével."
author: ChrisGarty
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 267914
ms.assetid: 4e6c7194-a059-4057-bd62-ec0c802c36fd
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 06fc9f8dda83fddea9ae331bb82c8874b15d76b9
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="use-the-excel-add-in"></a>Az Excel-bővítmény használata

[!include[banner](../includes/banner.md)]


Ez a témakör bemutatja, hogyan lehet megnyitni az entitásadatokat a Microsoft Excel programban, és hogyan lehet megtekinteni, frissíteni és szerkeszteni az adatokat az Excel Microsoft Dynamics Office beépülő moduljának segítségével. Az entitásadatok megnyitását elindíthatja az Excel vagy a Microsoft Dynamics 365 for Finance and Operations Enterprise edition programból.

Az entitásadatok megnyitásával a Microsoft Excel programban gyorsan és egyszerűen tekintheti meg és szerkesztheti az adatokat az Excel Microsoft Dynamics Office beépülő moduljának segítségével. A bővítmény használatához Microsoft Excel 2016 szükséges. **Megjegyzés:** Ha a Microsoft Azure Active Directory (Azure AD) bérlője az Active Directory összevonási szolgáltatások (AD FS) használatára van beállítva, meg kell győződnie arról, hogy a 2016. május frissítés telepítve van, hogy az Excel-bővítmény helyesen jelentkeztesse be.

## <a name="open-entity-data-in-excel-when-you-start-from-dynamics-365-for-finance-and-operations"></a>Nyissa meg az entitásadatokat az Excel programban a Dynamics 365 for Finance and Operations indításakor
1.  A Microsoft Dynamics 365 for Finance and Operations egyik lapján kattintson a **Megnyitás a Microsoft Office programban** lehetőségre. Ha az oldal gyökér adatforrása (tábla) megegyezik bármelyik entitás gyökér adatforrásával, létrejönnek a lap alapértelmezett **Megnyitás az Excel programban** beállításai. A **Megnyitás az Excel programban** lehetőségek megtalálhatók a gyakran használt lapokon, például az **Összes szállító** és **Összes vevő** oldalon.
2.  Kattintson az egyik **Megnyitás az Excel programban** lehetőségre, és nyissa meg a létrejövő munkafüzetet. Ez a munkafüzet kötési információkat tartalmaz az entitásra, egy mutatót a környezetre és egy mutatót az Excel-bővítményre.
3.  Az Excel programban kattintson a **Szerkesztés engedélyezése** lehetőségre az Excel-bővítmény futtatásának engedélyezéséhez. Az Excel-bővítmény egy panelen fut az Excel ablak jobb oldalán.
4.  Ha az Excel beépülő modult első alkalommal futtatja, kattintson az **Ez a bővítmény megbízható** lehetőségre.
5.  Ha a rendszer bejelentkezést kér, kattintson a **Bejelentkezés** lehetőségre, majd a Dynamics 365 for Finance and Operations bejelentkezéshez használt hitelesítő adatok használatával jelentkezzen be. Az Excel beépülő modul az Internet Explorer korábbi bejelentkezési kontextusát használva automatikusan bejelentkezik a rendszerbe, ha talál ilyet. Ezért ellenőrizze a felhasználónevet az Excel-bővítmény jobb felső sarkában.

Az Excel-bővítmény automatikusan beolvassa a kijelölt entitás adatait. Ne felejtse, hogy nincsenek adatok a munkafüzetben mindaddig, amíg be nem olvassa őket az Excel-bővítmény.

## <a name="open-entity-data-in-excel-when-you-start-from-excel"></a>Az entitás adatainak megnyitása az Excelben az Excel indításakor
1.  Az Excel programban a **Beszúrás** lapon, a **Bővítmények** csoportban, kattintson az **Áruház** lehetőségre az Office Áruház megnyitásához.
2.  Az Office Áruházban keressen a „Dynamics” kulcsszóra, majd kattintson a **Hozzáadás** lehetőségre a **Microsoft Dynamics Office-bővítmény** (az Excel-bővítmény) mellett.
3.  Ha az Excel beépülő modult első alkalommal futtatja, kattintson az **Ez a bővítmény megbízható** lehetőségre az Excel-bővítmény futásának engedélyezéséhez. Az Excel-bővítmény egy panelen fut az Excel ablak jobb oldalán.
4.  Kattintson a **Kiszolgáló adatainak hozzáadása** a **Beállítások** ablak megnyitásához.
5.  A böngésző URL-címét másolja ki a célként megadott Dynamics 365 for Finance and Operations példányból, illessze be a **Kiszolgáló URL-címe** mezőben, és töröljön mindent az állomás neve után. Az eredményül kapott URL-címet az állomásnevet kell rendelkeznie.
Ha például az URL-cím https://xxx.dynamics.com/?cmp=usmf&amp;mi=CustTableListPage, töröljön mindent a **https://xxx.dynamics.com**-on kívül.
6.  A módosítások megerősítéséhez kattintson az **OK**, majd az **Igen** elemre. Az Excel-bővítmény újraindul és betölti a metaadatokat. Most már elérhető a **Terv** menügomb. Ha az Excel-bővítmény rendelkezik egy **Kisalkalmazások betöltése** gombbal, akkor valószínűleg nem a megfelelő felhasználóként jelentkezett be. További információért lásd a „Látszik a Kisalkalmazások betöltése gomb” részt a témakör „Hibaelhárítás” című szakaszában.
7.  Kattintson a **Terv** pontra. Az Excel-bővítmény lekéri az entitás metaadatait.
8.  Kattintson a **Tábla hozzáadása** lehetőségre. Megjelenik az entitások listája. Az entitások „Név – címke” formátumban jelennek meg.
9.  Válasszon ki a listában egy entitást, például **Vevő - Vevők**, és kattintson a **Tovább** elemre.
10. Mező hozzáadásához a **Választható mezők** listáról a **Kijelölt mezők** listához, kattintson a mezőre, és kattintson a **Hozzáadás** elemre. Másik lehetőségként kattintson duplán a mezőre.
11. Miután befejezte a kívánt mezők hozzáadását a **Kijelölt mezők** listához, győződjön meg arról, hogy a kurzor a megfelelő helyen van a munkalapon (például az A1 cellán), és kattintson a **Kész** elemre. Kattintson a **Kész** elemre, és lépjen ki a tervezőből.
12. Kattintson a **Frissítés** elemre egy adatkészlet behúzásához.

## <a name="view-and-update-entity-data-in-excel"></a>Az entitásadatok megtekintése és frissítése az Excel programban
Miután az Excel-bővítmény beolvasta az entitásadatokat a munkafüzetbe, bármikor frissítheti az adatokat a **Frissítés** lehetőségre kattintva az Excel-bővítményben.

## <a name="edit-entity-data-in-excel"></a>Az Excel programban az entitás adatainak szerkesztése
Az entitásadatokat igény szerint módosíthatja, és aztán újra közzéteheti őket a **Közzététel** elemre kattintva az Excel-bővítményben. Egy rekord módosításához a munkalapon jelöljön ki egy cellát, és változtassa meg a cella értékét. Új rekord hozzáadásához hajtsa végre az alábbi lépések valamelyikét:

-   Kattintson bárhová az adatforrások táblázatában, majd az **Új** lehetőségre az Excel-bővítményben.
-   Kattintson az adatforrások táblázatának utolsó sorába, és nyomja le a Tab billentyűt mindaddig, amíg a kurzor ki nem lép a sor utolsó oszlopából, és új sor nem jön létre.
-   Kattintson a sorra közvetlenül az adatforrások táblázata alatt, és kezdjen el adatokat beírni egy cellába. Amikor a fókuszt kimozgatja a cellából, a táblázat kiegészül az új sorral.
-   A fejlécrekordok mezőkötéseihez kattintson az egyik mezőre, majd az Excel-bővítményben kattintson az **Új** lehetőségre.

Ne feledje, hogy csak akkor hozható létre új rekord, ha mind a kulcs, mind a kötelező mezők kötve vannak a munkafüzetben, illetve ha az alapértelmezett értékeket megadták a szűrőfeltétel használatával.
Rekord törléséhez hajtsa végre az alábbi lépések valamelyikét:

-   Kattintson a jobb gombbal a törölni kívánt munkalapsor melletti sorszámra, és kattintson a **Törlés** gombra.
-   Kattintson a jobb gombbal a törölni kívánt munkalapsorra, és kattintson a **Törlés** &gt; **Táblasorok** gombra.
Ha az adatforrásokat kapcsolódóként adták meg, akkor a fejléc a sorok elé kerül. Ha más adatforrások között függőségek vannak, előfordulhat, hogy módosítania kell az alapértelmezett közzétételi sorrendet. A közzétételi sorrend Excel-bővítményben való módosításához kattintson a **Beállítások** gombra (a fogaskerék jelre). Ezt követően az **Adatcsatlakozó** gyorslapon kattintson a **Közzétételi sorrend konfigurálása** lehetőségre.

## <a name="add-or-remove-columns"></a>Oszlopok hozzáadása vagy eltávolítása
A tervező segítségével igazíthatja az oszlopokat, amelyek automatikusan adódnak hozzá a munkalaphoz.

1.  Indítsa el az Excel-bővítmény adatforrás-tervezőjét a **Beállítások** gombra kattintva (fogaskerék szimbólum), és jelölje be a **Tervezés engedélyezése** jelölőnégyzetet.
2.  Kattintson a **Tervező** lehetőségre az Excel-bővítményben. Az összes adatforrás kilistázódik.
3.  Az adatforrás mellett kattintson a **Szerkesztés** gombra (ceruza jel).
4.  Állítsa be a listát a **Kijelölt mezők** listában, ha szükséges:
    -   Mező hozzáadásához a **Választható mezők** listáról a **Kijelölt mezők** listához, kattintson a mezőre, és kattintson a **Hozzáadás** elemre. Másik lehetőségként kattintson duplán a mezőre.
    -   Ha el szeretne távolítani egy mezőt a **Kijelölt mezők** listából, kattintson a mezőre, majd az **Eltávolítás** parancsra. Másik lehetőségként kattintson duplán a mezőre.
    -   A mezők sorrendjének módosításához kattintson a mezőre a **Kijelölt mezők** listában, kattintson egy mezőre, és kattintson a **Fel** vagy **Le** lehetőségre.

5. A **Frissítés** lehetőségre kattintva alkalmazhatja a módosításokat az adatforrásra. Kattintson a **Kész** elemre, és lépjen ki a tervezőből. 
6. Ha hozzáadott egy mezőt (oszlop), kattintson a **Frissítés** lehetőségre egy frissített adatkészlet behúzásához.

## <a name="troubleshooting"></a>Hibaelhárítás
Vannak bizonyos problémák, amelyek néhány egyszerű lépéssel megoldhatók.

-   **Látszik a Kisalkalmazások betöltése gomb.** Ha az Excel-bővítmény rendelkezik egy **Kisalkalmazások betöltése** gombbal a bejelentkezés után, akkor valószínűleg nem a megfelelő felhasználóként jelentkezett be. A probléma megoldásához ellenőrizze, hogy a helyes felhasználónév jelenik-e meg az Excel-bővítmény a jobb felső sarkában. Ha helytelen felhasználónév jelenik meg, kattintson rá, jelentkezzen ki, majd jelentkezzen be újra.
-   **A „Tiltott” üzenetet kapja.** Ha a „Tiltott” üzenetet kapja, miközben az Excel-bővítmény a metaadatok betöltését végzi, a fiók, amelyik be van jelentkezve az Excel-bővítménybe, nem rendelkezik engedéllyel a megcélzott szolgáltatás, példány vagy adatbázis használatához. A probléma megoldásához ellenőrizze, hogy a helyes felhasználónév jelenik-e meg az Excel-bővítmény a jobb felső sarkában. Ha helytelen felhasználónév jelenik meg, kattintson rá, jelentkezzen ki, majd jelentkezzen be újra.
-   **Egy üres weblap jelenik meg az Excel felett.** Ha üres weblap jelenik meg a bejelentkezési folyamat során, a fiók AD FS-t igényel, de az Excel-programnak a bővítményt futtató verziója nem elég friss a bejelentkezési párbeszédpanel betöltéséhez. A probléma megoldásához frissítse a használt Excel-verziót. Ha a vállalata a késleltetett csatornán van, az Excel verziójának frissítéséhez használja az [Office telepítési eszközt](https://technet.microsoft.com/library/jj219422.aspx) [a késleltetett csatornáról az aktuális csatornára váltáshoz](https://technet.microsoft.com/library/mt455210.aspx).





