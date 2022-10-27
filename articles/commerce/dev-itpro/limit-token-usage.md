---
title: Fizetési token használatának korlátozása
description: Ez a témakör azt a funkciót ismerteti, amely korlátozza a fizetési tokenek használatához használt funkciókat Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 10/20/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2022-09-20
ms.openlocfilehash: 8092ab0724f33f21759aa84d25e0bdcb5b2ad5dd
ms.sourcegitcommit: 6bd8822f7aa781d596b70956bead834117cf302c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/20/2022
ms.locfileid: "9709371"
---
# <a name="limit-payment-token-usage"></a>Fizetési token használatának korlátozása

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Ez a témakör azt a funkciót ismerteti, amely korlátozza a fizetési tokenek használatához használt funkciókat Microsoft Dynamics 365 Commerce. A tokenhasználat csak értékesítési rendelés hatókörére terjed ki, illetve amennyiben a vevő hozzájárul, fájlban tárolt kártyaként tárolódhat.

## <a name="key-terms"></a>Kulcsfogalmak

| Időszak | Leírás |
|---|---|
| Token | A Dynamics 365 rendszer hivatkozott XML-blobja, amely tranzakciós céllal tárolja a fizetési hivatkozásokat. |
| Kártya a fájlban | Mentett kártyahivatkozási jogkivonat, amely a Dynamics 365 rendszerben vagy a fizetési átjáróban jövőbeli használatra megállapodik, és amely a vevő számlájára vonatkozik. |

A fizetési tokenek használatának korlátai minden olyan környezetre érvényesek, amelyek ismétlődő tokeneket alkalmazó fizetési átjáró szolgáltatást alkalmaznak. A készleten [található Dynamics 365 Payment Connector for Adyen ismétlődő](adyen-connector.md) fizetési tokeneket használ a későbbi rendelési műveletek elvégzésére, például engedélyezési módosítások és újraengedélyezések elvégzésére.

Az ismétlődő **fizetési** tokenek rendszer egészében történő használatának szabályozására a Fizetési token használatának korlátozása a rendelési környezetre funkció az ismétlődő token használatát korlátozza a rendszerben értékesítési rendelések hatókörére. Ha engedélyezve van, a funkció a fizetési bemeneti lapok frissítésével és az új tranzakciópéldányok korábbi vevői fizetési hivatkozásainak kiválasztására való képesség korlátozásével módosítja a Commerce Headquarters felhasználói felületét.

Ez a funkció segít teljesíteni egyes fizetéskibocsátók, például a Visa használati szabályait. [A Visa Core szabályaiban és a Visa Product and Service Rules](https://usa.visa.com/content/dam/VCOM/download/about-visa/visa-rules-public.pdf) szabályaiban a Visa úgy határozza meg, hogy a fizetési tokenek használatát korlátozni kell a tranzakció hatókörére, hacsak a kártyatulajdonos másként nem állapodik meg.

A **Fizetési token használatának** korlátozása a rendelési környezetre szolgáltatás csak akkor van jelentősége, ha ismétlődő fizetési token-hivatkozásokat alkalmazó fizetésátjáró szolgáltatást használ.

## <a name="enable-the-feature"></a>A funkció engedélyezése

**Ha** engedélyezni szeretné a Fizetési jogkivonat használatának korlátozása a rendelési környezetre funkciót, a Commerce Headquarters for your environment **\>** alkalmazásban keresse meg és válassza ki a listában a Fizetési token használatának korlátozása a rendelési környezetre lehetőséget, **·** **majd válassza az Engedélyezés lehetőséget.**

## <a name="limit-payment-token-usage"></a>Fizetési token használatának korlátozása

Ha a funkció engedélyezve van, akkor a Commerce Headquarters fizetési mód rögzítésére használt lapjai frissítik, hogy hogyan hivatkoznak a vevő fájljában található vevői fizetési módokra. Ez a frissítés elsősorban két működési területet érint:

- Hogyan lehet a fájlban található vevőkártyát a vevő nevében megadni
- Hogyan tárolják a vevőkre vonatkozó fizetési adatokat a jövőbeni értékesítési rendelési fizetési bejegyzéseknél?

Amikor egy vevő a Commerce csatornával szemben tranzakciót ad meg, a fizetés részleteit értékesítési rendelési környezetben tárolja a rendszer. Az értékesítési rendelés környezete úgy korlátozza a fizetési tokent, hogy ne legyen fizetési hivatkozásként használva a Commerce Headquarters új vagy módosított értékesítési rendelési kifizetései fizetési lapjain található vevőrekordra.

### <a name="payment-form-changes"></a>Fizetési képernyő módosításai

Ha egy hívásközponti vagy a Commerce Headquarters egy felhasználója fizet a vevőnek egy értékesítési rendelés ellenében, akkor a fizetési lap bemutatja a fizetési mód kiválasztásának részleteit. Ha engedélyezve van **a** Fizetési jogkivonat használatának korlátozása a rendelési környezetre funkció, ha a felhasználó a fizetési lapon a pluszjelet (**+**) választja, akkor csak a fájlban található kártyarekordok jelennek meg. A változtatások megkövetelik, hogy a hívásközponti vagy a Commerce Headquarters **felhasználó** adja meg a vevő által az új értékesítési rendelési tranzakció vevői fizetési adatokkal kapcsolatos adatokat tartalmazó lapján megadott fizetési adatokat.

A Szám mező értékeinek **listája** csak olyan kártyahivatkozásokat tartalmaz, amelyek a fájlban található kártyát tartalmazó vevőhöz vannak társítva. Kiszűri a korábbi fizetési hivatkozásokat, amelyek nem tartoznak értékesítési rendeléshez.

A Szám mezőben található pluszjel (**+**) **elérhető** marad, és segítségével meg lehet adni a vevő által a feldolgozás alatt álló értékesítési rendeléshez kapcsolódó tranzakcióhoz megadott fizetési adatokat.

### <a name="how-cards-on-file-work"></a>Hogyan működnek a fájlkártyák

**Ha** engedélyezve van a Fizetési jogkivonat használatának korlátozása a rendelési környezetre funkció, a fájlban található kártya egy ismétlődő fizetési token, amely egy vevőrekordhoz menthető, és nem korlátozódik az értékesítési rendelés hatókörére. A fájlban található kártya gyorshivatkozást tesz lehetővé a Commerce Headquarters felhasználói számára, amikor kitöltik egy új értékesítési rendelés kifizetésének fizetési lapját. Ez a token-hivatkozás csak a Dynamics 365-környezetre érvényes. A fizetési átjáró szolgáltatást használó online csatornák számára, amelyek lehetővé teszi a fizetési mód mentését a iFrame fizetési modulban, a fizetési átjáró biztonságos módon tárolja ezeket a hivatkozásokat külön hivatkozásként a Dynamics 365 kártyához a fájlban.

Ha például az Adyen Fizetési csatlakoztatóját egy online csatornában használják, akkor azok a vevők, Dynamics 365 Commerce akik beírják hitelkártya-adataikat a fizetési modulba, iFrame csak az átjáró szolgáltatás mentett kártyahivatkozásai látják a következő online beszerzéshez, amikor azok hitelesítve vannak. A kifizetési modulban nem árolják a fájlban található Dynamics 365-környezetben tárolt kártyát iFrame. Hasonlóképpen, amikor a vásárló a hívásközponton keresztül ad fel rendelést, a hívásközponti felhasználónak nem jelennek meg online mentett kártyahivatkozásai. A hívásközponti felhasználó csak az előző kártyát látja a Dynamics 365 rendszerből származó fájlhivatkozásban (a vevő megállapodása szerint), hogy a jövőbeni rendelésekhez mentse a rendeléseket.

A Commerce Headquarters felhasználói a kiskereskedelmi és a kereskedelmi vevőkhöz megy, majd a **\>** vevői számlarekord kiválasztásával egy-egy vevő fájljában mentheti a fájlokat. A Vevő **beállítása \>** szakaszban azok a felhasználók, akiknek van jogosultságuk a fizetési lapok feldolgozására, a Hitelkártyabejegyzés lapon beírhat egy olyan kártyás fizetőeszközt, **amely** a jövőbeni tranzakciók fájljában tárolódhat. Ezzel a művelettel időt takaríthat meg a vevő jövőbeni értékesítési rendelési kifizetésének feldolgozása során. A hívásközponti és a Commerce Headquarters felhasználóinak csak akkor kell beírniuk a kártyát a fájlkártya adataiba, ha a vevő elfogadja, hogy a kártyahivatkozást jövőbeli tranzakciókhoz használja.

A **Commerce** Headquarters fizetési lapjainak alján található Mentés jövőbeni használatra jelölőnégyzet segítségével a felhasználók fájlba mentheti a kártyát későbbi használatra. Ezt a jelölőnégyzetet csak akkor kell használni, ha a vevő elfogadja a kártya jövőbeni tranzakciókban való használatát a fájlban. A Mentés jövőbeli **használatra** **jelölőnégyzetet a Commerce Headquarters** **·** **Hívásközpont** paraméterei lap Fizetés lapján található Vevőkártya engedélyezése fájlon beállításával lehet megjelenítése vagy korlátozása. Ha ez a beállítás **Igen**, a Commerce Headquarters fizetési lapok feldolgozására jogosultsággal rendelkező felhasználói a mentés jövőbeli használatra jelölőnégyzet segítségével menthetik a **fájlba** a kártyákat. Ha a beállítás **Nem**, akkor ez a jelölőnégyzet nem érhető el a Commerce Headquarters olyan felhasználói számára, akik engedéllyel vannak a fizetési lapok feldolgozására. **A "Vevőkártya** engedélyezése fájlban" beállítás akkor használható, ha a vállalat korlátozni szeretné az ismétlődő tokenek használatát a Commerce Headquarters szolgáltatásban, de még nem szeretné engedélyezni a fájlban található kártya mentését a megadott eljárás nélkül, hogy a vevő hozzájárul a jóváhagyáshoz.

### <a name="commerce-headquarters-pages-where-the-recurring-token-restrictions-are-enforced"></a>A Commerce Headquarters olyan oldalai, amelyekre az ismétlődő tokenek megszorításai érvényben vannak

A tokenkorlátozások felmásolása a Commerce Headquarters következő területeit érinti a funkció engedélyezése esetén:

- Vevői kifizetés adatai az értékesítési **rendelés kifizetésében \> - Adja \> meg a vevői kifizetést.**
- Folytonos rendelések
- Részletfizetések
- Kinnlevőségek hitelkártyás kifizetése

### <a name="manage-payment-tokens-archiving-or-removal"></a>Fizetési tokenek kezelése (archiválás vagy eltávolítás)

**Azok** a fizetési tokenek, amelyek még a Fizetési token használatának korlátozása rendelési környezetre funkciójelző engedélyezése előtt (vagy a funkció letiltása közben) engedélyezve maradnak a rendszerben, és a Commerce Headquarters fizetési oldalának kiválasztási listáiban is hivatkozhatók. Ezek a tokenek rendszeres időközönként, kétféleképpen távolíthatók el a Commerce Headquarters rendszerből:

- A hitelkártya-tranzakciók **adatainak** archiválási lapján beállíthatja a fizetési tokenek rendszeres kiürítése vagy archiválását. Ha az Adatok törlése **archiválás** **nélkül** beállítást Igen beállításra adja meg, **akkor a rendszer törli a Minimális tranzakciókorúra (napokban)** beállításnak megfelelő tokeneket. A további tudnivalókat lásd a hitelkártya-tranzakciók [adatainak archiválását.](archive-cc-data.md)
- Az új hitelkártyakivonat-törlési lap (**·** **\>\> Kinnlevőségek – Lekérdezések és jelentések: Hitelkártyatokenek törlése) használatával futtathatók és beállíthatók a fizetési jogkivonatokat törlése kötegelt feladatok.\>** A következő paraméterek beállítása:

    - A **token minimális korának** 90 napnál vagy annál többnek kell lennie.
    - A **Futtatás a háttérben beállítás** segítségével meghatározhatja az ismétlődési **vagy** a **figyelmeztetési beállításokat**.
    - A kötegcsoport egy adott csoportra vonatkozó feladat futtatására is hozzárendelhető.
    - Ha a **Személyes** beállítás **Igen**, csak az a felhasználó futtathatja, aki létrehozza a feladatot.
    - A Kritikus feladat **beállítás Igen beállítása gondoskodik** **arról**, hogy a rendszer aktív módon nyomon követi a feladat állapotát.

A törölt tokenek nem olvashatók be. **Állítsa a Minimális tokenkorú** nap mezőjét egy olyan tartományra, amely megfelel a környezet leghosszabban futó tranzakciós élettartamának (a rögzítésre vagy visszatérítésre való engedélyezéstől).

## <a name="additional-resources"></a>További erőforrások

[Kifizetésekkel kapcsolatos GYIK](payments-retail.md)

[Pénztármodul](../add-checkout-module.md)

[Fizetési modul](../payment-module.md)
