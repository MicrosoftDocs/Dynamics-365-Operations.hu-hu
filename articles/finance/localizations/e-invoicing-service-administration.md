---
title: Elektronikus számlázás adminisztrációs összetevői
description: Ez a témakör az Elektronikus számlázás adminisztrációval kapcsolatos összetevőiről nyújt tájékoztatást.
author: gionoder
ms.date: 03/29/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 2e859875e124796e49000cd5ea94cfb75ecd768a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840028"
---
# <a name="electronic-invoicing-administration-components"></a>Elektronikus számlázás adminisztrációs összetevői

[!include [banner](../includes/banner.md)]


Ez a témakör az Elektronikus számlázás adminisztrációval kapcsolatos összetevőiről nyújt tájékoztatást. Arról is tájékoztatást tartalmaz, hogyan kell konfigurálni az Elektronikus számlázás szolgáltatást.

## <a name="azure"></a>Azure

A Microsoft Azure használatával létrehozhatja a kulcstartó és a tárfiók titkos kódjait. Ezután használja az Elektronikus számlázás konfigurációjában használt titkos kódokat.

## <a name="lifecycle-services"></a>Lifecycle Services

A Microsoft Dynamics Lifecycle Services (LCS) használatával engedélyezze a mikroszolgáltatást az LCS-telepítési projekt mikroszolgáltatásai számára.

> [!NOTE]
> A mikroszolgáltatások LCS-szolgáltatásba való telepítéséhez legalább egy 2. szintű virtuális gép szükséges. A környezet tervezésével kapcsolatos további tudnivalókat lásd: [Környezet tervezése](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).
 

## <a name="regulatory-configuration-services"></a>Regulatory Configuration Services

A Dynamics 365 Regulatory Configuration Services (RCS) interfész segítségével konfigurálhatja az Elektronikus számlázást. Az erőforrások, például a környezetek és az elektronikus számlázási funkciók létrehozása, karbantartása és tárolása az RCS-rendszerben történik. Amikor az erőforrások készen állnak, a rendszer közzéteszi őket az Elektronikus számlázásban.

Az RCS-regisztrációval kapcsolatban lásd: [Regulatory services](https://marketing.configure.global.dynamics.com/).

Az RCS-szel kapcsolatos további információért lásd a [Regulatory Configuration Services (RCS) szolgáltatás – Globalizációs funkciók](rcs-globalization-feature.md) részt.

### <a name="integration-with-electronic-invoicing"></a>Integráció az Elektronikus számlázással 

Ahhoz, hogy az RCS használatával konfigurálni tudja az elektronikus számlákat, be kell állítania, hogy az RCS lehetővé tegye a kommunikációt az Elektronikus számlázással. Ezt a konfigurációt az **Elektronikus jelentéskészítés paraméterei** oldal **Elektronikus számlázás** lapján lehet végrehajtani.

#### <a name="service-endpoint"></a>Szolgáltatás végpontja

Az Elektronikus számlázás számos Azure adatközpont földrajzi régióban elérhető. Az alábbi tábla felsorolja a régiónkénti elérhetőségeket.

| Azure adatközpont földrajzi régió |
|----------------------------|
| USA keleti régiója                    |
| USA nyugati régiója                    |
| Észak-EU                   |
| Nyugat-EU                    |

### <a name="service-environments"></a>Szolgáltatáskörnyezetek

A szolgáltatási környezetek olyan logikai partíciók, amelyek az Elektronikus számlázás elektronikus számlázási funkcióinak végrehajtását támogatják. A biztonsági titkos kódokat és digitális tanúsítványokat, valamint a cégirányítást (azaz a hozzáférési engedélyeket) a szolgáltatási környezet szintjén kell konfigurálni.

Az ügyfelek annyi szolgáltatási környezetet hozhatnak létre, amennyit csak akarnak. Az ügyfél által létrehozott összes szolgáltatási környezetek egymástól függetlenek.

A szolgáltatási környezeteket RCS-ben kell létrehozni és karbantartani. Amikor a szolgáltatási környezetek készen állnak, a közzé kell őket tenni az Elektronikus számlázásban.

#### <a name="service-environment-status"></a>Szolgáltatási környezet állapota

A szolgáltatási környezeteket kezelése állapotokkal történik. Lehetséges választások:

- **Nincs közzétéve** – a környezetet létrehozták, de még nincs közzétéve.
- **Közzétéve** – a környezetet közzétették az Elektronikus számlázásban.
- **Módosítva** – a közzétett környezet attribútumai megváltoztak, de a módosítások még nincsenek közzétéve.

#### <a name="customer-secrets"></a>Vevő titkos kódjai

Az Elektronikus számlázási szolgáltatás a felelős a vállalat tulajdonában lévő Azure-erőforrásokban lévő összes üzleti adatának tárolásáért. Ha biztosítani szeretné, hogy a szolgáltatás megfelelően működjön, és hogy az elektronikus számlázáshoz szükséges, illetve az általa létrehozott összes üzleti adat megfelelően elérhet legyen, akkor két fő Azure-erőforrást kell létrehoznia:

- Az elektronikus számlák tárolásához szükséges Azure tárfiókot (Blob-tároló)
- Egy Azure-kulcstartót a tanúsítványok és a tárolási fiók Uniform Resource Identifier (URI) tárolásához

> [!NOTE]
> A dedikált kulcstartót és a vevői tárfiókot kifejezetten az Elektronikus számlázással történő használatra kell felosztani.

További információért lásd az [Azure tárfiók és kulcstartó létrehozása](e-invoicing-create-azure-storage-account-key-vault.md) lehetőséget.

#### <a name="users"></a>Felhasználók

Minden szolgáltatási környezetben fel kell sorolni azokat a felhasználókat, akik csatlakozni tudnak a Dynamics 365 Finance és a Dynamics 365 Supply Chain Management modulból az Elektronikus számlázáshoz.

#### <a name="publication"></a>Közzététel

A szolgáltatási környezeteket használat előtt közzé kell őket tenni az Elektronikus számlázásban. A Finance and Supply Chain Management modul csak közzétett környezeteket tud elérni. Ezenkívül a szolgáltatási környezetet közzé kell tenni, mielőtt az attribútumainak frissítése hatályba lép az elektronikus számlázási szolgáltatáson.

### <a name="connected-applications"></a>Csatlakoztatott alkalmazások

A csatlakoztatott alkalmazások Finance and Supply Chain Management modul példányai, amelyeket az RCS-rendszer segítségével érdemes elérni. Az alkalmazás URL-címe és bérlője mellett a csatlakoztatott alkalmazás tartalmazza azokat a hitelesítő adatokat, amelyek alapján az RCS csatlakozhat a környezethez.

A csatlakoztatott alkalmazásokon keresztül a Finance and Supply Chain Management modul elektronikus számlázási szolgáltatásának egy részét konfigurálni lehet, hogy a teljes elektronikus számlázási funkció működjön.

## <a name="finance-and-supply-chain-management"></a>Finance and Supply Chain Management

### <a name="integration-with-electronic-invoicing"></a>Integráció az Elektronikus számlázással

Ahhoz, hogy a Finance and Supply Chain Management modul segítségével elektronikus számlákat tudjon kiállítani az Elektronikus számlázáson keresztül, a bővítményt úgy kell konfigurálni, hogy lehetővé tegye a szolgáltatással való kommunikációt.

#### <a name="electronic-invoicing-integration-feature"></a>Az Elektronikus számlázás integrációs funkciója

A Finance and Supply Chain Management modul és az Elektronikus számlázási bővítmény közötti kommunikáció engedélyezéséhez be kell kapcsolnia az **Elektronikus számlázás integrációja** funkciót a **Funkciókezelés** munkaterületen.

#### <a name="service-endpoint"></a>Szolgáltatás végpontja

A szolgáltatásvégpont az az URL-cím, ahol az Elektronikus számlázás található. Ahhoz, hogy a Finance and Supply Chain Management modul segítségével elektronikus számlákat tudjon kiállítani a szolgáltatásvégpontot úgy kell konfigurálni, hogy lehetővé tegye a szolgáltatással való kommunikációt.

A szolgáltatásvégpont beállításához lépjen a **Szervezeti adminisztráció \> Beállítás \> Elektronikus dokumentum paramétere** lehetőségre, majd a **Benyújtási szolgáltatások** oldal **Elektronikus számlázás URL-címe** mezőben adja meg az URL-címet a **Szolgáltatávégpont** szakaszban ismertetett módon.

#### <a name="environments"></a>Környezetek

A Finance and Supply Chain Management modulban megadott környezetnév annak a környezetnek a nevére vonatkozik, amelyet az RCS-ben hoztak létre, és az Elektronikus számlázásban tettek közzé.

A környezetet be kell állítani az **Elektronikus dokumentum paraméter** oldal **Benyújtási szolgáltatások** lapján, hogy minden elektronikus számla kiadási kérése tartalmazza azt a környezetet, ahol az Elektronikus számlázás eldöntheti, hogy melyik elektronikus számlázási funkciónak kell feldolgoznia a kérést.

## <a name="additional-resources"></a>További erőforrások

- [Elektronikus számlák konfigurálása az RCS szolgáltatásban](e-invoicing-configuration-rcs.md)
- [Elektronikus számlák kibocstása a Finance és Supply Chain Management szolgáltatásokban](e-invoicing-issuing-electronic-invoices-finance-supply-chain-management.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
