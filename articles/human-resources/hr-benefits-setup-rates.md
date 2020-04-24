---
title: Díjak konfigurálása
description: A Microsoft Dynamics 365 Human Resources szolgáltatásban a mértékek határozzák meg, hogy a munkáltatók és az alkalmazottak mennyivel járulnak hozzá a juttatáshoz.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 26b1e0e5f259e012cfb9079eb75898a9337a300d
ms.sourcegitcommit: a9461650d11d6845e1942865ebf7e35f75f61ad3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/06/2020
ms.locfileid: "3229832"
---
# <a name="configure-rates"></a>Díjak konfigurálása

A Microsoft Dynamics 365 Human Resources szolgáltatásban a mértékek határozzák meg, hogy a munkáltatók és az alkalmazottak mennyivel járulnak hozzá a juttatáshoz. Az érték a konfigurációtól függően lehet összeg vagy rugalmas jóváírás.

A mértékek használatával meghatározhatja, hogy az alkalmazottak és a munkáltatók milyen mértékben fizetnek az egyes juttatásokért, több tényező alapján. A fedezeti mértékekhez érvényességi dátum tartozik, így megőrizheti a mértékek előzményeinek nyilvántartását. 

## <a name="set-up-rates"></a>Mértékek beállítása

1. A **Juttatások kezelése** munkaterület **Beállítás** részén válassza a **Mértékek** elemet.

2. Válassza az **Új** lehetőséget.

3. Adjon meg értékeket a következő mezőkben:

   | Mező | Leírás |
   | --- | --- |
   | **Díj** | A juttatási mértéket azonosító egyedi név. |
   | **Leírás** | A juttatási mérték rövid leírása. |
   | **Hatályos** | A mérték érvényességének dátuma. Az alapértelmezett érték az aktuális rendszerdátum. 
   | **Lejárat** | A mérték záró dátuma. Az alapértelmezett érték a 2154. 12. 31., ami a „soha” megfelelője. |
   | **Szintek használata** | A juttatási mérték kiszámításához használandó szint. Szimpla szint az egyszintű juttatási mértékhez vagy dupla szint a kétszintű juttatási mértékhez. Dupla szint lehet például a nemen és az életkoron alapuló szint. |
   | **Fizetés gyakorisága** | A fizetési gyakoriság, amely meghatározza, hogy milyen gyakran történik a juttatási díj kifizetése a juttatási szolgáltató számára. Ha például a fizetés gyakorisága havonkénti, akkor a juttatási mérték havi kifizetett összeget jelent. |
   | **Fizetési gyakoriság mértékének kerekítése** | Az árfolyam kerekítésének módja: normál vagy csonkolt. |
   | **Nem dohányzó alkalmazott összege** | A nem dohányzó alkalmazottnak a juttatásszolgáltató által adott díj összege. Ez az az összeg, amelyet a munkáltató fizet a juttatásszolgáltatónak, és a mértékbeállítás kifizetési gyakoriságán kell alapulnia. |
   | **Nem dohányzó munkáltató összege** | A nem dohányzó alkalmazottnak a juttatásszolgáltató által adott díj összege. Ez az az összeg, amelyet a munkáltató fizet a juttatásszolgáltatónak, és a mértékbeállítás kifizetési gyakoriságán kell alapulnia. |
   | **Dohányzó alkalmazott összege** | A dohányzó alkalmazottnak a juttatásszolgáltató által adott díj összege. Ez az az összeg, amelyet a munkáltató fizet a juttatásszolgáltatónak, és a mértékbeállítás kifizetési gyakoriságán kell alapulnia. |
   | **Dohányzó munkáltató összege** | A dohányzó alkalmazottnak a juttatásszolgáltató által adott díj összege. Ez az az összeg, amelyet a munkáltató fizet a juttatásszolgáltatónak, és a mértékbeállítás kifizetési gyakoriságán kell alapulnia. |
   | **Adminisztratív összeg** | Harmadik fél rendszergazdája által felszámított adminisztratív összeg. Ez az az összeg, amelyet a munkáltató fizet a harmadik fél adminisztrátorának, és a mértékbeállítás kifizetési gyakoriságán kell alapulnia. |
   | **Rugalmas jóváírási díjalap** | A juttatás költségének megfelelő rugalmas jóváírások száma. Ez csak a rugalmas jóváírási programokhoz társított juttatási konstrukciók díjaira vonatkozik. Ha használja a szintmértékeket, akkor a rugalmas jóváírás mérteke a Műveletek > Szintmértékek beállításnál adható meg. |
   | **Módosítás érvénybe lépési dátuma** | A juttatási mérték érvénybe lépésének dátuma. A rendszer automatikusan megváltoztatja a juttatás mértékét, és frissíti az ehhez a mértékhez kapcsolódó összes juttatási konstrukciót, amikor futtatja a mérték módosításának frissítési feldolgozását. Ezt a dátumot csak akkor adja meg, ha azt szeretné, hogy a rendszer automatikusan frissítse az alkalmazottak juttatási konstrukcióit a mérték alapján. Ez általában az automatikus jövőbeli mértékmódosítás feldolgozásához van fenntartva. A módosítás érvényességi dátumának a juttatási mérték érvényességi dátuma és a lejárati dátuma között kell lennie. |
   | **A díjalap módosítása befejeződött** | A rendszer automatikusan bejelöli a **Mérték módosítása befejeződött** jelölőnégyzetet, amikor a mértékfrissítési módosítás feldolgozása végrehajtotta a juttatási mérték módosításait. |

4. A juttatásimérték-beállítások változásainak követéséhez és karbantartásához válassza a **Műveletek**, majd a **Verziók karbantartása** lehetőséget.

5. Válassza a **Mentés** lehetőséget. 

## <a name="set-up-tier-rates"></a>Szintmértékek beállítása

Ha a mérték különböző tényezőktől függően változik, akkor használhat szintmértékeket a mértékbeállításához. A szintmértékeket beállíthatja például úgy, hogy ha az életkor max. 34,99, akkor a nem dohányzó összeg 2. Ha az életkor max. 39,99, akkor a nem dohányzó összeg 3.

Dupla szinteket is használhat. Ha a **Mérték beállítása** képernyőn a **Dupla szint** értéket választja a **Szintek használata** beállításnál, akkor két dimenzió alapján definiálhatja a mértékeket. Konfigurálhat például dupla szintrendszert: ha a nem férfi és az életkor max. 34,99, akkor a nem dohányzó összeg 2. Ha a nem férfi és az életkor max. 39,99, akkor a nem dohányzó összeg 3. Ha a nem nő és az életkor max. 34,99, akkor a nem dohányzó összeg 1,8. Ha a nem nő és az életkor max. 39,99, akkor a nem dohányzó összeg 2,8.

1. A **Juttatások kezelése** munkaterület **Beállítás** részén válassza a **Mértékek** elemet.

2. Válasszon egy vagy több mértéket a listáról, és válassza a **Műveletek**, majd a **Szintmértékek** lehetőséget.

3. Válassza az **Új** lehetőséget.

3. Adjon meg értékeket a következő mezőkben:

   | Mező | Leírás |
   | --- | --- | 
   | **Leírás** | A Leírás mező értékét a mértékbeállítási rekordban megadott leírás adja. Ez alapján megállapíthatja, hogy a szintmértékek melyik mértékbeállításhoz kapcsolódnak. |
   | **Szint kódja** | Válasszon szintkódot. A szintkódokat a Szintkódok képernyőn definiálhatja. A rendszer automatikusan megjeleníti a szintkód leírását a balra lévő rácson. |
   | **Szint típusa** | Megadja, hogy melyik mezőt kell használni kiválasztási feltételként a szintmértékszámítási folyamathoz. Példa:</br></br><ul><li>Az életkor használata esetén a rendszer az alkalmazott születésnapját fogja használni a juttatási mérték kiszámítási folyamatában.</li><li>A fizetés használata esetén a rendszer az alkalmazott évi juttatásfizetési összegét fogja használni a juttatási mérték kiszámítási folyamatában.</li><li>A feladattípus használata esetén a rendszer az alkalmazott aktuális aktív pozíciójának rekordját használja a beosztáshoz kapcsolódó feladattípus meghatározására.</li></ul></br></br>A szinttípusok a következők: Életkor, Fizetés, Tényleges, Nem, Teljes munkaidőssel egyenértékű, Feladattípus, Kompenzációs régió és Szint. | 
   | **Szint** | Az az érték, amelyet a rétegtípussal kell használni a juttatási mérték kiszámításának folyamata során. Példa:</br></br><ul><li>Ha a szinttípus az Életkor, akkor ez lesz az életkor értéke.</li><li>Ha a szinttípus a Fizetés, akkor ez lesz a fizetés összege.</li><li> Ha a szinttípus a Feladattípus, akkor ez lesz a feladat típusa.</li></ul></br></br>Életkor vagy Fizetés szinttípus esetén a rendszer növekvő megközelítést alkalmaz a szinttípus kiválasztása során, ami azt jelenti, hogy a Szint mezőben lévő érték a szint alsó határát jelöli. Feladattípus szinttípus esetén a rendszer pontos egyeztetési módszert alkalmaz a szinttípus kiválasztása során. |
   | **Számítás típusa** | Megadja, hogyan kell használni az összeget a számítási összeg mezőjében, és szükség esetén milyen matematikai számítást kell végrehajtani. Ha a számítás típusa fix összeg, akkor a rendszer az összegmezőket használja. Ha a számítás típusa a fizetés vagy a fedezet $ összege, akkor a rendszer a számítás összegét és a számítási irányt használja a matematikai számításaiban.</br></br>Ha a számítás típusa a fizetés $ összege, akkor a rendszer a következő matematikai egyenletet fogja használni:</br></br>Évi juttatásfizetés osztva a számítási összeggel (felfelé vagy lefelé kerekítve), szorozva a dohányzó vagy nem dohányzó alkalmazott vagy munkáltató összegével.</br></br>Ha a számítás típusa a fedezet $ összege, akkor a rendszer a következő matematikai egyenletet fogja használni:</br></br>Fedezet összege osztva a számítási összeggel (felfelé vagy lefelé kerekítve), szorozva a dohányzó vagy nem dohányzó alkalmazott vagy munkáltató összegével.</br></br>Mindkét számításban a számítási irány határozza meg, hogy felfelé vagy lefelé kell-e kerekíteni a számítás összegével elosztott évi juttatásfizetés vagy fedezet összegét. |
   | **Számítási összeg** | A juttatási mérték kiszámítási folyamata során használandó összeg. Ez az összeg lesz az osztó a szintmérték matematikai számításakor. |
   | **Számítás iránya** | A kiszámított eredmény összegének kerekítési iránya (növelés vagy csökkentés). A rendszer három számítási irányt támogat: nincs (pontos módszer), növelés és csökkentés.</br></br><ul><li>Ha nincs irány, akkor a rendszer a fizetés/fedezet összegének a számítás összegével elosztott pontos értékét fogja használni. Ha az értéknek van törtrésze, akkor a rendszer használni fogja ezt a számításban.</li><li>Ha az irány a növelés, akkor a rendszer a következő egész számra növeli a fizetés/fedezet összegének a számítás összegével elosztott értékét, vagyis például a 12,25 értéket 13-ra kerekíti.</li><li>Ha az irány a csökkentés, akkor a rendszer az aktuális egész számra csökkenti a fizetés/fedezet összegének a számítás összegével elosztott értékét, vagyis például a 12,25 értéket 12-re kerekíti.</li></ul> |
   | **Nem dohányzó alkalmazott összege** | A nem dohányzó alkalmazottnak a juttatásszolgáltató által adott díj összege. Ez az az összeg, amelyet a munkáltató fizet a juttatásszolgáltatónak, és a mértékbeállítás kifizetési gyakoriságán kell alapulnia. |
   | **Nem dohányzó munkáltató összege** | A nem dohányzó alkalmazottnak a juttatásszolgáltató által adott díj összege. Ez az az összeg, amelyet a munkáltató fizet a juttatásszolgáltatónak, és a mértékbeállítás kifizetési gyakoriságán kell alapulnia. |
   | **Dohányzó alkalmazott összege** | A nem dohányzó alkalmazottnak a juttatásszolgáltató által adott díj összege. Ez az az összeg, amelyet a munkáltató fizet a juttatásszolgáltatónak, és a mértékbeállítás kifizetési gyakoriságán kell alapulnia. |
   | **Dohányzó munkáltató összege** | A nem dohányzó alkalmazottnak a juttatásszolgáltató által adott díj összege. Ez az az összeg, amelyet a munkáltató fizet a juttatásszolgáltatónak, és a mértékbeállítás kifizetési gyakoriságán kell alapulnia. |
   | **Adminisztratív összeg** | Harmadik fél rendszergazdája által felszámított adminisztratív összeg. Ez az az összeg, amelyet a munkáltató fizet a harmadik fél adminisztrátorának, és a mértékbeállítás kifizetési gyakoriságán kell alapulnia. |
   | **Rugalmas jóváírás nem dohányzó mértéke** | A juttatás költségének megfelelő rugalmas jóváírások száma, a nem dohányzókhoz meghatározott szint számítása alapján. Ha például a számítási típus **fedezet $ összege**, akkor a számítási összeg 10 000, és a rugalmas jóváírás nem dohányzó mértéke 6, ami azt jelenti, hogy ha egy nem dohányzó alkalmazott a 10 000 $ fedezetet választja, akkor ennek költsége 6 rugalmas jóváírás lesz. Ha a 20 000 $ fedezetet választja, akkor ennek költsége 12 rugalmas jóváírás lesz stb. |
   | **Rugalmas jóváírás dohányzó mértéke** | A juttatás költségének megfelelő rugalmas jóváírások száma, a dohányzókhoz meghatározott szint számítása alapján. |

5. Válassza a **Mentés** lehetőséget. 
