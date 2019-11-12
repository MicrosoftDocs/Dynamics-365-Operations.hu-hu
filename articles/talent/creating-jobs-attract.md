---
title: Állás létrehozása, jóváhagyása és közzététele az Attract alkalmazásban
description: Ez a témakör ismerteti az állásokkal kapcsolatos elemeket az Attract alkalmazásban. Azt is bemutatja, hogyan lehet létrehozni egy állást.
author: hasrivas
manager: AnnBe
ms.date: 07/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: hasrivas
ms.search.validFrom: 2018-10-24
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: db725c230de5e3dfe971098249b280d9da47ae20
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/03/2019
ms.locfileid: "2551072"
---
# <a name="create-approve-and-post-jobs-in-attract"></a>Állás létrehozása, jóváhagyása és feladása az Attract alkalmazásban

[!include [banner](includes/banner.md)]

Ez a témakör ismerteti az állásokkal kapcsolatos elemeket az Microsoft Dynamics 365 Talent: Attract alkalmazásban. Azt is bemutatja, hogyan lehet létrehozni egy állást.

## <a name="job-creation"></a>Állás létrehozása

Rendszergazdák, toborzásért felelős személyek és a vezetők hozhatnak létre állásokat. Amikor új állást hoz létre, szerepkört kell választania a folyamat során: felvételi vezető vagy toborzó. Miután kiválasztotta a szerepkört, válasszon egy folyamatsablont. Ha bejelöli **Kihagyást**, az alapértelmezett sablon használatos. Folyamatsablonokkal kapcsolatos további tudnivalókat lásd: [Folyamatsablon létrehozása az Attract alkalmazásban](./process-templates-attract.md).

Az Attract állásaihoz ezek tartoznak: állás részletei, felvételi csoport, álláshirdetések és analitika.

## <a name="job-details"></a>Feladat részletei

Az **Állás részletei** lap tartalmazza az állás felelősségeit és attribútumait. A beosztás, a munkaköri leírás és az állás helye mezők kötelezőek. A többi mező kitöltése nem kötelező.

Alapértelmezés szerint a **Pályázható álláshelyek száma** mező értéke **1**. Ez az érték azonban módosítható. Ha az ajánlat elő van készítve az álláshoz, a **Rendelkezésre álló pályázható álláshelyek száma** mező értéke csökken.

Ha a beosztáskezelés be van kapcsolva az Adminisztrációs központban, a **Beosztások frissítése** keresés elérhető. A keresési beolvassa JobPosition entitást a Common Data Service szolgáltatásból, és megjeleníti azokat az pozíciókat, amelyek kiválaszthatók az álláshoz. Ha a kijelölt beosztások száma meghaladja a nyitott beosztások számát, figyelmeztetést kap. Akkor is figyelmeztetést kap, ha a beosztás több álláshoz van használva.

> [!NOTE]
> A beosztáskezelési az Átfogó felvételi bővítmény részeként érhető el.

A felvételi folyamat ajánlat tevékenységének beállításaitól függően egy pozíciószám kétszer is használható az ajánlathoz. További információ: [Toborzási folyamat](./activities-attract.md).

Az Attract alapértelmezett **Szakértelmek** készletét tartalmazza. A szakértelmek javaslatként jelennek meg beírás közben. Szakértelem újabb is hozzáadható, ha az új szakértelem szövegét beírja a mezőbe, és lenyomja az ENTER billentyűt.

Az Attract alapértelmezett **Beosztásfunkciók** készletét tartalmazza. Legfeljebb három további beosztásfunkciót is hozzáadhat, ha az új beosztásfunkciót beírja a mezőbe, és lenyomja az ENTER billentyűt.

Az Attract alapértelmezett **Vállalati ágazatok** készletét tartalmazza. Legfeljebb három további vállalati ágazatot is hozzáadhat, ha az új vállalati ágazatot beírja a mezőbe, és lenyomja az ENTER billentyűt.

## <a name="hiring-team"></a>Toborzó csapat

A **Felvételi csapat** lap a feladatban részt vevő személyek listáját tartalmazza. Felhasználók hozzáadásakor a felvételi csapathoz hozzá kell adni a felvételi csapatban betöltött szerepüket. A szerepkör határozza meg, hogy a felhasználó milyen adatokhoz kap hozzáférést, és milyen értesítéseket kap. A választható szerepek: **Toborzó**, **Felvételi vezető**, **Delegált** és **interjúkészítő**. A szerepkör-jogosultságokkal kapcsolatos további tudnivalókat lásd a „Szerepkörkezelés” dokumentumban. A felvételi vezetők és a toborzók megnevezhetnek egy vagy több delegáltat a nevükben végzett munkához. A delegáltakkal kapcsolatos további tudnivalókért tekintse át a [Biztonság és szerepkörkezelés az Attract alkalmazásban](./security-attract.md) részt.

A felvételi csapat frissíthető az állás aktiválása után.

## <a name="process"></a>Feldolgozás

A felvételi folyamat alapértelmezett adatai a folyamatsablonon alapulnak, amelyet az állás létrehozásakor választott ki. Ha egy adott sablon ekkor nincs kiválasztva, az alapértelmezett sablon lesz használva. A felvételi folyamat meghatározásakor hozzáadhat és eltávolíthat különböző szakaszokat, kivéve a Potenciális jelölt, Jelentkezés és Ajánlat szakaszokat. Annak ellenére, hogy a Potenciális jelölt szakasz nem távolítható el, ki lehet kapcsolni. Minden egyes szakaszon belül hozzáadható, illetve eltávolítható egy vagy több előre definiált tevékenység.

A felvételi folyamathoz hozzáadhatók tevékenységekkel kapcsolatos további tudnivalókat lásd: [Felvételi folyamat tevékenységei az Attract alkalmazásban](./activities-attract.md).

> [!NOTE]
> A felvételi folyamat nem frissíthető az állás aktiválása után.

## <a name="postings"></a>Feladások

Az állás az aktiválása után feladható. Csak a toborzók és a rendszergazdák adhatnak fel állásokat. Az állást a Talent Careers (a Dynamics 365 Talent karrierwebhelye) oldalon vagy a LinkedIn oldalán lehet feladni. Az Attract csoport folyamatosan dolgozik azon, hogy partneri megállapodásokat kössön az állásaggregátorokkal. Ezért ez a lista idővel bővül majd. Amikor egy állást csak belsőleg adnak fel, a jelölteknek AAD-fiókkal kell rendelkezniük az állás megtekintéséhez és a jelentkezéshez. Ha az állás nyilvános, akkor a jelöltek bármely hitelesítési opcióval megtekinthetik az állásokat és jelentkezhetnek rájuk. 

Álláshirdetések kapcsolatos további tudnivalókat lásd: [Attract karrierwebhely funkciói](career-site.md).

> [!NOTE]
> Az állásfeladási funkciók csak az Attract alkalmazás Átfogó felvételi bővítményének része.

## <a name="activate"></a>Aktiválás

Az állást az aktiválása után lehet feladni, és a potenciális jelöltek és pályázók is adhatók hozzá. A potenciális jelöltek hozzáadása egy álláshoz Potenciális jelöltek tevékenységeinél van beállítva a felvételi folyamatban.

> [!NOTE]
> A felvételi folyamat nem frissíthető az állás aktiválása után.

## <a name="prospects-and-applicants"></a>Potenciális jelöltek és a pályázók

A potenciális jelöltek hozzáadása egy álláshoz [Potenciális jelöltek tevékenységeinél](./activities-attract.md#prospect-activity) van beállítva a felvételi folyamatban. Ezt a lehetőséget az állás aktiválása előtt kell beállítani. Az álláshoz az aktiválása után potenciális jelöltek és pályázók adhatók hozzá.

## <a name="approvals"></a>Jóváhagyások

Az Attract állások elküldhetők jóváhagyásra. Nem minden állást kell jóváhagyni. A követelmény a sablon szintjén van beállítva. Alapértelmezés szerint a jóváhagyások ki vannak kapcsolva a sablonban. Jóváhagyások beállításához menjen a folyamatsablonhoz, és állítsa a **Jóváhagyás** mezőt az Alapértelmezett értékre. Ezt követően válassza ki a sablont az állás létrehozásakor.

Az állás a mentése után elküldhető jóváhagyásra. A következő táblázat felsorolja a jóváhagyások használó dokumentum állapotait.

| Állapot   | Állami                                                               |
|----------|---------------------------------------------------------------------|
| Vázlat    | Az állás mentése megtörtént, de még nem lett elküldve egy munkafolyamatba. |
| Függőben  | Az állás el lett küldve a jóváhagyóknak.                            |
| Engedélyezve | Az állás már jóvá van hagyva, de még nem lett aktiválva.            |
| Elutasítva | Az állás el lett utasítva, és nem lehet aktiválni.               |
| Aktív   | Az állást jóváhagyták és aktiválták.                            |

Az álláslistában szűrheti az állás állapotára.

Jóváhagyásokat el lehet küldeni bármely Microsoft Azure Active Directory (Azure AD) felhasználónak a vállalatnál. A jóváhagyásokat párhuzamosan mindegyik jóváhagyóként felsorolt személy megkapja. Minden jóváhagyónak jóvá kell hagynia az állást, mielőtt előrébb juthat. Ha egyetlen jóváhagyó is visszautasítja az állást, akkor az állás **Elutasítva** állapottal jelenik meg. Az állás a jóváhagyása után aktiválható.

Ha egy felhasználó a jóváhagyás után, de az aktiválás előtt módosítja az állást, akkor az állás állapotát a rendszer visszaállítja **Tervezet** értékre, és újból el kell küldeni jóváhagyásra. Miután egy jóváhagyott állást aktiváltak, már nem szerkeszthető.

A jóváhagyóként felsorolt személyek jóváhagyási értesítést kapnak az Attract rendszerében, és egy e-mailt, amely tájékoztatja őket arról, hogy egy elem a jóváhagyásukra vár.  Az e-mailben a jóváhagyó rákattinthat a hivatkozásra, amellyel megnyithatja az állást, áttekintheti a részleteket, és jóváhagyhatja vagy elutasíthatja. Miután az állás állapota **Jóváhagyva** vagy **Elutasítva** lett, a beküldőt az Attract értesíti, és küld neki egy e-mailt. A jóváhagyó is kapnak egy emlékeztető e-mailt, ha nem válaszoltak a jóváhagyási kérelemre 24 órán belül.

> [!NOTE]
> A jóváhagyási e-mailekhez egyéni e-mail-sablonokat is létrehozhat. További információért lásd: [E-mail-sablonok létrehozása és kezelése](https://docs.microsoft.com/dynamics365/unified-operations/talent/email-templates).

## <a name="create-a-job"></a>Feladat létrehozása

Kövesse az alábbi lépéseket egy állás létrehozásához.

1. Nyissa meg a következőt: **Állások**.
2. Válassza az **Új** lehetőséget.
3. A **Beosztás** mezőbe írja be a beosztás. A **Szerepkör** mezőbe írja be a szerepkörét.
4. A **Sablon** mezőben válasszon egy sablont. Másik lehetőségként válassza a **Kihagyás** lehetőséget. Ha bejelöli a **Kihagyás** lehetőséget, az alapértelmezettként megjelölt sablon lesz használva.

    Ha a dokumentumnak végig kell haladnia a jóváhagyási folyamaton, válasszon egy sablont, ahol a **Jóváhagyási folyamat** mező értéke az **Alapértelmezett**.

5. A **Részletek** lapon adja meg az állás részleteit. A **Beosztás**, a **Munkaköri leírás** és az **Állás helye** mezők kötelezőek.
6. Válassza a **Mentés** lehetőséget.
7. A **Felvétel csapat** lapon adja hozzá a felvételi vezetőt, a toborzót vagy az interjúkészítőt.
8. Válassza a **Mentés** lehetőséget.
9. A **Folyamat** lapon adja hozzá vagy távolítsa el a szakaszokat szükség szerint:

    - Egy szakasz hozzáadásához jelölje ki a **+ Új szakasz** elemet.
    - Egy szakasz eltávolításához vigye a kurzort az eltávolítandó szakasz fölé, majd válassza ki a megjelenő szemeteskuka gombot.

        > [!NOTE]
        > A Jelölt, Pályázat és Ajánlat szakaszokat nem lehet eltávolítani.

10. Adja hozzá vagy távolítsa el a tevékenységeket szüksége szerint:

    - Egy tevékenység hozzáadásához húzza át a jobb oldalon található listáról a megfelelő szakaszba. Másik lehetőségként kattintson duplán a tevékenységre, és válassza ki a szakaszt, amelyikhez hozzá szeretné adni.
    - Egy tevékenység eltávolításához bontsa ki a tevékenységet, majd kattintson a tevékenység fejlécében a szemeteskuka gombra.

11. Válassza a **Mentés** lehetőséget.
12. Ha bejelölte a jóváhagyási folyamat alkalmazását, tegye a következőket:

    1. Válassz a **+Jóváhagyó hozzáadása** lehetőséget, majd adjon meg a felhasználót, aki Azure AD-fiókkal rendelkezik. Több jóváhagyót is hozzáadhat.
    2. Válassza a **Küldés jóváhagyóknak** lehetőséget.

    Az **Állás állapota** mező értéke az állás esetében **Függő**. Miután az **Állás állapota** mező értéke **Jóváhagyva** lesz, az állás aktiválható.

13. Ha aktiválni szeretné az állást, kattintson az **Aktiválás** parancsra.
14. Az állás feladásához menjen a **Feladások** lehetőséghez, majd válassza ki a **Feladás most** lehetőséget a Talent Careers vagy a LinkedIn alatt.
