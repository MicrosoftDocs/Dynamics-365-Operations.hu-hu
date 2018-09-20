---
title: "Online pénzügyi konszolidációk"
description: "Ez a témakör leírja az online pénzügyi konszolidációkat a főkönyvben."
author: aprilolson
manager: AnnBe
ms.date: 07/09/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.translationtype: HT
ms.sourcegitcommit: 2a9ceb774a8f205e39abe6a12a0deb69dd4cb69b
ms.openlocfilehash: fd29dc5f932c9cd274a42923e1ff659dd5d8e9d6
ms.contentlocale: hu-hu
ms.lasthandoff: 08/20/2018

---

# <a name="consolidate-online"></a>Online konszolidálás

[!include [banner](../includes/banner.md)]

Ez a témakör leírja az online pénzügyi konszolidációkat a főkönyvben. Ezen témakör elolvasása előtt olvassa el a [Pénzügyi konszolidáció és devizaátváltás](financial-consolidations-currency-translation.md) témakört.

A beállítás befejezése után adja meg a konszolidáció részleteit a **Konszolidálás [Online]** oldalon. Amikor végzett, kattintson az **OK** VAGY a **Köteg** lehetőségre a konszolidáció feldolgozásához.

## <a name="criteria"></a>Feltételek
A **Feltételek** lapon a **Konszolidálás [Online]** oldalon megadhatja a számlákat, az időszakokat és a konszolidálandó adatok típusát.

![Feltételek lap](./media/criteria-consolidate-online.png "Feltételek lap")

Itt találja a lap különböző mezőinek magyarázatát:

- **Leírás** – Az éppen konszolidálni kívánt időszak pontos leírása.
- **Fő számla** – Ezen rész mezői segítségével határozhatja meg, hogy mely fő számlákat fogja feldolgozni.

    - **Kezdőéték** és **Záróérték** – Megadhatja a feldolgozandó fiókokat. Ha üresen hagyja ezeket a mezőket, minden vállalat minden számlája átkerül a konszolidációs vállalathoz. Következésképpen ha négy vállalatot konszolidál és mindegyik vállalatnál különböző számlatükörrel rendelkezik, mind a négy vállalat minden számlája létre lesz hozva a konszolidációs vállalatnál.
    - **Konszolidációs számla használata** – Ha ezt a lehetőséget, **Igen** értékre állítja a **Konszolidációs számla kiválasztásának forrása** mező elérhetővé válik. Ebben a mezőben megadhatja hogy az összes számla konszolidálva legyen a konszolidációs számlára, amely be van állítva a **Fő számlák** lapon, és azt, hogy szeretné-e a konszolidációsszámla-csoportok közül kiválasztani a számlát.
    - **Konszolidációsszámla-csoport** – Kiválaszthatja a csoportot, amely használva lesz a fő fiók hozzárendeléséhez a konszolidációhoz.

- **Konszolidációs időszak** – Ennek a résznek a mezői segítségével határozhatja meg a konszolidációs időszakot.

    - **Kezdőérték** és **Végérték** – Itt adhatja meg a konszolidáció dátumtartományát. Ha üresen hagyja ezeket a mezőket, a konszolidációs vállalat főkönyvi naptárában a meghatározott minden időszakra fel lesz dolgozva a konszolidáció. Javasoljuk, hogy ezeket a mezőket ne hagyja üresen.
    - **Tényleges összegek belefoglalása** – Állítsa ezt a beállítást **Igen** értékre a tényleges adatok konszolidálásához.
    - **Költségvetési összegek belefoglalása** – Állítsa ezt a beállítást **Igen** értékre a költségvetési tételjegyzék adatainak konszolidálásához.
    - **Egyenlegek újraépítése a konszolidálási folyamat során** – Nem ajánlott, hogy ezt a lehetőséget az **Igen** értékre állítsa. Ehelyett az egyenlegek újraépítését külön kötegelt feladatként végezze.

- **Költségvetési modellek** – Ha a kijelölt költségvetési adatokat konszolidációra, ezen szakasz a mezőinek segítségével határozza meg a költségvetési modelleket.

    - **Kezdőéték** és **Záróérték** – Megadhatja a használandó modelleket.
    - **Költségvetési árfolyamtípus** –A használandó költségvetési árfolyam kiválasztása a költségvetési adatokhoz.

## <a name="financial-dimensions"></a>Pénzügyi dimenziók
A **Pénzügyi dimenziók** lapon meghatározhatja, hogy mely dimenzióknak kell szerepelnie a konszolidációs vállalatban. Dimenzió kiválasztásához állítsa a **Meghatározás** mezőt **Dimenzió** értékre, és adja meg a dimenzió sorrendjét a konszolidációs vállalatban.

![Pénzügyi dimenziók lap](./media/financial-dimensions-cons.png "Pénzügyi dimenziók lap")

Függetlenül attól, hogy milyen sorrendet határozott meg mindig a **Fő számla** lesz az első szegmens.

## <a name="legal-entities"></a>Jogi személyek
A **Jogi személyek** lapon meghatározhatja, hogy mely vállalatoknak kell szerepelnie a konszolidációs vállalatban. Ezeknek a vállalatoknak tulajdonosi százalékát is meghatározza. Kisebb, mint 100 %-os tulajdoni hányadot ad meg, a megadott százalék összegezve lesz a konszolidációs vállalattal. Az esetleges átváltási különbségekhez az **Átváltási különbözetek számlatípusa** mező segítségével választhatja ki a fő számlát a **Számlák automatikus tranzakciókhoz** lapon.

![Jogi személyek lap](./media/legal-entities-cons.png "Jogi személyek lap")

![Számlák automatikus tranzakciókhoz lap](./media/accounts%20for%20automatic%20(cons).png "Számlák automatikus tranzakciókhoz lap")

## <a name="elimination"></a>Eltávolítás
Az **Eltávolítás** lapon az eltávolítások feldolgozására három lehetőség van:

- Válassza ki az eltávolítási szabályt, majd a **Javaslatbeállítások** mezőben válassza ki a **Csak javaslat** lehetőséget. Ez a beállítás feldolgozza az eltávolítást a konszolidálási folyamat során, de nem ad fel mindent egy lépésben. Lehetőség van a napló későbbi feladására.
- Válassza ki az eltávolítási szabályt, majd a **Javaslatbeállítások** mezőben válassza ki a **Csak feladás** lehetőséget. Ez a beállítás feldolgozza az eltávolítást a konszolidálási folyamat során, és mindent felad egy lépésben.
- Az eltávolítási napló használatával futtaható egy eltávolítási javaslat külön a konszolidációs folyamattól.

![Eltávolítás lap](./media/elimination-cons-onl.png "Eltávolítás lap")

Az eltávolítással kapcsolatos további információkért, lásd: [Eltávolítási szabályok](./elimination-rules.md).

## <a name="currency-translation"></a>Devizaátváltás
A **Devizaátváltás** lapon megadhatja a jogi személyt, a számlát és az árfolyamtípust és értéket. Három lehetőség érhető el a **Következő dátumú árfolyam alkalmazása** mezőben:

- **Konszolidáció dátuma** – a Konszolidáció dátumát veszi figyelembe az árfolyamok beolvasásához. Az árfolyam megegyezik az azonnali vagy hónap végi árfolyammal. Az előnézete jelenik meg, de szerkesztésre nincs lehetőség.
- **Tranzakció dátuma** – Az egyes tranzakciók dátuma használandó az árfolyam kiválasztásához. Ez a beállítás leggyakrabban a tárgyi eszközökhöz használatos, és korábbi árfolyamnak is gyakran nevezik. Az árfolyam előnézete nem látható, mivel a számlatartomány különböző tranzakcióinak sok árfolyama lesz.
- **Felhasználó által definiált árfolyam** – Miután ezt a lehetőséget választja, megadhatja a használni kívánt átváltási árfolyamot. Ez a beállítás akkor átlagos árfolyamokhoz vagy rögzített árfolyammal szemben hasznos.

![Pénznem átszámítása lap](./media/currency-translation-cons-online.png "Pénznem átszámítása lap")

## <a name="additional-resources"></a>További erőforrások

További információért a konszolidációról, és a pénznem átváltásokhoz tekintse meg jelen témakör szülő témakörét, [Pénzügyi konszolidáció és devizaátváltás](./financial-consolidations-currency-translation.md).

További információért azzal kapcsolatosan, hogy hol generálhat konszolidált pénzügyi kimutatásokat, lásd: [Konszolidált pénzügyi kimutatások létrehozását](./generating-consolidated-financial-statements.md).

