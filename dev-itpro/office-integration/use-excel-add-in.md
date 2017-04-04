---
title: "Az Excel-bővítmény használata"
description: "Ez a témakör bemutatja, hogyan entitás adatait a Microsoft Excel programban megnyitni és tekintse meg, frissítése és az Excel a Microsoft Dynamics Office beépülő modul segítségével szerkesztheti az adatokat. Nyissa meg az entitás adatait, elindíthatja az Excel vagy a Microsoft Dynamics 365 műveletekhez."
author: ChrisGarty
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 267914
ms.assetid: 4e6c7194-a059-4057-bd62-ec0c802c36fd
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: af7e7288f741b3c519227e2778c4c4311c3a2012
ms.openlocfilehash: 8af663b47117759ed3b2e2ed8eee85ae4df100d1
ms.lasthandoff: 03/31/2017


---

# <a name="use-the-excel-add-in"></a>Az Excel-bővítmény használata

Ez a témakör bemutatja, hogyan entitás adatait a Microsoft Excel programban megnyitni és tekintse meg, frissítése és az Excel a Microsoft Dynamics Office beépülő modul segítségével szerkesztheti az adatokat. Nyissa meg az entitás adatait, elindíthatja az Excel vagy a Microsoft Dynamics 365 műveletekhez.

Entitásadatai nyissa meg a Microsoft Excel programban, akkor gyorsan és egyszerűen megtekintheti és szerkesztheti az adatokat az Excel a Microsoft Dynamics Office beépülő modul segítségével. A bővítmény szükséges a Microsoft Excel 2016. **Megjegyzés:**, ha a Microsoft Azure Active Directory (Azure AD) bérlő az Active Directory összevonási szolgáltatások (AD FS) használatára van beállítva, meg kell győződnie arról, hogy a 2016. május frissítés telepítve van, úgy, hogy az Excel-bővítmény is helyesen bejelentkezik a rendszerbe.

## <a name="open-entity-data-in-excel-when-you-start-from-dynamics-365-for-operations"></a>Nyissa meg az Excel entitásadatai Dynamics 365 műveletekhez történő indításkor
1.  A Microsoft Dynamics 365 műveletek lapján kattintson a **nyissa meg a Microsoft Office**. Ha a gyökér adatforráshoz (tábla) az oldal megegyezik a jogalanyok számára a gyökér adatforrásnak, alapértelmezés szerint **az Excel programban megnyitott** beállítások lap jön létre. **Nyissa meg az Excel** beállítások megtalálhatók a gyakran használt lapok, például a **az összes szállító** és **vevőket**.
2.  Kattintson egy **a Microsoft Excelben** lehetőséget, és nyissa meg a munkafüzetet, amely jön létre. Ez a munkafüzet a kötelező érvényű felvilágosítás az entitás, egy mutatót a környezet és az Excel-bővítmény mutató rendelkezik.
3.  Az Excel programban, kattintson a **engedélyezzük a** ahhoz, hogy az Excel-bővítmény futtatásához. Az Excel beépülő modul fut egy ablak az Excel ablak jobb oldalán.
4.  Ha az Excel-bővítmény első alkalommal futtatja, kattintson a **a Hozzáadás a megbízható**.
5.  Ha a bejelentkezéshez kéri, kattintson a **be**, és majd bejelentkezni a Dynamics 365 műveletekhez használt hitelesítő adatok használatával jelentkezzen be. Az Excel-bővítmény használja az Internet Explorer korábbi bejelentkezési környezet, és automatikusan bejelentkezik a rendszerbe, ha talál ilyet. Ezért ellenőrizze a felhasználónév a jobb felső sarkában az Excel-bővítmény.

Az Excel-bővítmény automatikusan beolvassa az adatokat a kijelölt entitás. Ne felejtse, hogy ott nincsenek adatok a munkafüzet mindaddig, amíg nem olvassa be azt az Excel-bővítmény.

## <a name="open-entity-data-in-excel-when-you-start-from-excel"></a>Nyissa meg az Excel entitás adatait az Excel indításakor
1.  Az Excel programban a a **beszúrása** lapon, az a **-bővítmények** csoport, kattintson a **tár** lehet megnyitni az Office.
2.  Az Office üzlet "Dynamics" kulcsszó keresése, majd kattintson az **hozzáadása** mellett a **a Microsoft Dynamics Office-bővítmény** (az Excel-bővítmény).
3.  Ha az Excel-bővítmény első alkalommal futtatja, kattintson a **a Hozzáadás a megbízható** ahhoz, hogy az Excel-bővítmény futtatásához. Az Excel beépülő modul fut egy ablak az Excel ablak jobb oldalán.
4.  Kattintson a **server adatok felvétele** megnyitása a **beállítások** ablak.
5.  A böngésző URL másolása a célként megadott Dynamics 365 példány műveletek, illessze be a **kiszolgáló URL-címe** mezőben, és törölje az összes állomás neve után (például delete **/? cmp = usmf & mi = CustTableListPage**). Az eredményül kapott URL-címet kell az állomásnév (például **https://xxx.dynamics.com**).
6.  Kattintson a **OK**, és kattintson a **Igen** a módosítás megerősítését. Az Excel hozzáadása újraindul és a metaadatok. A **Tervező** gomb már elérhető. Ha az Excel-bővítmény van egy **kisalkalmazások betöltése** gomb, akkor valószínűleg nem rögzíti a megfelelő felhasználó. További információt "a terhelés kisalkalmazások gomb látható" Lásd a témakör "Hibaelhárítás" című szakaszában.
7.  Kattintson a **Tervező**. Az Excel-bővítmény átveszi az entitás metaadatainak.
8.  Kattintson a **a tábla hozzáadása**. Szervezetek listája jelenik meg. Az entitások "Neve – címke" formátumban jelennek meg.
9.  Egyed kiválasztása a listában például a **vevő - ügyfelek**, és kattintson a **tovább**.
10. Az új mező hozzáadásához az **mezők** a lista a **kijelölt mezők** listában, kattintson a mezőre, és kattintson a **hozzáadása**. Másik lehetőségként kattintson duplán a mezőre.
11. Miután hozzáadtuk a kívánt mezőket, hogy a **kijelölt mezők** listában, győződjön meg arról, hogy a kurzort a megfelelő helyen a munkalapon (például a A1 cella), és kattintson a **végzett**. Kattintson a **végzett**, lépjen ki a tervezőből.
12. Kattintson a **frissítési** Ha az adatok.

## <a name="view-and-update-entity-data-in-excel"></a>Megtekintheti és frissítheti az entitás adatait az Excel programban
Miután az Excel-bővítmény entitás adatokat olvas be a munkafüzetbe, frissítheti az adatokat bármikor kattintva **frissítési** az Excel-bővítmény.

## <a name="edit-entity-data-in-excel"></a>Az Excel programban entitás adatainak szerkesztése
Entitásadatai igényelnek, és tegye közzé újra kattintva módosíthatja **közzététel** az Excel-bővítmény. Bejegyzés módosítása a munkalapon jelöljünk ki egy cellát, és változtassuk meg a cella értékét. Új bejegyzés hozzáadásához hajtsa végre az alábbi műveletek valamelyikét:

-   Kattintson bárhová a munkalapon, majd a **új** az Excel-bővítmény.
-   Kattintson a munkalap utolsó sorában, és nyomja le a Tab billentyűt mindaddig, amíg a kurzor az utolsó sor-oszlopból, és az új sor jön létre.
-   Kattintsunk azon sor alatt közvetlenül a munkalapon, és indítsa el a adatokat ír egy cellába. Amikor a fókuszt ki, hogy a cella a munkalap kiegészíthetjük az új sort.

Rekord törléséhez hajtsa végre az alábbi műveletek valamelyikét:

-   Kattintson a jobb gombbal a törölni, és kattintson a munkalap sor mellett sor száma **törlése**.
-   A munkalap sor törléséhez kattintson a jobb gombbal, és kattintson a **törlése**&gt;**táblázat sorainak**.

## <a name="add-or-remove-columns"></a>Oszlopok hozzáadása vagy eltávolítása
A tervező segítségével módosítsa az oszlopokat, amelyek automatikusan hozzáadódnak a munkalapon.

1.  Adatok forrása tervezője az Excel-bővítmény indításához kattintson a **beállítások** gomb (a sebességváltó-jel), és válassza a **lehetővé teszi a tervező** jelölőnégyzetet.
2.  Kattintson a **Tervező** az Excel-bővítmény. Az adatforrások jelennek meg.
3.  Az adatforrás mellett kattintson a **szerkesztése** (a Ceruza jel) gombra.
4.  Állítsa be a lista a **kijelölt mezők** van szüksége, lista:
    -   Az új mező hozzáadásához az **mezők** a lista a **kijelölt mezők** listában, kattintson a mezőre, és kattintson a **hozzáadása**. Másik lehetőségként kattintson duplán a mezőre.
    -   Mező eltávolítása a **kijelölt mezők** listában, kattintson a mezőre, és kattintson a **távolítsa el**. Másik lehetőségként kattintson duplán a mezőre.
    -   A mezők sorrendjének módosításához kattintson a mező a **kijelölt mezők** listában, és kattintson a **fel** vagy **le**.

5.  Kattintva alkalmazza a módosításokat az adatforrás **frissítés**. Kattintson a **végzett**, lépjen ki a tervezőből. Ha hozzáadott mező (oszlop), kattintson a **frissítési**, húzd be egy frissített adatkészletet.

## <a name="httpspowerappsmicrosoftcomenustutorialsdataplatforminteractiveexceltroubleshootingtroubleshooting"></a>[](https://powerapps.microsoft.com/enus/tutorials/dataplatforminteractiveexcel/#troubleshooting)Troubleshooting
Vannak bizonyos problémák néhány egyszerű lépést feloldható.

-   **A terhelés kisalkalmazások gomb jelenik meg.** Ha az Excel-bővítmény van egy **kisalkalmazások betölteni** gomb után-bejelentkezés, akkor valószínűleg nem felhasználóként bejelentkezve a megfelelő. A probléma megoldásához ellenőrizze, hogy a helyes felhasználónév megjelenik a jobb felső sarkában az Excel-bővítmény. Ha egy helytelen felhasználónév jelenik meg, kattintson rá, kijelentkezés, és majd jelentkezzen be.
-   **A "Megtiltva" üzenetet kapja.** Ha az Excel-bővítmény metaadatok betöltése közben "Megtiltva" üzenetet kapja, a számlát, amelyre be van jelentkezve, az Excel-bővítmény nincs engedélye a megcélzott szolgáltatás, példány vagy adatbázis. A probléma megoldásához ellenőrizze, hogy a helyes felhasználónév megjelenik a jobb felső sarkában az Excel-bővítmény. Ha egy helytelen felhasználónév jelenik meg, kattintson rá, kijelentkezés, és majd jelentkezzen be.
-   **Egy üres weblap Excel felett jelenik meg.** Üres weblap jelenik meg a bejelentkezési folyamat során, ha a fiók Active Directory összevonási szolgáltatások szükséges, de az Excel a futó verziója nem elég friss betölteni a bejelentkezési párbeszédpanel. A probléma megoldásához frissítse az éppen használt Excel verziójának. Te vagy az a gazdálkodó, amely a halasztott csatorna Excel verziója frissítéséhez használja a [Office telepítési eszköz](https://technet.microsoft.com/library/jj219422.aspx), [a halasztott csatorna áthelyezése az aktuális csatorna](https://technet.microsoft.com/library/mt455210.aspx).



