---
title: Az adószámítás első lépései
description: Ez a témakör bemutatja, hogyan állítsuk be az adószámítást.
author: wangchen
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: a90455a338067331a6a44cab36b578ed01ed56eb
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2021
ms.locfileid: "5890298"
---
# <a name="get-started-with-the-tax-calculation-preview"></a>Első lépések az adószámításban (előzetes verzió)

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Ez a témakör az adószámítással kapcsolatos első lépésekről nyújt tájékoztatást. Első lépésként végigvezeti a Microsoft Dynamics Lifecycle Services (LCS), Regulatory Configuration Service (RCS), és a Dynamics 365 Finance és a Dynamics 365 Supply Chain Management konfigurációs lépésein. Ezt követően áttekinti a Finance és a Supply Chain Management tranzakcióiban az adószámítási funkciója használatának közös folyamatát.

A beállítás négy fő lépésből áll:

1. Telepítse az adószámítást az LCS-be.
2. Az RCS-ben állítsa be az adószámítás funkciót. Ez a beállítási adat nem specifikus jogi személyre. Megosztható a Finance és a Supply Chain Management jogi személyei között.
3. A Finance és a Supply Chain Management alkalmazásokban állítsa be az adószámítási paramétereket jogi személy szerint.
4. A Finance és a Supply Chain Management alkalmazásban hozzon létre tranzakciókat, például értékesítési rendeléseket, és az adószámítás segítségével határozza meg és számítsa ki az adókat.

## <a name="prerequisites"></a>Előfeltételek

Mielőtt elvégezhetné az ebben a témakörben ismertetett eljárásokat, a következő előfeltételeknek kell megfelelnie:

- Hozzáférése van az LCS-fiókjához, és telepített egy LCS-projektet egy 2. vagy magasabb szintű környezettel, amelyik a Dynamics 365 10.0.18-as vagy újabb verzióját futtatja.
- Hozzáférése van az RCS-fiókjához.
- Felvette a kapcsolatot a Microsofttal, hogy engedélyezze a tesztelést az üzembe helyezett Finance vagy Supply Chain Management környezetben.

## <a name="set-up-tax-calculation-in-lcs"></a>Állítsa be az adószámítást az LCS-be.

1. Jelentkezzen be az [LCS-be](https://lcs.dynamics.com)
2. Végezze el a Microsoft Power Platform integráció beállítását. További informáciért lásd: [Bővítmények áttekintése](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).
3. Jelölje ki az üzembe helyezett nem éles környezetek egyikét, majd válassza az **Új bővítmény telepítése** lehetőséget.
4. Válassza az **Adószámítás (előzetes verzió)** lehetőséget.
5. Olvassa el és fogadja el a feltételeket, majd válassza a **Telepítés** lehetőséget.

## <a name="set-up-tax-calculation-in-rcs"></a>Állítsa be az adószámítást az RCS-be.

Az ebben a szakaszban található lépések nem egy adott jogi személyhez kapcsolódnak. Ezt az eljárást csak egyszer kell elvégeznie, és az RCS bármely jogi személyében elvégezheti.

1. Bejelentkezés az [RCS](https://marketing.configure.global.dynamics.com/) alkalmazásba.
2. A Finance-ben az **Elektronikus jelentéskészítés** munkaterületen adjon hozzá egy új konfigurációszolgáltatót. Használja a vállalat nevét a szolgáltató neveként. További információért tekintse át a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md) eljárást.
3. Jelölje ki az éppen létrehozott konfigurációs szolgáltatót, majd válassza a **Beállítás aktívként** lehetőséget.
4. Jelölje ki **a Microsoft** konfigurációs szolgáltatót, majd válassza az **Adattárak** lehetőséget.
5. A **Típus** mezőben válassza ki a **Globális** lehetőséget.
6. Válassza ki a **Megnyitás** lehetőséget.
7. Válassza az **Adóadatok modell** lehetőséget, bontsa ki a fájlfát, majd válassza az **Adókonfiguráció** lehetőséget.
8. Jelölje ki a legújabb verziót, majd kattintson az **Importálás** gombra.
9. Térjen vissza a **Globalizációs szolgáltatások (Előzetes verzió)** munkaterületre, válassza a **Szolgáltatások** lehetőséget, jelölje ki az **Adószámítás** csempét lehetőséget, majd kattintson a **Hozzáadás** gombra.
10. Válassza ki az alábbi szolgáltatástípusok valamelyikét:

    - **Új funkció** – Hozzon létre egy üres tartalmú funkcióbeállítást.
    - **Meglévő funkció alapján** – Hozzon létre egy funkciót egy meglévő funkcióból, és másolja a tartalmat a meglévő funkcióbeállításból.

11. Adja meg a funkció nevét és leírását, majd válassza a **Funkció létrehozása** lehetőséget.

    A funkció létrehozása után a program automatikusan létrehoz egy piszkozatverziót.

12. Jelölje ki a funkció piszkozatverzióját, majd kattintson a **Szerkesztés** gombra. Ki van töltve az **Adószámítás beállítása** lap.
13. Válassza a **Konfiguráció verziója** lehetőséget. Látnia kell a 8. lépésben importált konfigurációverziót.

    A Microsoft alapértelmezett adókonfigurációt biztosít az adószámítási bővítményhez. Ez a konfiguráció az adószámítási viselkedések legtöbb követelményét lefedi. A piaci visszajelzések alapján frissítjük majd. Ha ki kell bővítenie a konfigurációt, hogy megfeleljen bizonyos követelményeknek, a [Bővítmény létrehozása adószolgáltatásban](./tax-service-add-data-fields-tax-integration-by-extension.md) rész tartalmaz információt azzal kapcsolatosan, hogyan hozhatja létre és jelölheti ki a saját adókonfigurációját.

    A **Konfigurációs verzió** kiválasztása után több további lap jelenik meg:

    - **Adókódok** – ez a lap kötelező. Az adókódok alapadatainak karbantartására használják. Az ezen a lapon létrehozott összes adókód automatikusan szinkronizálódik a Finance alkalmazásba, amikor engedélyezi az adószolgáltatás-beállítás aktuális verzióját a jogi személyben.
    - **Adókódok alkalmazhatósága** – ez a lap kötelező. Olyan mátrix meghatározására használható, amely meghatározza az adókódot, az adócsoportot és a cikk adócsoportját. Az adóösszeg kiszámításához a program a meghatározott áfakódot használja. Az **Áfakód**, **Áfacsoport** és **Cikkáfacsoport** mezők értékei visszakerülnek a Finance programba.
    - **Ügyfél adószámának alkalmazhatósága** – Ez a lap opcionális. Ha egy vevőhöz több adószáma is van, az adószámítás automatikusan meghatározhatja a helyes adószámot. Ezen a lapon lévő mátrixban megadhatja azokat a szabályokat, amelyeket a meghatározáshoz használ. Ellenkező esetben a Finance és a Supply Chain Management továbbra is az adóköteles dokumentumok alapértelmezett adószámát használja az értékesítési tranzakciókhoz.
    - **Szállító adószámának alkalmazhatósága** – Ez a lap opcionális. Ha egy szállítóhoz több adószáma is van, az adószámítás automatikusan meghatározhatja a helyes adószámot. Ezen a lapon lévő mátrixban megadhatja azokat a szabályokat, amelyeket a meghatározáshoz használ. Ellenkező esetben a Finance és a Supply Chain Management továbbra is az adóköteles dokumentumok alapértelmezett adószámát használja a vásárlási tranzakciókhoz.
    - **Listakód alkalmazhatósága** – ez a lap nem kötelező. Rugalmasabb és konfigurálhatóbb szabályokkal segíthet a **Listakód** mező értékének automatikus meghatározásában. Ezen a lapon lévő mátrixban megadhatja azokat a szabályokat, amelyeket a meghatározáshoz használ. Ellenkező esetben a Finance és a Supply Chain Management továbbra is az adóköteles dokumentumok alapértelmezett kódját használja.

14. Az **Adókódok** lapon válassza a **Hozzáadás** lehetőséget, és adja meg az adókódot és a leírást.
15. Válassza az **Adózási összetevő** lehetőséget. Az adózási összetevő a kiválasztott adózási konfiguráció előző verziójában definiált módszerek csoportja. A következő adózási összetevők állnak rendelkezésre:

    - Nettó összeg alapján
    - Bruttó összeg alapján
    - Mennyiség alapján
    - Árrés alapján
    - Adó az adón

16. Válassza a **Mentés** lehetőséget. A kiválasztott adózási összetevő alapján további mezők válnak elérhetővé.
17. Az áfakód jellegének azonosításához használja a következő beállításokat:

    - Adómentes
    - Importadóköteles
    - Fordított áfás
    - Kizárás az alapösszeg-számításból

    Az áfa importadó esetében egyetlen olyan adókódot kell beállítani, amely pozitív adókulcsot tartalmaz, és azt **Importadóköteles** értékkel kell megjelölni.

    Fordított adózás esetén állítson be két adókódot, amelyek közül az egyik pozitív adókulcsot tartalmaz, a másikhoz negatív adókulcs tartozik, de azonos áfaértékkel. A negatív adókód megjelölése **Fordított áfás**. A fordított áfa megoldásával kapcsolatos további tudnivalókat a Finance alkalmazásban lásd: [Fordított áfamechanizmus az ÁFA/GST sémához](emea-reverse-charge.md).
    
    Néhány olyan adótípusnál, amelyet ki kell hagyni az árat tartalmazó tranzakciók adóalapösszeg-számításában, mint egyes országokban a vám esetében válassza a **Kizárás az alapösszeg-számításból** jelölőnégyzetet.

    Adómértékek és az adóösszeg-korlátok karbantartása ehhez az adókódhoz.

18. Ismételje meg a 14.–17. lépéseket az összes szükséges adókód hozzáadásához.
19. Az **Adókódok alkalmazhatósága** lapon válassza ki azokat az oszlopokat, amelyek a helyes adókód meghatározásához szükségesek, majd válassza a **Hozzáadás** lehetőséget.
20. Adja meg vagy válassza ki az egyes oszlopok értékeit. Az **Áfakód**, **Áfacsoport** és **Cikkáfacsoport** mezők lesznek ennek a mátrixnak a kimenetei.
21. Ismételje meg a 19–20. lépést a vevői adószámok, szállítói adószámok és listakódok alkalmazhatóságának beállításához.
22. Válassza a **Mentés** gombot, majd zárja be az oldalt.
23. Válassza az **Állapot módosítása** \> **Teljes** lehetőséget. Ha az állapot **Kész** állapotúra változik, akkor a verzió már nem szerkeszthető.
24. Válassza az **Állapot módosítása** \> **Közzététel** lehetőséget. Az adófunkció beállításnak ez a verziója a globális tárházba lesz felküldve, és a Finance-ban minden jogi személy számára látható lesz.

## <a name="dynamics-365-setup"></a>A Dynamics 365 beállítása

Az RCS beállításainak befejezése után – az előző szakaszban leírtak szerint – elérhető lesz az adó funkció közzétett verziója. Hajtsa végre az alábbi lépéseket, ha be szeretné állítani az adószámítást a Finance-ban.

Az ebben a szakaszban található beállításokat jogi személy végzi. Be kell állítania mindegyik jogi személyhez, amelynél engedélyezni szeretné az adószámítást a Finance-ben.

1. A Finiance-ben válassza az **Adó** \> **Beállítás** \> **Adókonfiguráció** \> **Adószámítási beállítása (előzetes verzió)** lehetőséget.
2. Az **Általános** lapon állítsa be a következő mezőket:

    - **Adószámítás engedélyezése** – akkor jelölje be ezt a jelölőnégyzetet, ha engedélyezni szeretné az adószámítási bővítményt a jogi személyhez. Ha az aktuális jogi személyhez nincs engedélyezve, a jogi személy továbbra is a meglévő adómotor használatával határozza meg és számítja ki az adót.
    - **Funkció beállítása** – A közzétett adófunkció beállítás és verzió kiválasztása a jogi személyhez. A közzétett adó funkció beállításához és befejezéséhez kapcsolódó további tudnivalókat lásd a témakör előző szakaszában.
    - **Üzleti folyamat** – az engedélyezni kívánt üzleti folyamatok kiválasztása.
    - **Áfakód-helyesbítés engedélyezése** – A beállítás **Igen** értékre állításával az áfakódok helyesbítését engedélyezheti az áfaoldalon.

3. A **Számítás** lapon határozza meg a jogi személy elvárt kerekítési szabályát.
4. Adja meg a **Hibakezelés** lapon a jogi személy elvárt hibakezelési módját. Mindegyik eredménykódhoz három lehetőség áll rendelkezésre:

    - Nincs
    - Figyelmeztetés
    - Hiba

5. Mentse a beállításokat.
6. Ismételje meg a 1–5. lépést minden egyes jogi személyhez.

## <a name="transaction-processing"></a>Tranzakciófeldolgozás

Miután az összes beállítási eljárást befejezte, az adószámítás használatával meghatározhatja és kiszámíthatja a Finance-ben az adót. A tranzakciók feldolgozásának lépései változatlanok maradnak. A Finance 10.0.18-as verziója a következő tranzakciókat támogatja:

- Értékesítési folyamat

    - Értékesítési ajánlat
    - Értékesítési rendelés
    - Visszaigazolás
    - Kitárolási lista
    - Szállítólevél
    - Értékesítési számla
    - Jóváírás
    - Visszárurendelés
    - Fejlécdíj
    - Sorköltség

- Beszerzési folyamat

    - Beszerzési rendelés
    - Visszaigazolás
    - Bevételezések listája
    - Termékbevételezés
    - Beszerzési számla
    - Fejlécdíj
    - Sorköltség
    - Jóváírás
    - Visszárurendelés
    - Beszerzési igénylés
    - A beszerzési igénylési sor díja
    - Ajánlatkérés
    - Ajánlatkérés fejlécének díja
    - Ajánlatkérés sorának díja

- Készletfolyamat

    - Átmozgatási rendelések – szállítás
    - Átmozgatási rendelés - bevételezés