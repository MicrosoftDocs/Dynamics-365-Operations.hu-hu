---
title: A visszaadott cikkek bevételezésének rögzítése
description: A visszaküldött cikkek beérkezésének nyilvántartásba vételéhez a Beérkezés áttekintése képernyőt vagy a Regisztráció képernyőt használhatja.
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WMSArrivalOverview, InventTransRegister
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 04abaa65375224a5881ab8c0c245da627813471dc6366448dc61fc609b8334ae
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6735063"
---
# <a name="register-the-receipt-of-returned-items"></a>A visszaadott cikkek bevételezésének rögzítése 

[!include [banner](../includes/banner.md)]


Kétféle módszerrel lehet regisztrálni a visszajuttatott cikkek bevételezését. Az első módszer a **Beérkezés áttekintése** képernyőt használó raktári bevételezési folyamat. A második módszer a **Regisztráció** képernyőt használja.

## <a name="register-the-receipt-of-returned-items-in-the-arrival-overview-form"></a>A visszáru bevételezésének regisztrálása a Beérkezés áttekintése képernyőn

A visszáruk a **Beérkezés áttekintése** képernyő használatával azonosíthatóak a visszáru-jóváhagyási szám (Return Materials Authorization – RMA) alapján. Ha a **Beállítás** lapon meg van adva napló neve, és vannak olyan naplósorok, amelyek megfelelnek a **Beérkezés áttekintése** képernyőn kijelölt soroknak, az **Érkeztetés indítása**. elemre történő kattintáskor új naplófejléc jön létre.

1.  Kattintson a következőkre: **Készletkezelés** \> **Rendszeres** \> **Beérkezés áttekintése**.

2.  A **Beállítás neve** mezőben válassza ki a **Visszárurendelés** lehetőséget, és kattintson a **Frissítés** elemre.
    

    > [!TIP]
    > <P>A <STRONG>Tartomány</STRONG> mezők segítségével tovább szűrheti a keresés eredményeit. Ha tudja a pontos visszáru-jóváhagyási számot, akkor azt is megadhatja az <STRONG>RMA-szám</STRONG> mezőben. A megjelenített beérkezések körét korlátozó szűrősorozat megadásához és mentéséhez kattintson a <STRONG>Beállítás</STRONG> lapra. Szűréshez használhatóak többek között a típusok, a raktárak és területek.</P>

    

    > [!WARNING]
    > <P>A visszárurendelések nem keverhetők más érkeztetési típusokkal a <STRONG>Beérkezés áttekintése</STRONG> képernyőn. Így a hivatkozási alap minden esetben az értékesítési rendelés, a napló fejlécében azonban nem lesz megadva értékesítésirendelés-azonosító.</P>



3.  A **Bevételezések** rácsban keresse meg azt a sort, amely megfelel a visszajuttatott cikknek, majd jelölje be a **Kijelölés beérkezésre** oszlopban található jelölőnégyzetet.

4.  Ahhoz, hogy kizárjon a visszáru-bevételezésből bizonyos sorokat, például olyan cikkeket, amelyek az eredeti rendelésen szerepeltek, de a visszáru-szállítmányban nincsenek benne, akkor törölje a megfelelő sorok **Kijelölés beérkezésre** jelölőnégyzeteit a **Sorok** táblában, a képernyő alsó részén.

5.  Cikkérkezési napló létrehozásához kattintson az **Érkeztetés indítása** gombra.
    

    > [!NOTE]
    > <P>Egyszerre több visszáru-rendelést is kijelölhet, és ezeket egy menetben érkeztetheti. A program minden visszáru-rendelési sort átmásol a cikkbeérkezési napló megfelelő sorába.</P>

    

    > [!NOTE]
    > <P>A <STRONG>Cikk érkezése</STRONG> képernyő használatával manuálisan is létrehozhat cikkérkezési naplót. 



6.  Kattintson a következőkre **Készletgazdálkodás** \> **Naplók** \> **Cikkérkeztetés** \> **Cikkérkeztetés**.

7.  A **Naplósorok, helyek** képernyő megnyitásához jelölje ki az imént létrehozott cikkérkezési naplót, és kattintson a **Sorok** elemre.

8.  Szükség esetén módosítsa a számot az **Általános** lap **Mennyiség** mezőjében, majd rendeljen hozzá intézkedéskódot az **Intézkedéskód** mezőben.
    
    Másik megoldásként a **Karanténkezelés** jelölőnégyzet bejelölésével a visszaküldött cikkeket karanténutasítás keretében elvégzett, vizsgálati folyamatra utalhatja.
    

    > [!NOTE]
    > <P>Ha a visszaküldött cikkeket karanténba küldi, nem adhat meg intézkedési kódot.</P>



9.  Kattintson az **Ellenőrzés** gombra.

10. Ha az érvényesség-ellenőrzés nem jelez hibát, kattintson a **Feladás** gombra.

## <a name="register-the-receipt-of-returned-items-in-the-registration-form"></a>A visszáru bevételezésének regisztrálása a Rögzítés képernyőn

A **Beérkezés áttekintése** képernyő helyett másik lehetőségként a **Regisztráció** képernyő is használható a visszaküldött cikkek beérkezésének nyilvántartásba vételére.

1.  Kattintson a következőkre: **Értékesítés és marketing** \> **Közös** \> **Visszárurendelések** \> **MInden visszárurendelés**. Hozzon létre új visszárurendelést, vagy nyissa meg a listáról a visszárurendelést. Válassza ki a visszárurendelés-sort a **Sorok** gyorslapon. Kattintson a **Sor frissítése** gombra, majd kattintson a **Regisztráció** elemre.

2.  Rendeljen hozzá intézkedési kódot az **Intézkedéskód** mezőben, majd kattintson az **OK** gombra.
    

    > [!NOTE]
    > <P>A <STRONG>Regisztráció</STRONG> képernyő használata esetén a cikket nem lehet karanténutasítás formájában vizsgálatra küldeni.</P>



3.  Válasszon ki a rögzítendő tranzakciót a **Tranzakciók** rácsban.

4.  A **Regisztrálás most** rácson kattintson **Hozzáadás** elemre. Addig ismételje az előző két lépést, amíg az összes visszaküldött cikk meg nem jelenik a **Regisztrálás most** rácsban.

5.  Kattintson a **Összes feladása** elemre.

## <a name="see-also"></a>Lásd még

[Beérkezés áttekintése (képernyő)](https://technet.microsoft.com/library/hh227654\(v=ax.60\))

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]