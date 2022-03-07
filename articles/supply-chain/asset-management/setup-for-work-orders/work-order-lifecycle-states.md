---
title: Munkarendelés életciklus-állapotai
description: Ez a témakör a munkarendelés életciklus-állapotait mutatja be az Eszközkezelésben.
author: johanhoffmann
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderLifecycleState, EntAssetWorkOrderLifecycleModel
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: fa0980438ec629ef7ae6bf711d5ae87efca131e6ab86dfcaa1f17d953725147a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6768666"
---
# <a name="work-order-lifecycle-states"></a>Munkarendelés életciklus-állapotai


[!include [banner](../../includes/banner.md)]

 

A Munkarendelés életciklusának állapotai határozzák meg, hogy a Munkarendelés milyen állapotokat vehet fel. Ilyenek például: **Létrehozva**, **Ütemezve**, **Folyamatban**, és **Befejezve**. A Munkarendelés életciklusával kapcsolatos állapotok manuálisan is frissíthetők egy munkarendelésen, vagy automatikusan módosíthatók (például a Munkarendelés ütemezése során).

A munkarendelésekhez szükséges munkarendelés életciklus-állapotait a megfelelő projektállapotokhoz kell csatolni a **Projektvezetési és könyvelési paraméterek** oldalon (**Projektvezetési és könyvelés** \> **Projektvezetési és könyvelési paraméterek**). Elsőként a projekt fázisait a Projektvezetési és könyvelés részben állíthatja be. Ezután az Eszközkezelésben beállíthatja a munkarendelési életciklus-állapotokat és munkarendelési életciklus-modelleket.

A következő táblázat leírja a lehetőségeket a **Munkarendelés életciklus-állapota** oldal **Általános** gyorslapjának **Munkarendelés** és **Ütemezés** szakaszaiban (**Eszközkezelés** \> **Beállítás** \> **Munkarendelések** \> **Életciklus-állapotok**).

![Munkarendelés életciklus-állapota oldal.](media/09-setup-for-work-orders.png)

| Beállítás neve                   | Leírás |
|-------------------------------|-------------|
| Aktív                        | Állítsa a beállítást **Igen** értékre, ha a munkarendelésnek aktívnak kell lennie, miközben ebben az életciklus-állapotban van. |
| Sor hozzáadása                      | Akkor állítsa ezt a beállítást **Igen** értékre, ha a Munkarendelés-feladatok hozzáadhatók egy olyan munkarendeléshez, amely ebben az életciklus-állapotban van. |
| Eltávolítás                        | Állítsa a beállítást **Igen** értékre, ha egy munkarendelés törölhető, miközben ebben az életciklus-állapotban van. |
| Sor törlése                   | Akkor állítsa ezt a beállítást **Igen** értékre, ha a Munkarendelés-feladatok törölhetők egy olyan munkarendelésből, amely ebben az életciklus-állapotban van. |
| Ütemezés engedélyezése              | Állítsa a beállítást **Igen** értékre, ha egy munkarendelés ütemezhető, miközben ebben az életciklus-állapotban van. |
| Tényleges kezdés beállítása              | Állítsa ezt a beállítást **Igen** értékre, ha a felhasználónak meg kell adnia a tényleges kezdési dátumot és időpontot a munkarendeléshez, amikor az adott életciklus-állapotra módosul. |
| Tényleges befejezés beállítása                | Állítsa ezt a beállítást **Igen** értékre, ha a felhasználónak meg kell adnia a tényleges befejezési dátumot és időpontot a munkarendeléshez, amikor az adott életciklus-állapotra módosul. |
| Naplók feladása                 | Akkor állítsa ezt a beállítást **Igen** értékre, ha a Munkarendelés-naplókat automatikusan közzé kell tenni, amikor a munkarendelést erre az életciklus-állapotra frissítik. Ha hiba történik a napló feladásakor, akkor egy üzenet jelenik meg, és a Munkarendelés életciklus-állapotának frissítése érvénytelenítve van. Egy munkarendeléshez tartozó naplósorok megtekintéséhez válassza ki az **Eszközkezelés** \> **Általános** \> **Munkarendelések** \> **Összes munkarendelés**, **Aktív munkarendelések**, vagy **Saját munkarendelések** elemet, válassza ki a munkarendelést a listán, majdválassza ki a **Naplók** elemet. A munkarendelés naplójának automatikus közzétételi beállítása egy adott életciklus-állapotnál ugyanaz, mintha kiválasztaná a **Naplók közzététele** lehetőséget a **Munkarendelési naplók** oldalon.<p>**Megjegyzés:** Ha a beállítást **igen** értékűre állítja, akkor a program automatikusan feladja a naplókat, ha nincs beállítva jóváhagyási munkafolyamat. Ha a vállalata napló-jóváhagyási beállítást használ, amelyet a **Napló jóváhagyása** oldalon konfiguráltak (**Projektkezelés és könyvelés** \> **Beállítás** \> **Naplók** \> **Napló jóváhagyása**), akkor egy vezetőnek vagy adminisztrátornak ellenőriznie és közzétennie kell a felhasználási regisztrációt.</p> |
| Karbantartási ellenőrző lista feldolgozása | Akkor állítsa ezt a beállítást **Igen** értékre, ha az összes csatolt karbantartási ellenőrzőlistát fel kell dolgozni, amikor a munkarendelést erre az életciklus-állapotra frissítik. Ennek a feldolgozásnak a részeként a program felveszi a karbantartási ellenőrzőlistán végrehajtott összes számlálási regisztrációt, és kiértékeli a teljes karbantartási ellenőrzőlista eredményeit. A **Megfelelt** és **Ne felelt meg** eredménnyel rendelkező karbantartási ellenőrzőlista-sorokat a rendszer kiértékeli, és ha legalább egy sor nem felelt meg, akkor az Eszközkezelésben a teljes karbantartási ellenőrzőlista **Nem felelt meg** jelölést kap. |
| Elkészült                         | Akkor állítsa ezt a beállítást **Igen** értékre, ha az összes, munkarendelésen létrehozott munkarendelési feladat Munkarendelési feladatütemezési állapota automatikusan frissüljön **Készen áll** állapotra, amikor a munkarendelést erre az életciklus-állapotra frissítik. |
| Kezdete                         | Akkor állítsa ezt a beállítást **Igen** értékre, ha az összes, munkarendelésen létrehozott munkarendelési feladat Munkarendelési feladatütemezési állapota automatikusan frissüljön **Elkezdve** állapotra, amikor a munkarendelést erre az életciklus-állapotra frissítik. |
| Vége                           | Akkor állítsa ezt a beállítást **Igen** értékre, ha az összes, munkarendelésen létrehozott munkarendelési feladat Munkarendelési feladatütemezési állapota automatikusan frissüljön **Befejezve** állapotra, amikor a munkarendelést erre az életciklus-állapotra frissítik. |
| Ütemezési sorok törlése         | Akkor állítsa ezt a beállítást **Igen** értékre, ha az összes, már ütemezett munkarendelésen létrehozott munkarendelési feladat ütemezését törölje a rendszer, amikor a munkarendelést erre az életciklus-állapotra frissítik. Más szóval az eszköz kapacitásfoglalásai, a kapcsolódó karbantartási dolgozó és a kapcsolódó eszközök törlődni fognak. Például ezt a beállítást **Igen** értékre állítja egy munkarendelés életciklus-állapotán, amelynek neve **Becsülve**. Ezt követően, ha egy munkarendelést erre az életciklus-állapotra dobja vissza a rendszer, mert az újraütemezés szükséges, akkor az ütemezés törölhető az adott munkarendelésen. |

## <a name="set-up-project-stages-and-work-order-lifecycle-states"></a>A projekt fázisainak és a Munkarendelés életciklus-állapotainak beállítása

1. Válassza a **Projektvezetés és könyvelés** \> **Beállítás** \> **Projektvezetési és könyvelési paraméterek** lehetőséget.
2. A **Projektfázis** lapon minden használni kívánt fázishoz válassza ki a jelölőnégyzetet minden olyan projekttípus esetén, amely szükséges a munkarendelésekhez. A projekttípusok határozzák meg a megengedett pénzügyi feladatokkal kapcsolatos szabályokat. A pénzügyi feladatokhoz tartozik például az előrejelzés létrehozása, becslések létrehozása és kezdő egyenlegek létrehozása.

    > [!IMPORTANT]
    > Ha egy projektfázis nincs kiválasztva egy projekttípushoz, de a projektfázis használatban van egy munkarendelési életciklus-állapotnál, a munkarendelés projektjeit a rendszer nem frissíti a megfelelő módon.

3. Zárja be a **Projektvezetési és könyvelési paraméterek** oldalt.
4. Válassza ki az **Eszközkezelés** \> **Beállítás** \> **Munkarendelések** \> **Életciklus-állapotok** elemet.
5. Válassza az **Új** lehetőséget egy új munkarendelési életciklus-állapot létrehozásához.
6. Az **Életciklus-állapot** mezőben adja meg az életciklus-állapot azonosítóját.
7. A **Név** mezőben adjon meg egy nevet.

    A **Részletek** gyorslapon az **Életciklusmodellek** mezőben látható az adott életciklus-állapotot használó munkarendelés életciklusmodelljeinek a száma.

8. Az **Általános** gyorslapon a **Munkarendelés** szakaszban válassza ki a funkciókat, amelyek elérhetőknek kell lenniük ennél az életciklus-állapotnál az **Igen** érték kiválasztásával a releváns beállításoknál. A választható lehetőségek leírását a témakör korábbi részében szereplő táblázatban találja.
9. A **Projekt** szakaszban, a **Fázis** mezőben válassza ki azt a projektfázist, amelynek az életciklus-állapothoz kell kapcsolódnia.
10. A **Projekt** szakaszban állítsa a **Tevékenységek bezárása** beállítást **Igen** értékre, ha az egyes munkarendelési feladatokhoz kapcsolódó projekttevékenységeket a rendszer automatikusan zárja be, amikor a munkarendelés ebben az életciklus-állapotban van.

    > [!NOTE]
    > A munkarendelési feladathoz kapcsolódó projekttevékenység számának megkereséséhez válassza az **Eszközkezelés** \> **Általános** \> **Munkarendelések** \> **Összes munkarendelés**, **Aktív munkarendelések** vagy **Saját aktív munkarendelések** lehetőséget. Nyissa meg a munkarendelést, majd válassza ki a Munkarendelés feladatát. A tevékenység száma a **Sor részletei** gyorslap **Általános lapján**, a **Projekt** szakasz **Tevékenységszám** mezőjében látható.

11. Az **Előrejelzés** szakaszban állítsa be az **Óra-előrejelzés másolása**, **Cikk-előrejelzés másolása** és/vagy **Költség-előrejelzés másolása** lehetőséget **Igen** értékre, ha a munkarendelés projekt-előrejelzéseit a rendszer automatikusan másolja a munkarendelési naplókba, amikor a munkarendelés ebben az életciklus-állapotban van.
12. Az **Ütemezés** szakaszban állítsa a beállítások egyikét **Igen** értékre, ha a munkarendelési feladatok ütemezési állapotát frissíteni kell, amikor a Munkarendelés ebben az életciklus-állapotban van. A **Készen áll**, **Indítás**, **Befejezés** és **Ütemezési sorok törlése** beállítások leírásait a témakör korábbi részében látható táblázatban találja.

    > [!NOTE]
    > A munkarendelési feladathoz kapcsolódó ütemezési sorok megtekintéséhez válassza az **Eszközkezelés** \> **Általános** \> **Munkarendelések** \> **Összes munkarendelés**, **Aktív munkarendelések** vagy **Saját aktív munkarendelések** lehetőséget. Nyissa meg a munkarendelést, válassza ki a munkarendelési feladatot a **Munkarendelési feladatok** gyorslapon, és tekintse meg a kapcsolódó információkat a **Sor részletei** gyorslapon. Az **Ütemezés** lap **Állapot** mezőjében látható a munkarendelési feladat állapota. Az **Állapot** mező a következő értékekre állítható be: **Ütemezve**, **Készen áll**, **Elindítva**, **Leállítva** és **Befejezve**.

13. A **Karbantartási kérések** szakasz **Életciklus-állapot** mezőjében válassza ki a karbantartási kérés életciklusának állapotát, amelyre a kapcsolódó karbantartási kéréseket frissíteni kell. Ez a frissítés automatikusan történik. Csak akkor hajtható végre, ha a karbantartási kérés életciklus-állapota ki van választva a karbantartási kérés életciklusmodelljében, amely a karbantartási kéréshez használatos.
14. Az **Eszköz** szakaszban állítsa az **Eszköz DBJ frissítése** beállítást **Igen** értékre, ha az összes, munkarendelésen használt cikket automatikusan frissíteni kell az **Eszköz DBJ** oldalon, amikor a munkarendelés erre az életciklus-állapotra frissül. Ez a beállítás akkor lehet fontos, ha például a Munkarendelés életciklusának állapota a befejezettként vagy készként határozza meg a munkarendelést.
15. A **Munkarendelés-gyűjtő** szakaszban állítsa a **Gyűjtőreferencia törlése** beállítást **Igen** értékre, ha az adott életciklus-állapotban levő munkarendeléseket automatikusan törölni kell a Munkarendelés-gyűjtőkből.
16. Az **Ellenőrzés** gyorslapon válassza ki, hogy milyen ellenőrzési típusokat kell aktiválni ebben az életciklus-állapotban a megfelelő beállítások **igen** értékre állításával. Ezt követően az egyes kiválasztott ellenőrzési típusok **Típus** mezőjében válassza ki az üzenet típusát, amely megjelenik, ha az ellenőrzési típushoz kapcsolódó kötelező mezőket még nem ellenőrizték. Ha a **hiba** lehetőséget választja, akkor a Munkarendelés életciklus-állapotának frissítése mindaddig érvénytelenítve van, amíg a kapcsolódó kötelező mezőket nem frissítették a munkarendelésen.

    - A **Karbantartási miatti üzemkimaradás**, **Karbantartási ellenőrzőlista**, **Hiba tünete**, **Hiba oka** és **Hiba megoldása** beállítások a **Munkarendelési típusok** oldal **Kötelező** szakaszában levő beállításokhoz kapcsolódnak (**Eszközkezelés** \> **Beállítás** \> **Munkaarendelések** \> **Munkarendelési típusok**). Ezen ellenőrzések aktiválásához a kapcsolódó beállítást is **Igen** értékre kell állítani azon a munkarendelés-típuson, amelyet a munakrendeléshez használnak.
    - Ha a **Karbantartási ellenőrzőlista** beállítás **igen** értékre van állítva annál az életciklus-állapotnál, amelyre a Munkarendelés frissítve van, akkor a rendszer ellenőrzi, hogy a karbantartási ellenőrzőlista **Kötelező** jelöléssel rendelkező sorait regisztrálták-e **Ellenőrzött** vagy **Nem alkalmazható** jelöléssel. Ha egyik regisztrációt sem végezték el a kötelező sorokban, akkor egy tájékoztató, hiba- vagy figyelmeztető üzenet jelenik meg, ha a Munkarendelés az adott életciklus-állapotra frissül.
    - Ha a **Vállalt költség** beállítást **igen** értékre állítja az életciklus-állapot esetében, amelyre a Munkarendelés frissítve van, akkor a vállalt költségek teljes összege (azaz a jogi személy által vállalt költségek teljes összege) számítása minden munkarendelési feladathoz megtörténik. Egy üzenet jelenik meg, ha a vállalt költség összege több, mint 0 (nulla). Kiválaszthatja a költségekkel kapcsolatos kötelezettség típusait, amelyek szerepelnek a **Projektvezetési és könyvelési paraméterek** oldal **Költségkontroll** lapjának **Költségkötelezettségek** gyorslapján (**Projektvezetés és könyvelés** \> **Beállítás** \> **Projektvezetési és könyvelési paraméterek**).
    - Ha a **karbantartás miatti üzemkimaradás** beállítása **igen** értékre van állítva annál az életciklus-állapotnál, amelyre a Munkarendelés frissítve van, akkor a karbantartás miatti üzemkimaradás ellenőrzése a munkarendeléshez kapcsolódó eszközön történik. Ha regisztrálták a karbantartás miatti üzemkimaradást, de nincs **Befejezve** regisztráció, akkor megjelenik egy üzenet, amikor a munkarendelést az adott életciklus-állapotra frissítik.
    - Ha a szokásos projektbeállításban nem szerepel az összes fázis, amelyre szükség van az Eszközkezelés beállításához, beállíthat felhasználó által meghatározott projektfázisokat a **Projektfázisok** lapon a **Projektvezetési és könyvelési paraméterek** oldalon. Az alábbi ábrán látható a **Projektvezetési és könyvelési paraméterek** oldal **Projektfázis** lapja.

    ![Állítsa be a projektfokozatokat a különböző projekttípusokhoz oldal.](media/10-setup-for-work-orders.png)

> [!NOTE]
> Ha az életciklus-állapot inaktív, amelyre frissíti a munkarendelést, a munkarendeléshez kapcsolódó, még közzé nem tett naplók automatikusan törlődnek. Ez a viselkedés segít a nem használt adatok automatikus tisztításának biztosításában. (Az életciklus-állapot inaktív, ha az **aktív** beállítás **nem** értékre van állítva a **Munkarendelés életciklus-állapota** lap **Általános** gyorslapján.)
>
> Azonban ha a munkarendelést manuálisan inaktívra állítja, a munkarendeléshez kapcsolódó, még közzé nem tett naplók **nem** törlődnek automatikusan. ( Egy Munkarendelés manuális inaktiválásához válassza az **Eszközkezelés** \> **Általános** \> **Munkarendelések** \> **Összes munkarendelés** vagy az **Aktív munkarendelések** lehetőséget. Nyissa meg a munkarendelést, és váltson át a **Fejléc** nézetre. Válassza az **Általános** gyorslap **szerkesztés** elemét, majd állítsa az **aktív** beállítást **Nem** értékre.)

## <a name="relations-among-work-order-lifecycle-models-work-order-types-and-work-order-lifecycle-states"></a>A munkarendelés életciklus-modelljei, a munkarendelés-típusok és a munkarendelés életciklus-állapotai közti kapcsolatok

Az életciklus-modellek a munkafolyamatokra és életciklus-állapotokra hivatkoznak, amelyek az életciklusmodellben sorrendben vannak kiválasztva. Az életciklusmodellek a Munkarendelés-típusokon állíthatók be. A munkarendelés-típusok határozzák meg a munkafolyamatok méretét és terjedelmét. Például a **Karbantartás**, amely egy normál munkarendelés-típus, olyan munkarendelési életciklusmodellhez kapcsolható, amelynek számos életciklus-állapota van. Ezzel szemben előfordulhat, hogy a **Helyesbítő** munkarendelés-típus olyan munkarendelésekhez van használatban, amelyek nem lettek ütemezve, illetve olyan munkarendelések esetében, amelyeknél a feladat a munkarendelés létrejötte előtt befejeződik sürgős helyzet miatt. Ez a munkarendelés-típus csak néhány életciklus-állapotot tartalmazó munkarendelési életciklusmodellhez kapcsolható.

A típusok használatának oka az, hogy ha egy típust például egy munkarendelésen vagy egy eszközön határoznak meg, akkor a program automatikusan definiálja a kapcsolódó munkafolyamatokat (életciklus-állapotokat). A munkarendelések típusainak beállításáról a [Munkarendelések típusai](../setup-for-work-orders/work-order-types.md) című cikkben talál további információt.

> [!NOTE]
> Az életciklus-állapotok, a életciklusmodellek és -típusok a munkarendeléseken kívül a munkavégzési helyszínekre, eszközökre és karbantartási kérésekre is érvényesek.

A következő ábra a Munkarendelés-típusok, az életciklusmodellek és az életciklus-állapotok közötti kapcsolatot mutatja.

![A Munkarendelés típusa lap és a Munkarendelés életciklusmodellek összehasonlítási oldal.](media/11-setup-for-work-orders.png)

## <a name="work-order-lifecycle-models"></a>Munkarendelés életciklusmodelljei

Miután létrehozta a munkarendelésekhez szükséges munkarendelési életciklus-állapotokat, azok feloszthatók munkarendelési életciklus-modellekre. Legalább egy normál életciklus-modellt létre kell hozni.

1. Válassza ki az **Eszközkezelés** \> **Beállítás** \> **Munkarendelések** \> **Életciklusmodellek** elemet.
2. Válassza az **Új** lehetőséget egy új munkarendelési életciklusmodell létrehozásához.
3. Az **Életciklusmodell** mezőben adja meg az életciklusmodell azonosítóját.
4. A **Név** mezőben adjon meg egy nevet.

    A **Részletek** gyorslapon az **Életciklus-állapotok** mezőben látható az adott életciklusmodellben kiválasztott életciklus-állapotok száma. A **Munkarendelések típusai** mezőben az ezen életciklus-modellt használó munkarendelési típusok száma látható.

5. Az **Életciklus-állapotok** gyorslapon válassza ki azokat az életciklus-állapotokat, amelyeket fel kell venni az életciklus-modellbe:

    - Ha életciklus-állapotot szeretne használni az életciklus-modellhez, válassza ki azt a **Hátralévő életciklus-állapotok** szakaszban, majd válassza a jobb nyílgombot ![Jobb nyíl.](media/12-setup-for-work-orders.png) elemet az áthelyezéshez az **Életciklus-állapotok kiválasztva** szakaszba.
    - Ahhoz, hogy az összes elérhető életciklus-állapotot feltüntesse az életciklusmodellben, nyomja meg az **Összes elérhető fázis kiválasztása** ![Összes elérhető fázis kiválasztása](media/13-setup-for-work-orders.png) gombot. Az összes életciklus-állapot a **Kijelölt életciklus-állapotok** szakaszba kerül.
    - Ha életciklus-állapotot szeretne eltávolítani az életciklus-modellből, válassza ki azt a **Kiválasztott életciklus-állapotok** szakaszban, majd válassza a bal nyílgombot ![Bal nyíl.](media/14-setup-for-work-orders.png) elemet az áthelyezéshez a **Fennmaradó életciklus-állapotok** szakaszba.

6. Válassza az **Életciklus-állapot frissítései** elemet, amellyel meghatározhatja a kijelölt életciklus-állapotot követő életciklus-állapotokat.
7. A **Frissítések** gyorslap **Ütemezett állapot** mezőjében válassza ki azt az életciklus-állapotot, amelyet mindig ki kell választani olyan munkarendeléshez, amelyhez megtörtént a munkarendelés ütemezése, függetlenül a munkarendelés korábbi életciklus-állapotától.
8. A **Nem ütemezett életciklus-állapot** mezőben válassza ki azt az életciklus-állapotot, amelyet mindig ki kell jelölni egy munkarendeléshez, ha a Munkarendelés ütemezése törlődik.
9. Mentse el a munkarendelés életciklusmodelljét.

![Munkarendelés életciklusmodelljei oldal.](media/15-setup-for-work-orders.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]