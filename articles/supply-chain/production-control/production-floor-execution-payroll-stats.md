---
title: Szabadságegyenlegek megjelenítése a termelési emelet végrehajtási felületén
description: Ez a témakör egy olyan példát mutat be, amely bemutatja, hogyan lehet beállítani a Microsoftot Dynamics 365 Supply Chain Management, hogy a bérstatisztikák segítségével a dolgozók áttekintést adjanak az adott évre vonatkozó szabadságegyenlegről.
author: johanhoffmann
ms.date: 04/22/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-04-22
ms.dyn365.ops.version: 10.0.XX
ms.openlocfilehash: a97858c72b0be50609cee552bd0635e2d68ea478
ms.sourcegitcommit: d715e44b92b84b1703f5915d15d403ccf17c6606
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/27/2022
ms.locfileid: "8648164"
---
# <a name="show-vacation-balances-in-the-production-floor-execution-interface"></a>Szabadságegyenlegek megjelenítése a termelési emelet végrehajtási felületén

[!include [banner](../includes/banner.md)]

Ez a témakör egy olyan példát mutat be, amely bemutatja, hogyan lehet beállítani a Microsoftot Dynamics 365 Supply Chain Management, hogy a bérstatisztikák segítségével minden dolgozó áttekintést adjon az adott évre vonatkozó szabadságegyenlegről. A dolgozók a Saját nap **párbeszédpanelen** láthatják a szabadságukat az üzem végrehajtási felületén.

Ez a helyzet a dán ünneptörvényt használja, ahol a szabadság éve szeptember 1-től augusztus 31-ig tart. Ebben az esetben a vállalat egy új dolgozót vett fel, és 10 nap egyenleget biztosít a dolgozónak a jelenlegi szabadság hátralévő részére.

## <a name="turn-on-the-required-features"></a>A szükséges szolgáltatások bekapcsolása

Ha futtatni szeretné ezt az esetet, *engedélyeznie kell a "Saját nap" nézetet a*[termelésirányítási felület funkció szolgáltatásában](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). Az erre és a [termelési emelet végrehajtási felületére vonatkozó egyéb funkciók engedélyezéséről a Termelési üzem végrehajtási felületének konfigurálása nyújt tájékoztatást](production-floor-execution-configure.md).

## <a name="make-sample-data-available"></a>A mintaadatok elérhetővé tétele

Ha ezt a forgatókönyvet az itt megadott mintaadatok és értékek alapján kívánja elvégezni, akkor egy olyan rendszert kell használnia amelynél a szokásos [demóadatok](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) telepítve vannak. Emellett az **USMF** jogi személyt is ki kell választani a kezdés előtt.

## <a name="create-a-new-pay-type"></a>Új fizetéstípus létrehozása

Új fizetéstípus létrehozásával kezdeni *, amely nyomon követi a dolgozók által megszerzett szabadságnapokat (más néven szabadságegyenlegüket* *).* A fizetéstípusok jellemzően a dolgozók fizetésének kiszámítására használatosak. Az itt létrehozott fizetéstípust azonban a program az egyenleg kiszámítására használja.

1. Ugrás a Idő- **és jelenlét beállítása \> bérlistatípusokhoz \>\>**.
1. A műveleti ablakpanelen válassza ki az **Új** lehetőséget, ha hozzá szeretne adni egy sort a rácshoz.
1. Az új sorban állítsa be a következő értékeket:

    - **Fizetés típusa:** *5151-1*
    - **Leírás:** *A dolgozó szabadságnapokat számlálója*
    - **Szerepeljen exportban:** *Nem*

## <a name="update-the-pay-agreement"></a>Fizetési megállapodás frissítése

Ebben a szakaszban egy meglévő fizetési megállapodást szerkeszthet az új fizetéstípus hozzáadásával, és beállítja azokat a szabályokat, *amelyek* meghatározzák, hogy a szabadság napjainak regisztrálva vannak-e a dolgozó szabadságaik egyenlege.

1. Ugrás a Idő- **és jelenlét beállítása \> bérlista-fizetési \>\> megállapodásokhoz**.
1. Válassza ki azt a fizetési megállapodást, amelybe be szeretné állítani a szabadságra vonatkozó házirendet. (Ha szabványos USMF mintaadatokkal dolgozik, csak egy fizetési megállapodás van, *Man*.)
1. Győződjön meg róla, hogy a kiválasztott fizetési megállapodás érvényes az aktuális dátumra. Ha szabványos USMF-mintaadatokkal dolgozik, előfordulhat, **·** *hogy* a Man fizetési megállapodás Céldátum mezőjében múltbeli dátum van beállítva. Ha szükséges, módosítsa úgy az értéket, hogy egy vagy két jövőbeli év legyen.
1. A munkaablakban válassza ki a Megállapodás **sorait**.
1. A Fizetési **megállapodás sorai** lap **Áttekintés** gyorslapján állítsa be a következő értékeket az eszköztáron:

    - Az első legördülő listában válassza a Hétfő **lehetőséget**.
    - A második legördülő listában válassza a Távollét **lehetőséget**.

1. A műveleti ablakpanelen válassza ki az **Új** lehetőséget, ha hozzá szeretne adni egy sort a rácshoz.
1. Az új sorban állítsa **a Fizetéstípus** mezőt az esethez létrehozott fizetéstípusra (*5151-1*). Hagyja az összes többi mezőt az alapértelmezett értékére beállítva.
1. Amíg az új sor ki van választva, az **Általános** gyorsábra a következő értékeket adja meg:

    - **Távollét kódja:** *Szabadság*
    - **Rögzített mennyiség használata:** *Igen*
    - **Konstans:** *-1*

1. A műveletpanelen válassza a Nap másolása **lehetőséget**.
1. A Nap **másolása** párbeszédpanelen állítsa be a következő értékeket:

    - **kedd**, **szerda**, **csütörtök** és **péntek:** *Igen*
    - **Felülírás:** *Igen*
    - **Távollét:** *Igen*

1. Válassza ki az **OK** lehetőséget.

## <a name="create-a-payroll-statistic-group"></a>Bérstatisztika-csoport létrehozása

*A bérstatisztika-csoportok* segítségével lehet adott időszak dolgozói regisztrációihoz statisztikát beállítani. Ebben az esetben a bérstatisztika-csoport használatával lehet kiszámítani a szabadság napjainak a számát, amit a dolgozók meg fognak keresni a szabadság időszaka alatt. Dániában a szabadság időszaka szeptember 1-től augusztus 31-ig tart.

1. Ugrás a Idő- **és jelenlét beállítása \> bérlista \> statisztikai \> csoportjaihoz**.
1. A műveleti ablakpanelen válassza ki az **Új** lehetőséget, ha hozzá szeretne adni egy sort a rácshoz.
1. Az új sorban állítsa be a következő értékeket:

    - **Bérstatisztika-csoport:** *TKK*
    - **Leírás:** *Szabadság egyenlege*
    - **Átvitel:** *Nem*

1. Amíg az új sor ki van választva, válassza a **Beállítás** lehetőséget a munkaablakban.
1. A beállítási **lap** munkaablakában, az Új **gombra** kattintva adjon hozzá egy sort a rácshoz.
1. Az új sorban állítsa **a Fizetéstípus mezőt** *5151-1-re*.
1. Jelölje ki és tartsa lenyomva (vagy kattintson a jobb gombbal) az Időszakkód **mezőre**, majd válassza a **Részletek megtekintése lehetőséget**. Most beállíthatja azt az időszakkódot, amelyről később hozzárendeli ezt a mezőt.
1. Az Időszaktípusok **lapon**, a munkaablakban válassza az Új **lehetőséget**, ha sort szeretne hozzáadni a rácshoz.
1. Az új sorban állítsa be a következő értékeket:

    - **Időszaktípusok:** *Ear*
    - **Leírás:** *Szabadság (év)*
    - **Gyakoriság:** *évek*

1. Amíg az új sor ki van választva, válassza az Időszakok **létrehozása a** munkaablakban lehetőséget.
1. Az Időszakok **létrehozása** párbeszédpanelen állítsa be a következő értékeket:

    - **Adja meg az időszak kezdő dátumát:** *2021. szeptember 1.*
    - **Időszak hossza:** *5*

1. Válassza ki az **OK** lehetőséget.
1. A Bérstatisztika-csoportok **lapra** való visszatéréshez zárja be **az Időszaktípusok lapot**.
1. Állítsa az **Időszakkód mezőt** az előbb létrehozott időszaktípusra (*Ear*).

## <a name="create-a-statistical-balance-setup"></a>Statisztikai egyenlegbeállítás létrehozása

Ebben a szakaszban létrehozhat egy statisztikai egyenlegbeállítást, *amely* az előző szakaszban létrehozott bérstatisztika-csoporthoz kapcsolódik. Később ezt a statisztikai egyenlegbeállítást **a termelési emelet végrehajtási felületének Saját napi** nézethez csatolja. A **Saját nap** nézetben így látható lesz a kapcsolódó bérstatisztikai csoporthoz társított fizetéstípus szabadságegyenlege.

1. Ugrás a Idő- **és jelenlét beállítása \> – Bérlista \>\> statisztikai egyenlegének beállítása**.
1. A műveleti ablakpanelen válassza ki az **Új** lehetőséget, ha hozzá szeretne adni egy sort a rácshoz.
1. Az új sorban állítsa be a következő értékeket:

    - **Bérstatisztika-csoport:** *TKK*
    - **Külső név: szabadság** *egyenlege*
    - **Rugalmas idő:** *Nem*

## <a name="create-a-manual-premium"></a>Manuális prémium létrehozása

*A manuális prémiumok* általában a dolgozók külön fizetésének megadására használatosak a kiegészítő munkáért. Ebben az esetben manuális prémiumot hoz létre, amely az egyes dolgozók kezdeti szabadságegyenlegének beállítását fogja használni.

1. Ugrás a Idő- **és jelenlét beállítása \> bérlista \>\> manuális prémiumaihoz**.
1. Rekord hozzáadásához válassza **a munkaablak Új** lehetőséget.
1. Az új rekordban állítsa be a következő értékeket:

    - **Prémiumok:** *TKK*
    - **Leírás:** *A dolgozók szabadságegyenlegének helyesbítése*
    - **Fizetés típusa:** *5151-1*

## <a name="set-a-workers-initial-vacation-balance-and-adjust-it-by-one-day"></a>A dolgozó kezdeti szabadságegyenlegének beállítása és annak kiigazítása egy nappal

A bérszámfejtési rendszergazdák **a** Jóváhagyás lapon áttekintik és jóváhagyják a dolgozók napi regisztrációit. Ebben az esetben egy adminisztratív szerepkört kell be vennie, hogy beállíthatja egy dolgozó kezdeti szabadságegyenlegét, és regisztrálhatja a dolgozó által igénybe veve szabadság napjait.

1. Menjen a Idő- **és jelenlét-ellenőrzéshez \>, és hagyja jóvá a \> jóváhagyást**.
1. A Jóváhagyás **párbeszédpanelen** állítsa be a következő mezőket:

    - **Jóváhagyási csoport** – válassza ki azt a jóváhagyási csoportot, amelyhez tartozik. (Ha szabványos USMF mintaadatokkal dolgozik, csak egy jóváhagyási csoport van: *AdmMan*.)
    - **Teljes csoport megtekintése, 1 nap** – válassza ki a lehetőséget, majd állítsa a mezőt az aktuális dátumra.

1. Válassza ki az **OK** lehetőséget.
1. A **Jóváhagyás** lapon a feltételeknek megfelelő rekordok listája jelenik meg. Válassza ki a jóváhagyni kívánt dolgozót. Ha szabványos USMF mintaadatokkal dolgozik, *válassza ki a dolgozói adatokat (* *000496 Portra*).
1. A kiválasztott dolgozó számára 10 nap szabadság megadása:

    1. Amíg a dolgozó még ki van választva, válassza ki **a Prémium sorokat** a munkaablakban.
    1. A Prémiumsorok **lapon**, a munkaablakban válassza az Új **lehetőséget**, ha sort szeretne hozzáadni a rácshoz.
    1. Az új sorban állítsa be a következő értékeket:

        - **Prémiumok:** *TKK*
        - **Mennyiség:** *10*

    1. Zárja be a **Prémiumsorok** lapot.

1. A Jóváhagyás **lapon** regisztrálja, hogy a dolgozó a szabadsága valamelyik napját az aktuális dátumon használta:

    1. Amíg a dolgozó még ki van választva, a lap alsó részén, **az** Áttekintés lapon válassza **az** Eszköztár Új elemét, és adjon hozzá egy sort a rácshoz.
    1. Az új sorban állítsa be a következő értékeket:

        - **Naplóregisztráció típusa:** *Távollét*
        - **Hivatkozás:** *szabadság*

    1. A lap felső részében az eszköztár Átvitel **gombjára kattintva alkalmazza a szabadság egyenlegét,** és számítsa ki a levonást.

## <a name="configure-the-production-floor-execution-interface-so-that-it-includes-the-my-day-dialog-box"></a>A termelés-végrehajtási felület konfigurálása úgy, hogy tartalmazza a Saját nap párbeszédpanelt

Ebben a szakaszban egy Saját nap gombot ad hozzá a **termelési** emelet végrehajtási felülethez. A dolgozók ezután ezzel a gombbal nyitják meg a **Saját nap párbeszédpanelt**.

1. Lépjen a **Gyártásvezérlés \> Beállítás \> Gyártásvégrehajtás \> termelési üzem végrehajtásának konfigurálása** részre.
1. Válasszon egy konfigurációt (például *Alapértelmezett*).
1. A munkaablakban válassza a Tervezés **lapot**.
1. A Tervezés **lap** listaablakában válassza *az* Összes feladat lehetőséget a lap beállításainak megtekintéséhez. A **Fő nézet mezőnek** most az Összes feladat értéket kell *mutatnia*.
1. A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.
1. Válassza a **Saját nap** lehetőséget a Másodlagos **eszközsáv gyorssávján az Elérhető** műveletek **oszlopban**. Ezután a jobbra nyílgombra kattintva helyezze át a Kijelölt **műveletek oszlopba**.

## <a name="check-your-balance-in-the-production-floor-execution-interface"></a>Egyenlegének ellenőrzése a termelési emelet végrehajtási felületén

Ebben a szakaszban a termelés-végrehajtási felületre az a dolgozó jelentkezik be, akinek korábban beállított szabadságát már beállította. Ezt követően a Saját nap **párbeszédpanelt megnyitva** megtekintheti saját szabadságegyenlegét.

1. Ugrás a Gyártásvezérlés **beállítása – \>\> Gyártás-végrehajtási \> termelés - üzem végrehajtási lépéshez**
1. Ha a program arra kéri, hogy válasszon ki egy konfigurációt, válassza ki az ebben az esetben korábban beállított konfigurációt (*alapértelmezett*).
1. Jelentkezzen be felhasználóként, aki az eset korábbi verzióiban be van állítva. Ha szabványos USMF-mintaadatokkal dolgozik, *a 123-as* **számnak** a Belépőkártya-azonosító mezőben való megadásával jelentkezhet be. Ez a belépőkártya-azonosító megfelel Annak portrának.
1. Válassza a **Saját nap** lehetőséget a bal oldali eszköztáron.
1. A párbeszédpanel **Egyenlegek** szakaszának vizsgálata. Ebben a szakaszban meg kell mutatni, hogy önnek kilenc szabadságnapja van.
