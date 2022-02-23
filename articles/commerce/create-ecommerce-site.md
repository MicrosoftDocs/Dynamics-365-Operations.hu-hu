---
title: E-kereskedelmi webhely létrehozása
description: Ez a témakör bemutatja azokat a lépéseket és információkat, amelyek egy új e-kereskedelmi webhely létrehozásához szükségesek Dynamics 365 Commerce webhelyépítőben.
author: bicyclingfool
manager: AnnBe
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: cf084f90d203d84c91ddf7c0d963780b895ef23d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4963035"
---
# <a name="create-an-e-commerce-site"></a>E-kereskedelmi webhely létrehozása

[!include [banner](includes/banner.md)]

Ez a témakör bemutatja azokat a lépéseket és információkat, amelyek egy új e-kereskedelmi webhely létrehozásához szükségesek Dynamics 365 Commerce webhelyépítőben.

A Dynamics 365 Commerce e-kereskedelmi lehetőségek licencelése esetén a webhelykészítő a saját webhely alapjaként használható kezdő webhellyel lesz biztosítva. Ha azonban a nulláról szeretné kezdeni, vagy egy második webhelyet szeretne létrehozni, akkor egy új helyet kell létrehoznia a webhelylétrehozási környezetben. 

## <a name="set-up-your-site"></a>A webhely beállítása

A webhelyének beállításához tegye a következőket.

1. A webhelyépítő környezet megnyitása. A Microsoft Lifecycle Services (LCS) alkalmazásban találja meg a webhelyépítőt a környezeti funkciók oldalon a Commerce alkalmazáshoz.
1. A webhely-létrehozási környezet kezdőlapján válassza az **Új webhely** elemet.
1. Az **Új webhely** párbeszédpanelen adja meg a következő adatokat.

| Mező                               | Leírás |
|-------------------------------------|-------------|
| Webhely neve                           | Adja meg, hogy milyen megjelenítési nevet kell használni a webhely számára a webhely-létrehozási környezetben. Ez a név csak a szerzői környezetben látható, és nem jelenik meg a vevők számára. |
| A webhely rendszergazdájának biztonsági csoportja | A webhelyen webhely-rendszergazdai szerepkörrel rendelkező felhasználók kezelésére szolgáló Microsoft Azure Active Directory (Azure AD) biztonsági szerepkört adja meg. |
| Alapértelmezett csatorna (üzemi egység száma) | Válassza ki azt az online áruházat, amelynek a webhely a webes kirakataként fog szolgálni. Ha azt szeretné, hogy az e-kereskedelmi webhely több online üzletet támogasson, akkor a webhely beállítása után a **Webhely beállításai** között társítania kell az üzleteket a webhelyhez. |
| Alapértelmezett nyelv                            | Adja meg az online áruház és piac alapértelmezett nyelvét. Az online áruházak több nyelvet is támogathatnak. Ha azt szeretné, hogy a program több nyelvet támogasson ehhez az online áruházhoz vagy egy másik online áruházhoz, akkor a webhely beállítását követően a **Webhely beállításai** között konfigurálhatja ezt a támogatást.  |
| Tartomány                              | Válassza ki annak a tartománynak a nevét, amely ennek az online áruháznak a tartományaként fog szolgálni. Ha nem konfigurált tartományokat az LCS-ben, akkor ezt a mezőt üresen hagyhatja. Miután a tartományt az LCS-ben konfigurálta, hozzá kell adnia az online áruházhoz a **Webhely beállításai** között.  |
| Útvonal                              | Amikor a webhely egynél több nyelvet támogat egy adott tartománynévhez, használja az elérési út mezőt, és hozzon létre egy egyedi webhely-URL-címet ahhoz a tartomány és nyelv kombinációhoz. Ha az **Alapértelmezett nyelv** mezőben megadott nyelv az egyetlen olyan nyelv, amelyet ebben a tartományban támogatni fog, vagy továbbra is az alapértelmezett nyelv lesz, miután a webhelyet további nyelvekre lokalizálta, azt ajánljuk, hogy hagyja üresen ezt a mezőt. |


Miután létrehozta a webhelyet, a **Termékek** lap kiválasztásával ellenőrizheti, hogy az online áruházhoz van-e társítva. Az online áruházhoz rendelt termékek választékát kell látnia. A lap bal felső részén található legördülő menü segítségével is megnyithatja a hozzárendelt termékeket kategóriánként.

## <a name="additional-resources"></a>További erőforrások

[Tartománynév konfigurálása](configure-your-domain-name.md)

[Új e-kereskedelmi bérlő telepítése](deploy-ecommerce-site.md)

[Dynamics 365 Commerce webhely társítása online csatornával](associate-site-online-store.md)

[Robots.txt fájlok kezelése](manage-robots-txt-files.md)

[URL-átirányítások tömeges feltöltése](upload-bulk-redirects.md)

[B2C-bérlő beállítása a Commerce-ben](set-up-B2C-tenant.md)

[Felhasználói bejelentkezéshez használt egyéni lapok beállítása](custom-pages-user-logins.md)

[Több B2C-bérlő konfigurálása egy Commerce környezetben](configure-multi-B2C-tenants.md)

[Tartalomkézbesítési hálózat (CDN) támogatásának hozzáadása](add-cdn-support.md)

[Helyalapú áruházészlelés engedélyezése](enable-store-detection.md)
