---
title: Tervezési változáskezelés GYIK
description: Ez a témakör válaszokat ad a tervezési változáskezelési funkcióval kapcsolatos gyakori kérdésekre.
author: t-benebo
ms.date: 03/25/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-03-25
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 69232eed8520bafeb734ffad43b333bf9e36909e
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018685"
---
# <a name="engineering-change-management-faq"></a>Tervezési változáskezelés GYIK

[!include [banner](../includes/banner.md)]

Ez a témakör válaszokat ad a tervezési változáskezelési funkcióval kapcsolatos gyakori kérdésekre.

## <a name="should-i-track-the-version-in-transactions"></a>Kövessem nyomon a verziót a tranzakciókban?

Tervezésiváltozás-kategória létrehozásakor a **Tervezésiváltozás-kategória részletei** oldal biztosít egy **Verziókövetés a tranzakciókban** elnevezésű lehetőséget. Mi ez a beállítás, és mire használatos?

- Ha a **Verziókövetés a tranzakciókban** beállítást *Igen* értékre állítja, a rendszer úgy szűri a **Dimenziócsoport** mezőt, hogy ez csak az olyan dimenziócsoportokat mutatja, ahol a verzió aktív dimenzió.
- Ha a **Verziókövetés a tranzakciókban** beállítást *Nem* értékre állítja, a rendszer úgy szűri a **Dimenziócsoport** mezőt, hogy ez csak az olyan dimenziócsoportokat mutatja, ahol a verziódimenzió **nem** aktív dimenzió.

### <a name="if-you-track-the-version-in-transactions"></a>Tranzakciók verziókövetése esetén

Az olyan tervezési kategóriáknál, ahol a kiválasztott dimenziócsoport esetén a verzió aktív dimenzió, követni fogja a verziókat az adott kategóriába tartozó termékek tranzakcióiban. Ebben az esetben a tervezés terméke alaptermék lesz, és a termék minden verziója a verziódimenziót használó termékváltozat lesz. Más dimenziók is használhatók a verziódimenzióval együtt.

Ebben az esetben minden tervezési verziót a rendszer változatként kezeli az összes folyamatban. Ezért ha egy megadott változat szerepel egy tranzakcióban (hogy megállapíthassa, hogy melyik változatot értékesítették vagy vásárolták meg), minden egyes verzióhoz kezelnie kell a készlelet, az alaptervezés megtervezi az ellátást minden egyes verzióra, és így tovább. Ha visszavon egy verziót a piacról, akkor manuálisan kell módosítania a hozzá tartozó érvényesség kezdetének és végének dátumát, hogy tükrözzék a módosítást. Úgy kell kezelnie a készletet, hogy a raktárakban ne szerepeljenek a cikkek nem használt verziói.

Bár ez a beállítás több felügyeleti munkát igényel, olyan esetben is javasoljuk, amikor magas szintű nyomonkövethetőségre van szükség az egyes tranzakciókban használt megadott verzióknál.

### <a name="if-you-dont-track-the-version-in-transactions"></a>Ha nem végez verziókövetést a tranzakciókban

Az olyan tervezési kategóriáknál, ahol a kiválasztott dimenziócsoport esetén a verzió **nem** aktív dimenzió, **nem** fogja követni a verziókat az adott kategóriába tartozó termékek tranzakcióiban. Ebben az esetben, ha nem használ más dimenziót, a tervezési termék egyedi termék lesz. A termék továbbra is verziószámozott lesz, és kezelni lehet a meghatározott verziókra (például az darabjegyzékre \[DBJ] és az útvonalra) vonatkozó adatokat, de nem lehet nyomon követni, hogy melyik verziót használta az egyes tranzakciókban. Az érvényesség kezdetének és végének dátuma jelzi az egyes verziók érvényességét.

Ez a lehetőség sokkal egyszerűbben kezelhető, mivel ha át szeretne váltani egyik verzióról a másikra, akkor egyszerűen a szükséges módosításokat el kell végeznie egy módosítási utasításban, majd frissítenie kell a tervezési verzióban szereplő érvényesség kezdetének és végének dátumát. A termelési folyamatok ezután felveszik a termékhez (és annak adott verziójához) szükséges darabjegyzéket és útvonalat.

A legtöbb szervezet ezt a lehetőséget választja, mivel verzió- és változáskezelést biztosít, de nem adja hozzá a minden tranzakcióban való verziókövetés további többletköltségeit a készletben és az alaptervezés során.

## <a name="which-fields-are-copied-to-the-released-item-template"></a>Mely mezőket másolja a rendszer a kiadott cikksablonba?

Amikor egy tervezési vállalat létrehoz egy tervezési terméket, az a termék egy kiadott termékként jön létre a tervezési vállalatban. A létrehozott kiadott termék a kiválasztott *kiadott cikksablonon* alapul. (A kiadott cikksablon maga egy létező kiadott termék.) A kiadott cikksablont akkor is használja a rendszer, amikor a terméket egy operatív vállalatnak kiadták. A kiadott cikksablon minden esetben meghatározza a kiadott termék mezőértékének nagy részét, és ezek az értékek a **Kiadott termék részletei** lapról származnak.

A következő táblák bemutatják a folyamatok során másolt mezőket.

| Gyorslap | A termék létrehozásakor a tervezési vállalatban másolt mezők | Operatív vállalatnak való kiadás során másolt mezők |
|---|---|---|
| **Általános** | Az **Adminisztráció** szakasz minden mezője | Ugyanazok a mezők, amelyek másolva vannak a tervezési vállalatnál |
| **Beszerzés** | Minden mező | Összes mező, kivéve **Egység** |
| **Eladás** | A következő szakaszok minden mezője: **Értékesítési rendelés**, **Adminisztráció**, **Adózás**, **Árfrissítés**, **Alap eladási ár**, **Költségek**, **Engedmények** és **Alternatív termék** | Ugyanazok a mezők, amelyek másolva vannak a tervezési vállalatnál, kivéve **Egység** |
| **Külkereskedelem** | Minden mező | Minden mező |
| **Készletkezelés** | Az összes mező és szakasz, *kivéve* **Fizikai dimenziók** és **Tényleges súly** | Ugyanazok a mezők, amelyek másolva vannak a tervezési vállalatnál, kivéve **Egység** |
| **Tervező**, **Terv**, **Költségek kezelése**, **Projektek kezelése**, **Pénzügyi dimenziók**, és **Raktár** | Minden mező | Összes mező, kivéve **DBJ egysége** |
| **Termékváltozatok** | Az **Alapértelmezett termékváltozat** szakasz összes mezője | Ugyanazok a mezők, amelyek másolva vannak a tervezési vállalatnál |

Az előző táblában megjelenő mezőkön kívül minden alapértelmezett rendelési beállítást átmásol a program a kiadott cikksablonból, akkor is, amikor a terméket a tervezési vállalatnál létrehozták, és akkor is, amikor kiadták egy operatív vállalatnak. (A kiadott cikksablon alapértelmezett rendelési beállításainak megtekintéséhez nyissa meg a megfelelő **Kiadott termék részletei** oldalt, majd a műveleti ablaktáblán a **Készlet kezelése** lapon az **Alapértelmezett rendelési beállítások** elemet válassza.)

## <a name="should-i-create-a-separate-legal-entity-for-engineering-products-or-use-an-existing-legal-entity"></a>Egy különálló jogi személyt kell létrehozni a tervezési termékekhez, vagy meglévő jogi személyt kell használni?

Az üzleti követelmények határozzák meg, hogy létre kell-e hozni egy új jogi személyt a tervezési termékekhez.

Egy különálló tervezési vállalat létrehozásával a tervezési adatokat külön lehet tartani, majd a helyi operatív vállalatok számára szükséges módosításokat lehet hozzáadni. Így elérheti a következő célokat:

- Külön entitást lehet tartani a tervezési termékek létrehozása és kezelése között.
- Annak megakadályozása, hogy a tervezési termékek a többi kiadott termékkel együtt megjelenjenek addig, amíg nem állnak készen és ki nem adták őket.
- Egyértelműen meg kell különböztetni a tervezési és a helyi adatok által meghatározott adatokat.

Ha azonban a következő feltételek érvényesek Önre, akkor érdemes egy meglévő jogi személyt tervezési vállalatként használnia:

- A rendszerben csak egy jogi személy található, és/vagy nem szükséges egyértelműen elválasztani a tervezési termékeket.
- Nem szeretne ismétlődő adatokat, például erőforráscsoportokat, erőforrásokat, műveleteket és (esetleg) telephelyeket.

## <a name="what-is-the-nomenclature-for-engineering-versions-and-variants"></a>Mi a tervezési verziók és változatok elnevezési szabálya?

A termékek és termékváltozatok elnevezési szabálya a következő módon működik:

- A tervezési termékhez (azaz ha nem használ dimenziókat, egyedi termékhez, vagy dimenziók használata esetén az alaptermékhez), a számszabály elnevezési szabálya a tervezési termékkategóriában kerül meghatározásra. Itt lehetőség van egy számsorozat, szöveges konstansok, attribútumnevek és értékek használatára.
- A tervezési termék minden egyes változatához (ha a tervezési termék alaptermék, a változatok a dimenziócsoport megadásának megfelelő mérnöki termékkategóriában vannak beállítva), az egyes változatok számszabályának elnevezési szabálya a dimenziócsoportban van meghatározva. Ebben az esetben használhatja az alaptermék termékazonosítóját, valamint a dimenzióértékeket és -neveket.
