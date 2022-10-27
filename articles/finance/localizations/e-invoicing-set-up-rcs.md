---
title: A szabályozó konfigurációs szolgáltatás (RCS) beállítása
description: Ez a témakör bemutatja a szabályozó konfigurációs szolgáltatás (RCS) beállítását.
author: gionoder
ms.date: 10/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.custom: 97423,  ""intro-internal
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 32ced98925ee66e02f0b073b4acbd586666ac20c
ms.sourcegitcommit: 1ecfc1d8afb2201ab895ae6f93304ba2b120f14b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/21/2022
ms.locfileid: "9710781"
---
# <a name="set-up-regulatory-configuration-service-rcs"></a>A szabályozó konfigurációs szolgáltatás (RCS) beállítása

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja a szabályozó konfigurációs szolgáltatás (RCS) beállítását.

## <a name="turn-on-globalization-features"></a>A globalizációs funkciók bekapcsolása

1. Jelentkezzen be a RCS-fiókba.
2. Válassza ki a **Funkció kezelése** csempét.
3. A **Funkció kezelése** munkaterületen válassza ki a **Globalizációs funkciókat** a listán, majd válassza az **Engedélyezés most** lehetőséget.

A globalizációs funkciók munkaterületének **csempe** megjelenőnek kell lennie a fő RCS-vezérlőpulton.

## <a name="set-up-the-parameters-for-rcs-integration-with-electronic-invoicing"></a>RCS-integráció paramétereinek beállítása az Elektronikus számlázással

1. A **Globalizációs funkciók** munkaterületen, a **Kapcsolódó beállítások** szakaszban, válassza az **Elektronikus jelentéskészítés paraméterei** hivatkozást.
2. A paraméterek első beállításakor a rendszer rákérdez, hogy csatlakozzon az életciklus-szolgáltatásokhoz. Kattintson **ide a Lifecycle Services** szolgáltatáshoz való csatlakozáshoz, és a kapcsolat létrejötte után válassza az **OK gombra**.

    > [!IMPORTANT]
    > Egyes országokban vagy régiókban, ahol az adatok lakhelyét érvényesítik, és az RCS-et más területen létesítik, ahol az LCS létesítve van, a következő kapcsolati hibaüzenet jelenik meg az RCS szolgáltatásban: "Nem található olyan HTTP erőforrás, amely megfelel az URI-nak". Válassza ki az **OK** lehetőséget. Újabb hibaüzenetet kaphat az RCS szolgáltatásban: "Nem sikerült generálni a Dynamics Lifecycle services felhasználói jogkivonatát a felhasználó () nevében. Forduljon a rendszergazdához."
    >  
    > Ez azért fordul elő, mert az LCS egy globális szolgáltatás, amely az Egyesült Államok régiójában van létesítve. Az aktuális régióból származó RCS-ek az adatokra vonatkozó tartózkodási kötvény miatt nem tudnak csatlakozni az LCS-hez. Ezen a módon két lehetséges megoldás lehetséges:
    > - Törölje az RCS-t az aktuális régióból, és hozza létre újra az EGYESÜLT Államok régiójában.
    > - A hibák figyelmen kívül hagyása és folytatás az Elektronikus számlázás beállítással. Ezek a hibák nincsenek hatással az elektronikus számlázás funkcióra.

3. Az Elektronikus **számlázás** **lap Szolgáltatási végpont URI** Microsoft Azure mezőjében adja meg a földrajzi régió megfelelő szolgáltatási végpontját, amint azt a következő táblázat mutatja.

    | Adatközpont Azure földrajzi régió | Szolgáltatási végpont URI-címe |
    |----------------------------|----------------------|
    | Egyesült Államok              | <p>`https://gw.us-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il103.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il104.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il105.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il106.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il107.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il108.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il109.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Európa                     | <p>`https://gw.eu-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il103.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il104.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il105.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il106.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il107.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il108.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il109.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il110.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Egyesült Királyság             | <p>`https://gw.uk-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.uk-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Ázsia                       | <p>`https://gw.as-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.as-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Japán                      | <p>`https://gw.jp-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Svájc                | <p>`https://gw.ch-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Brazília                     | <p>`https://gw.br-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> <p>`https://gw.br-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Egyesült Arab Emírségek       | <p>`https://gw.ae-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Ausztrália                  | <p>`https://gw.au-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> <p>`https://gw.au-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Kanada                     | <p>`https://gw.ca-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> <p>`https://gw.ca-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Franciaország                     | <p>`https://gw.fr-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | India                      | <p>`https://gw.in-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Norvégia                     | <p>`https://gw.no-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Dél-Afrika               | <p>`https://gw.za-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |

3. Ellenőrizze és adja meg az **Alkalmazásazonosító mezőben** a rögzített értéket **0cdb527f-a8d1-4bf8-9436-b352c68682b2**. Győződjön meg arról, hogy csak egy globálisan egyedi azonosítót (GUID) adott meg, és az érték nem tartalmaz más szimbólumokat, például szóközt, vesszőt, időszakot vagy idézőjelet.
4. **Az LCS környezetazonosító** mezőbe írja Microsoft Dynamics be a Lifecycle Services (LCS) környezet azonosítóját. Ez az érték annak a pénzügyi vagy ellátásilánc-kezelési környezetnek a hivatkozása, amely az elektronikus számlázási szolgáltatással használható. Az azonosító bejezéséhez jelentkezzen [be az LCS-be](https://lcs.dynamics.com/), nyissa meg a projektet, **·** **·** **majd** a Környezet kezelése lap Környezet részletei szakaszÁnak Környezetazonosító mezőjében keresse meg.

    > [!IMPORTANT]
    > Ha az elektronikus számlázás bővítmény több pénzügyi vagy ellátásilánc-kezelési környezetben is telepítve van az LCS szolgáltatásban, akkor mindig a legutóbb telepített környezet környezeti azonosítóját használja. Ha úgy dönt, hogy a bővítményt új környezetbe telepíti az Elektronikus számlázás funkció beállítása és használata után, **a legfrissebb értékre frissítse az RCS LCS-környezetazonosító** mezőjét.

5. Válassza a **Mentés** gombot, majd zárja be az oldalt.

## <a name="configuration-providers"></a>Konfigurációszolgáltatók

A konfigurációszolgáltatókkal megkülönböztetheti az elektronikus számlázási folyamatokban és a tulajdonosok globalizációs funkcióiban használt elektronikus jelentési (ER) konfigurációkat. A Microsoft által biztosított és a globális tárházban közzétett minden globalizációs funkciónál a konfigurációszolgáltató a **Microsoft**`http://microsoft.com` ().

Csak az aktív konfigurációszolgáltatóhoz tartozó ER-konfigurációk és globalizációs funkciók módosíthatók. Ezeket a konfigurációkat és szolgáltatásokat sablonként használhatja az aktív konfigurációszolgáltatóhoz tartozó konfigurációk és funkciók létrehozásához, hogy aztán módosítani tudja azokat.

Először hozza létre a konfiguráció-szolgáltatókat. Ezután állítsa az egyiket aktívként. A Microsoft **konfigurációs szolgáltató nem** lehet aktív.

### <a name="create-a-configuration-provider"></a>Konfigurációszolgáltató létrehozása

1. Az **Elektronikus jelentéskészítés** munkaterületen, a **Kapcsolódó hivatkozások** szakaszban, válassza a **Konfigurációszolgáltatók** elemet.
2. Válassza az **Új** lehetőséget.
3. A Név **mezőbe** írja be a konfigurációszolgáltató egyedi nevét.
4. Az Internetcím **mezőben** adja meg a konfigurációs szolgáltató egyedi URL-címét.
5. Válassza a **Mentés** gombot, majd zárja be az oldalt.

### <a name="select-a-configuration-provider-as-active"></a>Konfigurációszolgáltató kiválasztása aktívként

1. A konfigurációs szolgáltatók listájában válassza ki azt a konfigurációs szolgáltatót, amely aktívként szeretné beállítani.
2. Válassza ki az **Aktív beállítása** elemet.

## <a name="import-er-configurations-from-the-global-repository"></a>ER-konfigurációk importálása a globális tárházból

1. Az **Elektronikus jelentéskészítés** munkaterületen, a **Kapcsolódó hivatkozások** szakaszban, válassza a **Konfigurációszolgáltatók** elemet.
2. A konfigurációs szolgáltatók listájában válassza ki **a Microsoftot**, majd válassza ki a **tárházakat**.
3. Válassza a **Globális** lehetőséget, majd a munkaablakban válassza a Megnyitás **lehetőséget**.
4. A következő ER modellek importálása:

    - **Vevői számlakontextus-modell**
    - **Számlamodell**
    - **Pénzügyi bizonylatok** (szükség esetén brazil helyzetekre)
    - **Válaszüzenet-modell**

5. Ha **a számlamodell megfeleltetését** nem importálta automatikusan, importálja.
6. Zárja be a lapot.
