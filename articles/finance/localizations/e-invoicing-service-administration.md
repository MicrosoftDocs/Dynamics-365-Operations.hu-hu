---
title: Az elektronikus számlázási bővítmény adminisztrációs összetevői
description: Ez a témakör az Elektronikus számlázási bővítmény adminisztrációval kapcsolatos összetevőiről nyújt tájékoztatást.
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
ms.openlocfilehash: 70ef47dd45200a14c9d780f3c280c554d0e52ac3
ms.sourcegitcommit: 543772ee97efe215cf6f2ec6e092cc1568919f20
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/13/2021
ms.locfileid: "5592574"
---
# <a name="electronic-invoicing-add-on-administration-components"></a>Az elektronikus számlázási bővítmény adminisztrációs összetevői

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Ez a témakör az Elektronikus számlázási bővítmény adminisztrációval kapcsolatos összetevőiről nyújt tájékoztatást. Arról is tájékoztatást tartalmaz, hogyan kell konfigurálni az Elektronikus számlázási bővítmény szolgáltatást.

## <a name="azure"></a>Azure

A Microsoft Azure használatával létrehozhatja a kulcstartó és a tárfiók titkos kódjait. Ezután használja az Elektronikus számlázási bővítmény konfigurációjában használt titkos kódokat.

## <a name="lifecycle-services"></a>Lifecycle Services

A Microsoft Dynamics Lifecycle Services (LCS) használatával engedélyezze a bővítményt az LCS-telepítési projekt mikroszolgáltatásai számára.

> [!NOTE]
> A mikroszolgáltatások bővítményének LCS-szolgáltatásba való telepítéséhez legalább egy 2. szintű virtuális gép szükséges. A környezet tervezésével kapcsolatos további tudnivalókat lásd: [Környezet tervezése](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).
 

## <a name="regulatory-configuration-services"></a>Regulatory Configuration Services

A Dynamics 365 Regulatory Configuration Services (RCS) interfész segítségével konfigurálhatja az Elektronikus számlázási bővítményt. Az erőforrások, például a környezetek és az elektronikus számlázási funkciók létrehozása, karbantartása és tárolása az RCS-rendszerben történik. Amikor az erőforrások készen állnak, a rendszer közzéteszi őket az Elektronikus számlázási bővítményben.

Az RCS-regisztrációval kapcsolatban lásd: [Regulatory services](https://marketing.configure.global.dynamics.com/).

Az RCS-szel kapcsolatos további információért lásd a [Regulatory Configuration Services (RCS) szolgáltatás – Globalizációs funkciók](rcs-globalization-feature.md) részt.

### <a name="integration-with-the-electronic-invoicing-add-on"></a>Integráció az elektronikus számlázási bővítménnyel

Ahhoz, hogy az RCS használatával konfigurálni tudja az elektronikus számlákat, be kell állítania, hogy az RCS lehetővé tegye a kommunikációt az Elektronikus számlázási bővítménnyel. Ezt a konfigurációt az **Elektronikus jelentéskészítés paraméterei** oldal **Elektronikus számlázási bővítmény** lapján lehet végrehajtani.

#### <a name="service-endpoint"></a>Szolgáltatás végpontja

Az Elektronikus számlázásbővítmény számos Azure adatközpont földrajzi régióban elérhető. Az alábbi tábla felsorolja a régiónkénti elérhetőségeket.

| Azure adatközpont földrajzi régió |
|----------------------------|
| USA keleti régiója                    |
| USA nyugati régiója                    |
| Észak-EU                   |
| Nyugat-EU                    |

### <a name="service-environments"></a>Szolgáltatáskörnyezetek

A szolgáltatási környezetek olyan logikai partíciók, amelyek az Elektronikus számlázási bővítmény elektronikus számlázási funkcióinak végrehajtását támogatják. A biztonsági titkos kódokat és digitális tanúsítványokat, valamint a cégirányítást (azaz a hozzáférési engedélyeket) a szolgáltatási környezet szintjén kell konfigurálni.

Az ügyfelek annyi szolgáltatási környezetet hozhatnak létre, amennyit csak akarnak. Az ügyfél által létrehozott összes szolgáltatási környezetek egymástól függetlenek.

A szolgáltatási környezeteket RCS-ben kell létrehozni és karbantartani. Amikor a szolgáltatási környezetek készen állnak, a közzé kell őket tenni az Elektronikus számlázási bővítményben.

#### <a name="service-environment-status"></a>Szolgáltatási környezet állapota

A szolgáltatási környezeteket kezelése állapotokkal történik. Lehetséges választások:

- **Nincs közzétéve** – a környezetet létrehozták, de még nincs közzétéve.
- **Közzétéve** – a környezetet közzétették az Elektronikus számlázási bővítményben.
- **Módosítva** – a közzétett környezet attribútumai megváltoztak, de a módosítások még nincsenek közzétéve.

#### <a name="customer-secrets"></a>Vevő titkos kódjai

Az Elektronikus számlázásbővítmény szolgáltatás a felelős a vállalat tulajdonában lévő Azure-erőforrásokban lévő összes üzleti adatának tárolásáért. Ha biztosítani szeretné, hogy a szolgáltatás megfelelően működjön, és hogy az elektronikus számlázásbővítményhez szükséges, illetve az általa létrehozott összes üzleti adat csak a bővítmény számára legyen érhető el, akkor két fő Azure-erőforrást kell létrehoznia:

- Az elektronikus számlák tárolásához szükséges Azure tárfiókot (Blob-tároló)
- Egy Azure-kulcstartót a tanúsítványok és a tárolási fiók Uniform Resource Identifier (URI) tárolásához

> [!NOTE]
> A dedikált kulcstartót és a vevői tárfiókot kifejezetten az Elektronikus számlázásbővítménnyel történő használatra kell felosztani.

További információért lásd az [Azure tárfiók és kulcstartó létrehozása](e-invoicing-create-azure-storage-account-key-vault.md) lehetőséget.

#### <a name="users"></a>Felhasználók

Minden szolgáltatási környezetben fel kell sorolni azokat a felhasználókat, akik csatlakozni tudnak a Dynamics 365 Finance és a Dynamics 365 Supply Chain Management modulból az Elektronikus számlázási bővítményhez.

#### <a name="publication"></a>Közzététel

A szolgáltatási környezeteket használat előtt közzé kell őket tenni az Elektronikus számlázási bővítményben. A Finance and Supply Chain Management modul csak közzétett környezeteket tud elérni. Ezenkívül a szolgáltatási környezetet közzé kell tenni, mielőtt az attribútumainak frissítése hatályba lép az elektronikus számlázási szolgáltatáson.

### <a name="connected-applications"></a>Csatlakoztatott alkalmazások

A csatlakoztatott alkalmazások Finance and Supply Chain Management modul példányai, amelyeket az RCS-rendszer segítségével érdemes elérni. Az alkalmazás URL-címe és bérlője mellett a csatlakoztatott alkalmazás tartalmazza azokat a hitelesítő adatokat, amelyek alapján az RCS csatlakozhat a környezethez.

A csatlakoztatott alkalmazásokon keresztül a Finance and Supply Chain Management modul elektronikus számlázási szolgáltatásának egy részét konfigurálni lehet, hogy a teljes elektronikus számlázási funkció működjön.

## <a name="finance-and-supply-chain-management"></a>Finance and Supply Chain Management

### <a name="integration-with-electronic-invoicing-add-on"></a>Integráció az Elektronikus számlázási bővítménnyel

Ahhoz, hogy a Finance and Supply Chain Management modul segítségével elektronikus számlákat tudjon kiállítani az Elektronikus számlázási bővítményen keresztül, a bővítményt úgy kell konfigurálni, hogy lehetővé tegye a szolgáltatással való kommunikációt.

#### <a name="electronic-invoicing-add-on-integration-feature"></a>Az Elektronikus számlázási bővítmény integrációs funkciója

A Finance and Supply Chain Management modul és az Elektronikus számlázási bővítmény közötti kommunikáció engedélyezéséhez be kell kapcsolnia az **Elektronikus számlázási bővítmény integrációja** funkciót a **Funkciókezelés** munkaterületen.

#### <a name="service-endpoint"></a>Szolgáltatás végpontja

A szolgáltatásvégpont az az URL-cím, ahol az Elektronikus számlázási bővítmény található. Ahhoz, hogy a Finance and Supply Chain Management modul segítségével elektronikus számlákat tudjon kiállítani a szolgáltatásvégpontot úgy kell konfigurálni, hogy lehetővé tegye a szolgáltatással való kommunikációt.

A szolgáltatásvégpont beállításához lépjen a **Szervezeti adminisztráció \> Beállítás \> Elektronikus dokumentum paramétere** lehetőségre, majd a **Benyújtási szolgáltatások** oldal **Elektronikus számlázási bővítmény URL-címe** mezőben adja meg az URL-címet a **Szolgáltatávégpont** szakaszban ismertetett módon.

#### <a name="environments"></a>Környezetek

A Finance and Supply Chain Management modulban megadott környezetnév annak a környezetnek a nevére vonatkozik, amelyet az RCS-ben hoztak létre, és az Elektronikus számlázási bővítményben tettek közzé.

A környezetet be kell állítani az **Elektronikus dokumentum paraméter** oldal **Benyújtási szolgáltatások** lapján, hogy minden elektronikus számla kiadási kérése tartalmazza azt a környezetet, ahol az Elektronikus számlázási bővítmény eldöntheti, hogy melyik elektronikus számlázási funkciónak kell feldolgoznia a kérést.

## <a name="additional-resources"></a>További erőforrások

- [Elektronikus számlák konfigurálása az RCS szolgáltatásban](e-invoicing-configuration-rcs.md)
- [Elektronikus számlák kibocstása a Finance és Supply Chain Management szolgáltatásokban](e-invoicing-issuing-electronic-invoices-finance-supply-chain-management.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
