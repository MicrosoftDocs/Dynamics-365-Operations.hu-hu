---
title: Karbantartási tervek ütemezése
description: Ez a témakör bemutatja az eszközkezelés karbantartási terveinek ütemezését.
author: johanhoffmann
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: fc9212d0945c05af9dbc054a5a1d2bf7b996b93f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8857982"
---
# <a name="schedule-maintenance-plans"></a>Karbantartási tervek ütemezése

[!include [banner](../../includes/banner.md)]

 

A megelőző karbantartás ütemezése az eszközökön beállított karbantartási konstrukciók alapján hozza létre az eszközök naptári bejegyzéseit. A naptári bejegyzéseket a kiválasztott karbantartási tervek, eszközök típusai és eszközei alapján lehet ütemezheti.

1. Kattintson az **Eszközkezelés** > **Időszakos** > **Megelőző karbantartás** > **Karbantartási tervek ütemezése** elemre.

2. Az **Időszak** és **Időszak gyakorisága** mezőben kiválaszthatja az időintervallumot.

>[!NOTE]
>Az **Időszak** és **Időszak gyakorisága** mező azt jelzi, hogy időben mennyire előre szeretne karbantartási ütemezési sorokat létrehozni a már létrehozott (időalapú vagy számláló alapú) karbantartási tervek alapján. Az alábbi ábrán a karbantartási ütemezés sorai (= munkarendelési javaslatok) az aktuális dátumtól, három hónapra előre vannak létrehozva.

3. Válassza ki az „Igen” lehetőséget az **Automatikus létrehozás, ha meg van adva a sorban** váltógombon, amennyiben a karbantartási terv sora alapján automatikusan kell létrehozni a munkarendeléseket.

>[!NOTE]
>Ha ennek a váltógombnak az értéke „Igen”, *és* az **Automatikus létrehozás** jelölőnégyzet is be van jelölve a karbantartási terv sorainál a **Karbantartási tervek** szakaszban, akkor a munkarendelések a munkarendelési terv sorai alapján jönnek létre, és a rendszer a „Munkarendelés létrehozva” állapotú karbantartási ütemezési sorokat is létrehozza. Ha csak egy beállítás van kiválasztva (az **Automatikus létrehozás, ha meg van adva a sorban** váltógomb ezen a párbeszédpanelen vagy az **Automatikus létrehozás** jelölőnégyzet a **Karbantartási tervek** űrlapon), akkor csak a karbantartási ütemezés sorai jönnek létre „Létrehozva” állapottal. Ebben az esetben nem jön létre munkarendelés.

4. Lehetőség van arra is, hogy karbantartási tervek (idő vagy számláló), eszközök, eszköztípusok, munkavégzési helyszínek és munkavégzési helyszínek típusai alapján hozzon létre naptárbejegyzéseket. Kattintson a **Szűrő** gombra, és ha szükséges, adja meg a kívánt beállításokat.

- Tudnivalók a munkavégzési helyszínekkel kapcsolatos karbantartási tervek ütemezéséről: ha frissíti a karbantartási tervek eszköztípusainak, eszközgyártóinak és eszközmodelljeinek a beállítását az **Összes munkavégzési helyszín** > **Karbantartási tervek** gyorslapján a karbantartási tervek ütemezését követően, a munkavégzési helyszínnel kapcsolatos meglévő karbantartási ütemezési bejegyzések automatikusan törölve lesznek. Ha olyan új naptárbejegyzéseket szeretne létrehozni, amelyek megfelelnek a frissített karbantartási terv beállításának a munkavégzési helyszínen, akkor az adott munkavégzési helyszínhez új karbantartásiterv-ütemezést kell futtatnia. A munkavégzési helyszínek eszköztípusainak, gyártóinak és modelljeinek beállításáról további információt itt talál: [Munkavégzési helyszínek létrehozása](../functional-locations/create-functional-locations.md).

>*Példa:* egy megadott munkavégzési helyszínhez szeretne létrehozni karbantartási tervet olyan módon, hogy a munkavégzési helyszín összes, mindenkori eszközbeállítása szerepeljen benne, amikor a karbantartási tervet ütemezi. Ebben az esetben hozzon létre egy karbantartási tervet, és válassza ki a megfelelő munkavégzési helyszínt, de NE adjon eszközöket a karbantartási tervhez. Ennek eredményeképpen a karbantartási terv ütemezésekor létrejönnek a karbantartási ütemezési sorok minden olyan eszközhöz, amelyek az adott időpontban a munkavégzési helyszínhez kapcsolódnak.

- Ha módosítja az eszköztípusokat, az eszközgyártókat és az eszközmodelleket  az **Eszköztípusok** menüpontban, ezek a módosítások csak a frissített eszköztípust használó új eszközöket érintik. Az eszköztípusok beállításairól további információt itt talál: [Eszköztípusok](../setup-for-objects/object-types.md).  

5. Az **OK** gombra kattintva megkezdheti az eszközök karbantartási ütemezési bejegyzéseinek létrehozását. A létrehozott bejegyzések az **Összes karbantartási ütemezés** listaoldalon jelennek meg. A következő ábra egy példát mutat be a **Karbantartási tervek ütemezése** párbeszédablakra.

![1. ábra](media/09-preventive-maintenance.png)

- A **Karbantartási tervek ütemezése** párbeszédpanelen beállíthatja, hogy a kötegelt feladatok a **Futtatás a háttérben** gyorslapon szabályos időközönként automatikusan létrehozzák a naptári bejegyzéseket.  
- A megelőző karbantartás ütemezése során a rendszer nem hozza létre az olyan várható kezdő dátummal és időponttal rendelkező karbantartási ütemezési sorokat, amelyek korábbiak a rendszerdátumnál és -időpontnál.  

Az alábbi ábra az időalapú karbantartási terv kiszámításának grafikus szemléltetését mutatja be.  

![2. ábra](media/10-preventive-maintenance.jpg)

Tudnivalók a számláló alapú karbantartási tervekkel kapcsolatban: az alábbi ábrákon két különböző számlálóregisztrációs ciklus jelenik meg. Ezek a „V0001” eszközhöz konfigurált karbantartási terven alapulnak, ahol az az eszköz (autó) havonta kb. 2000 km-t fut.

Az első példában a várható 2000 km-t nem minden hónapban érik el. A számlálóalapú karbantartási terv szerint a küszöb 2000 km, ami azt jelenti, hogy a karbantartási terv ütemezésének futtatásakor minden alkalommal létre kell hozni egy karbantartási ütemezési sort az 2000-km-es küszöbérték elérésekor. Az 1. példában 4 regisztrációs sor van, de a 2000 km-es küszöbértéket csak egyszer érik el. Ez azt jelenti, hogy ha például egy három hónapos időszakra vonatkozóan szeretne ütemezési karbantartási terveket futtatni ehhez az eszközhöz, akkor csak egy karbantartási ütemezési sor jön létre.

A következő ábra azt mutatja, hogy havonta legalább 2000 km-t regisztrálnak. Ezért három karbantartási sor jön létre, ha három hónapos időszakra ütemezi a tárgyi eszköz karbantartási terveit. 

Az itt leírt példák azt mutatják, hogy az eszközön végrehajtott összes számlálóregisztráció az eszköz elhasználódásának tendenciájára utal. Ez a tendencia a számítás alapja a karbantartási terv ütemezésének időpontjában.

![3. ábra](media/11-preventive-maintenance.png)

![4. ábra](media/12-preventive-maintenance.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]