---
title: Karbantartási körök
description: Ez a témakör az Eszközkezelés karbantartási köreit ismerteti.
author: josaw1
manager: tfehr
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetRoundTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: af0461588971342b62104fce9b5bfa25e329d7c9
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5252990"
---
# <a name="maintenance-rounds"></a>Karbantartási körök

[!include [banner](../../includes/banner.md)]

 

Az **Eszközkezelésben** különböző olyan eszközökhöz lehet karbantartási köröket létrehozni, amelyekhez rendszeres időközönként hasonló feladatot kell végrehajtani. Például olyan kenési vagy biztonsági ellenőrzési feladatok esetén, amelyeket több gépen kell végrehajtani adott időközönként. Első lépésként létre kell hozni egy karbantartási kört, többek között azokat az eszközöket, amelyekhez ugyanazt a karbantartási feladatot kell végrehajtani. Ezután ütemezheti a karbantartási köröket. Ha befejezte a karbantartási körök ütemezését, akkor az **Összes karbantartási ütemezés** és a **Nyitott karbantartási ütemezés** sorban láthatja a körhöz kapcsolódó feladatok rekordjait.

>[!NOTE]
>A karbantartási köröket a munkavégzési helyszíneken is be lehet állítani, hogy a munkavégzési helyszíneken működő eszközökön, a köralapú munkarendelés létrehozásakor történjen meg a feladat. A karbantartási körök munkavégzési helyszíneken történő beállításáról a [Munkavégzési helyszínek létrehozása](../functional-locations/create-functional-locations.md) című témakörben talál további információt.

## <a name="set-up-a-maintenance-round"></a>Karbantartási kör beállítása

1. Kattintson az **Eszközkezelés** > **Beállítások** > **Megelőző karbantartás** > **Karbantartási körök** elemre.

2. Új karbantartási kör létrehozásához kattintson az **Új** gombra.

3. Szúrja be és adja meg az azonosítót a **Karbantartási kör** mezőbe, és adja meg a karbantartási kör nevét a **Név** mezőben.

4. A **Kezdő dátum** mezőben válassza ki a kör kezdő dátumát.

5. A **Befejezés ennyi nap múlva** és **Befejezés ennyi óra múlva** mezőkbe a várható záró dátumot napokban vagy órákban lehet beszúrni. A várható záró dátumot a karbantartási ütemezés sorainak létrehozásakor, a kezdő dátumhoz viszonyítva számítja ki a rendszer. Adja meg például a „7” számot a **Befejezés ennyi nap múlva** mezőben, ha a kapcsolódó feladatot a kezdő dátumtól egy héten belül kell végrehajtani.

6. Válassza az „Igen” lehetőséget az **Automatikus létrehozás** váltógombnál, ha a munkarendeléseket automatikusan létre szeretné hozni az ebből a karbantartási körből létrehozott karbantartási ütemezési sorokból.

7. A **Munkarendelés típusa** mezőben válassza ki azt a munkarendelés-típust, amelyet a karbantartási körből létrehozott munkarendelésekhez kíván használni.

8. A **Szolgáltatásszint** mezőben válassza ki a munkarendelés azon szolgáltatásszintjét, amelyet a karbantartási körből létrehozott munkarendelésekhez kíván használni.

9. Az **Eszközsorok** gyorslapon a **Hozzáadás** gombra kattintva vehet fel eszközt a karbantartási körbe.

10. A rendszer automatikusan beszúrja a sorszámot a **Sorszám** mezőbe; ez jelöli az eszközök karbantartási körön belüli sorrendjét.

11. Az **Eszköz** mezőben válassza ki az eszközt.

12. A **Karbantartási feladat típusa** mezőben válassza ki a karbantartási feladat típusát az eszközhöz.

13. Ha szükséges, adja meg a karbantartási feladat típusához a **Karbantartási feladat típusának változata** és a **Kereskedelem** beállítást.

14. Válassza ki az ismétlődést (nap, hét stb.) az **Időszak típusa** mezőben.

15. Az **Időszak gyakorisága** mezőben adja meg a karbantartási körhöz tartozó ismétlődések számát. Példa: Ha a „Nap” beállítást adta meg az **Időszak típusa** mezőben, és itt a „7” írja be, akkor a megelőző karbantartás ütemezése során a program hetente egyszer hoz létre új sorokat a karbantartási körhöz.

16. A **Kezdő dátum** mezőben válassza ki azt a kezdő dátumot az eszközhöz, amelyet fel szeretne venni a karbantartási körbe. Ez a dátum eltérhet a karbantartási körhöz megadott kezdő dátumtól.

17. A 9–16. lépések megismétlésével további eszközöket vehet fel a karbantartási körbe.

18. A **Munkavégzési helyszín sorai** gyorslapon a **Hozzáadás** gombra kattintva vehet fel munkavégzési helyszínt a karbantartási körbe. Tekintse át a fenti kapcsolódó mezőkben lévő leírást. Ugyanezek a mezők használhatók az eszközsorok létrehozásához, de szükség esetén a **Gyártó** és a **Modell** beállítást is megadhatja a munkavégzési helyszínhez. Ha csak egy munkavégzési helyszínt választ ki egy sorban, de nem adja meg az **Eszköztípus**, a **Gyártó**, a **Modell**, a **Karbantartási feladat típusa**, a **Karbantartási feladat típusának változata** és a **Kereskedelem** beállítást, az adott munkavégzési helyszínhez a karbantartási ütemezés időpontjában kapcsolódó összes eszköz a szerepelni fog a karbantartási körben.

19. A **Csoportok** gyorslap **Hozzáadás** gombjára kattintva kiválaszthatja a karbantartási körben szerepeltetni kívánt munkarendelés-gyűjtőt. Egy karbantartási körhöz több munkarendelés-gyűjtő is csatlakoztatható.

20. Mentse a beállításokat.

>[!NOTE]
>A **Fejléc** gyorslap **Részletek** csoportjában lévő **Eszközök** és **Sorok** mezőjében látható a kiválasztott karbantartási körhöz kapcsolódó eszközök és sorok teljes száma.

Az alábbi ábra három tárgyi eszközt tartalmazó karbantartási fordulóra mutat be példát.

![1. ábra](media/13-preventive-maintenance.png)


## <a name="schedule-maintenance-rounds"></a>Karbantartási körök ütemezése

Ha beállította a karbantartási kört, akkor ütemezési feladatot futtathat a karbantartási körhöz kapcsolódó feladatok ütemezéséhez.

1. Kattintson az **Eszközkezelés** > **Időszakos** > **Megelőző karbantartás** > **Karbantartási körök ütemezése** vagy az **Eszközkezelés** > **Közös** > **Karbantartási ütemezés** > **Összes karbantartási ütemezés** vagy a **Nyitott karbantartási ütemezés** vagy a **Nyitott karbantartási ütemezési csoportok** > a lista kiválasztott karbantartási ütemezési sora > **Karbantartási körök** gombra.

2. Az **Időszak** mezőben válassza ki az ütemezési feladathoz használandó időszaktípust.

3. Az **Időszak gyakorisága** mezőben adja meg, hogy hány időszak szerepeljen az ütemezési feladatban. Az ütemezés az aktuális dátummal kezdődik.

4. Ha egy munkarendelést automatikusan létre kell hozni egy karbantartási kör alapján, akkor adja meg az „Igen” értéket az **Automatikus létrehozás** váltógombnál.

>[!NOTE]
>Ha ennek a váltógombnak az értéke „Igen”, és az **Automatikus létrehozás** váltógomb értéke is „Igen” a **Karbantartási körök** űrlapon lévő karbantartási körnél, akkor a munkarendelések a karbantartási kör sorai alapján jönnek létre, és „Munkarendelés létrehozva” állapotú karbantartási ütemezési sorok is létrejönnek. Ha csak az egyik **Automatikus létrehozás** váltógomb értéke „Igen”, ebben a legördülő menüben vagy a **Karbantartási körök** beállításnál, csak a „Létrehozott” állapotú karbantartási ütemezési sorok jönnek létre. Ebben az esetben nem jön létre munkarendelés.

5. Ha szükséges, kiválaszthat konkrét ütemezési köröket, illetve másik kezdő dátumot az ütemezési feladathoz. Kattintson a **Szűrő** elemre, és adja hozzá a szerepeltetni kívánt köröket.

6. Kattintson az **OK** gombra.

7. Most már látni fogja a karbantartási körök feladatait az **Eszközkezelés** > **Közös** > **Karbantartási ütemezés** > **Összes karbantartási ütemezés** vagy **Nyitott karbantartási ütemezés** sorban. Ha az ütemezett köröket munkarendelési csoporttal kapcsolja össze, akkor a karbantartási ütemezés sorai is láthatók a **Nyitott karbantartási ütemezési csoportok** részen. A kör alapján létrehozott karbantartási ütemezési sorok hivatkozástípusa „Karbantartási körök”.

Az alábbi két illusztráció egy ütemezési feladatot mutat be a **Karbantartási körök ütemezése** párbeszédablakban, és az ütemezési feladat alapján az **Összes karbantartási ütemezésben** létrehozott karbantartási ütemezési sorokat.

![2. ábra](media/14-preventive-maintenance.png)

![3. ábra](media/15-preventive-maintenance.png)

- Ha a munkarendelések létrehozása manuálisan, egyszállítói garanciával fedezett eszközhöz történik, egy párbeszédpanel jelenik meg, amely a felhívja a felhasználó figyelmét a jótállásra. A munkarendelés létrehozása ezt követően visszavonható. Az automatikusan létrehozott munkarendelések a jótállási kapcsolat keresése ki van hagyva.  
- A **Futtatás a háttérben** gyorslapon beállítható kötegelt feladat a körök szabályos időközönként történő ütemezéséhez.  
- Ha egy kör több munkarendelési gyűjtőben is szerepel (lásd: [Munkarendelés-gyűjtők](../work-orders/work-order-pools.md)), akkor minden gyűjtőhöz egy rekord jelenik meg a **Nyitott karbantartási ütemezési csoportok** részen. Ez a munkarendelés-gyűjtők szűrési beállításainak optimalizálására szolgál.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]