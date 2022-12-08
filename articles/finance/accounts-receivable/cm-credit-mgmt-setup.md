---
title: Hitelkezelési pereméterek beállítása
description: Ez a témakör ismerteti azokat a beállításokat, amelyek segítségével a hitelkezelést a vállalat igényeinek megfelelően konfigurálhatja.
author: JodiChristiansen
ms.date: 11/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 8955518e7b5c0200d3827c1c22b7d150a09be244
ms.sourcegitcommit: fb9b6969218f2b82f0a4c72bfad75387fe00395c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/22/2022
ms.locfileid: "9799545"
---
# <a name="credit-management-parameters-setup"></a>Hitelkezelési pereméterek beállítása

[!include [banner](../includes/banner.md)]

Ez a témakör ismerteti azokat a beállításokat, amelyek segítségével a hitelkezelést a vállalat igényeinek megfelelően konfigurálhatja. A Hitelkezelés szolgáltatásai használatának megkezdéséhez be kell állítani a paramétereket **Követelések és beszedések paraméterei** oldalon (**Követelések és beszedések \> Beállítások \> Követelések és beszedések paraméterei**).

## <a name="credit-parameters"></a>Hitelparaméterek

Négy gyorslap van a **Hitel** szakaszban, ahol megváltoztathatja a Hitelkezelést szabályozó paramétereket: **Hitelvárakoztatások**, **Hitelkezelési ellenőrzőpont**, **Hitelkezelési statisztikák** és **Hitelkorlátok**. A következő szakaszok az egyes gyorslapokon elérhető beállításokat írják le.

### <a name="credit-holds"></a>Hitelfelfüggesztések

- Állítsa be az **Értékesítési rendelések értékei módosításának engedélyezése a várakoztatás feloldását követően** beállítást **Nem**, hogy meg legyen követelve az, hogy a feladási szabályok ismét ellenőrizve legyenek ha az értékesítési rendelés értéke (kiterjesztett ár) növelve lett, amióta az értékesítési rendelést felszabadították a várakoztatási listából.
- A **Visszavont rendelések okai** mezőben válassza ki azt a felszabadítási okot, amelyet alapértelmezésként fog használni, amikor az értékesítési rendelést, amely a hitelkeretkezelésen esett át érvényteleníti.
- A **Ügyfelek hitelcsoportjainak hitelkorlátjának ellenőrzése** beállítást állítsa **Igen** értékre, ha ellenőrizni szeretné egy ügyfélhitelcsoport hitelkorlátját, ha az értékesítési rendelés egy ügyfélhitelcsoporthoz tartozik. A rendszer ellenőrzi a csoport hitelkeretét, majd ha szükséges, a program ellenőrzi a vevő hitelkeretét.
- Állítsa be a **Hitelkorlát ellenőrzése, aha a fizetési feltételek magasabbak lettek** beállítás **Igen** értékre, hogy a fizetési feltételek rangsorolása ellenőrizve legyen annak meghatározásához, hogy a fizetési feltételek az értékesítési rendelésen eltérnek az ügyfél alapértelmezett fizetési feltételeitől. Ha az új fizetési feltételek magasabb rangúak, mint az eredeti fizetési feltételek, akkor a rendelés a hitelkeretkezeléssel kapcsolatos várakoztatásra kerül.
- Állítsa be a **Hitelkorlát ellenőrzése, ha a kiegyenlítési engedmény magasabb lett** beállítás **Igen** értékre, hogy a kiegyenlítési kedvezmények rangsorolása ellenőrizve legyen annak meghatározásához, hogy a készpénzfizetési engedmény az értékesítési rendelésen eltér-e az ügyfél alapértelmezett készpénzfizetési engedményétől. Ha az új készpénzfizetési engedmény magasabb rangú, mint az eredeti készpénzfizetési engedmény, akkor a rendelés a hitelkeretkezeléssel kapcsolatos várakoztatásra kerül.
- A **Módosított rendelések felszabadításának** oka mezőben válassza ki azt a felszabadítási okot, amelyet alapértelmezésként fog használni, amikor a módosított rendeléseket a program automatikusan felszabadítja a hitelkezelési várakoztatásból.
- Állítsa be a **A hitelkeret elévült zárolási szabályának figyelmen kívül hagyása , ha a lejárati dátum üres** beállítást **Igen** értékre a **Hitelkorlát lejárt** szabály viselkedésének szabályozásához. A rendelés blokkolásához, ha a lejárati dátum üres állítsa a beállítást **Nem** értékre.
- A Raktárkezelés modulban a rakományok az értékesítési rendelés bevitele alkalmával hozhatók létre. A **Zárolt sorok eltávolítása** beállítást állítsa **Nem** értékre, ha az értékesítésirendelés-sorokat a rakományon szeretné hagyni, ha az értékesítési rendelés hitelkezelésre kerül. A rakomány nem dolgozható fel, amíg az értékesítési rendelés várakoztatva van. A beállítást állítsa **Igen** értékre, ha az értékesítésirendelés-sorokat a rakományról el szeretné távolítani, ha az értékesítési rendelés hitelkezelésre kerül. A rakományt ezután fel lehet dolgozni.
- Az értékesítési rendelések automatikusan felszabadíthatók a hitelkezelési felülvizsgálatból. Az **Automatikus felszabadítás oka** mezőben válassza ki azt a felszabadítási okot, amelyet a rendszer alapértelmezés szerint az értékesítési rendelések felszabadításakor használ.
- Az értékesítési rendelések automatikusan felszabadíthatók a hitelkezelési felülvizsgálatból. Az **Automatikus felszabadítás** mezőben válassza a **Feladás nélkül** lehetőséget, hogy egy rendelésen felszabadítsa a várakoztatást. A rendelést várakoztatásra helyező folyamatot manuálisan kell futtatnia. Válassza a **Feladással** lehetőséget a visszatartás eltávolításához és a dokumentum feladásához ugyanazzal a feladási eljárással történik, amelyet a rendszer a visszatartáskor futtatott.

### <a name="credit-management-checkpoint"></a>Hitelkezelési ellenőrzőpont

Beállíthat ütemezést, amely használva lesz az értékesítési rendelések ellenőrzéséhez hitelproblémák szempontjából. A **Hitelkezelési ellenőrzőpont** gyorslap a hitelnyújtási szabályok feldolgozását tartalmazó dokumentum-feladási folyamatokat azonosítja. A hitelezési szabályokat akkor is ellenőrizheti, ha egy pro-forma feladást végez vagy az értékesítési rendelést teljesen feladja. A jelölőnégyzetek beírásával meghatározhatja azokat a feladási folyamatokat, amelyek miatt a rendeléseket fel kell függeszteni, ha probléma van a hitelkezelési zárolási szabályok feldolgozása után.

Megadhatja azt is, hogy hány nap türelmi idő elteltével vizsgálják újra a hitelezési szabályokat. Annak ellenére, hogy meghatározhatja azt, hogy a hitelkezelési szabályok ellenőrizve legyenek a feladáskor a szabályokat a megadott türelmi idő alatta a rendszer nem ellenőrzi. Visszaigazolódhat például az értékesítési rendelés az első napon, és két türelmi napot ad meg a visszaigazolási lépéshez. Ebben az esetben a jóváírási szabályokat a következő feladási lépésnél (például a csomagjegyzék létrehozása vagy a rendelés számlázása) a négy napig nem ellenőrzi a rendszer. A negyedik napon vagy azt követően a rendszer a feladáskor ismét ellenőrzi a szabályokat, és a türelmi napok száma a következő feladási ellenőrzőpontnál megadott értékre módosul.

Ha nem adja meg a türelmi idő napjainak számát, a rendszer minden olyan feladási lépésnél ellenőrizni fogja a hitelszabályokat, amely a hitelkezelési szabályok futtatására van beállítva. Ha feladás nélkül szabadítja fel az értékesítési rendelést, majd újrafuttatja ugyanezt a rendelésfeldolgozási lépést, akkor a program újra ellenőrzi a hitelszabályokat. Előfordulhat például, hogy egy rendelés a visszaigazolást követően várakoztatva lesz, és a felszabadíthatja azt feladással vagy anélkül. Ebben az esetben a rendelés újra várakoztatva lesz, ha ismételten megerősíti azt. Használja a türelmi napokat, ha a rendelésnek át kell kerülnie a következő feldolgozási lépéshez anélkül, hogy ismét várakoztatva lenne.

> [!Note]
> Ha egy feladási ellenőrzőponthoz türelmi nap van megadva, minden feladásra megjelölt ellenőrzőpontnak türelmi napjai vannak.

- Jelölje be **a Feladás** jelölőnégyzetet, ha a sorban látható feladási ellenőrzőpont futtatásakor futtatni kell a jóváírás-kezelési szabályokat. Ha nem jelöl be ezt a jelölőnégyzetet, a szabályok csak egyszer lesznek ellenőrizve a teljes feladási folyamat során.
- Ha bejel megadja **a** Feladás jelölőnégyzetet, adja meg, hogy hány türelmi időnek kell eltelni a blokkolási szabályok újraellenőrzése előtt. Nem adhat hozzá türelmi napokat, ha **a Feladás** jelölőnégyzet nincs be ellenőrizve.
- Jelölje be **a Pro forma jelölőnégyzetet**, ha a sorban látható pro forma feladási ellenőrzőpont futtatásakor futtatni kell a jóváírás-kezelési szabályokat. A legtöbb esetben az értékesítési rendelés feladásakor megjelenő párbeszédpanelen a **Feladás** mező értéke **Nem**.
- Ha bejel megadja **a** Feladás jelölőnégyzetet, adja meg, hogy hány türelmi időnek kell eltelni a blokkolási szabályok újraellenőrzése előtt. Nem adhat hozzá türelmi napokat, ha **a Feladás** jelölőnégyzet nincs be ellenőrizve.

### <a name="credit-management-statistics"></a>Hitelkezelési statisztika

A **vevői hitelkezelési statisztika** adatterületen számos hitelezési statisztika szerepel a **Vevő** oldalon. Meg kell adnia több értéket, amelyek szükségesek a statisztikák kiszámításához. Adja meg, hogy hány hónap legyen felhasználva a következő értékek számítására a **Vevői hitelezési statisztikák** adatterületen:

1. Kintlevőség-elmaradási napok száma 1
2. Kintlevőség-elmaradási napok száma 2
3. Átlagos egyenleg 1
4. Átlagos egyenleg 2
5. Átlagos hitelkorlát %-os értéke
6. Átlagos expozíció %-os értéke

### <a name="credit-limits"></a>Hitelkeretek

- A Hitelkezelés esetében a vevői hitelkorlát a vevő pénznemében jelenik meg. Meg kell adnia az árfolyamtípust a hitelkerethez az ügyfél pénznemében. A **Hitelkorlát árfolyamtípusa** mezőben válassza ki azt az árfolyamtípust, amelyet az elsődleges hitelkeret és a vevő hitelkeretének átváltásához kíván használni.
- A **Hitelkeret manuális szerkesztésének engedélyezése** beállítás **Nem** értékre állításával megakadályozhatja, hogy a felhasználók módosítsák a hitelkorlátot a **Vevő** oldalon. Ha ez a beállítás **Nem** értékre van állítva, akkor a vevő hitelkeretének módosítása csak hitelkorlát-korrekciós tranzakciók feladásával végezhető el.
- A Készletfoglalások **mellőzése** beállítás Igen **beállítással** figyelmen kívül hagyja a készletfoglalásokat, ha a hitelkezelés zárolási szabályainak be van jelölve. Ebben az esetben a program ellenőrzi a mennyiségeket, és ellenőrzi a türelmi időszakokat, függetlenül a készletfoglalási mennyiségtől.
- Ha a Hitelkezelés engedélyezve van, **akkor** a hitelkeret-túli idő túllépése esetén az Üzenet beállítás csak a szabadszöveges számlák feldolgozására használható. Bár a vevők akkor is hozzáadnak üzeneteket az értékesítési rendelésekhez, ha túllépték a hitelkeretüket, az üzenetek jelenléte nem tiltja le a visszaigazolást, a kitárolási listák és csomagjegyzékek nyomtatását, illetve a számlák feladását.

    Alapértelmezés szerint engedélyezve van a hitelkezelés, de le lehet tiltani. Ha engedélyezve van, a jóváírás-kezelés blokkolási szabályai és ellenőrzőpontjai segítségével lehet azonosítani, hogy a vevők mikor lépték túl a hitelkeretét. Ha a mező le van tiltva, akkor a hitelkeret túllépése esetén az értékesítési rendelésekhez az Üzenet mező beállítása alapján hozzáadott üzenetek segítséget adnak annak azonosításához, **hogy** a vevők mikor lépték túl a hitelkeretét.

### <a name="number-sequences-and-shared-number-sequence-parameters"></a>Számsorozatok és megosztott számsorozat paraméterei

A hitelkorlát-korrekciók feldolgozásához egy napló-azonosító szükséges. Meg kell adnia a hitelkorlát-korrekció számát, amely a naplóazonosító generálására szolgál.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
