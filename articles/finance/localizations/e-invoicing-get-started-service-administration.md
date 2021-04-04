---
title: Első lépések az Elektronikus számlázási bővítmény szolgáltatásfelügyeletének használata során
description: Ez a témakör bemutatja az Elektronikus számlázási bővítmény szolgáltatásfelügyeletének használatának első lépéseit.
author: gionoder
manager: AnnBe
ms.date: 03/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 05b00380cec7511adad2467d3f252799a4aaee5c
ms.sourcegitcommit: 543772ee97efe215cf6f2ec6e092cc1568919f20
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/13/2021
ms.locfileid: "5592526"
---
# <a name="get-started-with-electronic-invoicing-add-on-service-administration"></a>Első lépések az Elektronikus számlázási bővítmény szolgáltatásfelügyeletének használata során

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

## <a name="prerequisites"></a>Előfeltételek

Mielőtt teljesítené az ebben a témakörben ismertetett eljárásokat, a következő előfeltételeknek kell megfelelnie:

- Hozzá kell férnie a Microsoft Dynamics Lifecycle Services (LCS) fiókjához.
- Olyan LCS-projekttel kell rendelkeznie, amely a Microsoft Dynamics 365 Finance és a Dynamics 365 Supply Chain Management 10.0.17-as vagy újabb verzióját tartalmazza. Ezenkívül ezeket az alkalmazásokat a következő Azure földrajzi régiók egyikében kell telepíteni:

    - USA keleti régiója
    - USA nyugati régiója
    - Észak-EU
    - Nyugat-EU

- Hozzá kell férnie a Dynamics 365 Regulatory Configuration Services (RCS) fiókjához.
- Aktiválnia kell a Globalizációs funkciót az RCS-fiókjához a Funkciókezelőben. További információért lásd a [Kapcsolódás a Regulatory Configuration Services (RCS) szolgáltatáshoz – Globalizációs funkciók](rcs-globalization-feature.md) részt.
- Létre kell hoznia egy kulcstartót és egy tárfiókot az Azure szolgáltatásban. További információért lásd az [Azure tárfiók és kulcstartó létrehozása](e-invoicing-create-azure-storage-account-key-vault.md) lehetőséget.

## <a name="install-the-add-on-for-microservices-in-lifecycle-services"></a>A mikroszolgáltatások bővítményének telepítése a Lifecycle Services szolgáltatásba

1. Jelentkezzen be a LCS-fiók.
2. Válassza az **Előzetes funkció kezelése** csempe lehetőséget.
3. A **Nyilvános előzetes verzió** szakaszban válassza az **e-számlázási szolgáltatás** lehetőséget.
4. Ellenőrizze, hogy az **Előzetes funkció engedélyezve** értéke **Igen** értékre van-e állítva.
5. Válassza ki az LCS-telepítési projektet az LCS-irányítópulton. Az LCS-projektnek futnia kell.
7. A **Környezetbővítmények** lapon válassza az **Új bővítmény telepítése** lehetőséget.
8. Válassza ki az **e-számlázási szolgáltatások** lehetőséget, az **AAD alkalmazás azonosítója** mezőbe pedig írja be a következőt: **091c98b0-a1c9-4b02-b62c-7753395ccabe**. Ez egy rögzített érték.
10. Az **AAD-bérlőazonosító** mezőbe írja be az Azure előfizetési fiókja bérlőazonosítóját.
11. Olvassa el az Általános Szerződési Feltételeket, majd jelölje be a jelölőnégyzetet.
12. Válassza a **Telepítés** parancsot.


## <a name="set-up-the-parameters-for-rcs-integration-with-the-electronic-invoicing-add-on"></a>RCS-integráció paramétereinek beállítása az Elektronikus számlázási bővítménnyel

1. Jelentkezzen be a RCS-fiókba.
2. Az **Elektronikus jelentéskészítés** munkaterületen, a **Kapcsolódó hivatkozások** szakaszban, válassza az **Elektronikus jelentéskészítés paraméterei** elemet.
3. Az **e-számlázási szolgáltatás** lapon a **Szolgáltatási végpont URI** mezőben adja meg az Azure földrajzi régió megfelelő szolgáltatási végpontját, amint azt a következő tábla mutatja.

    | Adatközpont Azure földrajzi régió | Szolgáltatási végpont URI-címe                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | USA keleti régiója                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | USA nyugati régiója                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | Észak-EU                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | Nyugat-EU                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

4. Ellenőrizze, hogy az **Alkalmazásazonosító** mező **0cdb527f-a8d1-4bf8-9436-b352c68682b2** értékre legyen állítva. Ez egy rögzített érték.
5. Az **LCS-környezet azonosítója** mezőbe írja be az LCS előfizetési fiókja azonosítóját.
6. Válassza a **Mentés** gombot, majd zárja be az oldalt.

## <a name="create-key-vault-secret"></a>Key Vault titkos kód létrehozása

1. Jelentkezzen be a RCS-fiókba.
2. A **Globalizációs funkció** munkaterületen a **Környezet** szakaszban válassza ki az **Elektronikus számlázás bővítmény** csempét.
3. A **Környezet beállítása** lapon a Művelet ablaktáblán válassza ki a **Szolgáltatási környezet**, majd a **Key Vault-paraméterek** lehetőséget.
4. Kulcstartó titkos kód létrehozásához válassza az **Új** lehetőséget.
5. A **Név** mezőben adja meg a kulcstartó titkos kód nevét. Adjon meg egy leírást a **Leírás** mezőben.
6. A **Key Vault – URI** mezőbe másolja be a titkos kódot az Azure Key Vault megoldásból.
7. Válassza a **Mentés** lehetőséget.

## <a name="create-storage-account-secret"></a>Titkos kód létrehozása tárfiókhoz

1. Menjen a **Rendszerfelügyelet** > **Beállítás** > **Key Vault-paraméterek** pontra , és válassza ki a kulcstartó titkos kódját.
2. A **Tanúsítványok** szakaszban válassza a **Hozzáadás** lehetőséget.
3. A **Név** mezőbe írja be a tárfiók titkos kódjának nevét, és adjon meg egy leírást a **Leírás** mezőben.
4. A **Típus** mezőben válassza ki a **Tanúsítvány** lehetőséget.
5. Válassza a **Mentés** gombot, majd zárja be az oldalt.

## <a name="create-a-digital-certificate-secret"></a>Digitális tanúsítvány titkos kódjának létrehozása

1. Menjen a **Rendszerfelügyelet** > **Beállítás** > **Key Vault-paraméterek** pontra , és válassza ki a kulcstartó titkos kódját.
2. A **Tanúsítványok** szakaszban válassza a **Hozzáadás** lehetőséget.
3. A **Név** mezőbe írja be a digitális tanúsítvány titkos kódjának nevét, és adjon meg egy leírást a **Leírás** mezőben.
4. A **Típus** mezőben válassza ki a **Tanúsítvány** lehetőséget.
5. Válassza a **Mentés** gombot, majd zárja be az oldalt.

## <a name="create-an-electronic-invoicing-add-on-environment"></a>Az Elektronikus számlázási bővítmény környezetének létrehozása

1. Jelentkezzen be a RCS-fiókba.
2. A **Globalizációs funkció** munkaterületen a **Környezet** szakaszban válassza ki az **Elektronikus számlázás bővítmény** csempét.

## <a name="create-a-service-environment"></a>Szolgáltatási környezet létrehozása

1. A **Környezet beállítása** oldalon a Művelet ablaktáblán válassza a **Szolgáltatási környezet** lehetőséget.
2. Válassza ki az **Új** lehetőséget egy új szolgáltatási környezet létrehozásához.
3. A **Név** mezőben adja meg az e-számlázási környezet nevét. Adjon meg egy leírást a **Leírás** mezőben.
4. A **Tárterület SAS-token titkos kód** mezőben válassza ki azon tárfiók titkos kódjának a nevét, amely a tárfiókhoz való hozzáférés hitelesítéséhez szükséges.
5. A **Felhasználók** szakaszban válassza a **Hozzáadás** lehetőséget annak a felhasználónak a hozzáadásához, aki számára engedélyezett az elektronikus számlák elküldése a környezetben, valamint a tárfiókhoz való csatlakozás.
6. A **Felhasználói azonosító** mezőbe írja be a felhasználó aliasát. Az **E-mail** mezőbe írja be a feladó e-mail-címét.
7. Válassza a **Mentés** lehetőséget.
8. Ha az ország-/régióspecifikus számlákhoz egy tanúsítványlánc szükséges a digitális aláírások alkalmazásához, akkor válassza a Művelet ablaktábla **Key Vault-paraméterek** elemét, majd a **Tanúsítványlánc** lehetőséget, és kövesse az alábbi lépéseket:

    1. Tanúsítványlánc létrehozásához válassza az **Új** lehetőséget.
    2. A **Név** mezőbe írja be a tanúsítványlánc nevét. Adjon meg egy leírást a **Leírás** mezőben.
    3. A **Tanúsítványok** szakaszban válassza a **Hozzáadás** lehetőséget, ha tanúsítványt szeretne hozzáadni a lánchoz.
    4. A **Fel** és a **Le** gombbal módosíthatja a tanúsítványnak a láncon belül elfoglalt pozícióját.
    5. Válassza a **Mentés** gombot, majd zárja be az oldalt.
    6. Zárja be a lapot.
9. A Művelet ablaktáblán válassza a **Szolgáltatási környezet**, majd a **Közzététel** lehetőséget a környezet felhőben történő közzétételéhez. Az **Állapot** mező értéke **Közzétéve** értékre módosul.

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

## <a name="set-up-the-electronic-invoicing-add-on-integration-in-finance-and-supply-chain-management"></a>Elektronikus számlázási bővítmény integrációjának beállítása a Finance and Supply Chain Management szolgáltatásban

### <a name="turn-on-the-electronic-invoicing-add-on-integration-feature"></a>Az Elektronikus számlázásbővítmény integráció funkció bekapcsolása

1. Jelentkezzen be a Finance vagy Supply Chain Management-példányába.
2. A **Funkciókezelés** munkaterületen keresse meg az **Elektronikus számlázási bővítmény integrációja** funkciót. Ha ez a funkció nem jelenik meg az oldalon, válassza a **Frissítések keresése** lehetőséget.
3. Válassza ki a bekapcsolni kívánt funkciót, majd a részletek ablaktáblán válassza az **Engedélyezés most** lehetőséget.

### <a name="set-up-the-service-endpoint-url"></a>A szolgáltatásvégpont URL-címének beállítása

1. Menjen a **Szervezeti adminisztráció \> Beállítás \> Elektronikus dokumentumparaméterek** lehetőségre.
2. A **Beküldési szolgáltatás** lapon a **Szolgáltatási végpont URL** mezőben adja meg az Azure földrajzi régió megfelelő szolgáltatási végpontját, amint azt a következő tábla mutatja.

    | Adatközpont Azure földrajzi régió | Szolgáltatási végpont URL-címe                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | USA keleti régiója                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | USA nyugati régiója                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | Észak-EU                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | Nyugat-EU                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

3. A **Környezet** mezőben adja meg az Elektronikus számlázási bővítmény környezetének nevét.
4. Válassza a **Mentés** gombot, majd zárja be az oldalt.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
