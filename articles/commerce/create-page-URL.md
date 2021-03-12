---
title: Weblap URL-jének létrehozása
description: Ez a témakör egy lap URL-címének a webhelyén történő létrehozásával kapcsolatos alapfogalmakat és eljárásokat ismerteti.
author: bicyclingfool
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 062a49df93e442dbe402ac9a78244c966958aaa2
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4965253"
---
# <a name="create-a-page-url"></a>Weblap URL-jének létrehozása


[!include [banner](includes/banner.md)]

Ez a témakör egy lap URL-címének a webhelyén történő létrehozásával kapcsolatos alapfogalmakat és eljárásokat ismerteti.

## <a name="overview"></a>Áttekintés

A webhely egy lapjára mutató teljes vagy abszolút URL-cím különböző részekből áll. Például a `https://www.contoso.com/en-us/contactus` URL-cím a következő részekből áll:

- `https://www.contoso.com`– A HTTP protokoll és a webhely tartománya.
- `/en-us`– A webhely nyelvi elérési útja.
- `/contactus`– A **Kapcsolat** lap relatív URL-címe. A relatív URL ismert URL *alkategória* néven is.

A webhelye tartományát és az opcionális nyelvi útvonalat a webhely beállításakor hozhatja létre. A webhely beállításai között található online áruházi lapok segítségével további tartományokat és nyelvi útvonalakat adhat hozzá a webhelyhez.

A lap URL alkategóriája önálló entitásként létezik a webhelylétrehozási környezetben. A lap URL-címe két részből áll: az URL alkategóriát képviselő névből, valamint a webhelye vagy egy külső webhely egyik lapjára irányuló mutatóból. A lap URL-címe beállítható úgy is, hogy a webhelye vagy egy külső webhely másik lapjára irányítson át.

## <a name="create-a-page-url"></a>Weblap URL-jének létrehozása

Kétféle módon hozhatók létre lap URL-ek:

- Automatikusan a lap létrehozásakor
- Manuálisan, az **URL-ek** lapról

### <a name="create-a-page-url-when-you-create-a-page"></a>Lap URL létrehozása a lap létrehozásakor

Ha egy új lap létrehozásakor megad egy nevet az **URL** mezőben, akkor az **URL-ek** lapon automatikusan létrejön egy lap URL, amely erre a lapra mutat. Miután közzétette az URL-címet és a lapot, amelyre mutat, a webhely felhasználói (az Ön ügyfelei) hozzáférhetnek az URL-címhez társított laphoz.

> [!NOTE]
> Ha egy URL-címet anélkül a lap nélkül tesz közzé, amelyre mutat, akkor a webhely felhasználói 404 hibaüzenetet kapnak, amikor megpróbálnak hozzáférni a laphoz. Ha a weblapot a rámutató URL közzététele nélkül teszi közzé, akkor a lap nem érhető el URL használatával.

### <a name="manually-create-a-page-url"></a>Lap URL manuális létrehozása

Amikor új lapokat hoz létre, nem kell megadnia a lap URL-jét. Ha üresen hagyja az URL mezőt, akkor a lap egy hivatkozás nélküli állapotban jön létre. Ebben az esetben a vevők nem férhetnek hozzá a laphoz még akkor sem, ha az közzé van téve. A lap elérhetővé tételéhez manuálisan kell létrehoznia az URL-címet, és társítania kell azt a laphoz.

A lap URL-címének manuális létrehozásához hajtsa végre az alábbi lépéseket.

1. Az **URL-ek** lapon válassza az **Új** lehetőséget.
1. Válassza ki a webhelynek az URL-hez társítani kívánt lapját.
1. Adja meg az URL alkategóriát, majd kattintson az **OK** gombra.

Ezen a ponton az URL piszkozat állapotban van. Közzé kell tenni ahhoz, hogy a webhely felhasználói elérjék a társított oldalt.

## <a name="update-a-page-url"></a>Lap URL-címének frissítése

A lap URL céllapjának frissítéséhez hajtsa végre az alábbi lépéseket.

1. Az **URL-ek** lapon válassza ki a frissítendő URL-címet.
1. A jobb oldali tulajdonságlapon nyomja meg a céllap mező melletti három pont gombot (**...**).
1. A párbeszédpanelen válasszon ki egy másik lapot, majd kattintson az **OK** gombra.
1. Mentse és tegye közzé az URL-t.

## <a name="redirect-a-page-url"></a>Lap URL-címének átirányítása

Bizonyos esetekben előfordulhat, hogy a vevőknek egy másik lapot kíván megjeleníteni, amikor egy adott URL-címet kérnek. Ezekben az esetekben a legjobb és legegyszerűbb módszer, ha módosítja a lapot, amelyre a lap URL-címe mutat. Előfordulhat azonban, hogy jogos oka van arra, hogy a HTTP 301-es vagy 3023-as átirányítások használatával az adott URL-címre vonatkozó kéréseket egy eltérő URL-címre irányítsa át.

Az URL-címnek egy eltérő URL-címre való átirányításához kövesse az alábbi lépéseket.

1. Az **URL-ek** lapon válassza ki a frissítendő URL-címet.
1. A jobb oldali tulajdonságlapon válassza az **Átirányítás** elemet.
1. Válassza ki az átirányítás célját:

    - Ha a webhely egy másik lapjára szeretne mutatni, válassza a **Belső URL** lehetőséget, nyomja meg a három pont gombot (**...**), majd válassza ki azt az URL-címet, amelyre át szeretné irányítani.
    - Ha egy külső webhelyen található lapra szeretne átirányítani, válassza ki a **Külső URL** lehetőséget, majd írja be a lap teljes URL-címét. Ne feledje el belefoglalni a protokollt. Például írja be, hogy `https://domain.com/new/page`. Ha egy URL-cím már át van irányítva egy belső URL-címre, akkor válassza a **Kijelölés törlése** lehetőséget, mielőtt megadna egy külső URL-címet.

1. Válasszon egy átirányítástípust:

    - **Állandó átirányítás (301)** – Akkor válassza ezt a lehetőséget, ha tudja, hogy a tartalom véglegesen áthelyezésre került, és nem lesz visszaállítva a korábbi URL-címre. A keresőmotorok hozzárendelik az átirányító URL keresőmotor-optimalizálási (SEO) értékét az átirányított URL-címhez, és frissítik a rekordjaikat, hogy azok az új URL-címet jelenítsék meg. 
    - **Ideiglenes átirányítás (302)** – Válassza ezt a lehetőséget, ha a forgalmat a keresőmotorok frissítése nélkül szeretné átirányítani. Ez a módszer általában akkor használatos, ha a tartalom hamarosan visszatért a korábbi URL-címre.

1. Amikor készen áll az átirányítás végrehajtására, mentse és tegye közzé az URL-címet.

## <a name="additional-resources"></a>További erőforrások

[Webhely-navigáció testreszabása](customize-site-navigation.md)

[Új webhelyoldal hozzáadása](add-new-page.md)

[A tartománynév konfigurálása](configure-your-domain-name.md)

[Nyelvek hozzáadása a webhelyhez](add-languages-to-site.md)
