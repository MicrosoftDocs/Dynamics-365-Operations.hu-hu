---
title: Robots.txt fájlok kezelése
description: Ez a témakör a robots. txt fájl kezelésének módját ismerteti a Microsoft Dynamics 365 Commerce alkalmazásban.
author: BrianShook
manager: annbe
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: ''
ms.search.region: Global
ms.search.industry: retail
ms.author: brishoo
ms.search.validFrom: 2019-12-18
ms.dyn365.ops.version: ''
ms.openlocfilehash: 4b3856a7a0b4b198e71ce9af6691b1d90362f3e7
ms.sourcegitcommit: adf196c51e2b6f532d99c177b4c6778cea8a2efc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/02/2020
ms.locfileid: "3533413"
---
# <a name="manage-robotstxt-files"></a>Robots.txt fájlok kezelése


[!include [banner](includes/banner.md)]

Ez a témakör a robots. txt fájl kezelésének módját ismerteti a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A robotkizárási szabvány, vagy a robots.txt egy olyan szabvány, amelyet a webhelyek a webrobotokkal való kommunikációra használnak. A webrobotokat utasítja a webhely minden olyan területével kapcsolatban, amit nem kell felkeresniük. A robotokat gyakran használják a keresőmotorok webhelyek indexeléséhez.

A robotok kiszolgálóról való kizárásához egy fájlt kell létrehoznia a kiszolgálón. Ebben a fájlban megad egy hozzáférési irányelvet a robotok számára. A fájlnak HTTP-n keresztüli elérhetőnek kell lennie a **/robots.txt** helyi URL-címen. A robots.txt fájl segítségével a keresőmotorok indexelik a webhely tartalmát.

A Dynamics 365 Commerce lehetővé teszi, hogy feltöltsön egy robots.txt fájlt a tartományához. A Commerce környezetben található minden tartományhoz feltölthet egy robots.txt fájlt, és azt hozzárendelheti az adott tartományhoz.

Ha többet szeretne tudni a robots.txt fájlról, keresse fel a [Webrobotok oldalait](https://www.robotstxt.org/).

## <a name="upload-a-robotstxt-file"></a>Robots.txt fájl feltöltése

Miután létrehozta és módosította a robots.txt fájlt a [robotkizárási szabvány](https://www.robotstxt.org/orig.html) szerint, ellenőrizze, hogy a fájl elérhető-e azon a számítógépen, amelyen a Commerce szerkesztőeszközöket fogja használni. A fájlnak a **robots.txt** nevet kell adni. A legjobb eredmény érdekében a szabványban megadott formátummal kell rendelkeznie. Minden egyes Commerce-ügyfél felelős a robots.txt fájl tartalmának érvényesítéséért és fenntartásáért. A robots.txt fájl feltöltéséhez be kell jelentkeznie a Commerce rendszerbe rendszergazdaként.

A robots.txt fájl feltöltéséhez a Commerce alkalmazásban, kövesse az alábbi lépéseket.

1. Rendszergazdaként jelentkezzen be a Commerce rendszerbe.
2. A bal oldali navigációs ablaktáblán válassza ki a **Bérlői beállítások** (a fogaskerék szimbólum mellett) lehetőséget a kibontáshoz.
3. A **Bérlő beállításai** területen válassza a **Robots.txt** fájlt. A környezetéhez társított összes tartomány listája megjelenik az ablak fő részében.
4. Válassza a **Kezelés** lehetőséget a robots.txt fájl feltöltéséhez a környezete egyik tartományához.
5. A jobb oldali menüben kattintson a **Feltöltés** gombra (felfelé mutató nyíl) a robots.txt fájlhoz társított tartomány mellett. Megjelenik egy fájlböngésző párbeszédpanel.
6. A párbeszédpanelen tallózással keresse meg és jelölje ki azt a robots.txt fájlt, amelyet fel szeretne tölteni a társított tartományra, majd válassza a **Megnyitás** lehetőséget a feltöltés befejezéséhez.

> [!NOTE] 
> A feltöltés során a Commerce ellenőrzi, hogy a fájl szövegfájl-e, de nem érvényesíti a fájl tartalmát.

## <a name="download-a-robotstxt-file"></a>Robots.txt fájl letöltése

A robots.txt fájl letöltéséhez a Commerce alkalmazásban, kövesse az alábbi lépéseket.

1. Rendszergazdaként jelentkezzen be a Commerce rendszerbe.
2. A bal oldali navigációs ablaktáblán válassza ki a **Bérlői beállítások** (a fogaskerék szimbólum mellett) lehetőséget a kibontáshoz.
3. A **Bérlő beállításai** területen válassza a **Robots.txt** fájlt. A környezetéhez társított összes tartomány listája megjelenik az ablak fő részében.
4. Válassza a **Kezelés** lehetőséget a robots.txt fájl letöltéséhez a környezete egyik tartományához.
5. A jobb oldali menüben kattintson a **Letöltés** gombra (lefelé mutató nyíl) a robots.txt fájlhoz társított tartomány mellett. Megjelenik egy fájlböngésző párbeszédpanel.
6. A párbeszédpanelen keresse meg a helyi meghajtón a kívánt helyet, erősítse meg vagy adja meg a fájlnevet, majd válassza a **Mentés** lehetőséget a letöltés befejezéséhez.

> [!NOTE]
> Ezzel az eljárással csak a korábban a Commerce szerkesztőeszközökkel feltöltött robots.txt fájlok tölthetők le.

## <a name="delete-a-robotstxt-file"></a>Robots.txt fájl törlése

A robots.txt fájl törléséhez a Commerce alkalmazásban, kövesse az alábbi lépéseket.

1. Rendszergazdaként jelentkezzen be a Commerce rendszerbe.
2. A bal oldali navigációs ablaktáblán válassza ki a **Bérlői beállítások** (a fogaskerék szimbólum mellett) lehetőséget a kibontáshoz.
3. A **Bérlő beállításai** területen válassza a **Robots.txt** fájlt. A környezetéhez társított összes tartomány listája megjelenik az ablak fő részében.
4. Válassza a **Kezelés** lehetőséget a robots.txt fájl törléséhez a környezete egyik tartománya esetében.
5. A jobb oldali menüben kattintson a **Törlés** gombra (szemeteskuka szimbólum) a robots.txt fájlhoz társított tartomány mellett. Megjelenik egy fájlböngésző ablak.
6. A fájlböngésző ablakban tallózással keresse meg és jelölje ki azt a robots.txt fájlt, amelyet törlni szeretne a tartomány esetében, majd válassza a **Megnyitás** lehetőséget a feltöltés befejezéséhez. Megjelenik egy figyelmeztető üzenetpanel.
7. Az üzenetpanelen válassza a **Törlés** lehetőséget a robots.txt fájl törlésének jóváhagyásához.

> [!NOTE] 
> Ezzel az eljárással csak a korábban a Commerce szerkesztőeszközökkel feltöltött robots.txt fájlok törölhetők.

## <a name="additional-resources"></a>További erőforrások

[A tartománynév konfigurálása](configure-your-domain-name.md)

[Új e-commerce webhely telepítése](deploy-ecommerce-site.md)

[E-kereskedelmi webhely létrehozása](create-ecommerce-site.md)

[Online webhely társítása csatornával](associate-site-online-store.md)

[URL-átirányítások feltöltése ömlesztett formában](upload-bulk-redirects.md)

[B2C-bérlő beállítása a Commerce-ben](set-up-B2C-tenant.md)

[Felhasználói bejelentkezéshez használt egyéni lapok beállítása](custom-pages-user-logins.md)

[Több B2C-bérlő konfigurálása egy Commerce környezetben](configure-multi-B2C-tenants.md)

[Tartalomkézbesítési hálózat (CDN) támogatásának hozzáadása](add-cdn-support.md)

[Helyalapú áruházészlelés engedélyezése](enable-store-detection.md)
