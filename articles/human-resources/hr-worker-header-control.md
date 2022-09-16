---
title: Dolgozói fejléc ellenőrzése
description: Ez a cikk a Microsoft Dolgozó lapján található, az Alkalmazotti önkiszolgáló, a Személyek központ és a Dolgozó lapon személyre szabható fejlécvezérlővel kapcsolatban tartalmaz tájékoztatást Dynamics 365 Human Resources.
author: twheeloc
ms.date: 09/06/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2867a952df79161aaee657dbc3df1f3298294dd5
ms.sourcegitcommit: 167f73a834629752c6b79c312d744e52df7f0927
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/08/2022
ms.locfileid: "9445988"
---
# <a name="worker-header-control"></a>Dolgozói fejléc ellenőrzése

A Microsoft Dynamics 365 Human Resources személyre szabható fejlécellenőrzést biztosít **az** Alkalmazotti önkiszolgáló áruházban, **a Személyek** központban és a dolgozó rendszer rendszerezhető **lapján**. A fejléc fontos adatokat tartalmaz a dolgozóról, és egy kattintásra műveleteket is tartalmaz, például e-mailben való elküldezést, hívást vagy üzenetkezelést. A fejléc módosítható mezők törlésével, illetve mezők hozzáadásával, beleértve az egyéni mezőket is, további adatok megjelenítése érdekében. Az új fejlécvezérlő használatához menjen a **Funkciókezeléshez**, és **engedélyezze a Dolgozói fejléc vezérlő szolgáltatását**.

## <a name="personalization"></a>Személyre szabás

A dolgozói fejlécvezérlő egyik fő előnye a fejlécben megjelenő információk személyre szabása.

A fejléc jobb felső részén három mező található, amelyek az alkalmazott állapotától függően eltérő adatokat mutatnak. Ezt a mezőcsoportot a fejléc "Egész" részének nevezik. A fejléc Egész része személyre szabható az aktuális mezők törlésével vagy mezők hozzáadásával. A fejlécvezérlőBen a Hozzáadás részhez hozzáadható mezők eltérőek az **Alkalmazott** önkiszolgáló, **a Személyek** **központ és a Dolgozó** lap esetében.

## <a name="employee-self-service"></a>Alkalmazotti önkiszolgáló rendszer

A dolgozó fejléce az Alkalmazott **önkiszolgáló lapon** a következő információkat tartalmazza:

- Dolgozó neve
- Személyzeti szám
- Beosztás címe
- Részlegek
- Dolgozó típusa
- Munkaviszonyban áll jogi személy
- Szolgálati évek
- Jelentések a (vezető) számára
- Beosztás típusa

A fejléc egyetlen kattintással szerkeszthető műveletet is tartalmaz a személy személyes adatainak szerkesztéséhez. Válassza a **Személyes adatok szerkesztése lehetőséget** a **Személyes adatok lap megnyitásához** az Alkalmazott **önkiszolgáló rendszerében**.

## <a name="people-hub"></a>Személyközpont

A Személyek központ dolgozói **fejléce** (**a Személyek munkaterülete** lap) a következő adatokat tartalmazza:

- Dolgozó neve
- Személyzeti szám
- Beosztás címe
- Részlegek
- Dolgozó típusa
- Munkaviszonyban áll jogi személy
- Szolgálati évek
- Jelentések a (vezető) számára
- Beosztás típusa

A fejléc egy kattintásra is tartalmaz műveleteket, például e-mailben való elküldés, hívás vagy üzenetkezelés. Ha egy felhasználó megtekinti **a saját adatait a Személyek** munkaterületi lapon, **az egy kattintásra megjelenő műveletszakasz tartalmazza a Személyes adatok szerkesztése** gombot. A felhasználó ezzel a gombbal megnyithatja **a Személyes adatok** lapot az Alkalmazott **önkiszolgáló rendszerében**.

## <a name="streamlined-worker-page"></a>Leegyszerűsített dolgozóoldal

Az egyszerű Dolgozó lapon **a dolgozófejléc** a következő információkat tartalmazza:

- Dolgozó neve
- Személyzeti szám
- Beosztás címe
- Részlegek
- Dolgozó típusa
- Munkaviszonyban áll jogi személy

Az alkalmazott állapotától függően változhatnak a fejlécben található adatok. Ha például az alkalmazott már kilépett a vállalatból, **a fejlécvezérlő egy Kilépés belépőkártyát**, a foglalkoztatás záró dátumát és a felmondás okát tartalmazza.

Az alábbi táblázat a különböző alkalmazotti állapotok fejlécében megjelenő adatokat mutatja be.

| Alkalmazott állapota | Megjelenő adatok | Megjegyzés |
|-----------------|--------------------|------|
| Függőben | <ul><li>Név</li><li>Személyzeti szám</li><li>Beosztás címe</li><li>Részleg</li><li>Dolgozó típusa</li><li>Jogi személy</li><li>Függőben lévő belépőkártya</li><li>Kezdés dátuma</li><li>Közvetlen felettes</li><li>Beosztás típusa</li></ul> | |
| Legutóbbi felvétel | <ul><li>Név</li><li>Személyzeti szám</li><li>Beosztás címe</li><li>Részleg</li><li>Dolgozó típusa</li><li>Jogi személy</li><li>Legutóbbi felvételi belépőkártya</li><li>Szolgálati évek</li><li>Közvetlen felettes</li><li>Beosztás típusa</li></ul> | Alapértelmezés szerint a legutóbbi **felvételi** belépőkártya megjelenik az elmúlt hét napban felvett alkalmazottak számára. A beállítás módosítása **érdekében** **·** **adjon meg egy időkeretet az Emberi erőforrások paraméterei lap Általános lapján a Legutóbbi felvétel dátumtartománya** területen. Például az **elmúlt** 14 napban felvett alkalmazottak közelmúltbeli felvételi belépőkártyája megtekintéséhez állítsa az Időszak mezőt 14-re **·** **,** **az** Egység mezőben pedig a Napok **mezőt**. |
| Aktív alkalmazott | <ul><li>Név</li><li>Személyzeti szám</li><li>Beosztás címe</li><li>Részleg</li><li>Dolgozó típusa</li><li>Jogi személy</li><li>Kezdés dátuma</li><li>Közvetlen felettes</li><li>Beosztás típusa</li></ul> | |
| Kilépés | <ul><li>Név</li><li>Személyzeti szám</li><li>Beosztás címe</li><li>Részleg</li><li>Dolgozó típusa</li><li>Jogi személy</li><li>Kilépés a belépőkártyáról</li><li>Szolgálati évek</li><li>Közvetlen felettes</li><li>Beosztás típusa</li></ul> | Alapértelmezés szerint a **Kilépés** belépőkártya megjelenik az alkalmazottak számára, akik a következő hét napban el fognak indulni. A beállítás módosítása **érdekében** **·** **adjon** meg egy időkeretet az Emberi erőforrások paraméterei lap Általános lapján a Kilépés a dolgozói dátumtartományból szakaszból. Például a **következő** 14 napban kilépő alkalmazottak kilépési belépőkártyáját beállíthatja 14-re **·** **,** **az** Egység mezőben pedig a Nap **mezőt**. |
| Kilépett | <ul><li>Kilépési belépőkártya</li><li>Személyzeti szám</li><li>Munkaviszony záró dátuma</li><li>Okkód</li></ul> | Alapértelmezés szerint a **kilépési belépőkártya** megjelenik az alkalmazottak számára, akik az elmúlt hét napban kilépettek. A beállítás módosítása **érdekében** **·** **adjon** meg egy időkeretet az Emberi erőforrások paraméterei lap Általános lapján, a Kilépett dolgozók dátumtartománya területen. Ha például **az** elmúlt 14 napban ellépett alkalmazottak kilépési belépőkártyáját meg megtekinteni, állítsa az Időszak mezőt 14-re **·** **,** **az** Egység mezőben pedig a Napok **mezőt**. |
