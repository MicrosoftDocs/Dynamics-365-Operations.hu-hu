---
title: "Termékéletciklus állapota"
description: "A termékéletciklus állapota egy kiadott termék vagy termékváltozat életciklus-állapotát dokumentálja."
author: cvocph
manager: AnnBe
ms.date: 12/08/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductLifecycleState, EcoResReleasedProductLifecycleStateChanges
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: cvocph
ms.dyn365.ops.version: 7.3
ms.search.validFrom: 2017-12-31
ms.translationtype: HT
ms.sourcegitcommit: 33130a4061f22335aeeffa69c478b693604393a9
ms.openlocfilehash: a57f306ba02c5758c39c4bd29d9a4fa0d7efbcd3
ms.contentlocale: hu-hu
ms.lasthandoff: 12/20/2017

---

# <a name="product-lifecycle-state"></a>Termékéletciklus állapota 

[!include[banner](../includes/banner.md)]


A termékéletciklus állapota egy kiadott termék vagy termékváltozat életciklus-állapotát dokumentálja. A termékéletciklus-állapotokat a felhasználó határozza meg, általában egy termékmenedzser vagy egy termékalapadat-menedzser. Adott üzleti folyamatokra, például a fő tervezésre, hatással lehet egy adott termékéletciklus-állapot.   
 
Egy kiadott termék vagy termékváltozat társítható egy termékéletciklus-állapottal, amely azt dokumentálja, hogy jelenleg milyen életciklus-állapotban van az adott termék vagy változat. Tetszőleges számú termékéletciklus-állapot adható meg egy állapotnév és egy leírás hozzárendelésével. Kiválasztható egy életciklus-állapot az újonnan kiadott termékek alapértelmezett állapotának. A kiadott termékváltozatok öröklik termékéletciklus-állapotukat a kiadott alapterméküktől a létrehozásakor. Egy kiadott alaptermék életciklus-állapotának módosításakor lehetőség van az összes olyan létező változat frissítésére, amelynek ugyanaz az eredeti állapota.  

## <a name="create-a-new-product-lifecycle-state"></a>Új termékéletciklus-állapot létrehozása 
 
- Új termékéletciklus-állapot létrehozásáhaz játssza le vagy olvassa el a következő feladat-útmutatót: **Új termékéletciklus-állapot létrehozása**. 

-  Alapértelmezett termékéletciklus-állapot létrehozásáhaz játssza le vagy olvassa el a következő feladat-útmutatót: **Alapértelmezett termékéletciklus-állapot létrehozása**.   

## <a name="associate-product-lifecycle-states-to-released-products"></a>Termékéletciklus-állapotok társítása kiadott termékekhez  

Többféleképpen lehet társítani egy termékéletciklus-állapotot kiadott termékekhez vagy termékváltozatokhoz.

-  Új kiadott termék létrehozáskor automatikusan történik meg az alapértelmezett **Termékéletciklus-állapot** hozzárendelése. 
-  Termék kiadásakor egy jogi személy számára automatikusan történik meg az alapértelmezett **Termékéletciklus-állapot** hozzárendelése. 
-  Termékváltozat kiadásakor egy jogi személy számára a jogi személynél a kiadott alaptermékhez társított **Termékéletciklus-állapot** automatikusan hozzá lesz rendelve az új változathoz. 

A termékéletciklus-állapot manuálisan frissíthető a következők használatával: 

-    A **Kiadott termékek** listaoldal vagy a **Részletek nézet**. 
-  A **Kiadott termékváltozatok** listaoldal vagy a **Részletek nézet**. 
-  Keresse meg az elavult termékeket vagy termékváltozatokat igény alapján, és társítson hozzájuk egy életciklus-állapotot.  

A termékéletciklus-állapotok társítására vonatkozó részletes tudnivalókért játssza le vagy olvassa el a következő feladat-útmutatót.

-  Egy termékéletciklus-állapot társításához egy kiadott alaptermékhez, játssza le vagy olvassa el a következő feladat-útmutatót: **Termékéletciklus-állapot társítása egy kiadott alaptermékhez**. 

-  Egy termékéletciklus-állapot társításához egy kiadott termékhez, játssza le vagy olvassa el a következő feladat-útmutatót: **Termékéletciklus-állapot társítása egy kiadott termékhez**. 

## <a name="impact-on-master-planning"></a>Hatás az alaptervezésre 

A termékéletciklus-állapotnak egyetlen vezérlőjelzője van: **Aktív a tervezéshez**. Alapértelmezés szerint a beállított értéke **Igen** az összes létrehozott termékéletciklus-állapotra, de meg is változtatható **Nem** értékre. Ha a beállítás **Nem**, a társított kiadott termékek és kiadott termékváltozatok: 

-  Ki vannak zárva az alaptervezésből. 
-  Ki vannak zárva az anyagjegyzékszint-számításból. 

Részletes információkért arról, hogyan lehet a termékéletciklus-állapotot termékek kizárására használni az alaptervezésből és az anyagjegyzékszint-számításból, játssza le vagy olvassa el a következő feladat-útmutatót: **Termékéletciklus-állapot létrehozása termékek kizárására az alaptervezésből**.

> [!NOTE]
> A megfelelő teljesítmény érdekében ajánlott társítani az összes elavult kiadott terméket vagy termékváltozatot, különösen, ha nem újrahasználható termékkonfigurációs változatokkal dolgozik, az alaptervezéshez inaktivált termékéletciklus-állapottal.  
 
## <a name="default-migration-import-and-export"></a>Alapértelmezett áttelepítés, importálás és exportálás 

Az adatentitások nem támogatják a termékéletciklus-állapotokat, és az életciklus-állapot nem állítható be változó állapotra a kiadott termék-adatentitásokon keresztül.

-  A korábbi verziókról való áttelepítés esetében az összes termék és a termékváltozat életciklus-állapota üres lesz.  
-  Kiadott termékek importálásakor egy adatentitáson keresztül, a rendszer az alapértelmezett életciklus-állapot fogja alkalmazni a létrehozáskor.  
-  Kiadott termékváltozatok importálásakor egy adatentitáson keresztül, a rendszer a kiadott alaptermék életciklus-állapotát fogja importálni.   
 
## <a name="find-obsolete-products-and-products-variants"></a>Elavult termékek és termékváltozatok keresése 
 
Lefuttatható egy elemzésszimuláció az elavult kiadott termékek vagy termékváltozatok felkutatására, és ezt követően frissíthető a termékéletciklus-állapotuk. Az elavult termékek felkutatásához játssza le vagy olvassa el a következő feladat-útmutatót: **Elavult termékváltozatok keresése és termékéletciklus-állapot hozzárendelése**. Ez a feladat-útmutató bemutatja, hogyan lehet megkeresni az elavult kiadott termékeket vagy termékváltozatokat, és hogyan lehet termékéletciklus-állapotot társítani az elavult termékekhez. Azt is bemutatja, hogyan lehet megtekinteni a szimulációs eredményeket, és kiértékeli, hogy hány termékhez és termékváltozathoz lesz új termékéletciklus-állapot társítva, ha a frissítést szimuláció nélkül futtatjuk.  
 
Az elemzés szimulációs üzemmódban való futtatásával az elavultként azonosított termékek és termékváltozatok egy erre a célra szolgáló képernyőn jelennek meg, ahol egyszerűen ellenőrizhetők. Az elemzés tranzakciókat és alapadatokat keres azzal a céllal, hogy azonosítsa azokat a termékeket, amelyek iránt nincs igény egy változtatható időperióduson belül, és nincs igényt eredményező alapadat. Az elemzésből ki lehet zárni a beállítható időn belül újonnan kiadott termékeket. Amikor az elemzésszimuláció visszaadja a várt eredményt, a felhasználó lefuttathatja az elemzést, és új termékéletciklus-állapotot állíthat be az összes, az elemzés által elavultként azonosított termékhez.  
 
> [!NOTE]
> Vegye figyelembe, hogy minden elemzést és frissítést ugyanazon a jogi személyen belül kell elvégezni.  
 
## <a name="criteria-to-select-and-update-released-products-or-product-variants"></a>Feltételek a kiadott termékek vagy termékváltozatok kiválasztásához és frissítéséhez 
 
Használja a következő feltételeket a kiadott termékek vagy termékváltozatok kiválasztásához és frissítéséhez: 

-    A termék vagy termékváltozat termékéletciklus-állapotának különböznie kell az új kívánt állapottól. 
-  A termék vagy termékváltozat létrehozása bizonyos számú napja történt, annak a napszámnak az alapján, amelyet a kiválasztási párbeszédpanelen írt be. 
-  Nincsenek nyitott termelési rendelések (= állapot < befejezett) a termékre vagy termékváltozatra nézve. 
-  Nincsenek nyitott készlettranzakciók (= állapotprobléma a ReservPhysical és QuotationIssue skálán, vagy állapotfogadás a Regisztrált és QuotationReceipt skálán) a termékre vagy a termékváltozatra. 
-  Az utóbbi napokban nincsenek készlettranzakciók a termékre vagy termékváltozatra. 
-  Nem áll fenn jövőbeli igény vagy ellátási előrejelzés a termékre vagy termékváltozatra.  
-  Nincs minimális készletszint beállítva a termékre vagy termékváltozatra a cikkfedezetben. 
-  Nincs aktív fix mennyiségi kanbanszabály a termékre vagy termékváltozatra.  
-  Nincs szervizrendeléssor a termékre vagy a termékváltozatra nézve. 
-  Nincs aktív vagy jövőbeli értékesítési vagy beszerzésiszerződés-sor a termékre vagy a termékváltozatra. 
-  A termék vagy a termékváltozat nincs használatban egy olyan anyagjegyzékben, amely társítva van egy le nem járt, jóváhagyott, tervezéshez aktív anyagjegyzék-verzióhoz a termékre vagy a termékváltozatra nézve.

## <a name="related-topics"></a>Kapcsolódó témakörök

-  Új termékéletciklus-állapot létrehozása
-  Alapértelmezett új termékéletciklus-állapot létrehozása
-  Termékéletciklus-állapot hozzárendelése egy kiadott alaptermékhez
-  Termékéletciklus-állapot hozzárendelése egy kiadott termékhez
-  Az elavult termékváltozatok megkeresése, és egy termékéletciklus-állapot hozzárendelése
-  Termékéletciklus-állapot létrehozása a termékek kizárásához az alaptervezésből

