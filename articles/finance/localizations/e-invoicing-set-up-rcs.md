---
title: A szabályozási konfigurációs szolgáltatás (RCS) beállítása
description: Ez a cikk a Szabályozási konfigurációs szolgáltatás (RCS) beállítását ismerteti.
author: gionoder
ms.date: 02/09/2022
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
ms.openlocfilehash: 63a4f77d6e80133947dff678cef3885167ec55be
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285787"
---
# <a name="set-up-regulatory-configuration-service-rcs"></a>A szabályozási konfigurációs szolgáltatás (RCS) beállítása

[!include [banner](../includes/banner.md)]

Ez a cikk a Szabályozási konfigurációs szolgáltatás (RCS) beállítását ismerteti.

## <a name="turn-on-globalization-features"></a>A globalizációs funkciók bekapcsolása

1. Jelentkezzen be a RCS-fiókba.
2. Válassza ki a **Funkció kezelése** csempét.
3. A **Funkció kezelése** munkaterületen válassza ki a **Globalizációs funkciókat** a listán, majd válassza az **Engedélyezés most** lehetőséget.

A Globalizációs funkciók **munkaterület csempéjének** most meg kell jelennie a fő RCS irányítópulton.

## <a name="set-up-the-parameters-for-rcs-integration-with-electronic-invoicing"></a>RCS-integráció paramétereinek beállítása az Elektronikus számlázással

1. A **Globalizációs funkciók** munkaterületen, a **Kapcsolódó beállítások** szakaszban, válassza az **Elektronikus jelentéskészítés paraméterei** hivatkozást.
2. **Az Elektronikus számlázás** lap Szolgáltatásvégpont URI-ja **mezőjében** adja meg a földrajzi helyének Microsoft Azure megfelelő szolgáltatásvégpontot az alábbi táblázatban látható módon.

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

3. Ellenőrizze, hogy az **Alkalmazásazonosító** mező **0cdb527f-a8d1-4bf8-9436-b352c68682b2** értékre legyen állítva. Ez egy rögzített érték. Győződjön meg arról, hogy csak egy globálisan egyedi azonosító (GUID) van megadva, és hogy az érték nem tartalmaz más szimbólumokat, például szóközöket, vesszőket, pontokat vagy idézőjeleket.
4. **Az LCS-környezetazonosító** mezőbe írja be az életciklus-szolgáltatási (LCS) környezet azonosítóját Microsoft Dynamics. Ez az érték az elektronikus számlázási szolgáltatással használni kívánt Pénzügyi vagy Ellátásilánc-kezelési környezetre való hivatkozás. Az azonosító lekéréséhez jelentkezzen be az LCS-be [...](https://lcs.dynamics.com/), nyissa meg a projektet, majd a **Környezet** kezelése lap **Környezet részletei** szakaszában keresse meg a **Környezetazonosító** mezőt.

    > [!IMPORTANT]
    > Ha az Elektronikus számlázás bővítmény több Finance vagy Supply Chain Management környezetben van telepítve az LCS-ben, mindig a legutóbb telepített környezet környezetazonosítóját használja. Ha úgy dönt, hogy új környezetbe telepíti a bővítményt Miután beállította és használta az Elektronikus számlázás funkciót, frissítse az LCS-környezetazonosító **mezőt az** RCS-ben a legújabb értékre.

5. Válassza a **Mentés** gombot, majd zárja be az oldalt.

## <a name="configuration-providers"></a>Konfigurációszolgáltatók

A konfigurációszolgáltatók segítségével megkülönböztetheti az elektronikus számlázási folyamatokban használt elektronikus jelentéskészítési (ER) konfigurációk tulajdonosait és a tulajdonosok globalizációs funkcióit. A Microsoft által biztosított és a globális adattárban közzétett összes globalizációs funkció esetében a konfigurációszolgáltató a Microsoft **() értékre** van állítva.`http://microsoft.com`

Csak az aktív konfigurációszolgáltatóhoz tartozó ER-konfigurációkat és globalizációs funkciókat módosíthatja. Ezeket a konfigurációkat és szolgáltatásokat sablonként használhatja az aktív konfigurációszolgáltatóhoz tartozó konfigurációk és szolgáltatások létrehozásához, így módosíthatja őket.

Először hozza létre a konfigurációs szolgáltatókat. Ezután állítsa be az egyiket aktívnak. A Microsoft **konfigurációszolgáltatóját nem állíthatja be** aktívként.

### <a name="create-a-configuration-provider"></a>Konfigurációszolgáltató létrehozása

1. Az **Elektronikus jelentéskészítés** munkaterületen, a **Kapcsolódó hivatkozások** szakaszban, válassza a **Konfigurációszolgáltatók** elemet.
2. Válassza az **Új** lehetőséget.
3. **A Név** mezőben adjon meg egy egyedi nevet a konfigurációszolgáltatónak.
4. **Az Internetcím** mezőbe írja be a konfigurációszolgáltató egyedi URL-címét.
5. Válassza a **Mentés** gombot, majd zárja be az oldalt.

### <a name="select-a-configuration-provider-as-active"></a>Válasszon ki egy konfigurációszolgáltatót aktívként

1. A konfigurációszolgáltatók listájában válassza ki azt a konfigurációszolgáltatót, amelyet aktívként szeretne beállítani.
2. Válassza ki az **Aktív beállítása** elemet.

## <a name="import-er-configurations-from-the-global-repository"></a>ER-konfigurációk importálása a globális adattárból

1. Az **Elektronikus jelentéskészítés** munkaterületen, a **Kapcsolódó hivatkozások** szakaszban, válassza a **Konfigurációszolgáltatók** elemet.
2. A konfigurációszolgáltatók listájában válassza **a Microsoft**, majd az Adattárak lehetőséget.**·**
3. Válassza a Globális **lehetőséget**, majd a Műveleti ablaktáblán válassza a Megnyitás **lehetőséget**.
4. Importálja a következő ER-modelleket:

    - **Vevői számlakontextus-modell**
    - **Számlamodell**
    - **Pénzügyi dokumentumok** (brazíliai forgatókönyvekhez, ha szükséges)
    - **Válaszüzenet-modell**

5. Ha **a számlamodell-leképezés** nem lett automatikusan importálva, importálja azt.
6. Zárja be a lapot.
