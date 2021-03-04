---
title: Az ajánlatkezelés beállítása az Attract szolgáltatásban
description: Ez a témakör az ajánlatok beállítását írja le a Microsoft Dynamics 365 Talent alkalmazásban.
author: andreabichsel
manager: AnnBe
ms.date: 12/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-18
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bc91a83afd5ce1627376685bcf612d6998ddbc02
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461390"
---
# <a name="set-up-offer-management-in-attract"></a>Az ajánlatkezelés beállítása az Attract szolgáltatásban

[!include [banner](includes/banner.md)]

Amikor egy jelölt átkerül a Dynamics 365 Talent: Attract alkalmazásban az ajánlati fázisba, győződjön meg arról, hogy az ajánlatokat gyorsan létre lehet hozni a pályázó számára, szükség szerint jóváhagyni, és a jelentkezőnek küldeni. Mivel a legtöbb ajánlat szabványos, azok újra felhasználható sablonokból is létrehozhatók. Az Attract szolgáltatásban valamennyi ajánlat belekerül egy ajánlatcsomagba, amely egy vagy több ajánlati dokumentum gyűjteménye. 

Ez a témakör felsorolja azokat a lépéseket, amelyeket az Attract rendszergazdának követnie kell különböző ajánlatcsomag-sablonok beállításához, amely az ajánlatkezelési lehetőségek része az Attract szolgáltatásban. A nem rendszergazdai szerepkörrel rendelkező felhasználóknak nincs hozzáférésük ezekhez a funkciókhoz.

>[!NOTE]
> Az ajánlatkezelési lehetőségek rendelkezésre állnak az Átfogó felvételi bővítmény részeként.

## <a name="offer-data"></a>Ajánlat adatai 

Az ajánlati adat az ajánlatcsomag-sablonban található legkisebb egység. Egy szokványos ajánlati szabványos szövegből és egy értékkészletből áll. Az értékkészletek az egyedüli elemek, amelyeket módosítani lehet az ajánlatok között. Az ajánlat létrehozásakor a legfontosabb szempont, hogy az ajánlatot létrehozó az ajánlati adatok helyőrzőinek listájára összpontosíthat egy ajánlaticsomag-sablonban. Ajánlati adatok beállításához tegye a következőket.

1.  Ugorjon az **Ajánlatkezelés** lehetőségre.

1.  Bontsa ki a **Könyvtár** szakaszt a bal oldali navigációs panelen, majd ugorjon az **Ajánlati adatok** részre.

    >[!NOTE]
    > Az **Ajánlati adatok** lapon vannak a **Jelölt adatai** és a **Projekt részletei** szakaszok. Az Attract néhány nem megszokott ajánlatiadat-helyőrzőt is kínál.
    > 
    > A lapon a különböző ajánlatiadat-helyőrzőket szakaszok rendezik logikai csoportokba. Ezek a szakaszok segíthetnek az ajánlati adatok és az adatok kitöltésének karbantartásában az ajánlat-létrehozási folyamat során.
    > 
    > Ha értéklistát szeretne létrehozni egy helyőrző számára, töltsön fel egy Excel-táblázatot, amelyben az egyik oszlop a helyőrzővel rendelkezik oszlopfejlécként, és tartalmazza a választási lehetőségek listáját az alatta lévő sorokban. Ha ugyanarra a helyőrzőre egy másik adatszabálykészlet is hivatkozik, akkor gondoskodjon arról, hogy közös értékhalmazzal rendelkezzenek.
    
1.  Új ajánlati adatok szakasz létrehozásához kattintson a **Szakasz hozzáadása** lehetőségre, és adjon meg egy egyedi nevet a szakasznak.

1.  Ajánlati adatok helyőrzőinek bármely szakaszhoz való hozzáadásához kattintson az **Ajánlati adatok hozzáadása** lehetőségre, és adjon meg egy egyedi nevet a helyőrzőnek.

1.  Szakasz nevének szerkesztéséhez vigye a kurzort a szakasz neve fölé, és frissítse a nevet.

1.  Bármely meglévő ajánlatiadat-helyőrző nevének módosításához először győződjön meg arról, hogy a helyőrző még nem része bármely sablonnak. Ezt követően vigye a kurzort az ajánlati adatok helyőrzőjének neve fölé, és frissítse a nevet szükség szerint.

1. Bármely meglévő ajánlatiadat-helyőrző törléséhez először győződjön meg arról, hogy a helyőrző még nem része bármely más sablonnak. Ezután vigye a kurzprt helyőrző fölé, és amikor a szemeteskuka ikon látható, kattintson a szemeteskukára az ajánlati adatok helyőrző törléséhez.
    >[!NOTE]
    > Megtekintheti, hogy egy ajánlatiadat-helyőrző hány sablon része, mégpedig az ajánlati adatok mellett található számindikátor alapján. 

1. A szakasz törléséhez vigye a kurzort a neve fölé. Ha a szakaszban levő ajánlati adatok helyőrzőinek egyike sem jelenik meg egy sablonban sem, rákattinthat a szemeteskuka ikonra a törléshez. 
    >[!NOTE]
    > A szakasz törlése a szakaszon belül az összes ajánlatiadat-helyőrzőket is törli.

Az ajánlati adatok helyőrzőinek beállítását követően bármely dokumentumsablonban felhasználhatja őket. Az ajánlati adatok helyőrzői nem korlátozódnak egy adott sablonra – ugyanaz a készlet az összes sablonban alkalmazható.

## <a name="offer-data-rules"></a>Ajánlat adataira vonatkozó szabályok

A legtöbb szervezet rendelkezik szabályokkal, hogy hogyan kell létrehozni az ajánlatokat. Például egy szervezet megkövetelheti, hogy egy bizonyos hely és szolgálati idő kombinációjához tartozó maximális éves fizetési ajánlata egy bizonyos tartományba tartozzon, hogy csak néhány meghatározott érték lehetséges az újonnan felvett dolgozó ajánlati szintjén. Az Attract jelenleg támogatja az összes adatszabályozást, amely CSV-fájlt használ.

A CSV-fájlból az adatszabályok létrehozásához tegye a következőket.

1.  Határozza meg az ajánlati adatok helyőrzőjét a szabálykészlethez. Például **Éves fizetés**.

1.  Azonosítsa az ettől függő ajánlati adatok helyőrzőjének értékeit. Például **Munkavégzési hely** és **Szint**.

1.  Határozza meg az 1. és 2. oszlopot mint **Munkavégzési hely** és **Szint**.

1.  Tartományérték feltöltéséhez legyen a 3. és 4. oszlop az **Éves fizetés**. Ha tartomány helyett egy meghatározott értéket szeretne feltölteni, legyen csak a 3. oszlop az **Éves fizetés**.

1.  A szükséges szerepkörök alapján töltse fel a Microsoft Excel-fájlt.

1.  Ellenőrizze, hogy minden sor az összes érték egyedi kombinációja.

1.  Mentse el a fájlt CSV-formátumban.

Az ajánlati adatokra vonatkozó szabályfájl feltöltéséhez tegye a következőket.

1.  Ugorjon az **Ajánlatkezelés** lehetőségre.

1.  Bontsa ki a **Könyvtár** szakaszt a bal oldali navigációs panelen, majd ugorjon az **Ajánlati adatszabályok** részre.

1.  Kattintson az **Új adatkészlet** lehetőségre, hogy megjelenítse a **Feltöltés** párbeszédablakot.

1.  Adjon egyedi nevet a szabálykészletnek, majd töltse fel a mentett CSV-fájlt.

1.  Kattintson a **Hozzáadás** gombra.
    A szabálykészletet a rendszer fel fogja dolgozni a háttérben, és értesítést fog küldeni az alkalmazáson belül és e-mailben a befejezés után.

    Értesítést fog kapni, ha hibák fordulnak elő a feltöltés feldolgozása közben. Ezután letöltheti a hibanaplót, javítsa ki a fájlt, és újból töltse fel.

1.  A három pont (ellipszis) gomb (**...**) lehetőség használatával letöltheti a szabálykészletet és frissítheti az értékkészletet. Frissítés után újra lehet feltölteni a fájlt.

1.  Egy meglévő szabálykészlet feltöltését törölheti, ha egy másik dokumentumsablonban nincs használatban az éppen definiált helyőrző.

>[!NOTE]
> - Minden helyőrző csak egy egyedi oszlopkészlettel rendelkezhet, amelytől függő. Például ha az **Éves fizetés** függ a **Munkavégzési hely** és **Szint** oszlopoktól, nem tölthető fel egy másik szabálykészlet, ahol az **Éves fizetés** egy másik oszlopkészlettől függ.

> - Letölthet ajánlati adatokra vonatkozó szabálykészlet-mintákat a **Minták** lapon az **Ajánlatiadat-szabályok** oldalon.

> - Ha az ajánlat létrehozója felülbírálja az értékeket, amelyek az ajánlati adatokra vonatkozó szabályok által ajánlottak, az ajánlat nem szabványosként lesz megjelölve, és ez az ajánlat-jóváhagyási munkafolyamat előírását eredményezi.

## <a name="document-templates"></a>Dokumentumsablonok

Az ajánlatdokumentum-sablon segíti a rendszergazdákat az ajánlólevelek létrehozásában. Az ajánlatdokumentum-sablon az ajánlat részének szánt szöveg és a meghatározott ajánlati adatok helyőrzőinek kombinációja. 

Az ajánlatdokumentum-sablon létrehozásához tegye a következőket.

1.  Ugorjon az **Ajánlatkezelés** lehetőségre.

1.  Bontsa ki a **Könyvtár** szakaszt a bal oldali navigációs panelen, és ugorjon a **Sablonok** részre.

    A **Sablonok** lap megjeleníti a már definiált dokumentumsablonok listáját.

1.  Új dokumentumsablon létrehozásához kattintson az **Új sablon** elemre.

1.  Adjon egyedi nevet a sablonnak, majd kattintson a **Létrehozás** lehetőségre.

1.  Rich text szerkesztővel beszúrhatja vagy szerkesztheti az ajánlati dokumentum tartalmát. Táblák, képek és hivatkozások beszúrhatók az elérhető beállítások segítségével, amelyek a szövegszerkesztő tetején találhatók.

1.  Az ajánlatsablon-dokumentumba ajánlati adatok helyőrzőit is beillesztheti a következő módon:

    - Húzza át a jobb panelből.

    - A hashtag segítségével helyezze a megfelelő helyre az ajánlatiadat-helyőrzőt. Gépelje be, hogy **\#**, majd kezdje el beírni az ajánlatiadat-helyőrző nevét. Lehetőségek jelennek meg a legördülő listából. Nyomja le vagy kattintson az **Enter** gombra az ajánlatiadat-helyőrző beszúrásához.

    >[!NOTE]
    > - Ahhoz, hogy egy helyőrzőt az ajánlatidokumentum-sablonhoz társítsa anélkül, hogy értékét felfedje a jelölt előtt, vigye a kurzort az ajánlatiadat-helyőrző fölé, majd kattintson a **Rögzítés** ikonra. Ez a helyőrzőt elküldi a **Rögzített ajánlati adatok** szakaszba az ajánlatdokumentum-sablonban. A rögzítés feloldásához kövesse ugyanazokat a lépéseket, de az ajánlatiadat-helyőrzők listájában kattintson a **Rögzítés feloldása** elemre.

    > - Az aktív ajánlati adatok helyőrzői listájának megtekintéséhez váltson át az **Aktív** lapon a jobb oldali panelen.

    > - Ha beszúr egy helyőrzőt, amelyet egy ajánlati adatokra vonatkozó szabálykészlet vezérlik megtekintheti a függőséget, amely az adott ajánlatiadat-helyőrző és más értékek között fennáll.

    > - Egyéb esetben **importálhatja** egy .docx fájl tartalmát a helyi számítógépére, ahol szükség szerint szerkesztheti. Ezzel a módszerrel nem kell begépelnie a szerkesztőbe minden tartalmat.

1. Az ajánlati dokumentum előnézetének megtekintéséhez használja az **Előnézet** lehetőséget az oldal tetején.

1. Szabályozhatja, hogy az ajánlat létrehozó szerkesztheti-e az ajánlati dokumentum tartalmát az oldal tetején található **Engedélyek kezelése** lehetőséggel. Ha azt szeretné, hogy az ajánlat létrehozója ne módosíthassa a szöveget, és csak a helyőrző értékeit illeszthesse be, állítsa az engedély értékét **Nem** beállításra.

1. A folyamat előrehaladásának mentéséhez kattintson a **Mentés** gombra. A sablont a rendszer vázlat állapotúként menti.

1. A dokumentum véglegesítéséhez és közzétett állapotúként való megjelöléséhez kattintson a **Befejezés** lehetőségre.

1. Megtekintheti, melyik dokumentumsablonok jelenleg aktívak, melyek vannak vázlat módban, melyeket archiváltak és melyek már nincsenek használatban a dokumentumsablonok könyvtár érkezési élményében.

>[!NOTE]
> Bármely ajánlat dokumentumsablonját törölheti, amely nem szerepel egy meglévő ajánlaticsomag-sablonban.


## <a name="offer-package-templates"></a>Ajánlaticsomag-sablonok

Az ajánlatcsomagok olyan ajánlati műtermékek, amelyek a jelölttel meg vannak osztva, és egy vagy több ajánlati dokumentumsablon kombinációját tartalmazzák. Az ajánlatcsomag létrehozásához tegye a következőket.

1.  Ugorjon az **Ajánlatkezelés** lehetőségre.

1.  Ugorjon a **Csomagok** lehetőségre a bal oldali navigációs panelben.

    Az ajánlat-létrehozók számára elérhető aktív csomagsablonok listája jelenik meg.

1.  Ha új ajánlati csomagot szeretne létrehozni, kattintson az **Új csomag** gombra.

1.  Adjon egyedi nevet, majd kattintson a **Létrehozás** lehetőségre.

1.  Kattintson a **Sablon hozzáadása** lehetőségre.

    >[!NOTE]
    > - Választhat, hogy létrehoz egy új sablont, vagy választ egy már meglévőt.

    > - Ha a meglévő sablon hozzáadását választja, akkor győződjön meg arról, hogy az ajánlati dokumentumsablont mentették, véglegesítették és aktívként megjelölték.
    
    > - Tetszőleges számú dokumentumsablont lehet kiválasztani. 
    
1.  Kattintson a **Kész** lehetőségre a **Csomag kezelése** ponthoz való visszatéréshez.

    A dokumentumok sorrendjét beállíthatja, és azt is bejelölheti, hogy az adott ajánlati dokumentumra szükség van-e ajánlat létrehozása során. Az ajánlat létrehozójának lesz lehetőségre, hogy törölje a dokumentumokat, amelyek **Nem szükséges**-ként vannak megjelölve.

1. Az ajánlati csomag sablonjának olyan módon való mentéséhez, hogy azt az összes ajánlatkészítő használhassa, kattintson a **Mentés és közzététel** lehetőségre.

   Vázlatos ajánlaticsomag-sablonok megtekintéséhez ugorjon a **Vázlatok** lapra. Ha az ajánlaticsomag-sablon módosul, el kell menteni és újra közzétenni.

## <a name="configure-an-offer-process"></a>Ajánlati folyamat konfigurálása

Az ajánlatkészítési folyamatnak számos olyan része van, amelyet egy Attract-rendszergazda konfigurálhat.

- **Ajánlatok jóváhagyása** – Válassza ki, hogy az ajánlatok jóváhagyása szükséges-e, mielőtt az ajánlat elküldhető a jelöltnek. Rendszergazdaként eldöntheti azt is, hogy az összes ajánlatra vonatkozó jóváhagyás egymás utáni sorrendben vagy párhuzamos jóváhagyási munkafolyamattal történjen. Azt is előírhatja, hogy az ajánlatok jóváhagyóinak kell-e megjegyzést hozzáadniuk az ajánlat jóváhagyásához. A nem szabványos ajánlatok esetén az ajánlat-jóváhagyások kötelezőek.

- **Jelölt ajánlati élménye** - rendszergazdaként, lehetősége van azt beállítani, hogy minden ajánlathoz tartozik-e lejárati dátum, és ha igen, mi legyen az alapértelmezett eltolás a lejárati dátum esetén. Az is konfigurálható, hogy a pályázók elutasíthatja-e az ajánlatot.

- **e-aláírások** – Rendszergazdaként,kiválaszthatja, hogy a pályázók milyen módot használhatnak az aláírásokhoz.
    - Adobe Sign – Az összes ajánlati csomag küldése és aláírása az Adobe Sign használatával történik. Minden egyes ajánlatot létrehozó esetében kapcsolni kell Adobe Sign fiókot az Attract alkalmazáshoz. Adobe Sign licencekért és ingyenes próbaverzióért keresse fel ezt a [hivatkozást](https://acrobat.adobe.com/us/en/business/integrations/microsoft-dynamics-365-for-talent.html).

    - DocuSign – Az összes ajánlati csomag küldése és aláírása a DocuSign használatával történik. Minden egyes ajánlatot létrehozó esetében kapcsolni kell DocuSign fiókot az Attract alkalmazáshoz. 
    
    - ESign – Ez az alapértelmezett beállítás, amelyet az alkalmazás tartalmaz, a felhasználó neve és monogramja beírásával írhatja alá az ajánlatot.


Az ajánlat-létrehozási folyamattal kapcsolatos további tudnivalókért tekintse meg az [Ajánlatok létrehozása, jóváhagyása és aláírása](./creating-offers.md) című részt.


[!INCLUDE[footer-include](../includes/footer-banner.md)]