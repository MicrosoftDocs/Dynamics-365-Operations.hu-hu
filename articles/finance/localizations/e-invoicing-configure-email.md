---
title: E-mail csatorna konfigurálása
description: Ez a témakör bemutatja, hogyan kell konfigurálni egy e-mail csatornát az elektronikus számlák fogadására.
author: dkalyuzh
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 6a5896a033212cf0f29f686eec0ab6fb3bc1d2a6
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/02/2022
ms.locfileid: "8371884"
---
# <a name="configure-an-email-channel"></a>E-mail csatorna konfigurálása

[!include [banner](../includes/banner.md)]

Ha az Elektronikus számlázás funkció, amelyet létrehozott, az elektronikus szállítói számlákat importálja az e-mailben kapott csatolt fájlokból, konfigurálnia kell egy e-mail fiók csatornáját.

1. A Szabályozó konfigurációs szolgáltatásban (RCS) válassza ki a létrehozott elektronikus számlázási szolgáltatást. Győződjön meg róla, hogy a Vázlat állapotú verziót **választja**.
2. A Beállítások **lapon válassza a Hozzáadás lehetőséget** **.**
3. A Funkcióbeállítás **létrehozása legördülő** párbeszédpanel Új **mezőcsoport** mezőjében válassza az Egyéni **beállítás beállítást**.
4. A Beállítástípus **mezőcsoportban** válassza az Adatcsatorna **beállítást**.
5. Az Adatcsatorna **kiválasztása mezőben** adja meg a **Bejövő e-mail címet**.
6. Válassza a **Létrehozása** lehetőséget.
7. Válassza ki a létrehozott sort, majd válassza a Szerkesztés **lehetőséget**.
8. Az Adatcsatorna **lap** **Paraméterek szakaszában** állítsa be a következő kötelező mezőket.

    | Mező                | Leírás |
    |----------------------|-------------|
    | Adatcsatorna         | Az adatcsatornát azonosító egyedi név beírása. A név legfeljebb 10 karaktert tartalmazhat. A kommunikációs folyamat során alkalmazhatósági szabályok és a kapcsolódó alkalmazások hivatkoznak rá. |
    | Kiszolgáló címe       | Adja meg az e-mail fiók szolgáltatójának kiszolgálói címét. Például a szolgáltató kiszolgálói `https://outlook.live.com` címe már imap-mail.outlook.com. |
    | Kiszolgálóport          | Adja meg annak a portnak a számát, amely az e-mail fiók szolgáltatóját használja. A szolgáltató kiszolgálóportja `https://outlook.live.com` például 993. |
    | Felhasználónév titkos kódja     | Adja meg az e-mail Microsoft Azure felhasználói fiók azonosítóját tartalmazó Kulcs– És titkos kulcs nevét. Ezt a titkos kulcsot Létre kell hozni a Key Ügyfélszolgálatban, és be kell állítani a szolgáltatási környezetben. |
    | Felhasználói jelszó titkos kódja | Adja meg az e-mail felhasználói fiók jelszavát tartalmazó kulcskulcs- éskulcs-titkos kulcsot. |
    | Időtúllépés              | A maximális időkorlát ezredmásodpercben (ms), amely alatt a rendszernek a válaszra kell várnia. Az alapértelmezett érték 10 000 ms (10 másodperc). |
    | Fő mappa          | Adja meg az e-mail importálási forrását, vagy azt a mappát, amelyből a szolgáltatásnak fel kell feldolgoznia az e-maileket. |
    | Archiválási mappa       | Annak a mappának a megadása, ahol a feldolgozott e-maileket tárolni kell. Ha nem adja meg ezt a mappát, a rendszer automatikusan létrehozza azt. |
    | Hiba mappája         | Annak a mappának a megadása, amelybe a rendszernek e-maileket kell áthelyezni, ha a feldolgozás sikertelen. Ha nem adja meg ezt a mappát, a rendszer automatikusan létrehozza azt. |
    | Üzenet maximális mérete     | Adja meg a feldolgozott üzenetek maximális méretét bájtban. Az alapértelmezett érték a 20,000,000 bájt. |
    | Üzenet maximális száma   | Adja meg, hogy egy művelethez legfeljebb hány üzenetet kell feldolgozni. Ha nem szeretné korlátozni az üzenetek számát, **az értéket 0 (nulla**) értékre kell állítani. |
    | Feladó szűrője          | Írjon be egy karakterláncot a feladó címe alapján való szűréshez. A rendszer csak olyan e-maileket fog feldolgozni, amelyekben a feladó címe megegyezik a szűrővel. A mező kitöltése nem kötelező. Több feladó címének megadásához pontosvesszőket (;) elválasztóként. |
    | Tárgyszűrő       | Adjon meg egy karakterláncot a tárgy szerint való szűréshez. A rendszer csak olyan e-maileket fog feldolgozni, amelyekben a tárgy megfelel a szűrőnek. A mező kitöltése nem kötelező. A karakter egy egyszerű maszkja (például **\*smth\*.ext**) használható, ahol minden csillag (\*) bármely karakter nulla vagy több előfordulását képviseli. |
    | Dátumszűrő          | Adja meg a feldolgozott üzenetek maximális korát napban megadásával. A mező kitöltése nem kötelező. Az alapértelmezett érték 30 nap. |
    | Feldolgozási mód      | <p>Az alábbi lehetőségek egyikének kiválasztásával adhatja meg, hogy az e-mailben található mellékletek együtt dolgozhatók-e fel, vagy külön-külön kell-e feldolgozni az egyes mellékleteket:</p><ul><li><b>Melléklet szerint</b> – az e-mailben található minden egyes melléklethez új elektronikus dokumentum jön létre. Ha például egy e-mail több olyan fájlt tartalmaz, amelyek e-számlázási adatokat tartalmaznak, akkor a rendszerben minden fájl új e-számlának számít.</li><li><b>E-mailben</b> – a rendszer egy mellékletet fog alapmelléknek tekinteni, és egy elektronikus számlát hoz létre a rendszerben. A többi mellékletet támogató fájlként is fel lehet használni.</li></ul> |

9. Adja hozzá **a fájlszűrés** adatait a Mellékletek szűrőszakaszban. A rendszer csak a megadott szűrőnek megfelelő mellékleteket fogja feldolgozni. **\* Az .xml szűrő** például az .xml fájlnév kiterjesztésű mellékleteket szűri. A melléklet nevét a Dynamics 365 Finance vagy a Dynamics 365 Supply Chain Management beállítás során használja.

    - Ha az előző lépésben **e-mailben** **beállította** a Feldolgozási mód mezőt, itt több szűrőt is hozzáadhat. A név azonosítja az adott dokumentumot.
    - Ha a Feldolgozási mód **mezőt** **melléklet** szerint beállításra adja, akkor csak egy szűrőt adhat hozzá.

10. Az Alkalmazhatósági **szabályok** lapon szükség szerint tekintse át és frissítse a feltételeket. A Csatorna mező értékének **meg** **kell egynie a 8. lépésben az Adatcsatorna** mezőben megadott értékkel.
11. Válassza a **Mentés** gombot, és zárja be az oldalt.
