---
title: Nyomtatáskezelési rekord-specifikus ER-célpontok konfigurálása
description: Ez a témakör elmagyarázza, hogyan kell beállítani a nyomtatáskezelési rekordok célállomásspecifikus beállításait a kimenő dokumentumok generálására konfigurált Elektronikus jelentés (ER) formátumhoz.
author: NickSelin
ms.date: 08/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-08-01
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 1e06fafe8d8bbe92ddf4fcd94d7271a1fbb6362a
ms.sourcegitcommit: 7e32e5e39e762a4b1606161cb603a450d13b5251
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/23/2021
ms.locfileid: "7413597"
---
# <a name="configure-print-management-record-specific-er-destinations"></a>Nyomtatáskezelési rekord-specifikus ER-célpontok konfigurálása

[!include [banner](../includes/banner.md)]

Ez a témakör elmagyarázza, hogy a Rendszergazda vagy a Számviteli ügyintéző szerepkörben lévő felhasználók hogyan végezhetik el a következő feladatokat:

- Megnevezett [elektronikus jelentéstételi (ER)](general-electronic-reporting.md) célállomások konfigurálása szabadszöveges számlákat generáló ER-megoldáshoz.
- Egyetlen [nyomtatáskezelési](document-reporting-services.md) rekordhoz rendelhet ER-célpontot.

Az eljárásokat az USMF vállalatnál lehet elvégezni. Nincs szükség kódolásra.

## <a name="introduction"></a>Bevezetés

A kimenő dokumentum létrehozásához használt [ER-formátum](general-electronic-reporting.md#FormatComponentOutbound) [konfiguráció](general-electronic-reporting.md#Configuration) fájlkimeneti összetevőjében minden egyes mappához beállíthatja a [célállomásokat](electronic-reporting-destinations.md). Egy ilyen típusú ER-formátum futtatásakor, ha rendelkezik a megfelelő hozzáférési jogokkal, a konfigurált célbeállításokat is módosíthatja futás közben.

A Microsoft Dynamics 365 Finance **10.0.17-es és újabb verziójában** egy ER-formátumhoz műveleti kódot lehet [beállítani](er-apis-app10-0-17.md), amely meghatározza azt a műveletet, amelyet a felhasználók az adott ER-formátum futtatásával végeznek. Például a **Számlakövetelések** modulban a nyomtatáskezelési beállítások között kiválaszthat egy olyan ER formátumot, amely egy adott üzleti dokumentumot, például egy szabad szöveges számlát generál. Ezután a számla előnézeti képe megtekinthető a **Nézet** lehetőséggel, illetve a **Nyomtatás** gombbal elküldheti egy nyomtatóra. Ha a futó ER-formátumhoz futáskor átad egy műveletet, akkor a [különböző felhasználói műveletekhez különböző ER-célpontokat konfigurálhat.](er-action-dependent-destinations.md)

A Pénzügyek **10.0.21-es és újabb verziójában** egy ER-formátumhoz be lehet [állítani](er-apis-app10-0-21.md) egy nevesített célállomást, és azt hozzá lehet rendelni ahhoz a nyomtatáskezelési rekordhoz, amelyet az adott ER-formátum futtatásakor feldolgoznak. Például a **Számlakövetelések** modulban a Nyomtatáskezelési beállítások között az **Eredeti** rekordot a következő műveletek elvégzésére kívánja beállítani:

- Futtasson ER formátumot.
- A generált számla elküldése e-mailben az ügyfélnek.
- Állítsa be a **másolási** rekordot úgy, hogy ugyanezt a formátumot futtassa.
- Nyomtassa ki a számla másolatát egy hálózati nyomtatóra.

Ebben az esetben a futó ER-formátumhoz különböző ER-célállomásokat kell konfigurálnia, és a célállomásokat különböző nyomtatáskezelési rekordokhoz kell kiválasztania.

## <a name="prerequisites"></a>Előfeltételek

Mielőtt elkezdené, a [Funkciókezelés](../../fin-ops/get-started/feature-management/feature-management-overview.md#the-feature-management-workspace) munkaterületen be kell kapcsolnia az **ER célállomások beállításának engedélyezése nyomtatáskezelési elemenként** funkciót. A forráskódot is meg kell változtatni, hogy lehetővé tegye a nevesített ER-célpontok konfigurálását az aktuális pénzügyi példányban, és hogy engedélyezze az [új](er-apis-app10-0-21.md) ER API-t.

Ezenkívül a **szabad szöveges számla (Excel)** ER konfigurációt [be kell importálni](er-download-configurations-global-repo.md) a Pénzügyi példányba.

## <a name="configure-a-new-er-destination"></a>Új ER-célállomás konfigurálása

1. Válassza a következőt **Kinnlevőségek** \> **Számlák** \> **Kizárólag szabadszöveges számlák**.
2. Válasszon ki egy számlát az **US-001** ügyfélszámlához.
3. A **Szabad szöveges számla** lapon a **Számla** lapon a **Nyomtatáskezelés** csoportban válassza a **Nyomtatáskezelés** lehetőséget.
4. A **Nyomtatáskezelés beállítása** lapon bontsa ki a **Modul - számlakövetelések** \> **Dokumentumok** \> **Szabad szöveges számla**, válassza ki az **Eredeti** rekordot, majd kövesse az alábbi lépéseket:

    1.  Figyelje meg a kiválasztott rekord aktuális beállításait:
        -   A **Jelentésformátum** mezőben a **FreeTextInvoice.Report** alapértelmezett SSRS-jelentés van kiválasztva.
        -   A **\<Default\>** név jelenik meg a **Cél** mezőben, tájékoztatva arról, hogy a hozzárendelt SSRS-jelentéshez nincs egyéni célállomás kiválasztva. 
    2.  A **Jelentésformátum** mezőben válassza a **Szabad szöveges számla (Excel)** ER formátum konfigurációt.
        -   A **Cél** mező neve **Célállomás neve** értékre változik.
        -   A **\<No named destination\>** név jelenik meg a **Célállomás neve** mezőben, tájékoztatva arról, hogy a kijelölt ER-formátumhoz nincs kijelölt célállomás.
    3.  Válassza a **Célállomás neve** mező jobb oldalán lévő nyíl gombot.    
    4. Az **Elektronikus jelentés megnevezett célállomás** lapon a **Név** mezőbe írja be a **Fő célállomás** értéket.
    5. Válassza a **Mentés** lehetőséget.
    6. A **Fájlcélpont** gyorslapon [konfigurálja](er-destination-type-email.md) a **Jelentés** összetevő **e-mail** célpontját.
    7. Zárja be az **Elektronikus jelentés megnevezett céloldalát**.
    8. A **Nyomtatáskezelés beállítása** lapon a **Célállomás neve** mezőben válassza ki a **Fő célállomás** nevű célállomást.

    ![Nevezett ER-célállomás konfigurálása a kiválasztott ER-formátumhoz és hozzárendelése egy konfigurált nyomtatáskezelési rekordhoz a Nyomtatáskezelés beállítása lapon](./media/er-named-destinations-01.gif)

    Ön most beállította a megnevezett ER célállomás **Fő célállomás** a **Szabad szöveges számla (Excel)** formátumhoz, és hozzárendelte az **Eredeti** nyomtatáskezelési rekordhoz a **Modul - Számlakövetelések** \> **Dokumentumok** \> **Szabad szöveges számla** alatt.

5. Bontsa ki a **Modul - követelések** \> **Számla - US-001** \> **Szabad szöveges számla** ágat, válassza ki az **Eredeti** rekordot, majd kövesse az alábbi lépéseket:

    1. Jelölje ki és tartsa lenyomva (vagy kattintson a jobb gombbal a rekordra), majd válassza a **Felülbírálás** lehetőséget.
    2. Válassza a **Célállomás neve** mező jobb oldalán lévő nyíl gombot.
    3. Az **Elektronikus jelentés nevű céloldalon** a Műveletpanelen válassza az **Új** lehetőséget.
    4. A **Név** mezőbe írja be az **US-001 célállomás** értéket.
    5. A **Fájlcélpont** gyorslapon [konfigurálja](er-destination-type-print.md) a **Jelentés** összetevő **Nyomtató** célpontját.
    6. Zárja be az **Elektronikus jelentés megnevezett céloldalát**.
    7. A **Nyomtatáskezelés beállítása** lapon a **Célállomás neve** mezőben válassza ki az **US-001 célállomás** nevű célállomást.

    ![Nevezett ER-célállomás konfigurálása a kiválasztott ER-formátumhoz, és hozzárendelése a nyomtatáskezelés beállítása lapon a konfigurált nyomtatáskezelési rekordhoz](./media/er-named-destinations-02.gif)

    Ön most beállította az **US-001** nevű ER-célállomást a **Szabad szöveges számla (Excel)** formátumhoz, és hozzárendelte az **Eredeti** nyomtatáskezelési rekordhoz a **Modul - Számlakövetelések** \> **Számla - US-001** \> **Szabad szöveges számla** alatt.

Most, amikor egy szabad szöveges számla feldolgozására kerül sor, a **Szabad szöveges számla (Excel)** ER formátum lefut, és a következő események egyike következik be:

- Ha a szabad szöveges számla nem az US-001 ügyfélnek szól, a generált dokumentumot e-mailben küldi el.
- Ha a szabad szöveges számla az US-001 ügyfélre szól, a generált dokumentum kinyomtatásra kerül.

> [!NOTE]
> Ha a futásidőben feldolgozott nyomtatáskezelési rekordhoz nem definiáltak név szerinti célállomást, akkor az alapértelmezett ER-célállomások kerülnek felhasználásra, ha azok a futó ER-formátumhoz rendelkezésre állnak.

> [!IMPORTANT]
> Az **Elektronikus jelentés célállomása** lapon **(Szervezeti adminisztráció** \> **Elektronikus jelentés** \> **Elektronikus jelentés célállomása**), ha olyan ER formátumot választ ki, amelyhez legalább egy nevesített célállomást konfiguráltak, értesítést kap a nevesített célállomások jelenlétéről.
>
> ![Értesítés a kiválasztott ER-formátumhoz konfigurált névre szóló célállomások létezéséről az Elektronikus jelentés célállomása lapon](./media/er-named-destinations-03.png)
>
> Ha törli az alapértelmezett célállomást, az összes megnevezett célállomás is törlődik. Ha ezek a megnevezett célállomások ki voltak választva a nyomtatáskezelési rekordokhoz, a rendszer törli a megnevezett célállomások kiválasztását.

## <a name="copy-an-existing-er-destination-as-a-new-named-destination"></a>Meglévő ER-célpont másolása új, megnevezett célpontként

Ha egy ER-formátumhoz rendelkezésre áll az alapértelmezett nevesített ER-célállomás, akkor az új ER-célállomások sablonjaként használható. Az alapértelmezett célállomáson alapuló új ER-célállomás létrehozásához válassza az **Elektronikus jelentés megnevezett célállomás** lapon az **Alapértelmezettről másolás** lehetőséget. Az új célállomás neve **Alapértelmezett**. Ezt a lépést annyiszor ismételheti meg, ahányszor csak szükséges.

Bármely meglévő, névvel ellátott célállomás kiválasztható egy új, névvel ellátott célállomás sablonjaként. Ha egy új, egy kiválasztott, megnevezett célállomáson alapuló, megnevezett ER-célállomást szeretne létrehozni, válassza a **Másolás** lehetőséget az **Elektronikus jelentés megnevezett célállomás** lapon. Az új célállomás neve megegyezik a kiválasztott célállomás nevével, de a „Másolás” utótaggal egészül ki. Ezt a lépést annyiszor ismételheti meg, ahányszor csak szükséges.

## <a name="security-considerations"></a>Biztonsági megfontolások

A **Nyomtatáskezelés beállítása** lapon csak akkor állíthat be névre szóló ER-célpontokat, ha rendelkezik a feladat elvégzéséhez szükséges [jogosultsággal](../sysadmin/role-based-security.md#permissions). Az engedély akkor adható meg Önnek, ha az **Elektronikus jelentéskészítési formátum célállomás konfigurálása** [feladat](../sysadmin/role-based-security.md#duties) az Ön egyik [biztonsági szerepköréhez](../sysadmin/role-based-security.md#security-roles)van rendelve. További információért lásd a [Biztonsági megfontolások](electronic-reporting-destinations.md#security-considerations) című részt.

## <a name="additional-resources"></a>További erőforrások

[Elektronikus jelentéskészítés (ER) áttekintése](general-electronic-reporting.md)

[Elektronikus jelentéskészítés (ER) céljai](electronic-reporting-destinations.md)

[Elektronikus jelentési keretrendszer API módosításai az Application update 10.0.17 számára](er-apis-app10-0-17.md)

[Elektronikus jelentési keretrendszer API módosításai az Application update 10.0.21 számára](er-apis-app10-0-21.md)

[A kód módosítása, hogy a felhasználók számára lehetővé tegye a névre szóló ER-célpontok konfigurálását és használatát](er-api-named-destinations.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
