---
title: Helyek konfigurálása WMS szolgáltatással rendelkező raktárban
description: Ez az útmutató bemutatja, hogyan konfigurálhatja az új WMS-kompatibilis raktár (a speciális raktárkezelési folyamatokat alkalmazó raktár) helyének beállításait.
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventLocation, WHSLocationFormat, WHSLocationType, WHSLocationProfile, WHSParameters, WHSZoneGroup, WHSZone, WHSLocationBuild, WHSLocation, WHSPackSizeCategory, WHSLocationLimit, WHSInventFixedLocation, WMSLocationIdLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2be3c7cb33225041872e8b747ba28063f897dae9
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "337325"
---
# <a name="configure-locations-in-a-wms-enabled-warehouse"></a>Helyek konfigurálása WMS szolgáltatással rendelkező raktárban

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az útmutató bemutatja, hogyan konfigurálhatja az új WMS-kompatibilis raktár (a speciális raktárkezelési folyamatokat alkalmazó raktár) helyének beállításait. A folyamatot általában a raktár vezetője végzi el. Ezt az útmutatót az USMF bemutatócéggel vagy saját adataival is futtathatja. Előfeltétel, hogy legalább egy webhely legyen beállítva.


## <a name="create-a-new-warehouse"></a>Új raktár létrehozása
1. Ugrás a Raktárakhoz.
2. Kattintson az Új lehetőségre.
3. Érték beírása a Raktár mezőbe.
4. Írjon be egy értéket a Név mezőbe.
5. Érték beírása a Telephely mezőbe.
6. Bontsa ki vagy zárja be a Raktár szakaszt.
7. Állítsa A raktárkezelési folyamatok felhasználói hibanaplója opcióját erre: Igen.
    * Ezzel a beállítással raktározási folyamatokat futtathat raktármunkákkal és mobileszközökkel.  
8. Zárja be a lapot.

## <a name="define-a-location-format"></a>Helyformátum meghatározása
1. UGrás a Helyformátumokhoz.
    * A helyformátumok elnevezési rendszerével egyedi és egységes neveket hozhat létre a raktáron belül különböző helyeken tárolt rekeszekre vonatkozóan. Ez hasznos lehet az elválasztók használatához a helyformátum részeként, így könnyebben azonosíthatók lesznek a hely elemei, például a folyosószámok. Ebben a példában négy összetevővel fogunk neveket létrehozni. Például ezek lehetnek: folyosó, állvány, polc és rekesz.  
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Helyformátum mezőbe.
4. Írjon be egy értéket a Név mezőbe.
5. A Szegmens leírása mezőbe írjon egy értéket.
    * Ez azt mutatja be, hogy a helynév első része mit jelenít meg. Ez lehet például a folyosó.  
6. Adjon meg egy számot a Hosszúság mezőben.
    * Ez határozza meg, hogy a hely nevének ennek a részének hány karakterrel kell rendelkeznie. Vegye figyelembe, hogy az név összes eleme, beleértve az elválasztókat is, nem haladhatja meg a 10 karaktert.  
7. Érték beírása az Elválasztó mezőbe.
    * Ez határozza meg, hogy a név első és második része között melyik karaktert vagy szimbólumot használjuk.  
8. Kattintson az Új lehetőségre.
9. A Szegmens leírása mezőbe írjon egy értéket.
10. Adjon meg egy számot a Hosszúság mezőben.
11. Érték beírása az Elválasztó mezőbe.
12. Kattintson az Új elemre.
13. A Szegmens leírása mezőbe írjon egy értéket.
14. Adjon meg egy számot a Hosszúság mezőben.
15. Érték beírása az Elválasztó mezőbe.
16. Kattintson az Új elemre.
17. A Szegmens leírása mezőbe írjon egy értéket.
18. Adjon meg egy számot a Hosszúság mezőben.
19. Kattintson a Mentés gombra.
20. Zárja be a lapot.

## <a name="define-location-types"></a>Helytípusok definiálása
1. Ugrás a Helytípusokhoz.
    * A szűrési beállításokként használt helytípusokkal szabályozhatja a különböző raktárkezelési folyamatokat is. Legalább egy előkészítési és egy végső szállítási helytípust kell létrehoznia annak érdekében, hogy a kimenő raktárkezelési folyamatot meghatározza.  
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Helytípus mezőbe.
4. A Leírás mezőben adjon meg egy értéket.
5. Zárja be a lapot.

## <a name="define-location-profile"></a>Helyprofil definiálása
1. Ugorjon a Helyprofilok elemhez.
    * A helyprofilok meghatározása nagyon fontos. A csoportosított helyek kapacitását itt határozhatja meg, illetve azt is, hogy a tárolt készletre és a tárolási módra milyen irányelvek vonatkozzanak. A szűrési beállításokként használt helyprofilokkal szabályozhatja a különböző raktárkezelési folyamatokat is. Legalább egy felhasználói helyprofilt létre kell hoznia ahhoz, hogy a raktárkezelési folyamatokat engedélyezze.  
2. Kattintson az Új lehetőségre.
3. Írjon egy értéket a Helyprofil azonosítója mezőbe.
4. Írjon be egy értéket a Név mezőbe.
5. A Helyazonosító mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
6. A kívánt rekord megkeresése és kijelölése a listán
7. A listában kattintson a kijelölt sorban lévő hivatkozásra.
8. A Helyazonosító mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
9. Keresse meg és jelölje ki a kívánt rekordot a listán.
10. A listában kattintson a kijelölt sorban lévő hivatkozásra.
11. Jelölje be vagy törölje a Vegyes készletállapotok engedélyezése jelölőnégyzetet.
    * Kapcsolja be ezt a beállítást, ha szeretné engedélyezni a kevert készlet állapotának értékeit a helyprofil alapján csoportosított helyekben.  
12. Jelölje be vagy törölje a Kötegelési időszak szabályainak felülbírálása jelölőnégyzetet.
    * Ezt a lehetőséget akkor kapcsolja be, ha felül szeretné bírálni az arra vonatkozó szabályt, hogy hány napig különbözhetnek a készletkötegek lejárati dátumai annak érdekében, hogy a szabálynak nem engedelmeskedő készletkötegeket vegyíthesse a rendszer.  
13. Jelölje be a Ciklikus leltározás engedélyezése jelölőnégyzetet.
    * Kapcsolja be ezt a beállítást, ha szeretné engedélyezni a ciklikus leltározási feldolgozást a helyprofil alapján csoportosított helyekben.  
14. Bontsa ki vagy zárja be a Dimenziók szakaszt.
    * A Dimenziók lapon határozza meg a paramétereket és módszereket a terhelési kapacitáson belüli pontos számítási módszerek lehetővé tételéhez.  
15. Zárja be a lapot.

## <a name="enable-warehouse-management-parameters"></a>Raktárkezelési paraméterek engedélyezése
1. Ugorjon a Raktárkezelési paraméterek megtekintése részhez.
    * A raktármunka feldolgozása érdekében szükség lesz a felhasználói helyprofil, az előkészítési helytípus és a végső szállítási helytípus paramétereinek a beállítására Miután a kifelé mutató folyamat befejeződik az adott végső szállítási helytípusnál, a kapcsolódó kifelé mutató tranzakciókat a rendszer „Kitárolva” értékűre frissíti.  
2. Bontsa ki vagy zárja be a Helyprofilok szakaszt.
3. A Felhasználói hely mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
4. A listában kattintson a kijelölt sorban lévő hivatkozásra.
5. Bontsa ki vagy zárja be a Helytípusok szakaszt.
6. Az Előkészítő hely típusa mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
7. A listában kattintson a kijelölt sorban lévő hivatkozásra.
8. A Végleges kiszállítási hely típusa mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
9. A listában kattintson a kijelölt sorban lévő hivatkozásra.
10. Zárja be a lapot.

## <a name="define-warehouse-zone-groups"></a>Raktár zónacsoportjainak definiálása
1. Ugorjon a Raktár zónacsoportjai szakaszhoz.
    * A szűrési beállításokként használt raktárzónákkal szabályozhatja a különböző raktárkezelési folyamatokat is. Zónacsoportot kell létrehoznia a zóna definiálása előtt.  
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Zónacsoport azonosítója mezőbe.
4. Írjon be egy értéket a Zónacsoport neve mezőbe.
5. Zárja be a lapot.

## <a name="define-warehouse-zones"></a>Raktári zónák definiálása
1. Ugorjon a Zónák részre.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Zónaazonosító mezőbe.
4. Írjon be egy értéket a Zóna neve mezőbe.
5. A Zónacsoport azonosítója mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
6. A kívánt rekord megkeresése és kijelölése a listán
7. A listában kattintson a kijelölt sorban lévő hivatkozásra.
8. Zárja be a lapot.

## <a name="create-locations-using-the-location-setup-wizard"></a>A hely beállítása varázsló segítségével helyek létrehozása
1. Ugorjon a Hely beállítása varázslóhoz.
2. A Raktár mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
3. A kívánt rekord megkeresése és kijelölése a listán
4. A listában kattintson a kijelölt sorban lévő hivatkozásra.
5. A Zóna azonosítója mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
6. A kívánt rekord megkeresése és kijelölése a listán
7. A listában kattintson a kijelölt sorban lévő hivatkozásra.
8. A Helyprofil-azonosító mezőben kattintson a legördülő gombra a keresőlista megnyitásához.
9. A kívánt rekord megkeresése és kijelölése a listán
10. A listában kattintson a kijelölt sorban lévő hivatkozásra.
11. A listában jelölje meg a kiválasztott sort.
12. Írjon be egy számot a Kezdő szám mezőbe.
    * A Kezdő szám és a Befejező szám mezők határozzák meg, hogy hány hely fog létrejönni. Például ha a Kezdő száma 1 és a Befejező szám 3 a helyformátum mind a négy sorában, 81 hely jön létre (3 x 3 x 3 x 3).  
13. Írjon be egy számot a Befejező szám mezőbe.
14. Keresse meg és jelölje ki a kívánt rekordot a listán.
15. Írjon be egy számot a Kezdő szám mezőbe.
16. Írjon be egy számot a Befejező szám mezőbe.
17. A kívánt rekord megkeresése és kijelölése a listán
18. Írjon be egy számot a Kezdő szám mezőbe.
19. Írjon be egy számot a Befejező szám mezőbe.
20. A kívánt rekord megkeresése és kijelölése a listán
21. Írjon be egy számot a Kezdő szám mezőbe.
22. Írjon be egy számot a Befejező szám mezőbe.
23. Kattintson a Létrehozás lehetőségre.

## <a name="create-locations-manually"></a>Helyek létrehozása manuálisan
1. Ugorjon a Helyekre.
    * A raktáron belüli hely létrehozása manuálisan könnyen végrehajtható. A hely nevét és a hely profilazonosítóját kötelező megadni.  
2. Kattintson az Új lehetőségre.
3. Érték beírása a Raktár mezőbe.
4. Írjon be egy értéket a Hely mezőbe.
    * Vegye figyelembe, hogy mivel létrehozás egy új helyet, az új egyedi nevet be kell írnia egy meglévő kijelölése helyett.  
5. Írjon egy értéket a Helyprofil azonosítója mezőbe.
6. Zárja be a lapot.

## <a name="define-pack-size-categories"></a>Csomagméret-kategóriák definiálása
1. Ugorjon a Csomagméret-kategóriák megtekintéséhez.
    * A csomagméret-kategóriák használatával csoportosíthatja a hasonló fizikai mérettel rendelkező csoportcikkeket. Ebben a példában a csomag méretkategóriáját a kapacitás vezérléséhez használjuk majd a kitárolási helyen a raktár egy adott zónájában. Kérjük, vegye figyelembe, hogy a csomag méretkategória-azonosítóját hozzá kell rendelni egy kiadott termékentitáshoz annak érdekében, hogy a raktározási korlátok feldolgozásában az használható legyen.  
2. Kattintson az Új lehetőségre.
3. Adjon meg egy értéket a Csomagméret-kategóriaazonosító mezőben.
4. Adjon meg egy értéket a Csomagméret-kategórianév mezőben.
5. Zárja be a lapot.

## <a name="define-location-stocking-limits"></a>Hely rakodási korlátainak beállítása
1. Ugorjon a Hely rakodási korlátaihoz.
    * A helyraktározási korlátok segítségével győződjön meg arról, hogy a munka nem azért jön létre, hogy a készletet olyan helyre kérje, amelynek nincs meg a megfelelő fizikai kapacitása a készlet tárolásához.  
2. Kattintson az Új lehetőségre.
3. Érték beírása a Raktár mezőbe.
4. Írjon egy értéket a Helyprofil azonosítója mezőbe.
5. Adjon meg egy értéket a Csomagméret-kategóriaazonosító mezőben.
6. Adjon meg egy számot a Mennyiség mezőben.
7. Kattintson a Mentés gombra.
8. Zárja be a lapot.

## <a name="define-fixed-picking-locations"></a>Fix kivételi helyek definiálása
1. Ugorjon a Rögzített helyekhez.
    * A használni kívánt helyeket termékenként és termékváltozatonként határozhatja meg. Több rögzített helyet is létrehozhat ugyanahhoz a termékhez, ugyanabban a raktárban.  
2. Kattintson az Új lehetőségre.
3. A cikkmezőbe írjon egy értéket.
4. Érték beírása a Raktár mezőbe.
5. A Hely mezőben kattintson a legördülő gombra a keresőlista megnyitásához.
6. A listában kattintson a kijelölt sorban lévő hivatkozásra.
7. Zárja be a lapot.

