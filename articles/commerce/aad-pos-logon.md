---
title: Azure Active Directory-hitelesítés engedélyezése a pénztári bejelentkezéshez
description: Ez a témakör azt mutatja be, hogyan lehet konfigurálni a Microsoft Dynamics 365 Commerce pénztár (POS) bejelentkezési élményét, hogy a Azure Active Directory-hitelesítést használja.
author: boycezhu
manager: annbe
ms.date: 07/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.search.region: global
ms.author: boycezhu
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: ccb2d62b09153d03b064d9661227f3499d67bca2
ms.sourcegitcommit: dc1dcd0ccc40be5d45701114fa8c952c13488344
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/30/2020
ms.locfileid: "3641033"
---
# <a name="enable-azure-active-directory-authentication-for-pos-sign-in"></a>Azure Active Directory-hitelesítés engedélyezése a pénztári bejelentkezéshez
[!include [banner](includes/banner.md)]


A Microsoft Dynamics 365 Commerce szolgáltatást használó számos felhasználó szintén használ felhőalapú Microsoft szolgáltatásokat, és lehet, hogy Azure Active Directory (Azure AD) szolgáltatással kezelik az adott szolgáltatások felhasználói hitelesítő adatait. Ezekben az esetekben előfordulhat, hogy a vevők ugyanazt az Azure AD fiókot szeretnének használni több alkalmazásnál. Ez a témakör azt mutatja be, hogyan lehet konfigurálni a Commerce pénztár (POS) bejelentkezési élményét, hogy a Azure AD-hitelesítést használja.

## <a name="configure-azure-ad-authentication"></a>Azure AD-hitelesítés konfigurálása

Ahhoz, hogy az Azure AD az üzlet pénztári bejelentkezésének hitelesítési módszere legyen, konfigurálnia kell az üzlet funkcióprofiljának beállításait, majd alkalmazni a beállítást a pénztárkliensre.

A funkcióprofil konfigurálásához az alábbi lépéseket hajtsa végre.

1. Ugorjon a következő elemre: **Retail és Commerce** \> **Csatorna beállítása** \> **Pénztárbeállítás** \> **Pénztárprofilok** \> **Funkcióprofilok**.
1. Válassza ki a módosítani kívánt funkcióprofilt.
1. A **Funkciók**gyorslapon, a **Pénztár személyzeti bejelentkezés** szakaszban módosítsa a **Bejelentkezés hitelesítési módja** mező értékét **Személyzeti aozonosító és jelszó** értékről **Azure Active Directory** értékre.

Alapértelmezés szerint az összes funkcióprofil **személyzeti azonosítót és jelszót** használ a pénztár hitelesítési módszerként. Ennek megfelelően módosítania kell **Bejelentkezés hitelesítési módja** mező értékét, ha Azure AD-t szeretne használni. A módosítás hatással van minden olyan kiskereskedelmi üzletre, amely a kiválasztott funkcióprofilhoz van társítva.

A beállítások alkalmazásához a pénztárkliensre kövesse ezeket a lépéseket.

1. Ugorjon a **Kiskereskedelem és kereskedelem** \> **Kiskereskedelem és kereskedelem informatika** \> **Elosztási ütemezés** pontra.
1. Futtassa a **1070** (**Csatornakonfiguráció**) elosztási ütemezést.

> [!NOTE]
> Azure AD-hitelesítéshez internetkapcsolat szükséges. Nem működik, ha a pénztár offline módban van.
> 
> Jelenleg a **Vezetői felülbírálás** funkció nem támogatja a Azure AD-t hitelesítési módszerként. Még akkor is szükség van egy kezelői azonosítóra és jelszóra és jelszóra, ha a POS-bejelentkezés hitelesítési módszerének Azure AD van beállítva.

## <a name="associate-an-azure-ad-account-with-a-worker"></a>Azure AD-fiók társítása dolgozóval

Ahhoz, hogy egy üzlet dolgozója Azure AD-fiókkal jelentkezhessen be a pénztáralkalmazásba, az Azure AD-fiókot az adott dolgozóhoz kell társítani.

Az Azure AD-fiók dolgozóhoz való társításához kövesse az alábbi lépéseket.

1. Nyissa meg a következőt: **Kiskereskedelem és kereskedelem** \> **Alkalmazottak** \> **Dolgozók**.
1. A dolgozó részletes lapjának megnyitása.
1. A műveleti ablaktáblán a **Kereskedelem** lapon a **Külső identitás** csoportban válassza a **Meglévő identitás társítása** lehetőséget.
1. A **Meglévő külső identitás használata** párbeszédpanelen válassza a **Keresés e-maillel** parancsot, adja meg Azure AD-e-mail címet, majd válassza a **Keresés** lehetőséget.
1. Válassza ki a visszaadott Azure AD-fiókot, majd az **OK** elemet.

A rendszer kitölti az **Alias**, **UPN**, **Külső részazonosító** mezőket a dolgozó adatainak oldalának **Commerce** oldalán.

> [!NOTE]
> A dolgozói rekord frissítése után – például ha egy új Azure AD számlát társítanak hozzá – megváltozik egy jelszó vagy frissül egy dolgozói címjegyzék, javasoljuk, hogy futtassa az **1060** (**Személyzet**) elosztási ütemezést a legfrissebb személyzeti adatok csatornához történő szinkronizálásához. Így a pénztár alkalmazás be tudja olvasni a megfelelő adatokat a felhasználó hitelesítéséhez és a hitelesítés ellenőrzéséhez.

## <a name="additional-resources"></a>További erőforrások

[Kiterjesztett bejelentkezési funkció beállítása az MPOS-hez és a Cloud POS-hoz](extended-logon.md)

[Retail funkcióprofil létrehozása](retail-functionality-profile.md)

[ Dolgozó konfigurálása](https://docs.microsoft.com/dynamics365/commerce/tasks/worker)
