---
title: IoT-megoldás telepítése az Azure-ba
description: A belső adatintelligencia a csatlakozott adattárak adatait használja Microsoft Azure. Ez a témakör bemutatja, hogy hogyan telepítheti az Internet of Things (Internet of Things) megoldást az Azure-előfizetésre.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: IoTIntCoreAzureResourceDeploymentWizard
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 5f0f49c0f7daaacb85b75dc11b9f015b6aa4e997
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689721"
---
# <a name="deploy-an-iot-solution-on-azure"></a>IoT-megoldás telepítése az Azure-ba

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

A belső adatintelligencia a csatlakozott adattárak adatait használja Microsoft Azure. Ahhoz, hogy az Azure beolvassa Dynamics 365 Supply Chain Management az adatokat a telefonból, és megosztsa az adatait, az Azure-előfizetésre egy IM-megoldást (Internet of Things) kell telepítenie. A következő diagram diagramja áttekintést nyújt a megoldásról és annak összetevőiről.

![A belső adatintelligencia diagramja](media/sdi-architecture.png "Belső adatintelligencia -diagram")

## <a name="video-instructions"></a>Video-utasítások

Az alábbi videofelvétel bemutatja, hogyan [lehet bekapcsolni az Intelligens adatintelligencia](sdi-enable-feature.md) szolgáltatást, és telepíteni a szükséges Azure-erőforrásokat. A cikk másik része szöveges formátumú utasításokat tartalmaz.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE58g3I]

## <a name="procedure"></a>Eljárás

A következő lépések szerint telepítheti a szükséges erőforrásokat az Azure szolgáltatásban.

1. Jelentkezzen be rendszergazdaként az Ellátásilánc-kezelésbe.
1. Menjen a Rendszerfelügyelet **beállítása \>\> – Adatintelligencia \> telepítése szolgáltatáshoz, és csatlakozzon Az Azure erőforrásokhoz** a telepítési varázsló megnyitásához.
1. Az Üdvözlő **lapon** olvassa el az adatokat, majd válassza a Tovább **gombra**.
1. Olvassa el **az adatokat a Minta Azure-megoldás telepítése azure szolgáltatásba** oldalon, **majd** az Utasítások szakaszban válassza a Telepítés **lehetőséget**.
1. Megnyílik egy új böngésző lap, és a rendszer áttér az Azure-portálra, és telepítheti az Azure-erőforrásokat. Ha a rendszer megkérdezi, hogy Az Azure-előfizetés hitelesítő adatainak használatával jelentkezzen be.
1. Válassza ki az **előfizetést** **az Egyéni telepítési lapon, az Előfizetés** mezőben.
1. Az Erőforráscsoport **mezőben** válassza **az Új** létrehozása lehetőséget, ha erőforráscsoportot hoz létre a telepíteni kívánt Azure-összetevőkhöz.
1. A Név **mezőben** megjelenő legördülő párbeszédpanelen adjon nevet az új erőforráscsoportnak (*például IÓT-bemutató*). Majd kattintson az **OK** lehetőségre.
1. Állítsa be a következő mezőket:

    - **Erőforráscsoport** – válassza ki a most létrehozott erőforráscsoportot.
    - **Régió** – válasszon egy régiót, ideális esetben azt a régiót, ahová az ellátásilánc-kezelési környezetet telepítik. Tartsa szem előtt, hogy az Azure-régióknak más az árképzésük. Az adott régió becsült költségeit [az Intelligence árkalkulátor segítségével lehet megtekinteni](https://azure.com/e/c36c4947ebff4215b2e62590c2a24c68).
    - **Ellátásilánc-kezelési környezet URL-címe** – adja meg az ellátásilánc-kezelési környezet URL-címét.
    - **A meglévő Azure Azure-központ újbóli használatának** érdekében – hagyja a jelölőnégyzetet törölve.

1. Válassza a **Következőt: Áttekintés + Létrehozás**.
1. Ellenőrizze az **Egyéni telepítési** lapon, hogy az ellenőrzés elmúlt-e, **majd válassza a Létrehozás lehetőséget**.
1. A **telepítés folyamatban van,** ez a lap a telepítés előrehaladását követi nyomon. A telepítési folyamat akár 30 percig is eltarthat. **Ha a telepítés folyamatban** van, azt jelzi, hogy a telepítés befejeződött, válassza ki az erőforráscsoportnév hivatkozását egy olyan lap megnyitásához, amely megjeleníti a csoportba telepített erőforrások listáját.
1. Az erőforráslistán keresse meg **azt a rekordot, amelyben a Típus** mező felügyelt identitásra *van állítva*. A Név **oszlopban** válassza ki az erőforrás részletes adatait tartalmazó lapot.
1. Az Ügyfél azonosítója mező értékének **másolása** (például **a Másolás a vágólapra** gomb használatával).
1. Menjen vissza arra a böngészőlapra, ahol fut az Ellátásilánc-kezelés, *de ne zárja be az Azure-portál lapját*. A **Minta Azure-megoldás telepítése a Azure varázslóhoz** lapnak továbbra is nyitva kell lennie. 
1. Válassza ki **Következő** lehetőséget.
1. Az Azure-erőforrások csatlakoztatása **lap** Alkalmazás **Azure AD ügyfélazonosító mezőjébe másolja be** **a** másolt ügyfélazonosító értékét.
1. Menjen vissza arra a böngészőlapra, ahol meg van nyitva az Azure-portál, *de ne zárja be az Ellátásilánc-kezelés lapját*. Ennek az erőforrásnak továbbra is nyitva kell lennie a részletező lapnak.
1. Az új erőforráscsoportban található erőforrások listájára **való** visszatéréshez válassza a böngésző Vissza gombját.
1. Az erőforráslistán keresse meg azt a rekordot, **amelyben a Típus** mező *az Azure-gyorsítótárba van állítva a Redis fájlhoz*. A Név **oszlopban** válassza ki az erőforrás részletes adatait tartalmazó lapot.
1. A bal oldali navigációs ablakban válassza ki a Hozzáférési **kulcsokat**.
1. A Hozzáférési **kulcsok** lapon **másolja át az elsődleges kapcsolati karakterláncban (StackExchange.Redis)** látható értéket (például a **Másolás** a vágólapra gomb használatával).
1. Vissza arra a böngésző lapra, ahol az Ellátásilánc-kezelés fut. Az **Azure-erőforrások csatlakoztatása** lapnak nyitva kell lennie.
1. **A Redis metrikus üzlet kapcsolati karakterlánc** **mezőjébe másolja be a másolt Elsődleges kapcsolati karakterlánc (StackExchange.Redis)** értékét.
1. Válassza a **Befejezés** lehetőséget.

Most az Azure-előfizetésre telepítik az Azure-erőforrásokat az intelligens adatintelligencia számára.

> [!NOTE]
> Az Ellátásilánc-kezeléshez **mentett kapcsolati adatokat bármikor megtekintheti és szerkesztheti** az információs információs paraméterek lap megnyitásával. A további tudnivalókat lásd [a Paraméteradat-paramétereknél](sdi-parameters.md).
