--- 
title: "Lean manufacturing munkacellák meghatározása"
description: "A munkacella egy az erőforráscsoportok egy konkrét formája, amelyet lean manufacturing termelési folyamatokban lehet használni."
author: cvocph
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 1d2381c045f9f0f98b35912fa732f3627b038785
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="define-lean-manufacturing-work-cells"></a>Lean manufacturing munkacellák meghatározása

[!include[task guide banner](../../includes/task-guide-banner.md)]

A munkacella egy az erőforráscsoportok egy konkrét formája, amelyet lean manufacturing termelési folyamatokban lehet használni. A munkacelláknak vannak a bemeneti és kimeneti helyekeik és egy kapacitásdefiníciójuk, amely a termelési folyamatmodellen alapszik. További információkat a lean manufacturing munkacelláinak és kapacitásszámításainak alapkoncepcióiról a Lean manufacturing modellel foglalkozó tanulmányokban találhat. Ez az eljárás az USMF bemutatócéget használja.


## <a name="create-a-work-cell"></a>Hozzon létre egy munkacellát. 
1. Ugrás a Szervezet felügyelete > Erőforrások > Erőforráscsoportok részhez.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket az Erőforráscsoport mezőbe.
    * A munkacella azonosítója általában egy szisztematikus kódot a jogi személy számára egyedinek kell lennie.  
4. A Leírás mezőben adjon meg egy értéket.
    * A leírás tartalmazza a munkacella nevét vagy címét.  
5. A Hely mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
    * A munkacella egy adott telephelyen helyezkedik el. Bejövő és a kimeneti raktár és a hely is ezen a telephelyen kell legyenek.  
6. A listában kattintson a kijelölt sorban lévő hivatkozásra.
7. A Termelési egység mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
8. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * Válasszon ki egy termelési egységet, amelyhez ez a munkacella tartozik.  
9. Jelölje be a Munkacella jelölőnégyzetet.
    * Ha egy erőforráscsoportot lean munkacellaként akar használni, akkor a Minkacella jelölőnégyzetet be kell jelölni.  Vegye figyelembe, hogy ezt a tulajdonságot nem lehet módosítani az erőforrás-csoport létrehozása után.  
10. A Bemenő raktár mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
11. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * A számviteli és csomagolóanyag-ellenőrzés esetében az üzemben tárolt anyag általában egy konkrét virtuális raktárhoz van osztva. Azonban ha raktározási munkával szeretné feltölteni a helyeket, akkor a bevételező nyersanyagraktár részeinek kell lenniük.  
12. A Bemeneti hely mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
13. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * Vegye figyelembe, hogy egy folyamattevékenység esetében a bemeneti hely felülírható általánosságban vagy egy konkrét termékhez vagy termékváltozathoz olyan kitárolási tevékenységek definiálásával, amelyek a folyamattevékenységbe vezetnek. Egy munkacella bemeneti helyei nem lehetnek azonosítótáblás szabályozásúak.  
14. A Kimenő raktár mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
15. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Több tevékenység-termelésifolyamat vagy a -termelésisor esetében ez gyakran a következő munkacella bemenő raktára vagy az értékesítési vagy tranzit raktár, ahova a termékek rendszerint kerülnek a termelési folyamat után. Ne feledje, a lean manufacturing folyamatok modellezésénél a szállítás rendszerint pazarlás és a szállítás jelentése is.  
16. A listában kattintson a kijelölt sorban lévő hivatkozásra.
17. A Kimeneti hely mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
    * Egy termelési folyamatban, ahol több folyamattevékenység van ez gyakran a következő munkacella bemenő helye.  
18. Keresse meg és jelölje ki a kívánt rekordot a listán.
19. A listában kattintson a kijelölt sorban lévő hivatkozásra.
20. Bontsa ki vagy csukja össze a Művelet szakaszt.
    * Biztosítani kell egy futásidőkategóriát a lean kabanfeladatok költségszámításához és feldolgozásához.  
21. A Futásiidő-kategória mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
22. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * A futási idő költségkategória visszavezetéses költségelszámolás és a normál költségszámítás esetén is használatos.  
23. A listában kattintson a kijelölt sorban lévő hivatkozásra.
24. Bontsa ki vagy csukja össze a Naptárak szakaszt.
25. Kattintson a Hozzáadás gombra.
26. A Naptár mezőben kattintson a legördülő gombra a keresőlista megnyitásához.
27. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Általában egy telephely munkacellái ugyanazt a munkaidő naptárat használják. Ha a munkacellák rendelkezhetnek külön munkaidőkkel, akkor szükséges lehet egy munkaidőnaptárat létrehozni a munkacellának. Ne feledje, hogy a naptárhoz meg kell határozni egy normál munkaidőt, amikor lean munkacellához akarja használni, mert a kapacitásdefiníció rendszerint kapcsolatban áll egy munkanap normál munkaidejével.  
28. A listában kattintson a kijelölt sorban lévő hivatkozásra.
29. Bontsa ki vagy csukja össze a Munkacella-kapacitás adatok szakaszt.
30. Kattintson a Hozzáadás gombra.
31. A Termelési folyamatmodell mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
32. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Ezt az eljárás megköveteli a termelési folyamatmodell típusú teljesítményt, ahhoz hogy mutassa a teljesítménykapacitás definícióját.  
33. A listában kattintson a kijelölt sorban lévő hivatkozásra.
34. Válassza ki valamelyik lehetőséget az Kapacitásidőszak mezőben.
    * A lehetőségek a következők: Normál munkanap – A kapacitás a munkacella munkaidőnaptárában található normál munkanap hosszával van kifejezve. A egyes napok esetében a tényleges munkaidő a naptár alapján kerül meghatározásra, és a ténylegesen elérhető kapacitás ez alapján kerül kiszámításra.   Hét – Lehetővé teszi a heti kapacitásbontást. Az aktuális munkaidő nem módosít.   Hónap – Lehetővé teszi a havi kapacitásbontást. Az aktuális kapacitás nem módosít.   Általában a szokásos munkanap a napi időszakokhoz használatos, a heti kapacitása pedig a heti kapacitás időszakokhoz.  
35. Írjon be egy számot az Átlagos teljesítmény mezőbe.
    * Vegye figyelembe, hogy a lean művelet soha nem a lehetséges maximális kapacitásra van beállítva egy ideális környezetben. Ehelyett a kapacitást mindig tipikus körülmények között futó műveletekhez kell meghatározni.  
36. Az Egység mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
37. A listában kattintson a kijelölt sorban lévő hivatkozásra.
38. ResolveChanges az Egység.

## <a name="add-a-financial-dimension"></a>Pénzügyi dimenzió hozzáadása
1. Bontsa ki vagy csukja össze a Pénzügyi dimenziók szakaszt.
    * Vegye figyelembe, hogy a termelési folyamathoz definiált pénzügyi dimenziók felülbírálják egy adott munkacella pénzügyi dimenzióit.    A kiválasztható pénzügyi dimenziók a rendszer pénzügyi dimenzióitóinak konfigurációjától függnek. A következő lépések az USMF bemutatócég adatainak felelnek meg. Más adatok használata esetén előfordulhat, hogy a lépéseket nem alkalmazhatók.  
2. A CostCenter mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
3. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * A dimenziók, amelyeket ki kell választani lean típusú munkacellákhoz, a konkrét jogi személy könyvelési modelljének pénzügyi dimenzióitól függnek.  
4. A listában kattintson a kijelölt sorban lévő hivatkozásra.
5. Az ItemGroup mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
6. Keresse meg és jelölje ki a kívánt rekordot a listán.
7. A listában kattintson a kijelölt sorban lévő hivatkozásra.

## <a name="save"></a>Mentés
1. Kattintson a Mentés gombra.


