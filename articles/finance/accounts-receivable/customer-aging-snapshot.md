---
title: Vevő korosítási pillanatképek
description: Ez a témakör a vevőkorosítási pillanatképekkel kapcsolatban tartalmaz információkat. A korosítási pillanatkép kiszámítja egy vevőcsoport korosított egyenlegeit egy időpontra.
author: JodiChristiansen
ms.date: 05/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-05-05
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 7761366c0372c105ecbd4281c7bafa44bf6cf7b5
ms.sourcegitcommit: 905a8c7a0c1bc06ada2acfba913dfe5f7b44ea16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/14/2021
ms.locfileid: "6039927"
---
# <a name="customer-aging-snapshots"></a>Vevő korosítási pillanatképek

[!include [banner](../includes/banner.md)]

Ez a témakör a vevőkorosítási pillanatképekkel kapcsolatban tartalmaz információkat. A korosítási pillanatkép kiszámítja egy vevőcsoport korosított egyenlegeit egy időpontra. Létrehozhat korosítási pillanatképrekordokat minden vevőre vagy egy adott vevőgyűjtőben levő vevőkre vonatkozóan.

A korosítási pillanatkép információ megjelennek a **Korosított egyenlegek** listaoldalon és a **Beszedés** lapon. A listalap használatához előbb létre kell hozni egy korosítási pillanatképet a **Korosított egyenlegek** listaoldalon. A listaoldal csak olyan vevőkről sorol fel információt, amelyek számára lett korosítási pillanatkép készítve.

> [!NOTE]
> A korosítási pillanatképek létrehozásához szükséges idő csökkentése érdekében kapcsolja be a **Vevőkorosítási teljesítmény javítása** funkciót a **Szolgáltatáskezelés** munkaterületen. Ha viszont be van kapcsolva ez a funkció, ne használjon vevőgyűjtőket. Ha egy vevőgyűjtő van kiválasztva, a funkció nem működik, de így is létrehozhat korosítási pillanatképet.

Vevői korosítási pillanatkép létrehozásakor a következő mezők használatával adja meg a vevőre vonatkozó adatokat:

- **Korosítási időszak definíciója** – válassza ki a korosítási időszak definícióját a korosítási pillanatképhez. Egy korosítási pillanatképet rendelhet minden egyes korosítási időszak definíciójához. A korosítási pillanatképet és a korosítási időszak definícióját külön kell létrehozni.
- **Gyűjtőazonosító** – Ez a mező nem kötelező. A készlet használatával lehet meghatározni a korosítási pillanatképben feldolgozható vevők halmazát. Ha egy vevőgyűjtőt választ ki ebben a mezőpben jelölve, akkor egy korosítási pillanatkép csak az adott vevőgyűjtőhöz tartozó vevőfiókokhoz jön létre. A kijelölt vevőgyűjtőnek **Korosítási pillanatfelvétel** típusúnak kell lennie. Ha üresen hagyja ezt a mezőt, minden vevői számlához létrejön egy korosítási pillanatkép.

    > [!NOTE]
    > Ha a **Vevői korosítási teljesítmény javítása** funkció be van kapcsolva, ne válasszon ki vevőgyűjtőt.

- **Feltételek** – a korosítási pillanatkép a kiválasztott dátumtól függően lesz korosítva:

    - **Tranzakció dátuma** – Az egyes tranzakció korosítása a tranzakció dátuma alapján történik.
    - **Határidő** – Az egyes tranzakciók korosítása a határideje alapján történik.
    - **Bizonylat dátuma** – Az egyes tranzakciók korosítása a bizonylati dátumuk alapján.

- **Korosítás kezdete** – Válassza ki a korosítási pillanatképhez **Aktuális dátumként** használni kívánt dátumot. A korosítási időszakok számítása azon a dátumon alapul. 

    - **Mai dátum** – A rendszerdátum használata. Akkor válassza ezt a lehetőséget, ha a feldolgozás ismétlődő kötegként futtatásra van beállítva. Ezt követően a köteg minden futtatásakor annak a futtatásnak a rendszerdátumát használja a rendszer.
    - **Kiválasztott dátum** – Egy szabadon választott dátum használata. Ha ezt a lehetőséget választja, akkor korosítási dátumot is meg kell adnia.

    Az aktuális korosítási időszak például 30 nap. Ha a **Mai dátumot** választja ebben a mezőben, az aktuális korosítási időszak a mai napon kezdődik, és az előző 29 napot is tartalmazza. Ha a **Kiválasztott dátum** lehetőséget választja, és megad egy dátumot, az aktuális korosítási időszak a megadott dátumon kezdődik, és az előző 29 napot is tartalmazza.

- **Beszedési állapot frissítése** – Az **Igen** beállítással frissítheti a **Beszedések** lapon található tranzakciókat **Fizetési ígéret** értékről **Nem tartotta a fizetési ígéretet** értékre, ha a korosítási dátum túllépte a **Fizetési ígéret** mezőben megadott dátumot. Válassza a **Nem** lehetőséget, hogy a gyűjtemény állapotát változatlanul hagyja a **Beszedések** lapon.
- **Nulla egyenlegű vevőkkel együtt** –Állítsa ezt a beállítást **Igen**, ha az egyenlegüktől függetlenül minden vevőt szerepeltetni szeretne. Ha minden vevőt szerpeltet, javasoljuk, hogy kapcsolja be a **Vevői korosítási teljesítmény javítása** és ne használjon vevőgyűjtőket. Állítsa **Nem** beállításra, hogy csak egyenleggel rendelkező vevők szerepeljenek. Ez a beállítás segít felgyorsítani a teljesítményt, mert a program kihagyja az egyenleggel nem rendelkező vevőket.
- **Vállalattartomány** – a **Vállalattartomány** lapon válassza ki azokat a jogi személyeket (vállalatokat), amelyek bele vannak foglalva a korosítási pillanatképbe. Csak a központosított kifizetésekhez beállított jogi személyek érhetők el kiválasztásra. A kijelölt jogi személyek tranzakciói ezután a korosítási időszakokba kerülnek azokhoz a vevőkhöz, akiknek azonos a félazonosítója az összes ilyen jogi személynél. A pénznemértékek azon jogi személy könyvelési pénznemében lesznek átváltva amelyikkel a korosítási pillanatkép létrehozásakor bejelentkezett.

Javasoljuk, hogy ezt a folyamatot kötegben futtáshoz ütemezze.

> [!NOTE]
> A kötegteljesítmény javításához a korosítási pillanatképek létrehozásakor, írjon be egy számot a **Kötegfeladatok maximális száma** mezőben a **Beszedések alapértékei** gyorslapon a **Beszedések** lapon a **Kinnlévőségek paraméterei** oldalon. A **Vevői egyenlegek korosítása** mezőben ajánlott a **100**-as alapértelmezett értékkel kezdődni, majd az érték módosításával optimalizálni a feldolgozást az ön helyzetéhez.

A **Vevői jóváírások és beszedések** munkaterületen a vevők korosítása is látható. A további tudnivalókat lásd a [Jóváírás- és beszedéskezelés Power BI-tartalomban](credit-collections-power-bi.md).
