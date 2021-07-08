---
title: Díjak konfigurálása
description: A Microsoft Dynamics 365 Human Resources szolgáltatásban a mértékek határozzák meg, hogy a munkáltatók és az alkalmazottak mennyivel járulnak hozzá a juttatáshoz.
author: andreabichsel
ms.date: 06/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2b6767df573260f32de8409e487f649bdc4779b0
ms.sourcegitcommit: ecabf43282a3e55f1db40341aa3f3c7950b9e94c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/16/2021
ms.locfileid: "6266657"
---
# <a name="configure-rates"></a>Díjak konfigurálása

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

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
   | **Fizetési gyakoriság mértékének kerekítése** | Az árfolyam kerekítési módjai: Standard, Csonkolt, Normál, Lefelé és Felkerekítés. </br></br><ul><li>**Standard** – Mindig felfelé kerekítés. A 10,611-es kerekítés például 10,62 lesz. -10,231 kerekítése -10,23-ra. </li><li>**Csonkolt** – Mindig lekerekítés. A 10,619-es kerekítés például 10,61 lesz. -10,231 kerekítése -10,24-ra. </li><li>**Normál** – Az 5-re vagy annál nagyobbra végződő tizedesértékek nulláról kerekítve lesznek. A 4-re vagy annál kisebbre végződő tizedesértékek nullára kerekítnek. A 10,615-es kerekítés például 10,62 lesz. -10,235 kerekítése -10,24-ra. 10,614 kerekítése 10,61-ra. -10,234 kerekítése -10,23-ra. </li><li>**Lefelé** – Kerekítés nullához. A 10,619-es kerekítés például 10,61 lesz. -10,231 kerekítése -10,23-ra. </li><li>**Felkerekítés** - Kerekítés nulláról. A 10,619-es kerekítés például 10,62 lesz. -10,231 kerekítése -10,24-ra. |
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
   | **Leírás** | A **Leírás** mező értékét a mértékbeállítási rekordban megadott leírás adja. Ez alapján megállapíthatja, hogy a szintmértékek melyik mértékbeállításhoz kapcsolódnak. |
   | **Szint kódja** | Válasszon szintkódot. A szintkódokat a Szintkódok képernyőn definiálhatja. A rendszer automatikusan megjeleníti a szintkód leírását a balra lévő rácson. |
   | **Szint típusa** | Megadja, hogy melyik mezőt kell használni kiválasztási feltételként a szintmértékszámítási folyamathoz. Példa:</br></br><ul><li>Az **Életkor** használata esetén a rendszer az alkalmazott születésnapját fogja használni a juttatási mérték kiszámítási folyamatában.</li><li>A **Fizetés** használata esetén a rendszer az alkalmazott évi juttatásfizetési összegét fogja használni a juttatási mérték kiszámítási folyamatában.</li><li>A **Feladattípus** használata esetén a rendszer az alkalmazott aktuális aktív pozíciójának rekordját használja a beosztáshoz kapcsolódó feladattípus meghatározására.</li></ul></br></br>A szinttípusok a következők: **Életkor**, **Fizetés**, **Tényleges**, **Nem**, **Teljes munkaidőssel egyenértékű**, **Feladattípus**, **Kompenzációs régió** és **Szint**. | 
   | **Szint** | Az az érték, amelyet a rétegtípussal kell használni a juttatási mérték kiszámításának folyamata során. Példa:</br></br><ul><li>Ha a szinttípus az **Életkor**, akkor ez lesz az életkor értéke.</li><li>Ha a szinttípus a **Fizetés**, akkor ez lesz a fizetés összege.</li><li> Ha a szinttípus a **Feladattípus**, akkor ez lesz a feladat típusa.</li></ul></br></br>Az **Életkor** vagy **Fizetés** fokozattípus esetén a **Szint** mezőben szereplő érték a szint felső határát jelöli. **Feladattípus** szinttípus esetén a rendszer pontos egyeztetési módszert alkalmaz a szinttípus kiválasztása során. |
   | **Számítás típusa** | Megadja, hogyan kell használni az összeget a számítási összeg mezőjében, és szükség esetén milyen matematikai számítást kell végrehajtani. Ha a számítás típusa fix összeg, akkor a rendszer az összegmezőket használja. Ha a számítás típusa a fizetés vagy a fedezet $ összege, akkor a rendszer a számítás összegét és a számítási irányt használja a matematikai számításaiban.</br></br>Ha a számítás típusa a fizetés $ összege, akkor a rendszer a következő matematikai egyenletet fogja használni:</br></br>Évi juttatásfizetés osztva a számítási összeggel (felfelé vagy lefelé kerekítve), szorozva a dohányzó vagy nem dohányzó alkalmazott vagy munkáltató összegével.</br></br>Ha a számítás típusa a fedezet $ összege, akkor a rendszer a következő matematikai egyenletet fogja használni:</br></br>Fedezet összege osztva a számítási összeggel (felfelé vagy lefelé kerekítve), szorozva a dohányzó vagy nem dohányzó alkalmazott vagy munkáltató összegével.</br></br>Mindkét számításban a számítási irány határozza meg, hogy felfelé vagy lefelé kell-e kerekíteni a számítás összegével elosztott évi juttatásfizetés vagy fedezet összegét. |
   | **Számítási összeg** | A juttatási mérték kiszámítási folyamata során használandó összeg. Ez az összeg lesz az osztó a szintmérték matematikai számításakor. |
   | **Számítás iránya** | A kiszámított eredmény összegének kerekítési iránya. A rendszer három számítási irányt támogat: nincs (pontos módszer), **Növelés** és **Csökkentés**.</br></br><ul><li>Ha nincs irány, akkor a rendszer a fizetés/fedezet összegének a számítás összegével elosztott pontos értékét fogja használni. Ha az értéknek van törtrésze, akkor a rendszer használni fogja ezt a számításban.</li><li>Ha az irány a **Növelés**, akkor a rendszer a következő egész számra növeli a fizetés/fedezet összegének a számítás összegével elosztott értékét, vagyis például a 12,25 értéket 13-ra kerekíti.</li><li>Ha az irány a **Csökkentés**, akkor a rendszer az aktuális egész számra csökkenti a fizetés/fedezet összegének a számítás összegével elosztott értékét, vagyis például a 12,25 értéket 12-re kerekíti.</li></ul> |
   | **Nem dohányzó alkalmazott összege** | A nem dohányzó alkalmazottnak a juttatásszolgáltató által adott díj összege. Ez az az összeg, amelyet a munkáltató fizet a juttatásszolgáltatónak, és a mértékbeállítás kifizetési gyakoriságán kell alapulnia. |
   | **Nem dohányzó munkáltató összege** | A nem dohányzó alkalmazottnak a juttatásszolgáltató által adott díj összege. Ez az az összeg, amelyet a munkáltató fizet a juttatásszolgáltatónak, és a mértékbeállítás kifizetési gyakoriságán kell alapulnia. |
   | **Dohányzó alkalmazott összege** | A nem dohányzó alkalmazottnak a juttatásszolgáltató által adott díj összege. Ez az az összeg, amelyet a munkáltató fizet a juttatásszolgáltatónak, és a mértékbeállítás kifizetési gyakoriságán kell alapulnia. |
   | **Dohányzó munkáltató összege** | A nem dohányzó alkalmazottnak a juttatásszolgáltató által adott díj összege. Ez az az összeg, amelyet a munkáltató fizet a juttatásszolgáltatónak, és a mértékbeállítás kifizetési gyakoriságán kell alapulnia. |
   | **Adminisztratív összeg** | Harmadik fél rendszergazdája által felszámított adminisztratív összeg. Ez az az összeg, amelyet a munkáltató fizet a harmadik fél adminisztrátorának, és a mértékbeállítás kifizetési gyakoriságán kell alapulnia. |
   | **Rugalmas jóváírás nem dohányzó mértéke** | A juttatás költségének megfelelő rugalmas jóváírások száma, a nem dohányzókhoz meghatározott szint számítása alapján. Ha például a számítási típus **fedezet $ összege**, akkor a számítási összeg 10 000, és a rugalmas jóváírás nem dohányzó mértéke 6, ami azt jelenti, hogy ha egy nem dohányzó alkalmazott a 10 000 $ fedezetet választja, akkor ennek költsége 6 rugalmas jóváírás lesz. Ha a 20 000 $ fedezetet választja, akkor ennek költsége 12 rugalmas jóváírás lesz stb. |
   | **Rugalmas jóváírás dohányzó mértéke** | A juttatás költségének megfelelő rugalmas jóváírások száma, a dohányzókhoz meghatározott szint számítása alapján. |

5. Válassza a **Mentés** lehetőséget. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
