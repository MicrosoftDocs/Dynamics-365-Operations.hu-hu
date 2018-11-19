---
title: "Ajánlatok létrehozása, jóváhagyása és aláírása"
description: "Ez a témakör az ajánlatok létrehozását, jóváhagyását és aláírását ismertheti a Dynamics 365 for Talent megoldást használó jelöltek számára."
author: josaw
manager: AnnBe
ms.date: 10/19/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2018-10-19
ms.dyn365.ops.version: Talent October 2018 update
ms.translationtype: HT
ms.sourcegitcommit: e890e32049e930b70c2d0aac8aa8206ab999418a
ms.openlocfilehash: f6b17dca13431a9d674920833b4a44141fac0bd8
ms.contentlocale: hu-hu
ms.lasthandoff: 10/22/2018

---

# <a name="creating-approving-and-signing-offers"></a>Ajánlatok létrehozása, jóváhagyása és aláírása

[!include[banner](../includes/banner.md)]

Sok esetben egy ajánlati csomag előkészítésének a pályázó számára nagyon gyors folyamatnak kell lennie.
Az Attract rendszergazda által beállított sablonok használata időt és ráfordítást takarít meg az ajánlatkészítőknek, amikor ajánlatot állítanak össze és küldenek el a pályázónak.

## <a name="create-an-offer"></a>Egy ajánlat létrehozása

Ha az ajánlatkezelési alkalmazás be van kapcsolva, ha minden felhasználó, aki a felvételi vezető vagy toborzó szereppel rendelkezik, előkészíthet a pályázónak egy ajánlati csomagot. Az ajánlat előkészítéséhez tegye a következőket.

1.  Keresse meg az állást a jelölt jelentkezését, amelyhez az ajánlatot létrehozza.

1.  Ugrás? **Ajánlati szakasz**, és kattintson az **Ajánlat előkészítése** elemre.

    A rendszer átirányítja az ajánlat alkalmazáshoz, ahol megtekintheti a pályázót az **Új** állapottal. Más ajánlatokat is megtekinthet, amelyekhez hozzájár létrehozó vagy jóváhagyó szerepben.

1.  Kattintson: **Ajánlatkészítés**. 
    
    A rendszergazda által rendelkezésére bocsátott különböző ajánlatcsomagok választékát fogja látni.

1.  Egy csomagot kell kiválasztani, és kattintson a **Kész** elemre az ajánlatelőkészítés indításához.

    Az ajánlatcsomag sablon töltődik be, és fel lesz töltve a megfelelő állás és jelölti adatokkal.

1.  Az összes ajánlatadat-helyőrzők, amely az ajánlati csomag része, láthatók a nyitóoldalon. A csomag ezen az oldalon keresztül feltölthető értékekkel.

    A nyitóoldalon az ajánlati csomag részét képező összes ajánlati dokumentumsablont is megtekintheti.

1.  Most lehet szerkesztheti az ajánlat tartalmát, a sablon rendszergazda általi beállításától függően.

1.  Ha el kell távolítania nem szükségesként megjelölt dokumentumokat, akkor megteheti.

1. Ha minden ajánlatadat-helyőrző fel van töltve, kattintson a **Mentés** elemre az ajánlat vázlatának mentéséhez.

>[!NOTE]
> A vázlat mentése után az ajánlat vázat verziója törölhető, illetve ha szükséges, válasszon ki egy új csomagsablont.


## <a name="approve-an-offer"></a>Ajánlat jóváhagyása

A legtöbb ajánlatnak jóváhagyási folyamaton kell átesnie, hogy az ajánlat biztosan megfeleljen a szükséges szabványoknak. Ha egy ajánlat nem felel meg a szabványoknak, például ha az ajánlatot létrehozó nem követte el az ajánlati adatszabályokat és felülírta az ajánlatban szereplő értékeket, kiváltódik a jóváhagyási folyamat. Az ajánlat jóváhagyásra küldéséhez tegye a következőket.

1.  Ha az ajánlat vázlat állapotban van, a jóváhagyók hozzáadása a **Jóváhagyó panelen** történik. 
    >[!NOTE]
    > A felvételi vezetőket a rendszer alapértelmezés szerint hozzáadja jóváhagyóként. Bármely felhasználót kiválaszthat a szervezetből az ajánlat jóváhagyójaként.

1.  Szükség esetén a jóváhagyókat egymásra következő jóváhagyási módban vagy párhuzamos jóváhagyási módban rendelje hozzá. Ez a beállítás csak akkor érhető el, ha beállította egy rendszergazda.
    >[!NOTE]
    > Ha a jóváhagyási folyamat egymásra következő, a jóváhagyók sorozata szükség esetén szerkeszthető.

1.  Ha végzett a jóváhagyási lánc meghatározásával, szerkesztheti a jóváhagyó e-mail tartalmát, és elküldi az értesítést a jóváhagyóknak. Kattintson ide: **Küldés jóváhagyóknak**.
    >[!NOTE]
    > Ha az ajánlat nem szabványos, alátámasztás megadása szükséges.

1.  Ha az ajánlatot létrehozó úgy dönt, hogy egy jóváhagyót kihagy, beírhat egy megjegyzést, és ugorhat a következő jóváhagyóra.

A jóváhagyók e-mailt kapnak, ami az ajánlat jóváhagyására kéri őket. Az e-mailben levő hivatkozásra kattintva nyitható meg az ajánlat, áttekinthetik a teljes ajánlati csomagot, és jóváhagyhatják vagy az ajánlat létrehozójának visszaküldhetik. Az ajánlatjóváhagyóknak hozzá kell adniuk egy kiegészítő megjegyzést, ha elutasítják az ajánlati csomagot további módosításokra. 

Azokban az esetekben, amikor az ajánlatnak a jóváhagyó művelete előtt létrehozzák egy új verzióját, a jóváhagyó nem fogja tudni jóváhagyni vagy elutasítani az ajánlatot.

## <a name="offer-versioning"></a>Ajánlat verziói 

Amikor az ajánlatot jóváhagyták vagy további módosításokra visszaküldték, kiválaszthatja a **Szerkesztés engedélyezése** lehetőséget az ajánlat új verziójának létrehozásához. Az ajánlatverzió új verziója átviszik az előző verzióból az ajánlat minden adatértékét és azjóváhagyók listáját. 

A jóváhagyók az ajánlat különböző verziói között válthatnak, ha a verziókat jóváhagyásra megosztották velük. Emellett egy jóváhagyó vagy az ajánlat létrehozója választhatja azt, hogy töröl egy adott vázlat ajánlatverzió, hogy visszatérje az előző állapotba.


## <a name="send-an-offer-to-a-candidate"></a>Ajánlat elküldése egy jelöltnek 

Az ajánlat mentése és jóváhagyása után, amikor kész a pályázónak való elküldésre, kattintson **Küldés a pályázónak** elemre.

Számos művelet hajtható végre az ajánlat pályázónak való küldése előtt.
-  Megtekintheti a pályázónak elküldendő ajánlati csomag részét képező dokumentumok listáját.

-  Megadhatja az ajánlat lejárati dátumát. Pályázókkal szemben elvárás, hogy fogadják el vagy utasítsák el az ajánlatot a lejárati dátuma előtt.  A pályázónak a rendszer emlékeztetőt küld 48 órával az ajánlat lejárata előtt.

-  Lehetnek az ajánlat elfogadási folyamatának bevenni kívánt további dokumentumok. Lehetőség van a kötelező dokumentumtípus listázására.

-  Megtekintheti és szerkesztheti az e-mail sablont, szükség szerint.

Amikor készen áll az ajánlatot, és rákattint a **Küldés a pályázónak** elemre, a jelölt kap egy e-mailt, amely szerint az ajánlat ellenőrzésre vár.


## <a name="candidates-actions-after-receiving-an-offer"></a>Az ajánlat kézhezvétele utáni jelölti műveletek

Miután a pályázó értesítést kapott arról, hogy ajánlat van osztva vele, rákattinthat a hivatkozásra az e-mailben, hogy megnyissa az alkalmazás irányítópultot, és megnézheti az ajánlatot. Az irányítópult megjeleníti a pályázónak minden olyan tevékenységet, amelyet még el kell végeznie.

1.  Az ajánlat és minden kapcsolódó dokumentum megtekintéséhez a jelöltnek rá kell kattintania az **Ajánlat megtekintése** elemre.

    A pályázók le is tölthetik az ajánlati csomagot .zip formátumban.

1.  Az ajánlat elfogadásához a pályázónak rá kell kattintania az **Ugrás az aláíráshoz** elemre minden olyan dokumentumnál, amely az ajánlatcsomag része.

1.  Az összes dokumentum egyenkénti aláírása és elfogadása után a pályázó a jóváhagyási folyamat befejezéséhez kattintson az **Ajánlat elfogadása** elemre az oldal tetején.

1.  Az ajánlat elutasításához a jelölt kattintson az **Ajánlat elutasítása** elemre az oldal tetején, válassza ki a megfelelő okot, írjon megjegyzést szükség szerint, és kattintson az **Elutasítás** elemre.

1.  Az ajánlat elfogadása vagy elutasítása után a jelölt maradhat az ajánlat nézetben, vagy visszatérhet a pályázat irányítópultra.

1.  Ha más dokumentumokat is kértek az ajánlatelfogadási folyamat részeként, a jelöltnek szükség szerint ki kell választani a dokumentumokat a feltöltéshez, és meg kell címkéznie őket a kért típusú dokumentumként.

1.  Az ajánlatlétrehozó értesítést kap, amikor az összes bizonylat fel lett töltve, és az ajánlati csomag alá van írva.


## <a name="withdrawing-an-offer"></a>Ajánlat visszavonása

Az ajánlatot bármikor vissza lehet vonni különböző okokkal. 
1.  Visszavonható az ajánlat a (**...**) gombra kattintva, majd az **Ajánlat visszavonása** elemre kattintva. 

2. Egy üzenet jelenik meg, amely megkérdezi, hogy a jelentkezővel felvették-e a kapcsolatot az állapotmódosítás miatt. Ha még nem történt meg a pályázóval való kapcsolatfelvétel, akkor e-mailt küldhet a jelentkezőnek, tájékoztatva a további műveletekről. 

   Az ajánlat nem lesz többé elérhető a jelentkező számára.


## <a name="closing-an-offer"></a>Ajánlat lezárása 

Az ajánlat elfogadása, elutasítása vagy visszavonása után úgy, hogy nincs további műveletekre szükség, az ajánlatot lezárhatja, hogy további módosításokat ne lehessen végezni az ajánlati csomagon.

