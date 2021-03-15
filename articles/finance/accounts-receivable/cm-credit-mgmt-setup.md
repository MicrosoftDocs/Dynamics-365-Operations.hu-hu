---
title: Hitelkezelési pereméterek beállítása
description: Ez a témakör azt mutatja be, milyen beállításokkal lehet konfigurálni a Hitelkezelést a vállalkozás igényeinek kielégítésére.
author: mikefalkner
manager: AnnBe
ms.date: 08/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 98ea865812a0ef187697fadbfc6f576df6595db4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971753"
---
# <a name="credit-management-parameters-setup"></a>Hitelkezelési pereméterek beállítása

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, milyen beállításokkal lehet konfigurálni a Hitelkezelést a vállalkozás igényeinek kielégítésére. A Hitelkezelés szolgáltatásai használatának megkezdéséhez be kell állítani a paramétereket **Követelések és beszedések paraméterei** oldalon (**Követelések és beszedések \> Beállítások \> Követelések és beszedések paraméterei**).

## <a name="credit-parameters"></a>Hitelparaméterek

Négy gyorslap van a **Hitel** szakaszban, ahol megváltoztathatja a Hitelkezelést szabályozó paramétereket: **Hitelvárakoztatások**, **Hitelkezelési ellenőrzőpont**, **Hitelkezelési statisztikák** és **Hitelkorlátok**. A következő szakaszok az egyes gyorslapokon elérhető beállításokat írják le.

### <a name="credit-holds"></a>Hitelfelfüggesztések

- Állítsa be az **Értékesítési rendelések értékei módosításának engedélyezése a várakoztatás feloldását követően** beállítást **Nem**, hogy meg legyen követelve az, hogy a feladási szabályok ismét ellenőrizve legyenek ha az értékesítési rendelés értéke (kiterjesztett ár) növelve lett, amióta az értékesítési rendelést felszabadították a várakoztatási listából. .
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

Beállíthat ütemezést, amely használva lesz az értékesítési rendelések ellenőrzéséhez hitelproblémák szempontjából. A **Hitelkezelési ellenőrzőpont** gyorslap a hitelnyújtási szabályok feldolgozását tartalmazó dokumentum-feladási folyamatokat azonosítja. A hitelezési szabályokat akkor is ellenőrizheti, ha egy pro-forma feladást végez vagy az értékesítési rendelést teljesen feladja. Jelölje be a jelölőnégyzetet, ha meg szeretné határozni, hogy mely feladási folyamatok várakoztassanak egy rendelést, ha a hitelkezelés zárolási szabályai feldolgozását követően a rendszer hibát talál.

Megadhatja azt is, hogy hány nap türelmi idő elteltével vizsgálják újra a hitelezési szabályokat. Annak ellenére, hogy meghatározhatja azt, hogy a hitelkezelési szabályok ellenőrizve legyenek a feladáskor a szabályokat a megadott türelmi idő alatta a rendszer nem ellenőrzi. Például egy értékesítési rendelést az 1. napon megerősít, és két nap türelmi időt ad meg a visszaigazolási lépéshez. Ebben az esetben a hitelszabályok nem lesznek ellenőrizve a következő feladási lépésnél (például a rendelés csomagjegyzékének létrehozásakor vagy számlázáskor) a 4. napig. 4. napon vagy azt követően a program újra ellenőrzi a szabályokat a feladás alkalmával, és a türelmi idő napjainak száma a következő feladási ellenőrzőponthoz megadott értékre módosul.

Ha nem adja meg a türelmi idő napjainak számát, a rendszer minden olyan feladási lépésnél ellenőrizni fogja a hitelszabályokat, amely a hitelkezelési szabályok futtatására van beállítva. Ha feladás nélkül szabadítja fel az értékesítési rendelést, majd újrafuttatja ugyanezt a rendelésfeldolgozási lépést, akkor a program újra ellenőrzi a hitelszabályokat. Előfordulhat például, hogy egy rendelés a visszaigazolást követően várakoztatva lesz, és a felszabadíthatja azt feladással vagy anélkül. Ebben az esetben a rendelés újra várakoztatva lesz, ha ismételten megerősíti azt. Használja a türelmi napokat, ha a rendelésnek át kell kerülnie a következő feldolgozási lépéshez anélkül, hogy ismét várakoztatva lenne.

Nem adhat meg türelmi napot néhány feladási ellenőrzőponthoz, de mások esetében nem. Minden feladási ellenőrzőpontot be kell állítania, hogy a türelmi napok rendelkezésére álljanak, vagy mindegyiket be kell állítani, hogy ne legyenek türelmi napjaik.

- A **Feladás** jelölőnégyzet bejelölésével futtathatja a hitelkezelési szabályokat, amikor a sorban megjelenő feladási ellenőrzőpontot futtatja. Ha nem jelöli be a jelölőnégyzetet, akkor a program csak egyszer ellenőrzi a szabályokat a teljes feladási folyamat során.
- Ha bejelöli a **Feladás** jelölőnégyzetet, adja meg, hogy hány türelmi napnak kell eltelnie a zárolási szabályok újbóli ellenőrzése előtt. Ha a **Feladás** jelölőnégyzet nincs bejelölve, akkor nem adhat meg türelmi napokat.
- A **Pro forma** jelölőnégyzet bejelölésével futtathatja a hitelkezelési szabályokat, amikor a sorban megjelenő pro-forma feladási ellenőrzőpontot futtatja. A legtöbb esetben az értékesítési rendelés feladásakor megjelenő párbeszédpanelen a **Feladás** mező értéke **Nem**.
- Ha bejelöli a **Feladás** jelölőnégyzetet, adja meg, hogy hány türelmi napnak kell eltelnie a zárolási szabályok újbóli ellenőrzése előtt. Ha a **Feladás** jelölőnégyzet nincs bejelölve, akkor nem adhat meg türelmi napokat.

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

### <a name="number-sequences-and-shared-number-sequence-parameters"></a>Számsorozatok és megosztott számsorozat paraméterei

A hitelkorlát-korrekciók feldolgozásához egy napló-azonosító szükséges. Meg kell adnia a hitelkorlát-korrekció számát, amely a naplóazonosító generálására szolgál.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]