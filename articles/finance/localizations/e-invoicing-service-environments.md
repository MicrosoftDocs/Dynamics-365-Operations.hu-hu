---
title: Szolgáltatáskörnyezetek
description: Ez a cikk az elektronikus számlázás szolgáltatási környezeteit mutatja be, és bemutatja a beállításuk lépéseit.
author: dkalyuzh
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 8c743c5b2fbc7dcc3ae04fa4d7ca0e65de6c2507
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8901247"
---
# <a name="service-environments"></a>Szolgáltatáskörnyezetek

[!include [banner](../includes/banner.md)]

A szolgáltatási környezetek olyan logikai partíciók, amelyek a globalizációs funkciók és az elektronikus számlázási szolgáltatásban feldolgozott kapcsolódó dokumentumok támogatására vannak létrehozva. A biztonsági és digitális tanúsítványok, valamint a hozzáférési engedélyeket (vállalatirányítás) a szolgáltatási környezet szintjén kell konfigurálni.

Annyi szolgáltatási környezetet hozhat létre, amennyit csak szükséges. Minden létrehozott szolgáltatási környezet egymástól független. Javasoljuk, hogy hozzon létre legalább két szolgáltatási környezetet:

- Egy környezet fő fejlesztési és ellenőrzési célokra. Ez a környezet általában egy felhasználói elfogadási tesztelési (UAT) környezet.
- Egyetlen környezet termelési célokra. Ez a környezet általában termelési környezet.

Az ilyen típusú particionálás gondoskodik arról, hogy a termelésre való ugrás előtt érvényesítse és testre szabja az e-számlázási folyamatokat.

A szolgáltatási környezeteket a Regulatory Configuration Service (RCS) szolgáltatásban kell létrehozni és karbantartani. Ezután amikor készen állnak, közzé kell őket tenni az elektronikus számlázási szolgáltatásban. A közzétételi folyamat elküldi a szolgáltatási környezet paramétereit az RCS-példányról az elektronikus számlázási szolgáltatásba.

Ha nem fejeződik be a közzétételi folyamat, miután létrehozott egy új szolgáltatási környezetet, vagy módosította a meglévő szolgáltatási környezetet (Microsoft Azure például felhasználók hozzáadásával vagy törlésével), a módosítások nem lesznek hatályosak. Csak közzétett környezetek érhetők el a Dynamics 365 Pénzügy vagy a Dynamics 365 Supply Chain Management.

## <a name="service-environment-statuses"></a>Szolgáltatási környezet állapotai

A szolgáltatási környezetek az állapotukon keresztül kezelhetők. A környezetek állapotát a Szolgáltatáskörnyezet lapon **lehet** megtekinteni. A következő állapotok érhetők el:

- **Nincs közzétéve** – a környezetet létrehozták, de még nincs közzétéve.
- **Közzétéve** – a környezet közzé lett téve az elektronikus számlázási szolgáltatásban.
- **Módosítva** – a közzétett környezet attribútumai megváltoztak, de a módosítások még nincsenek közzétéve.

## <a name="users"></a>Felhasználók

Minden szolgáltatási környezetben fel kell sorolni azokat a felhasználókat, akik kapcsolódnak a Pénzügy és az Ellátásilánc-kezelés modulból származó elektronikus számlázáshoz.

## <a name="applications"></a>Pályázatok

Bizonyos helyzetekben előfordulhat, hogy a pénzügy- és az ellátásilánc-kezeléstől különböző alkalmazásoknak kapcsolódniuk kell az elektronikus számlázási szolgáltatáshoz, hogy elektronikus dokumentumokat küldjenek el további feldolgozásra, illetve beolvassák bizonyos adatokat (például a dokumentumok küldési állapotát). Ilyen helyzetekben az alkalmazást meg kell határozni az alkalmazások listájában. Ily módon hozzáférhet az elektronikus számlázási szolgáltatáshoz. A pályázatot alkalmazásként Azure Active Directory is Azure AD regisztrálni kell itt, és az objektum azonosítóját kell használni annak azonosítására. 

Mivel a Microsoft magas szintű biztonsági ellenőrzést igényel az elektronikus számlázási szolgáltatáshoz kapcsoló alkalmazások fölött, fel kell lépnie a Microsofttal <DGXRegulatoryservicesengineering@service.microsoft.com> a következő részletekkel:

- Azure AD-bérlő azonosítója
- Microsoft Dynamics Lifecycle Services (LCS) környezet azonosítója
- Alkalmazásazonosító (ügyfélazonosító)
- Objektumazonosító
- A pályázat indoklása és magas szintű leírása

A Microsoft kiértékeli az igénylést, és regisztrálja az alkalmazást a biztonsági nyilvántartásban, hogy az elektronikus számlázásokkal kezelni tudja az igénylést.

## <a name="number-sequences"></a>Számsorozatok

Ha az forgatókönyvekhez számsorozatok szükségesek (például fájlnevekben), használhatja az adott környezetben meghatározott számsorozatokat, de felhasználhatók akár a globalizációs funkcióknál, akár a globalizációs funkcióknál. Miután meghatározta a számsorozatot, felhasználhatja változókban és feldolgozási folyamatokban. Használatának nyomon követéséhez a **Számsorozatok** lapon keresse meg az Aktuális értéket **a** **Használatban** paraméterhez.

### <a name="working-with-number-sequences"></a>Számsorozatok
A Számsorozatok **lapon**: 

- Számsorozat **létrehozásához válassza az Új** lehetőséget. Adja meg a nevet és a leírást. 
- Ha **egy** számsorozatot törölni szeretne, válassza a Törlés lehetőséget, ha már nincs használva.
- A számsorozat módosításainak **közzétételéhez** nem szükséges a Közzététel gombra kattintva közzétennie a műveleteket. A frissítés automatikusan történik.

## <a name="create-a-key-vault-reference"></a>Kulcskulcs-létrehozási hivatkozás létrehozása

1. Jelentkezzen be a RCS-fiókba.
2. A **Globalizációs funkció** munkaterületen a **Környezet** szakaszban válassza ki az **Elektronikus számlázás bővítmény** csempét.
3. A Környezet **beállítása lapon**, a munkaablakban válassza a Szolgáltatáskörnyezetek **beállítást**.
4. A Szolgáltatási **környezetek** lapon, a munkaablakban válassza ki **a Kulcs paramétereit**.
5. A Kulcs **Paraméterei lapon** válassza az Új **gombra** a Kulcs– Referenciák hivatkozásának létrehozásához.
6. A Név **mezőben** adja meg a Kulcs – Mező hivatkozás nevét.
7. Adjon meg egy leírást a **Leírás** mezőben.
8. A Kulcs **– URI mezőben illessze be a Kulcs – URI azonosítót a kulcskulcs URI-éből** (`https://<your key vault>.vault.azure.net/`). A további tudnivalókat [lásd Az Azure-kulcs létrehozásáról az Azure-portálon](e-invoicing-create-azure-key-vault-azure-portal.md).
9. Válassza a **Mentés** lehetőséget.
    
## <a name="create-a-secret-for-the-storage-account-secret-token"></a>A tárolási fiók titkos jogkivonatának létrehozása

1. A Kulcs **– Paraméterek** lapon jelölje ki az előző eljárásban létrehozott Kulcs – Paraméterhivatkozást, **majd a Tanúsítványok szakaszban** válassza a Hozzáadás **lehetőséget**.
2. A **Név** mezőbe írja be a tárfiók titkos kódjának nevét. Ennek a névnek meg kell egyeznie a tárolási megosztott hozzáférési aláírást (SAS) tároló titkos kulcskulcs nevével. A további tudnivalókat [lásd Az Azure-tárfiók létrehozása az Azure-portálon](e-invoicing-create-azure-storage-account-azure-portal.md). 
3. Adjon meg egy leírást a **Leírás** mezőben.
4. A **Típus** mezőben válassza ki a **Titok** lehetőséget.
5. Válassza a **Mentés** lehetőséget.
    
## <a name="create-a-service-environment"></a>Szolgáltatási környezet létrehozása

1. A Szolgáltatáskörnyezet **lapon** válassza az Új **lehetőséget** szolgáltatási környezet létrehozásához.
2. A Név **mezőben** adja meg az elektronikus számlázási környezet nevét.
3. Adjon meg egy leírást a **Leírás** mezőben.
4. A **Tárterület SAS-token titkos kód** mezőben válassza ki azon tárfiók titkos kódjának a nevét, amely a tárfiókhoz való hozzáférés hitelesítéséhez szükséges.
5. A Felhasználók **szakaszban válassza** a Hozzáadás **lehetőséget** annak a felhasználónak a hozzáadásához, aki számára engedélyezett az elektronikus számlák elküldése a környezetben, és a tárolási fiókhoz való csatlakozás.
6. A **Felhasználói azonosító** mezőbe írja be a felhasználó aliasát. 
7. Az **E-mail** mezőbe írja be a feladó e-mail-címét.
8. Válassza a **Mentés** lehetőséget.
9. A munkaablakban a Közzététel **gombra kattintva** tegye közzé a környezetet az elektronikus számlázási szolgáltatásban. Győződjön meg róla, hogy **az Állapot** mező értékét Közzétett értékre **módosították**.
