---
title: Vevő korosítási pillanatképek
description: Ez a cikk az ügyfelek öregedési pillanatképeiről nyújt tájékoztatást. A korosítási pillanatkép kiszámítja egy vevőcsoport korosított egyenlegeit egy időpontra.
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
ms.openlocfilehash: 88145cdccfe3f1d0d3de4e31dfa519b27df6550a
ms.sourcegitcommit: c5f2cba3c2b0758e536eeaaa40506659a53085e1
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/12/2022
ms.locfileid: "9643685"
---
# <a name="customer-aging-snapshots"></a>Vevő korosítási pillanatképek

[!include [banner](../includes/banner.md)]

Ez a cikk az ügyfelek öregedési pillanatképeiről nyújt tájékoztatást. A korosítási pillanatkép kiszámítja egy vevőcsoport korosított egyenlegeit egy időpontra. Létrehozhat korosítási pillanatképrekordokat minden vevőre vagy egy adott vevőgyűjtőben levő vevőkre vonatkozóan.

A korosítási pillanatkép információ megjelennek a **Korosított egyenlegek** listaoldalon és a **Beszedés** lapon. A listalap használatához előbb létre kell hozni egy korosítási pillanatképet a **Korosított egyenlegek** listaoldalon. A listaoldal csak olyan vevőkről sorol fel információt, amelyek számára lett korosítási pillanatkép készítve.

A **Vevői jóváírások és beszedések** munkaterületen a vevők korosítása is látható. A további tudnivalókat lásd a [Jóváírás- és beszedéskezelés Power BI-tartalomban](credit-collections-power-bi.md).

> [!NOTE]
> Az öregedő pillanatkép létrehozásához szükséges idő csökkentése érdekében kapcsolja be a következő funkciókat a **Funkciókezelés** munkaterületen: **Az ügyfelek öregedési teljesítményének javítása Az ügyfelek öregedési teljesítményének javítása**
> **az ügyfélcsoportok segítségével**  
> Ha mindkét funkció engedélyezve van, **az ügyfélkészletek** használhatók az öregedési pillanatkép létrehozásakor. 

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
- **Nulla egyenlegű vevőkkel együtt** –Állítsa ezt a beállítást **Igen**, ha az egyenlegüktől függetlenül minden vevőt szerepeltetni szeretne. Ha az összes ügyfelet is bevonja, javasoljuk, hogy kapcsolja be mind az ügyfél öregedési teljesítményének javítását, mind **az** ügyfél öregedési teljesítményének javítását az ügyfélállomány funkcióival **.** Állítsa **Nem** beállításra, hogy csak egyenleggel rendelkező vevők szerepeljenek. Ez a beállítás segít felgyorsítani a teljesítményt, mert az egyenleggel nem rendelkező ügyfeleket kihagyja a rendszer.
- **Hitelkeret-számítások megkerülése az öregedés** során – Ha ez a beállítás Igen **értékre** van állítva, az öregedési folyamat nem számítja ki újra a Csomagolási bizonylat részösszegét **,** a Nyitott rendelés részösszegét **és** az **egyes ügyfelek számára elérhető** jóváírást. Ezek az egyenlegek az **Aged egyenlegek** oldalon jelennek meg, a FactBoxban, a Hitelkeret **alatt**. Az öregedési folyamat során a gyorsabb teljesítmény érdekében állítsa ezt a beállítást Igen **értékre**. Állítsa Nem **értékre** az egyensúlyok újraszámításához az öregedési folyamat futtatásakor. 
- **Vállalattartomány** – a **Vállalattartomány** lapon válassza ki azokat a jogi személyeket (vállalatokat), amelyek bele vannak foglalva a korosítási pillanatképbe. Csak a központosított kifizetésekhez beállított jogi személyek érhetők el kiválasztásra. A kijelölt jogi személyek tranzakciói ezután a korosítási időszakokba kerülnek azokhoz a vevőkhöz, akiknek azonos a félazonosítója az összes ilyen jogi személynél. A pénznemértékek azon jogi személy könyvelési pénznemében lesznek átváltva amelyikkel a korosítási pillanatkép létrehozásakor bejelentkezett.

Javasoljuk, hogy ezt a folyamatot kötegben futtáshoz ütemezze.

> [!NOTE]
> A kötegteljesítmény javításához a korosítási pillanatképek létrehozásakor, írjon be egy számot a **Kötegfeladatok maximális száma** mezőben a **Beszedések alapértékei** gyorslapon a **Beszedések** lapon a **Kinnlévőségek paraméterei** oldalon. **Az Életkori ügyfélegyenlegek mezőben azt javasoljuk**, hogy kezdje a 12 és **20** **közötti** értékkel, majd állítsa be az értéket, hogy optimalizálja a feldolgozást a helyzetéhez. Nem javasoljuk, hogy ezt az értéket 30-nál **nagyobbra** állítsa, mivel ez hatással lesz a teljesítményre. 

