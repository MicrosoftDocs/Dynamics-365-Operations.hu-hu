---
title: "Kiskereskedelmiperiféria-szimulátor"
description: "Ez a témakör a Perifériaszimulátor eszközt mutatja be, amely a része a Microsoft Dynamics 365 for Operations - Retail programcsomagjának."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 266544
ms.assetid: 16f31e70-15fc-441e-9727-e6a31c3a48f5
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
translationtype: Human Translation
ms.sourcegitcommit: 42dc414ff2bb6359b47d89c3bd3c510e4258f816
ms.openlocfilehash: b2229466040351d8c2b9494b30b4c928651820b8
ms.lasthandoff: 03/31/2017


---

# <a name="retail-peripheral-simulator"></a>Kiskereskedelmiperiféria-szimulátor

[!include[banner](includes/banner.md)]


Ez a témakör a Perifériaszimulátor eszközt mutatja be, amely a része a Microsoft Dynamics 365 for Operations - Retail programcsomagjának.

<a name="overview"></a>Áttekintés
--------

A Microsoft Dynamics 365 for Operations - Retail perifériaszimulátor egy olyan eszköz, amely segít a kiskereskedelmi környezetben használt perifériák beállításában, tesztelésében és hibaelhárításában. A perifériaszimulátor segítségével egyszerűsítheti a kiskereskedelmi perifériák tesztelését, és elszigetelheti azokat a problémákat, amelyeket a helytelen telepítés vagy az eszközillesztők hibás működése okoz. A perifériaszimulátor tartalmaz egy olyan asztali programot, amely a Dynamics 365 for Operations - Retail által támogatott eszközök virtuális verzióit tartalmazza. Egy-egy szakasz egy-egy virtuális eszköznél az eszköz és a kiskereskedelmi értékesítési pont (pénztár) közötti interakciót mutatja be. Használhatja azt is, hogy megadja a különböző pénztárforgatókönyvekre érvényes bemeneteket. A perifériaszimulátor támogatja a pénztár és a következő virtuális eszközök közötti interakciót:

-   **Nyomtató** – A perifériaszimulátor képes megjeleníteni a pénztárnyomtatókhoz konfigurált nyugtákat.
-   **Sor megjelenítése** – beállíthatja, hogy egy virtuális sor megjelenítése tevékenység jelenjenek meg a fizikai sor megjelenítése.
-   **Mágnescsík-olvasó (MSR)** – a POS szimulált mágnescsík események a rendszerből a perifériás szimulátor küldhet.
-   **Fiók** – fizikai pénzfiók szimulálható.
-   **2. fiók** – egy második pénzfiók a perifériás szimulátor a beállításával szimulálhatja egy POS-pénztárgép rendelkezik aktív két műszakban használó forgatókönyvekben.
-   **Lapolvasó** – a virtuális vonalkód-leolvasót a perifériás szimulátor támogató vonalkód beolvasási eseményeket adhat ki.
-   **Skála** – egy virtuális skála szimulálhatja a POS lemért elemek interakció.
-   **Személyi azonosító szám (PIN) pad** – PIN pad műveletek szimulálható. **Megjegyzés:** be kell állítani a támogatás a fizikai PIN-billentyűzet a fizetési csatlakozón keresztül.
-   **Aláírás-rögzítő** – a perifériás szimulátor tartalmaz egy virtuális aláírás-rögzítő eszköz, amelyet meg kell adni az egyes ajánlatok, például a vevői számla kifizetések szükséges aláírásoknak állíthat be.

A perifériás szimulátor segítségével szimulálása billentyűzet ék eseményeket egy vonalkód-leolvasót és MSR származik. A virtuális perifériás szimulátor kifejezetten támogatja az objektum csatolása és beágyazása a Retail POS (OPOS) eszközök.

## <a name="key-scenarios"></a>Kulcsesetek
### <a name="troubleshooting"></a>Hibaelhárítás

A perifériás szimulátor segítségével megoldhatja az eszköz beállítása. Ha nem rendelkezik a perifériás szimulátor vagy a második eszköz azonos osztályú, lehet nehéz meghatározni, ahol problémák származnak. Azonban ha a perifériás szimulátor, is beállítása virtuális eszközök, és futtassa az azonos kód elérési utak és üzleti logikát használt fizikai eszközöket. A perifériás szimulátor szempontjából a virtuális eszközök és fizikai eszközök közötti fő különbség a szolgáltatás tárgyait vagy a eszköz-illesztőprogram. Általában a fizikai eszköz szolgáltatásobjektumát az eszköz gyártója biztosítja. Ezzel szemben a perifériás szimulátor, a szolgáltatási objektumok szolgálnak a perifériás szimulátor részeként. A perifériás szimulátor nem működik megfelelően, ha az eszköz nem működik megfelelően az eszköz nevét a hardverprofilban valós eszköz nevének módosítása után, amikor azt feltételezik, hogy az a gyártó által biztosított szolgáltatás objektum probléma van.

### <a name="training"></a>Oktatás

A perifériás szimulátor segítségével reális pénztáros képzés, amikor a fizikai hardver beállítás nem érhető el a réteg hozzáadása. A perifériás szimulátor képzési forgatókönyvek szerepel, ha a pénztáros hatékonyabban kezelheti a POS azáltal, hogy például a termék kód ellenőrzés és ajándékutalvány bemeneti kártya swipes, és egy adott tranzakció nyomtatott dokumentumok betartásával.

### <a name="testing"></a>Tesztelés

A perifériás szimulátor segítségével termék vonalkódok, beérkezés formátumok és így tovább, anélkül, hogy telepíteni egy virtuális környezetben a fizikai hardver tesztelése. Fizikai hardver nem szükséges, és ne kelljen a POS-ügyfél hardver állomáson vagy fizikai számítógépen telepíteni, mert gyorsabban tesztelheti a back office végrehajtott módosításokat.

## <a name="set-up-the-peripheral-simulator"></a>Perifériaszimulátor beállítása
### <a name="set-up-a-hardware-profile"></a>Hardverprofil beállítása

1.  A perifériaszimulátor beállításához kattintson a **Kiskereskedelem és kereskedelem** &gt; **Csatorna beállítás** &gt; **POS beállítás** &gt; **POS profilok** &gt; **Hardverprofilok** elemre.
2.  Új profil létrehozásához kattintson az **Új** elemre.
3.  Írja be a **Profilszám** és a **Leírás** mezők értékeit.
4.  Az alábbi táblázat segítségével állítsa be a virtuális eszközök, meg kell vizsgálni. Az alábbiakban a táblázat oszlopainak magyarázatát találja:
    -   **Eszköz** – Ez az oszlop elnevezi a gyorslapon, bontsa ki az eszköz beállítása.
    -   **Eszköz típusa** – ebben az oszlopban látható értéket jelöli, az eszköz neve mezőjében válassza ki.
    -   **Eszköz neve** – ebben az oszlopban látható pontos érték, az eszköz nevét adja meg. **Fontos:** az itt megadott eszköz neve szükség, mert a hardver állomás ezeket a neveket használja az eszközök kezelésére. Ha nem használja ezeket a neveket, az eszköz nem lesz használható.

    | Eszköz            | Eszköztípus | Eszköznév              |
    |-------------------|-------------|--------------------------|
    | Nyomtató           | OPOS        | MockOPOSPrinter          |
    | Sor megjelenítése      | OPOS        | MockOPOSLineDisplay      |
    | MSR               | OPOS        | MockOPOSMSR              |
    | Kiállító            | OPOS        | MockOPOSDrawer1          |
    | Drawer2           | OPOS        | MockOPOSDrawers          |
    | Leolvasó           | OPOS        | MockOPOSScanner          |
    | Lépték             | OPOS        | MockOPOSScale            |
    | PIN-billentyűzet           | OPOS        | MockOPOSPinPad           |
    | Aláírás rögzítése | OPOS        | MockOPOSSignatureCapture |

**Megjegyzés:** a hardverprofilban nincs külön telepítési szimulálása a vonalkód-leolvasót és MSR ék billentyűesemények van szükség.

### <a name="assign-the-hardware-profile-to-a-register"></a>Hardverprofil társítása pénztárgéphez

1.  A Hardverprofil létrehozását követően: **Kiskereskedelem és kereskedelem** &gt; **Csatorna beállítása** &gt; **POS beállítása** &gt; **Pénztárgépek**.
2.  A a **POS-pénztárgépek** listáját, kattintson a hivatkozásra a **jegyzék száma** a nyilvántartásban a perifériás szimulátor használandó mezőt.
3.  Kattintson a **Szerkesztés**lehetőségre.
4.  A a **profilok** ebben a szakaszban a **hardverprofil** mezőben, válassza ki a létrehozott virtuális perifériákat hardverprofilt.
5.  Kattintson a **Mentés** gombra.

### <a name="synchronize-changes-to-the-channel-database"></a>A csatorna-adatbázist érintő módosítások szinkronizálása

1.  Ugorjon a **Kiskereskedelem és kereskedelem** &gt; **Kiskereskedelem Informatika** &gt; **Elosztási ütemezéspontra**.
2.  Az **1090** elosztási ütemezés kiválasztása
3.  Kattintson a **Futtatás most** lehetőségre a változások szinkronizálásához a pénztárgéppel.

Az adatok szinkronizálása után az új hardverprofil és a nyilvántartásban szereplő módosítások állnak rendelkezésre a csatorna adatbázisban.

## <a name="install-the-peripheral-simulator"></a>Perifériaszimulátor telepítése
1.  Lépjen a **Kiskereskedelem és kereskedelem** &gt; **Csatorna beállítás** &gt; **POS beállítás** &gt; **POS profilok** &gt; **Hardverprofilok** pontra.
2.  Kattintson a **Letöltés**, majd a **PeripheralSimulator** pontra. **Megjegyzés:** kapcsolja ki az előugróablak-blokkolók a perifériás szimulátor letöltése előtt.
3.  Miután a letöltés befejeződött, nyissa meg a **Letöltések** mappát, majd kattintson duplán a **VirtualPeripherals.msi** elemre a telepítő indításához.
4.  A perifériás szimulátor telepítése az alapértelmezett beállítások használatával.

A perifériás szimulátor mellett a közös ellenőrző objektumok Monroe konzultációt szolgáltatásokból kell telepítenie. Ellenkező esetben a perifériás szimulátor nem fog megfelelően működni. A közös ellenőrző objektumok letöltéséhez keresse fel: <http://monroecs.com/oposccos_current.htm>.

## <a name="using-the-peripheral-simulator"></a>Perifériaszimulátor használata
A perifériás szimulátor megkezdéséhez kattintson **Start** írja be a számítógép **kiskereskedelmi perifériás szimulátor**, majd válassza ki az alkalmazás a keresési eredmények között megjelenő. A perifériás szimulátor elindításához kattintson az eszköz neve a támogatott eszközök. Ezek az eszközök a lapfülek az ablak bal oldalán jelenik meg. Egy adott eszköz megtekintéséhez kattintson a lap az eszköznek.

### <a name="line-display-capabilities"></a>Sormegjelenítési lehetőségek

A sormegjelenítés az első eszköz, amely szerepel a perifériás szimulátornál. A virtuális megjelenítésére van beállítva, mutat sorokat, akkor ellenőrzi a POS-tranzakció. Vonal elemek mellett a táblázat mutatja a ajánlatot kijelölésekor a POS visszajáró összege. Azt is megmutatja az esedékes egyenleg Ha ajánlatot ad meg, de még mindig az egyensúlyt a tranzakció esedékes. A POS nincs használatban, ha egy üzenet jelzi, hogy bezárta-e a kasszaelrendezés jeleníthető meg. Konfigurálnia kell az üzenet a **Sor megjelenítése** a hardverprofilban gyorslapra.

### <a name="cash-drawer-capabilities"></a>Pénztárfiók funkciói

A pénztárfiók a második eszköz, amely szerepel a perifériás szimulátornál. A hardverprofil készpénz virtuális fiók használatára van beállítva, ha a POS fiók műveletekhez, például fizetőeszköz-elszámolások, válaszul a pénztárfiók, az aktív műszak megnyitása, és hogy a pénztáros teheti módosítása vagy készpénz letét szabványos cash-and-carry tranzakciók során. A virtuális készpénz szekrények vannak a címkék **fő fiók** és **másodlagos fiók**. Ezek a címkék ábrázolják fiók és 2 fiók a hardverprofilban, illetőleg. Ha a fiók le van zárva, zárt pénzfiók képe látható, és a lezárt pénzfiók gombja ki van jelölve – **Fiók kinyitása**. Ha erre a gombra kattint, a kép helyére egy nyitott pénzfiók annak jelzésére, hogy a fiók most nyissa meg a képet. A gomb a megnyitott pénzfiók címkével ellátott **Fiók becsukása**. A POS-nál több művelet is okozhat a pénztárfiók megnyitásához. Legtöbb olyan művelet nem hajtható végre, a pénztárfiók meg van nyitva. A kivételek közé tartoznak a nap végén műveletek. A POS-felhasználó kap egy hibaüzenet, amely arról tájékoztat, hogy egy művelet nem hajtható végre, amíg nyitva a pénztárfiók, ha a felhasználó a virtuális vagy fizikai pénzfiók a folytatáshoz zárja be. Ha a pénzfiók van megjelölve, **megosztott** a hardverprofilban, a rendszer nem győződjön meg arról, hogy a fiók le van zárva, a művelet előtt. A művelet folytatódik, a szokásos módon, még akkor is, ha meg nyitva a pénztárfiók. Ez a jelenség által támogatott forgatókönyvek értékesítési társult vállalkozások között megosztott készpénz szekrények, valamint ha egy társult a pénzfiók használja, míg egy másik társult vállalkozás saját POS eszköz független feladatokat hajtja végre. A pénztárfiók végrehajtott módosítások nem nyilvánvaló mindaddig, amíg az aktuális műszak le van zárva, és új műszak meg van nyitva.

### <a name="msr-capabilities"></a>MRS-képességek

A perifériás szimulátor robusztus támogatást nyújt virtuális MSR műveletekhez vagy OPOS vagy billentyűzet ék üzemmódban dolgozik. Az OPOS módhoz, hogy az MSR konfigurálni kell a hardverprofil OPOS eszközként működjön. Billentyűzet ék módban csak billentyűesemények ék adatokat küld a Microsoft Windows. Telepítő eltérései mellett OPOS és a billentyűzet ék módok különböznek az alábbi módon:

-   A POS-ügyfél lehetővé teszi, hogy adott esetben forgatókönyvek, amelyek lehetővé teszik a hűséges vagy Ajándékutalvány-kártya tételébe mágnescsík adatait például OPOS MSR eszközök.
-   Billentyűzet ék módban a perifériás szimulátor adatokat küld a billentyűzet ék a mező akkor aktív, ha az adatok. Ez a viselkedés hasonló a probléma akkor jelentkezik, ha az adatok a billentyűzetről. Az MSR használ egy billentyűzet-ék, a felhasználó át kell váltania a kiskereskedelmi Modern POS (MPOS), győződjön meg arról, hogy érkeztek-e adatok a megfelelő mezőben. Késés, így beállíthatja, hogy a felhasználó ideje kattintva győződjön meg arról, hogy az adatokat küldeni a megfelelő mező.

#### <a name="testing-gift-and-payment-card-swipes"></a>Ajándékutalvány és fizetési kártya swipes tesztelése

A virtuális MSR is biztosít a perifériás szimulátor ajándékutalvány és fizetési kártya swipes forgatókönyvek tesztelése MSR adatok beállítását teszi lehetővé. Kártya létrehozásához kattintson a plusz jelre (**+**) gombra, és válassza ki a kártyát. Ezután adja meg a kártya száma, vagy nyomon az adatokat, amelyek a POS a lejárat hónapja és éve a kártya, amely akkor kell küldeni. A kiválasztott érték a **kártya típusú** mező csak a kártya rendelt címke. Ez a címke megkönnyíti a kártyák azonosítsa azokat a perifériás szimulátor keresztül is Lehúzott. Választhatja a balra mutató nyíl segítségével a perifériás szimulátor a konfigurált kártyák (**&lt;**) és a jobbra nyíllal (**&gt;**) a kép, a kártya a fenti gombok. Kartonokat segítségével szerkesztheti és a **Szerkesztés** és **törlése** gomb melletti plusz jelre (**+**) gombra.

### <a name="pin-pad"></a>PIN-billentyűzet

Beállíthatja, hogy a PIN pad szimulátor szimulálja az OPOS PIN-billentyűzet. Az elektronikus átutalási (EFT) tranzakció történik a POS-nál, és csak a megadott PIN-kód, ha a hardver állomás meghívja a megadott PIN-kód kérése-PIN-kód eszköz. Működik, a PIN-billentyűzet a perifériás szimulátor az EFT összekötő támogatás szükséges.

### <a name="printer"></a>Nyomtató

A POS-ból nyomtatják a virtuális perifériás nyomtató csak beérkezések látható. Ha a nyomtatási művelet bevételezések, görgetheti a bevételek.

#### <a name="configure-receipt-printing"></a>Nyugtanyomtatás konfigurálása

1.  Lépjen a **Kiskereskedelem és kereskedelem** &gt; **Csatorna beállítás** &gt; **POS beállítás** &gt; **POS profilok** &gt; **Hardverprofilok** pontra.
2.  Válassza ki a létrehozott virtuális perifériákat hardverprofilt.
3.  A **Nyomtató** gyorslapon kattintson a **Szerkesztés** elemre.
4.  A **Nyugta profilazonosítója** mezőben jelölje be a nyugtaprofilt.
5.  Kattintson a **Mentés** gombra.

### <a name="scale"></a>Lépték

Ha egy termék skálázása hozzáadódik a POS-tranzakció, és a skála van beállítva, a POS átveszi a tömeg a skála. A mind a virtuális és fizikai méret a termék vagy a tömeg meg kell határozni a termék hozzáadódik a tranzakció előtt. A skála termék hozzáadása a tranzakcióhoz, mielőtt a skála a perifériás szimulátor lépjen, és használja a plusz jelre (**+**) és a mínuszjel (**–**) gombok jelentse a skála tömeg beállításához. Közvetlenül a kívánt szélességet is megadhatja az **Aktuális érték** mezőben. A pluszjel segítségével módosíthatja a tömeg a skála az egységek (**+**), **Szerkesztés**, és **törlése** gombok. Ezzel a módszerrel egységek lemérik a termékek vagy a területi hol van használatban a skála alapján megadható.

#### <a name="configure-a-scale-product"></a>Skálázott termék konfigurálása

1.  Nyissa meg a következőt: **Kiskereskedelem és** **kereskedelem** &gt; **Termékek és kategóriák** &gt; **Felszabadított termékek kategóriák szerint**.
2.  Nyissa meg a termékrekordot.
3.  Válassza ki a megmérni kívánt terméket.
4.  A a **kiskereskedelmi** gyorslapon állítsa a **skála termék** beállítás a **nem** a **Igen**.

#### <a name="synchronize-changes-to-the-channel-database"></a>A csatorna-adatbázist érintő módosítások szinkronizálása

1.  Ugorjon a **Kiskereskedelem és kereskedelem** &gt; **Kiskereskedelem Informatika** &gt; **Elosztási ütemezéspontra**.
2.  Az **1040** elosztási ütemezés kiválasztása
3.  Kattintson a **Futtatás most** lehetőségre a változások szinkronizálásához a pénztárgéppel.

Az adatok szinkronizálása esetén ha egy termék skálázása hozzáadódik a POS-tranzakció, és a POS ellenőrzi a mérlegen a súlyt.

### <a name="signature-capture"></a>Aláírás rögzítése

A virtuális aláírás-rögzítő eszköz figyelmezteti a felhasználót, ha a pályázat használt aláírást igényel aláírás biztosít a virtuális aláírás rögzítési pad. A felhasználó fogadhatja el az aláírást a POS megjelenítése. A pénztáros majd fogadhatja el az aláírást. Az aláírás majd a pályázat együtt menti, és az irodai és egyéb tranzakciós adatok szinkronizálva lesz.

#### <a name="set-up-a-tender-to-require-a-signature"></a>A pályázat kötelező aláírás be

1.  Nyissa meg a következőt: **Kiskereskedelem és kereskedelem** &gt; **Csatornák** &gt; **Kiskereskedelmi áruházak** &gt; **Minden kiskereskedelmi üzlet**.
2.  Válassza ki a kiskereskedelmi üzletet.
3.  Kattintson a **Szerkesztés**lehetőségre.
4.  Kattintson a **Beállítás** elemre, majd a **Beállítás** szakaszban kattintson a **Fizetési módok** lehetőségre.
5.  Kattintson a **Szerkesztés**lehetőségre.
6.  Jelölje be az aláírást igénylő fizetési módot.
7.  Az **Általános** szakasz alatti **Aláírás-rögzítő** pontnál állítsa be az **Aláírás-rögzítő eszköz használata** lehetőségnél az **Igen** beálíltást.
8.  Az **Aláírás-rögzítési minimumösszeg** mezőbe írja be a minimális összeget kell kiváltó aláírás rögzítése.

#### <a name="synchronize-changes-to-the-channel-database"></a>A csatorna-adatbázist érintő módosítások szinkronizálása

1.  Ugorjon a **Kiskereskedelem és kereskedelem** &gt; **Kiskereskedelem Informatika** &gt; **Elosztási ütemezéspontra**.
2.  Az **1070** elosztási ütemezés kiválasztása
3.  Kattintson a **Futtatás most** lehetőségre a változások szinkronizálásához a pénztárgéppel.

Után az adatok szinkronizálva, ajánlat szolgál, amelyhez az aláírást, és az összeg megfelel-e az aláírás küszöbértéket, a POS adatokat kér be a virtuális aláírás-rögzítő eszköz lévő aláírást.

## <a name="additional-configuration"></a>További konfiguráció
Módosíthatja a perifériás szimulátor konfigurációs fájl az éppen Tesztelési forgatókönyvek megfelelően megoldására. C: a konfigurációs fájlban található\\Program Files (x86)\\a Microsoft Dynamics 365\\70\\VirtualPeripherals\\Microsoft.Dynamics.Commerce.VirtualPeripherals.Client.exe.config. A konfigurációs fájl meghatározza azokat az egységeket, amelyek rendelkezésre állnak tesztelésre, a tesztelésre rendelkezésre álló kártyatípusokat, valamint a vonalkódtípusokat. Például a konfigurációs fájlban lévő szövegértékek módosításával új kártyatípust vagy mértékegységet adhat meg, amelyet a futás során ki lehet választani. Az új értékek az alkalmazás újraindítása után fognak megjelenni.

## <a name="troubleshooting"></a>Hibaelhárítás
A perifériás szimulátor tevékenységek a perifériás szimulátor belül jelentkezett. A naplóban található: C:\\Program Files (x86)\\a Microsoft Dynamics 365\\70\\VirtualPeripherals\\Microsoft.Dynamics.Commerce.VirtualPeripherals.Client.exe.config. A perifériás szimulátor a Windows eseménynaplójával kapcsolatos hibákat is jelent, amelyekhez itt férhet hozzá: **Alkalmazási és szolgáltatási naplók** &gt; **Microsoft** &gt; **DynamicsAX**. Ha a hardverprofil vagy más területeken végzett módosítások nem nyilvánvaló, MPOS vagy a perifériás szimulátor használata esetén, ellenőrizze a terjesztési Ütemezőfeladatok szinkronizálja az adatokat a csatorna adatbázishoz használt. Ha a változások szinkronizálásának, de még mindig nem nyilvánvaló a POS, indítsa újra a POS-ügyfél. Készpénz beállított fiók módosításai nem hatékony, új műszak létrehozásáig. Ha változtatásokat készpénz szekrények, mindenképpen mindig bezárja az új készpénz fiók beállítását szeretné ellenőrizni a meglévő műszak. Bizonyos esetekben a gyártó illesztőprogram van telepítve, a közös ellenőrző objektumok Monroe konzultációt szolgáltatások után, az illesztőprogram nem működik megfelelően a közös ellenőrző objektumok okozhat. Ebben az esetben telepítse újra a közös ellenőrző objektumokat.

<a name="see-also"></a>Lásd még
--------

[Kiskereskedelmi perifériák – áttekintés](retail-peripherals-overview.md)




