---
title: Vevő korosítási pillanatképek
description: Ez a cikk a vevők korosítási pillanatképekkel kapcsolatban tartalmaz tájékoztatást. A korosítási pillanatkép kiszámítja egy vevőcsoport korosított egyenlegeit egy időpontra.
author: JodiChristiansen
ms.date: 10/10/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2021-05-05
ms.dyn365.ops.version: 10.0.17
ms.search.form: ''
ms.openlocfilehash: e4ccc8ac9b5374ca0713167a17b8704727c687fd
ms.sourcegitcommit: 9740f9b41a7dcf1821c6baccb2e05b9865ac2966
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/15/2022
ms.locfileid: "9775241"
---
# <a name="customer-aging-snapshots"></a>Vevő korosítási pillanatképek

[!include [banner](../includes/banner.md)]

Ez a cikk a vevők korosítási pillanatképekkel kapcsolatban tartalmaz tájékoztatást. A korosítási pillanatkép kiszámítja egy vevőcsoport korosított egyenlegeit egy időpontra. Létrehozhat korosítási pillanatképrekordokat minden vevőre vagy egy adott vevőgyűjtőben levő vevőkre vonatkozóan.

A korosítási pillanatkép információ megjelennek a **Korosított egyenlegek** listaoldalon és a **Beszedés** lapon. A listalap használatához előbb létre kell hozni egy korosítási pillanatképet a **Korosított egyenlegek** listaoldalon. A listaoldal csak olyan vevőkről sorol fel információt, amelyek számára lett korosítási pillanatkép készítve.

A **Vevői jóváírások és beszedések** munkaterületen a vevők korosítása is látható. A további tudnivalókat lásd a [Jóváírás- és beszedéskezelés Power BI-tartalomban](credit-collections-power-bi.md).

> [!NOTE]
> A korosítási pillanatképek **létrehozásához** szükséges idő csökkentése érdekében kapcsolja be a szolgáltatáskezelés munkaterületének következő szolgáltatásait: 
> - **Vevői korosítási teljesítmény javítása** 
> - **Vevőkorosítási teljesítmény javítása vevőkészletekkel**  
>Ha mindkét funkció engedélyezve van, **a Vevőkészletek** használhatók a korosítási pillanatkép létrehozásakor. 

Vevői korosítási pillanatkép létrehozásakor a következő mezők használatával adja meg a vevőre vonatkozó adatokat:

- **Korosítási időszak definíciója** – válassza ki a korosítási időszak definícióját a korosítási pillanatképhez. Egy korosítási pillanatképet rendelhet minden egyes korosítási időszak definíciójához. A korosítási pillanatképet és a korosítási időszak definícióját külön kell létrehozni.
- **Gyűjtőazonosító** – Ez a mező nem kötelező. A készlet használatával lehet meghatározni a korosítási pillanatképben feldolgozható vevők halmazát. Ha egy vevőgyűjtőt választ ki ebben a mezőpben jelölve, akkor egy korosítási pillanatkép csak az adott vevőgyűjtőhöz tartozó vevőfiókokhoz jön létre. A kijelölt vevőgyűjtőnek **Korosítási pillanatfelvétel** típusúnak kell lennie. Ha üresen hagyja ezt a mezőt, minden vevői számlához létrejön egy korosítási pillanatkép.


- **Feltételek** – a korosítási pillanatkép a kiválasztott dátumtól függően lesz korosítva:

    - **Tranzakció dátuma** – Az egyes tranzakció korosítása a tranzakció dátuma alapján történik.
    - **Határidő** – Az egyes tranzakciók korosítása a határideje alapján történik.
    - **Bizonylat dátuma** – Az egyes tranzakciók korosítása a bizonylati dátumuk alapján.

- **Korosítás kezdete** – Válassza ki a korosítási pillanatképhez **Aktuális dátumként** használni kívánt dátumot. A korosítási időszakok számítása azon a dátumon alapul. 

    - **Mai dátum** – A rendszerdátum használata. Akkor válassza ezt a lehetőséget, ha a feldolgozás ismétlődő kötegként futtatásra van beállítva. Ezt követően a köteg minden futtatásakor annak a futtatásnak a rendszerdátumát használja a rendszer.
    - **Kiválasztott dátum** – Egy szabadon választott dátum használata. Ha ezt a lehetőséget választja, akkor korosítási dátumot is meg kell adnia.

   Az aktuális korosítási időszak például 30 nap. Ha a **Mai dátumot** választja ebben a mezőben, az aktuális korosítási időszak a mai napon kezdődik, és az előző 29 napot is tartalmazza. Ha a **Kiválasztott dátum** lehetőséget választja, és megad egy dátumot, az aktuális korosítási időszak a megadott dátumon kezdődik, és az előző 29 napot is tartalmazza.

- **Beszedési állapot frissítése** – Az **Igen** beállítással frissítheti a **Beszedések** lapon található tranzakciókat **Fizetési ígéret** értékről **Nem tartotta a fizetési ígéretet** értékre, ha a korosítási dátum túllépte a **Fizetési ígéret** mezőben megadott dátumot. Válassza a **Nem** lehetőséget, hogy a gyűjtemény állapotát változatlanul hagyja a **Beszedések** lapon.
- **Nulla egyenlegű vevőkkel együtt** –Állítsa ezt a beállítást **Igen**, ha az egyenlegüktől függetlenül minden vevőt szerepeltetni szeretne. Ha minden vevőt tartalmaz, javasoljuk, **·** **hogy a vevői korosítási teljesítmény javítását és a vevők korosítási teljesítményének javítását is kapcsolja be a vevői készlet funkcióival.** Állítsa **Nem** beállításra, hogy csak egyenleggel rendelkező vevők szerepeljenek. Ez a beállítás gyorsítsa a teljesítményt, mivel kimaradnak azok a vevők, akik nem egyenleggel.
- **A hitelkeret-számítások** kihagyása a korosítás során – **·** **ha** ez a beállítás Igen, a korosítási folyamat nem számítja újra a Csomagjegyzék részösszegét, **·** **a** Nyitott rendelés részösszegét és a Jóváírást, amely minden vevőnél rendelkezésre áll. Ezek az egyenlegek a Koros egyenlegek **oldalon**, a Hitelkeret alatti tényszámok **lapon jelennek meg**. A korosítási folyamat során gyorsabb teljesítmény érdekében állítsa Ezt a lehetőséget Igen **beállításra**. Állítsa Nem beállításra **az** egyenlegek újraszámításához a korosítási folyamat futtatásakor. 
- **Vállalattartomány** – a **Vállalattartomány** lapon válassza ki azokat a jogi személyeket (vállalatokat), amelyek bele vannak foglalva a korosítási pillanatképbe. Csak a központosított kifizetésekhez beállított jogi személyek érhetők el kiválasztásra. A kijelölt jogi személyek tranzakciói ezután a korosítási időszakokba kerülnek azokhoz a vevőkhöz, akiknek azonos a félazonosítója az összes ilyen jogi személynél. A pénznemértékek azon jogi személy könyvelési pénznemében lesznek átváltva amelyikkel a korosítási pillanatkép létrehozásakor bejelentkezett.

Javasoljuk, hogy ezt a folyamatot kötegben futtáshoz ütemezze.

> [!NOTE]
> A kötegteljesítmény javításához a korosítási pillanatképek létrehozásakor, írjon be egy számot a **Kötegfeladatok maximális száma** mezőben a **Beszedések alapértékei** gyorslapon a **Beszedések** lapon a **Kinnlévőségek paraméterei** oldalon. A Kor **vevői** egyenlegek mezőben javasoljuk, hogy 12 **és** 20 **közötti értékkel kezdődjon,** majd a feldolgozás optimalizálása érdekében módosítsa az értéket. Ezt az értéket nem javasolt **30-as** értéknél nagyobbra tenni, mert ez befolyásolja a teljesítményt. 

