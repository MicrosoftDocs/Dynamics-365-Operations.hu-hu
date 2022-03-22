---
title: E-kereskedelmi webhely létrehozása
description: Ez a témakör bemutatja azokat a lépéseket és információkat, amelyek egy új e-kereskedelmi webhely létrehozásához szükségesek Dynamics 365 Commerce webhelyépítőben.
author: bicyclingfool
ms.date: 03/04/2022
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 5e451b1c95c3e26d1292e7b8300b62af43c81f2f
ms.sourcegitcommit: b80692c3521dad346c9cbec8ceeb9612e4e07d64
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2022
ms.locfileid: "8388211"
---
# <a name="create-an-e-commerce-site"></a>E-kereskedelmi webhely létrehozása

[!include [banner](includes/banner.md)]

Ez a témakör bemutatja azokat a lépéseket és információkat, amelyek egy új e-kereskedelmi webhely létrehozásához szükségesek Dynamics 365 Commerce webhelyépítőben.

A Dynamics 365 Commerce e-kereskedelmi lehetőségek licencelése esetén a webhelykészítő a saját webhely alapjaként használható kezdő webhellyel lesz biztosítva. Ha azonban a nulláról szeretné kezdeni, vagy egy második webhelyet szeretne létrehozni, akkor egy új helyet kell létrehoznia a webhelylétrehozási környezetben. 

## <a name="site-creation-prerequisites"></a>Webhely létrehozásának előfeltételei

A webhelyszerkesztő egy felhasználója számára az e-commerce rendszer rendszergazdáihoz rendelt Biztonsági csoportban szerepelnie kell egy Microsoft Azure Active Directory Azure AD() Azure AD felhasználói fióknak. További tájékoztatás: Új [e-commerce bérlő telepítése](deploy-ecommerce-site.md).

> [!NOTE]
> Azure AD Előfordulhat, hogy a vendég felhasználóknak eltérő hozzáférési engedélyei vannak a bérlőjéhez Azure AD. Még ha az Azure AD e-commerce rendszer rendszergazdáihoz rendelt biztonsági csoport is tagja, előfordulhat, hogy a Azure AD **vendég** felhasználónak módosítania kell a külső felhasználók engedélybeállítását ahhoz, hogy létrehoz egy e-commerce webhelyet a Commerce rendszerben. 

A külső felhasználók Azure AD **beállításainak módosításához** kövesse ezeket a lépéseket.

1. Az Azure-portálon lépjen a bérlőhöz Azure AD.
1. Menjen a Felhasználói **beállításokhoz \> : Külső felhasználók**, és válassza **a Külső együttműködési beállítások kezelése hivatkozást**. Nyílik a Külső **együttműködési beállítások** lap, ahol be lehet állítani a vendégfelhasználó hozzáférését, a vendég meghívási beállításait és az együttműködési korlátozásokat. 
1. A külső együttműködési beállítások a vállalat biztonsági házirendje szerint módosíthatók. 

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

## <a name="rename-your-site"></a>A webhely átnevezése

A webhelyet a következő lépések szerint nevezheti át a webhelyre a webhelyszerkesztőben.

1. A webhelylista nézet megnyitásához válassza **a Webhely kapcsolóját** a jobb felső sarokban, majd **válassza a Helyek kezelése lehetőséget**. 
1. Jelölje be az átnevezni kívánt webhely melletti jelölőnégyzetet, **majd válassza az Átnevezés** lehetőséget a parancssorban.
1. Adja meg **az új webhely nevét az Új webhely neve** párbeszédpanelen, majd válassza az **OK gombra.** A webhelylista frissülni fog, hogy a hely új neve megjelenik.

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]
