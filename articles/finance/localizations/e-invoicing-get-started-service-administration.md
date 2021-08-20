---
title: Első lépések az elektronikus számlázási szolgáltatás adminisztrálása során
description: Ez a témakör bemutatja az Elektronikus számlázás szolgáltatásfelügyeletének használatának első lépéseit.
author: gionoder
ms.date: 05/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: feb8160cd920906765f7ef4a393e15c2be5d8c2cd60c3646e15648980ff27a06
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6765644"
---
# <a name="get-started-with-electronic-invoicing-service-administration"></a>Első lépések az elektronikus számlázási szolgáltatás adminisztrálása során

[!include [banner](../includes/banner.md)]

## <a name="prerequisites"></a>Előfeltételek

Mielőtt teljesítené az ebben a témakörben ismertetett eljárásokat, a következő előfeltételeknek kell megfelelnie:

- Hozzá kell férnie a Microsoft Dynamics Lifecycle Services (LCS) fiókjához.
- Olyan LCS-projekttel kell rendelkeznie, amely a Microsoft Dynamics 365 Finance és a Dynamics 365 Supply Chain Management 10.0.17-as vagy újabb verzióját tartalmazza. Ezenkívül ezeket az alkalmazásokat a következő Azure földrajzi régiók egyikében kell telepíteni:

    - Amerikai Egyesült Államok
    - Európa
    - Egyesült Királyság
    - Ázsia

- Hozzá kell férnie a Dynamics 365 Regulatory Configuration Services (RCS) fiókjához.
- Aktiválnia kell a Globalizációs funkciót az RCS-fiókjához a Funkciókezelőben. További információért lásd a [Kapcsolódás a Regulatory Configuration Services (RCS) szolgáltatáshoz – Globalizációs funkciók](rcs-globalization-feature.md) részt.
- Létre kell hoznia egy kulcstartót és egy tárfiókot az Azure szolgáltatásban. További információért lásd az [Azure tárfiók és kulcstartó létrehozása](e-invoicing-create-azure-storage-account-key-vault.md) lehetőséget.

## <a name="install-the-add-in-for-microservices-in-lifecycle-services"></a>A mikroszolgáltatások bővítményének telepítése a Lifecycle Services szolgáltatásba

1. Jelentkezzen be az LCS-fiókba, és az LCS projekt irányítópultján válasszon ki egy LCS-projektet.
2. A projektben, akörnyezet irányítópultján válassza ki az LCS-telepítési projektet. A kiválasztott projektnek futnia kell.
3. A **Power Platform Integráció** lapon a **Környezeti bővítmények** mezőcsoportban válassza az **Új bővítmény telepítése** lehetőséget.
4. Válassza az **Elektronikus számlázás** lehetőséget.
5. Az **AAD-alkalmazásazonosító** mezőbe írja: **091c98b0-a1c9-4b02-b62c-7753395ccabe**. Ez egy rögzített érték.
6. Az **AAD-bérlőazonosító** mezőbe írja be az Azure előfizetési fiókja bérlőazonosítóját.
7. Olvassa el az Általános Szerződési Feltételeket, majd jelölje be a jelölőnégyzetet.
8. Válassza a **Telepítés** parancsot.


## <a name="set-up-the-parameters-for-rcs-integration-with-electronic-invoicing"></a>RCS-integráció paramétereinek beállítása az Elektronikus számlázással

1. Jelentkezzen be a RCS-fiókba.
2. Az **Elektronikus jelentéskészítés** munkaterületen, a **Kapcsolódó hivatkozások** szakaszban, válassza az **Elektronikus jelentéskészítés paraméterei** elemet.
3. Az **e-számlázási szolgáltatás** lapon a **Szolgáltatási végpont URI** mezőben adja meg az Azure földrajzi régió megfelelő szolgáltatási végpontját, amint azt a következő tábla mutatja.

    | Adatközpont Azure földrajzi régió | Szolgáltatási végpont URI-címe                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | Amerikai Egyesült Államok              | <p>`https://gw.us-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il103.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il104.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il105.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il106.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il107.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il108.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il109.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Európa                     | <p>`https://gw.eu-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il103.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il104.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il105.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il106.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il107.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il108.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il109.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il110.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Egyesült Királyság             | <p>`https://gw.uk-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.uk-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Ázsia                       | <p>`https://gw.as-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.as-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |

4. Ellenőrizze, hogy az **Alkalmazásazonosító** mező **0cdb527f-a8d1-4bf8-9436-b352c68682b2** értékre legyen állítva. Ez egy rögzített érték.
5. Az **LCS-környezet azonosítója** mezőbe írja be az LCS környezet azonosítóját.
6. Válassza a **Mentés** gombot, majd zárja be az oldalt.

## <a name="create-key-vault-references"></a>Key Vault-hivatkozások létrehozása

1. Jelentkezzen be a RCS-fiókba.
2. A **Globalizációs funkció** munkaterületen a **Környezet** szakaszban válassza ki az **Elektronikus számlázás bővítmény** csempét.
3. A **Környezet beállítása** lapon a Művelet ablaktáblán válassza ki a **Szolgáltatási környezet**, majd a **Key Vault-paraméterek** lehetőséget.
4. Kulcstartó hivatkozás létrehozásához válassza az **Új** lehetőséget.
5. A **Név** mezőben adja meg a kulcstartó hivatkozásának nevét. Adjon meg egy leírást a **Leírás** mezőben.
6. A **Key Vault – URI** mezőbe másolja be a kulcstartó titkos kódját az Azure Key Vault megoldásból. További információért lásd az [Azure tárfiók és kulcstartó létrehozása](e-invoicing-create-azure-storage-account-key-vault.md) lehetőséget.
7. Válassza a **Mentés** lehetőséget.

## <a name="create-storage-account-secret"></a>Titkos kód létrehozása tárfiókhoz

1. A **Környezet beállítása** lapon a Műveleti ablaktáblán válassza ki a **Szolgáltatási környezet** > **Key Vault-paraméterek** lehetőséget.
2. Jelöljön ki egy **Key Vault-hivatkozást**, és a **Tanúsítványok** szakaszban válassza a **Hozzáadás** lehetőséget.
3. A **Név** mezőbe írja be a tárfiók titkos kódjának nevét. További információért lásd az [Azure tárfiók és kulcstartó létrehozása](e-invoicing-create-azure-storage-account-key-vault.md) lehetőséget.
4. Adjon meg egy leírást a **Leírás** mezőben.
5. A **Típus** mezőben válassza ki a **Titok** lehetőséget.
6. Válassza a **Mentés** gombot, majd zárja be az oldalt.

## <a name="create-a-digital-certificate-secret"></a>Digitális tanúsítvány titkos kódjának létrehozása

1. A **Környezet beállítása** lapon a Művelet ablaktáblán válassza ki a **Szolgáltatási környezet**, majd a **Key Vault-paraméterek** lehetőséget.
2. Jelöljön ki egy **Key Vault-hivatkozást**, majd a **Tanúsítványok** szakaszban válassza a **Hozzáadás** lehetőséget.
3. A **Név** mezőbe írja be a digitális tanúsítvány titkának a nevét. További információért lásd az [Azure tárfiók és kulcstartó létrehozása](e-invoicing-create-azure-storage-account-key-vault.md) lehetőséget.
4. Adjon meg egy leírást a **Leírás** mezőben.
5. A **Típus** mezőben válassza ki a **Tanúsítvány** lehetőséget.
6. Válassza a **Mentés** gombot, majd zárja be az oldalt.

## <a name="create-a-service-environment"></a>Szolgáltatási környezet létrehozása

1. Jelentkezzen be a RCS-fiókba.
2. A **Globalizációs funkció** munkaterületen a **Környezet** szakaszban válassza ki az **Elektronikus számlázás bővítmény** csempét.
3. A **Környezet beállítása** oldalon a Művelet ablaktáblán válassza a **Szolgáltatási környezet** lehetőséget.
4. Válassza ki az **Új** lehetőséget egy új szolgáltatási környezet létrehozásához.
5. A **Név** mezőben adja meg az e-számlázási környezet nevét. Adjon meg egy leírást a **Leírás** mezőben.
6. A **Tárterület SAS-token titkos kód** mezőben válassza ki azon tárfiók titkos kódjának a nevét, amely a tárfiókhoz való hozzáférés hitelesítéséhez szükséges.
7. A **Felhasználók** szakaszban válassza a **Hozzáadás** lehetőséget annak a felhasználónak a hozzáadásához, aki számára engedélyezett az elektronikus számlák elküldése a környezetben, valamint a tárfiókhoz való csatlakozás.
8. A **Felhasználói azonosító** mezőbe írja be a felhasználó aliasát. Az **E-mail** mezőbe írja be a feladó e-mail-címét.
9. Válassza a **Mentés** lehetőséget.
10. Ha az ország-/régióspecifikus számlákhoz egy tanúsítványlánc szükséges a digitális aláírások alkalmazásához, akkor válassza a Művelet ablaktábla **Key Vault-paraméterek** elemét, majd a **Tanúsítványlánc** lehetőséget, és kövesse az alábbi lépéseket:
    1. Tanúsítványlánc létrehozásához válassza az **Új** lehetőséget.
    2. A **Név** mezőbe írja be a tanúsítványlánc nevét. Adjon meg egy leírást a **Leírás** mezőben.
    3. A **Tanúsítványok** szakaszban válassza a **Hozzáadás** lehetőséget, ha tanúsítványt szeretne hozzáadni a lánchoz.
    4. A **Fel** és a **Le** gombbal módosíthatja a tanúsítványnak a láncon belül elfoglalt pozícióját.
    5. Válassza a **Mentés** gombot, majd zárja be az oldalt.
    6. Zárja be a lapot.
11. A Művelet ablaktáblán válassza a **Szolgáltatási környezet**, majd a **Közzététel** lehetőséget a környezet felhőben történő közzétételéhez. Az **Állapot** mező értéke **Közzétéve** értékre módosul.

## <a name="create-a-connected-application"></a>Csatlakoztatott alkalmazás létrehozása

1. A **Környezet beállítása** oldalon a Művelet ablaktáblán válassza a **Csatlakoztatott alkalmazások** lehetőséget.
2. Válassza ki az **Új** lehetőséget egy csatlakoztatott alkalmazás létrehozásához.
3. A **Név** mezőben adja meg a csatlakoztatni kívánt alkalmazás nevét.
4. Az **Alkalmazás** mezőben adja meg a csatlakozáshoz szükséges Finance and Supply Chain Management környezet URL-címét.
4. A **Bérlő** mezőben adja meg a Finance and Supply Chain Management környezet bérlőjét.
5. Válassza a **Mentés** lehetőséget.
6. A Művelet ablaktáblán válassza a **Kapcsolat ellenőrzése** lehetőséget a környezettel való kapcsolat teszteléséhez. Ezután zárja be az oldalt.

## <a name="link-connected-applications-to-environments"></a>Csatlakoztatott alkalmazások csatolása környezetekhez

1. A **Környezet beállítása** oldalon válassza az **Új** lehetőséget, ha a környezethez hozzá szeretne rendelni egy csatlakoztatott alkalmazást.
2. A **Csatlakoztatott alkalmazás** mezőben válasszaon ki egy csatlakoztatott alkalmazást.
3. Válassza ki a szolgáltatási környezetet a **Szolgáltatási környezet** mezőben.
4. Válassza a **Mentés** gombot, majd zárja be az oldalt.

## <a name="set-up-electronic-invoicing-integration-in-finance-and-supply-chain-management"></a>Elektronikus számlázásbővítmény integráció beállítása a Finance és a Supply Chain Management szolgáltatásban

### <a name="turn-on-the-electronic-invoicing-integration-feature"></a>Az Elektronikus számlázás integráció funkció bekapcsolása

1. Jelentkezzen be a Finance vagy Supply Chain Management-példányába.
2. A **Funkciókezelés** munkaterületen keresse meg az **Elektronikus számlázás integrációja** funkciót. Ha ez a funkció nem jelenik meg az oldalon, válassza a **Frissítések keresése** lehetőséget.
3. Válassza ki a bekapcsolni kívánt funkciót, majd a részletek ablaktáblán válassza az **Engedélyezés most** lehetőséget.

### <a name="set-up-the-service-endpoint-url"></a>A szolgáltatásvégpont URL-címének beállítása

1. Menjen a **Szervezeti adminisztráció \> Beállítás \> Elektronikus dokumentumparaméterek** lehetőségre.
2. A **Beküldési szolgáltatás** lapon a **Szolgáltatási végpont URL** mezőben adja meg az Azure földrajzi régió megfelelő szolgáltatási végpontját, amint azt a következő tábla mutatja.

    | Adatközpont Azure földrajzi régió | Szolgáltatási végpont URI-címe                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | Amerikai Egyesült Államok              | <p>`https://gw.us-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il103.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il104.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il105.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il106.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il107.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il108.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il109.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Európa                     | <p>`https://gw.eu-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il103.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il104.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il105.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il106.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il107.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il108.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il109.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il110.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Egyesült Királyság             | <p>`https://gw.uk-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.uk-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Ázsia                       | <p>`https://gw.as-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.as-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |

3. A **Környezet** mezőben adja meg az Elektronikus számlázásban közzétett szolgáltatási környezet nevét.
4. Válassza a **Mentés** gombot, majd zárja be az oldalt.

### <a name="enable-flighting-keys"></a>Tesztkulcsok engedélyezése

Engedélyezze a tesztkulcsokat a Microsoft Dynamics 365 Finance vagy a Microsoft Dynamics 365 Supply Chain Management 10.0.17-es vagy korábbi verzióihoz. 
1. Hajtsa végre a következő SQL-parancsot:

    ILLESSZE BE A SYSFLIGHTING (JÁRATNÉV, ENGEDÉLYEZETT) ÉRTÉKEKBE ('BusinessDocumentSubmissionServiceEnabled', 1)
    
    ILLESSZE BE A SYSFLIGHTING (JÁRATNÉV, ENGEDÉLYEZETT) ÉRTÉKEKBE ('ElectronicInvoicingServiceIntegrationFeature', 1)

2. IISreset parancs végrehajtása minden AOS-hoz.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
