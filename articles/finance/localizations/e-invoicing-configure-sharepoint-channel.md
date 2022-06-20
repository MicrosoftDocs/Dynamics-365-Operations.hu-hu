---
title: SharePoint csatorna konfigurálása
description: Ez a cikk bemutatja, hogyan kell konfigurálni egy Microsoft-csatornát SharePoint a bejövő elektronikus számlák feldolgozására.
author: dkalyuzh
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 89538adde4d14212fb0deccad05f828d146f16db
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8910041"
---
# <a name="configure-a-sharepoint-channel"></a>SharePoint csatorna konfigurálása

[!include [banner](../includes/banner.md)]

A Microsoft-csatorna SharePoint bejövő dokumentumok feldolgozására való konfigurálásához szükséges, [SharePoint hogy végrete kövesse a Kapcsolat konfigurálása lépéseit](e-invoicing-create-sharepoint-connection.md).

Ezután a csatornával elektronikus szállítói SharePoint számlákat importálhat a mappákban tárolt fájlokból SharePoint.

1. A webhelyen SharePoint hozza létre a következő mappákat:

    - **Főmappa** – az a mappa, amelyből a szolgáltatás feldolgozja a fájlokat.
    - **Archiválási** mappa – az a mappa, ahol a feldolgozott fájlok tárolódnak.
    - **Hibamappa** – az a mappa, amelybe a rendszer fájlokat fog áthelyezni, ha a feldolgozás sikertelen.

2. A Szabályozó konfigurációs szolgáltatásban (RCS) válassza ki a létrehozott elektronikus számlázási szolgáltatást. Győződjön meg róla, hogy a Vázlat állapotú verziót **választja**.
3. A **Beállítások lapon** válassza a Hozzáadás **lehetőséget**.
4. A Funkcióbeállítás **létrehozása legördülő** párbeszédpanel Új **mezőcsoport** mezőjében válassza az Egyéni **beállítás beállítást**.
5. A Beállítástípus **mezőcsoportban** válassza az Adatcsatorna **beállítást**.
6. Az Adatcsatorna **kiválasztása mezőben** válassza ki a mappát **SharePoint**.
7. Válassza a **Létrehozása** lehetőséget.
8. Válassza ki a létrehozott sort, majd válassza a Szerkesztés **lehetőséget**.
9. Az Adatcsatorna **lap** **Paraméterek szakaszában** állítsa be a következő kötelező mezőket.

    | Mező                 | Leírás |
    |-----------------------|-------------|
    | Adatcsatorna          | Az adatcsatornát azonosító egyedi név beírása. A név legfeljebb 10 karaktert tartalmazhat. A kommunikációs folyamat során az alkalmazhatósági szabályok és a kapcsolódó alkalmazások hivatkoznak rá. |
    | SharePoint-cím    | Adja meg az SharePoint URL-címet. Például írja be, hogy `<domain>.sharepoint.com`. |
    | Alkalmazásazonosító        | Adja meg a felhasználói fiók azonosítóját tartalmazó Azure-kulcs – Előfizetési SharePoint titkos kulcs nevét. Ezt a titkos kulcsot Létre kell hozni a Key Ügyfélszolgálatban, és be kell állítani a szolgáltatási környezetben. Az érték a Kapcsolat konfigurálása beállításból származó **alkalmazásazonosító**[(ügyfél) értéke SharePoint.](e-invoicing-create-sharepoint-connection.md) |
    | Alkalmazás titkos kulcsa    | Adja meg a felhasználói fiók jelszavát tartalmazó KulcsKulcs – Titkos SharePoint kulcs nevét. Az érték az alkalmazásregisztráció **titkos értéke a** Kapcsolat konfigurálása [beállításból SharePoint](e-invoicing-create-sharepoint-connection.md). |
    | Webhely neve             | Adja meg a telephely SharePoint nevét. |
    | Dokumentumtár neve | A dokumentumtár nevének SharePoint beírása. |
    | Időtúllépés               | Adja meg azt a maximális időt ezredmásodpercben (ms), ahányszor a rendszernek a válaszra kell várnia. Az alapértelmezett érték 10 000 ms (10 másodperc). |
    | Fő mappa           | Adja meg a fájl importálási forrását, vagy azt a mappát, amelyből a szolgáltatásnak fel kell feldolgoznia a fájlokat. |
    | Archiválási mappa        | Adja meg azt a mappát, ahol a feldolgozott fájlokat tárolni kell. |
    | Hiba mappája          | Annak a mappának a megadása, amelybe a rendszer fájlokat fog áthelyezni, ha a feldolgozás sikertelen. |
    | Maximális fájlméret         | Adja meg egyetlen feldolgozott fájl maximális méretét bájtban. Az alapértelmezett érték a 20,000,000 bájt. |
    | Fájlok maximális száma      | Adja meg, hogy legfeljebb hány fájlt kell feldolgozni egyetlen művelethez. Ha nem szeretné korlátozni a fájlok számát, **az értéket 0 (nulla**) értékre kell állítani. |
    | Fájlszűrő           | Írjon be egy karakterláncot a fájlnév alapján való szűréshez. A mező kitöltése nem kötelező. A karakter egy egyszerű maszkja (például **\*smth\*.ext**) használható, ahol minden csillag (\*) bármely karakter nulla vagy több előfordulását képviseli. Például írja be a **\*.pdf formátumot** a csatorna PDF-fájlok olvasásához való konfigurálához. |
    | Egyéni fájlnév      | Adja meg az ügyfélről származó egyéni fájl nevét. |

10. Az Alkalmazhatósági **szabályok** lapon szükség szerint tekintse át és frissítse a feltételeket. A Csatorna mező értékének **meg** **kell egynie az előző lépésben az Adatcsatorna** mezőben megadott értékkel.
11. Válassza a **Mentés** gombot, és zárja be az oldalt.
