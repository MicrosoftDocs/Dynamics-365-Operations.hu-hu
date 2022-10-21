---
title: A Számlarögzítés megoldás telepítése
description: Ez a cikk a Számlarögzítés megoldás telepítésének Microsoft Dynamics és a 365 Pénzügy alkalmazással való integrálásával kapcsolatban tartalmaz tájékoztatást.
author: sunfzam
ms.date: 09/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: zezhangzhao
ms.search.validFrom: 2022-09-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: d853e347c833345f34b65760fd7ee35cbb38c9a3
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690996"
---
# <a name="install-the-invoice-capture-solution"></a>A Számlarögzítés megoldás telepítése

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!IMPORTANT]
> Ha személyes előnézetben telepítette a megoldást, a folytatás előtt el kell távolítania a régi megoldást.

## <a name="prerequisites"></a>Előfeltételek

A Számlarögzítési megoldás csak a következő előfeltételek telepítése előtt telepíthető:

1. Alkalmazás regisztrálása és ügyféltitk hozzáadása a Microsofthoz Azure Active Directory (Azure AD) az Ön Azure-előfizetése alatt. A további tudnivalókat lásd [: Webalkalmazás regisztrálása az AAD szolgáltatásban](../../dev-itpro/data-entities/services-home-page.md#register-a-web-application-with-aad).

    > [!NOTE]
    > Jegyezze fel az alkalmazás **(ügyfél) azonosítóját**, **·** **az** ügyfél titkos azonosítóját és a bérlőazonosító értékét, mivel ezekre később szüksége lesz rájuk.

2. Regisztrálja az Azure-alkalmazást a Dynamics 365 Pénzügyi környezetben. További információ a Külső [pályázat regisztrálása oldalon található](../../dev-itpro/data-entities/services-home-page.md#register-your-external-application).

## <a name="install-and-set-up-the-solution"></a>A megoldás telepítése és beállítása

A Számlarögzítés megoldás AppSource [telepítéséhez kattintson a Dynamics 365 Számlarögzítés előnézeti verziójára, és válassza ki a hivatkozást](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics365-invoice-capture-preview?flightCodes=invoicecapture). A telepítés befejeződése után a kiválasztott környezetben telepített megoldást fogja látni a következőben Power Apps:

A következő lépések szerint hajtsa végre a telepítést.

1. Töltse le az [asszisztens megoldást](https://github.com/InvoiceCapture/InstallationTools/releases/download/latest/msdyn_InvoiceCaptureIntallationTools.zip), és adja meg a következő adatokat:

    - A kommunikáció és Microsoft Power Platform a pénzügyi környezet
    - A csatorna által Dataverse használt Office 365 kapcsolati hivatkozás és Outlook

2. Menjen Power Apps a környezetbe, és válassza az Importálás **megoldást**.
3. Válassza **a Tallózás** lehetőséget, válassza ki a letöltött asszisztens megoldáscsomagot, majd válassza a **Tovább gombra**.
4. Válassza ki **Következő** lehetőséget.
5. Rendeljen hozzá egy meglévő kapcsolatot, vagy hozzon létre egy újat az Új kapcsolat lehetőség **választásával**.
6. A csomag sikeres importálása után nyissa meg **a Dynamics 365 Számlarögzítés – telepítési eszközök eszközt**.
7. Futtassa a felhőfolyamot, hogy kapcsolatot létesítsen a Számlarögzítési megoldás és a Microsoft Power Platform Pénzügy között.
8. Válassza a **Futtatás** lehetőséget, és adja meg a következő paramétereket:

    - **Dynamics 365 Pénzügy URL-címe – annak a pénzügyi környezetnek az URL-címe**, amelybe integrálni szeretné az 5.
    - **Bérlőazonosító** – a pénzügyi környezet bérlőazonosítója.
    - **Ügyfél azonosítója** – a regisztrált Azure-alkalmazás azonosítója.
    - **Ügyféltitk** – az Azure-alkalmazás számára generált ügyféltitk.
