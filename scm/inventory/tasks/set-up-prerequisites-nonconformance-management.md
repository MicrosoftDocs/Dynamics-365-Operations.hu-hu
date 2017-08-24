--- 
title: "Menedzsment feltételeinek beállítása"
description: "Engedélyezze a szabálytalanság kezelési folyamatokat ezen eljárások segítségével"
author: perlynne
manager: AnnBe
ms.date: 06/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bibis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: e8f7ec305316b5290019ec28deed1cae382e93b3
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-prerequisites-for-management"></a>Menedzsment feltételeinek beállítása

[!include[task guide banner](../../includes/task-guide-banner.md)]

Engedélyezze a szabálytalanság kezelési folyamatokat ezen eljárások segítségével A szabálytalanság ismerteti azt az elemet vagy eljárást, amely minőségi problémával rendelkezik, ahol a leíró jellegű információ a forrást és a probléma típusát tartalmazza. Ez az eljárás az USMF bemutatócéget használja. Ezt az eljárást általában a minőségbiztosítási vezető végzi el.


## <a name="enable-quality-management-processes-within-the-company"></a>Engedélyezze a Minőségkezelési folyamatokat a vállalaton belül
1. Ugrás a Készletkezelés > Beállítás > Készlet- és raktárkezelési paraméterek lehetőségre.
2. Kattintson a Minőségkezelés lapra.
3. Válassza az Igen lehetőséget a Minőségkezelés használata mezőben.
    * Válassza ki ezt a paramétert a vállalat minőségirányítási folyamatainak engedélyezéséhez.  
4. Adjon meg egy számot az Órabér mezőben.
    * Az Órabér mező segítségével adja meg az óradíjat a helyi pénznemben. A rendszer az óradíjjal számítja ki a szabálytalansággal kapcsolatos műveletek költségeit. Az óradíj és a számított költségek csak a szabálytalanságokra vonatkoznak, más funkciókat nem érintenek.  
5. Kattintson a Jelentés-beállítás elemre.
    * Ez az oldal lehetővé teszi a különféle minőségirányítási jelentésekhez használandó minőségi-jelentés megjegyzéstípusainak meghatározását.  
6. Zárja be a lapot.
7. Zárja be a lapot.

## <a name="enable-user-for-nonconformance-processing"></a>Engedélyezze a szabálytalanságok feldolgozására a felhasználót
1. Ugrás a Rendszerfelügyelet > Felhasználók > Felhasználók elemre.
    * A szabálytalanság jóváhagyásának feldolgozásához azon felhasználónak, aki jóváhagyja vagy elutasítja a szabálytalanságokat a Felhasználók lapon hozzárendelt „Név” értékkel kell rendelkeznie. A dokumentummegjegyzések használatához a felhasználónak rendelkeznie kell a Dokumentumkezeléssel, amelyet a felhasználói beállításokban kell aktiválni.  
2. Rekordok kereséséhez használja a gyorsszűrőt. Végezzen szűrést a Név mezőben például a „Ricardo” értékkel.
    * A szűrő használatával keresse meg azt a felhasználót, aki jóváhagyja vagy elutasítja a Szabálytalanságrekordokat.  
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * A szabálytalanság jóváhagyásának feldolgozásához győződjön meg arról, hogy a felhasználó, aki jóváhagyja vagy elutasítja a szabálytalanságokat rendelkezik a Felhasználók lapon hozzárendelt „Név” értékkel.  
4. Kattintson a Felhasználói beállítások lehetőségre.
5. Kattintson a Beállítások fülre.
6. Válassza az Igen lehetőséget a Dokumentumkezelés engedélyezése mezőben.
    * A dokumentummegjegyzések használatához a felhasználónak rendelkeznie kell a Dokumentumkezeléssel, amelyet a felhasználói beállításokban kell aktiválni.  
7. Zárja be a lapot.
8. Zárja be a lapot.
9. Zárja be a lapot.

## <a name="define-diagnostic-types-for-nonconformance-processing"></a>Határozza meg a diagnosztikai típusokat a szabálytalanság feldolgozásához
1. Ugorjon a Készletgazdálkodás > Beállítás > Minőségkezelés > Diagnosztikai típusok pontra.
    * A Diagnosztikai típusok oldalon határozhatja meg a diagnosztikai műveletek osztályozását. A javítás meghatározza, hogy milyen típusú diagnosztikai műveletet kell végrehajtani a jóváhagyott szabálytalanságon, valamint hogy kinek kell elvégeznie, melyik napra kérték és mikorra tervezik a végrehajtást.  
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Diagnosztika mezőbe.
4. A Leírás mezőben adjon meg egy értéket.
5. Zárja be a lapot.

## <a name="define-quality-charges-for-nonconformance-processing"></a>Határozza meg a minőségbiztosítási költségeket a szabálytalanság feldolgozásához
1. Ugorjon a Készletkezelés > Beállítás > Minőségkezelés > Minőségbiztosítási költségek pontra.
    * A Minőségbiztosítási költségek lap használatával osztályozza azokat a költségeket, amelyeket a szabálytalanságokhoz kapcsolódó műveletekben használ.  
2. Kattintson az Új lehetőségre.
3. Érték beírása a Költségek mezőbe.
4. A Leírás mezőben adjon meg egy értéket.
5. Zárja be a lapot.

## <a name="define-the-operations-for-nonconformance-processing"></a>Határozza meg a műveleteket a szabálytalanság feldolgozásához
1. Ugorjon a Készletgazdálkodás > Beállítás > Minőségkezelés > Műveletek pontra.
    * A Műveletek lap használatával osztályozza a munkát, amelyet a jóváhagyott szabálytalanságokra vonatkozóan végezhet el. Amikor a szabálytalansághoz egy műveletet rendel, információkat adhat meg a kapcsolódó anyagról, a munkaidőről és a vegyes költségekről, amelyek a művelet végrehajtásához szükségesek. Ezek az adatok képezik az alapot a művelet becsült végrehajtási költségének kiszámításához.  
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Műveletek mezőbe.
4. A Leírás mezőben adjon meg egy értéket.
5. Zárja be a lapot.

## <a name="define-problem-types-for-nonconformance-processing"></a>Határozza meg a problématípusát a szabálytalanság feldolgozásához
1. Ugorjon a Készletgazdálkodás > Beállítás > Minőségkezelés > Problématípusok pontra.
    * A Problématípusok oldalon határozhatja meg a különböző szabálytalanságtípusok esetében felmerülő minőségproblémák osztályozását. A szabálytalanság típusai a következők lehetnek: Belső, Vevő, Szolgáltatáskérés, Termelés, és Társtermék gyártás. Egy problématípust több Szabálytalanságtípushoz lehet társítani.  
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Problématípus mezőbe
4. A Leírás mezőben adjon meg egy értéket.
5. Kattintson a Szabálytalanságtípusok lehetőségre.
    * A Szabálytalanságtípusok oldal használatával engedélyezze a problématípus használatát egy vagy több szabálytalanságtípusra vonatkozóan. Például egy hibás kódot érintő problématípus minden szabálytalanságtípusra alkalmazható, míg egy vevői panasz csak a vevői és szervizigénylési szabálytalanságtípusokra.  
6. Kattintson az Új lehetőségre.
7. A listában jelölje meg a kiválasztott sort.
8. Válasszon ki egy lehetőséget Szabálytalanságtípus mezőben.
9. Zárja be a lapot.
10. Zárja be a lapot.

## <a name="define-quarantine-zones-for-nonconformance-processing"></a>Határozza meg a Karanténzónákat a szabálytalanság feldolgozásához
1. Ugorjon a Készletkezelés > Beállítás > Minőségkezelés > Karanténzónák pontra.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Karanténzónák mezőbe.
4. A Leírás mezőben adjon meg egy értéket.
5. Zárja be a lapot.


