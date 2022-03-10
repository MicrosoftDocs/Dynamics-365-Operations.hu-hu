---
title: Leemlott bevásárlókocsik észlelése és értesítések küldése a vevőknek
description: Ez a témakör azt írja le, Microsoft Dynamics 365 Commerce hogyan lehet testreszabni az leomlott bevásárlókocsis mintaalkalmazást az értesített bevásárlókocsik észlelése és a vevőknek szóló emlékeztető e-mail értesítések küldése érdekében.
author: bicyclingfool
ms.date: 02/25/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 82848f1ff068cea0adfc6ec1b33fc4bb035f78dc
ms.sourcegitcommit: 374bbdde90fc9a68c0799158a50409bfbe8ca64e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/25/2022
ms.locfileid: "8353373"
---
# <a name="detect-abandoned-carts-and-send-notifications-to-customers"></a>Leemlott bevásárlókocsik észlelése és értesítések küldése a vevőknek

[!include [banner](../includes/banner.md)]

Ez a témakör azt írja le, Microsoft Dynamics 365 Commerce hogyan lehet testreszabni az leomlott bevásárlókocsis mintaalkalmazást az értesített bevásárlókocsik észlelése és a vevőknek szóló emlékeztető e-mail értesítések küldése érdekében.

Fontos lehetőség a bevétel helyreállítása és Dynamics 365 Commerce a vevők megtartása az üreskocsis értesítésekkel. A Commerce rendszer által elhagyott cart Connector mintaalkalmazás testreszabásával a kiskereskedők hozzáférnek a Retail Server olyan bevásárlókocsiihoz, amelyek nem módosultak a kiskereskedők által egy időablakban. Ezek a bevásárlókocsik ezután beolvashatók, kiegészíthetők a termék- és vevőadatokkal, és továbbküldhetők egy külső e-mail marketingszolgáltatónak, amely e-mail értesítéseket generálhat, és elküldheti a vevőknek.

Az összeomlott bevásárlókocsiba küldött e-mail értesítés, amely a vevőket fogadja, a következő adatokat tartalmazhatja:

- A vevő vezetékneve.
- A vevő vezetékneve.
- A vevő e-mail címe.
- Egy URL-cím, amely a vevőt a bevásárlókocsiba adja.
- A tranzakció pénzneme.
- A vevő bevásárlókocsiában található termékek listája. Az egyes termékekhez a következő információk tartoznak:

    - A termék megjelenítendő neve
    - A termékazonosító (a termékleírások oldalának URL-címének összeállításához használatos)
    - Olyan termékkép, amely automatikusan átméretezhetők a különböző nézetablak-méretekkel
    - Helyettesítő szöveg a termékképhez
    - A termék egységára

## <a name="abandoned-cart-connector-sample"></a>A bevásárlókocsi csatlakoztatójához kapcsolódó minta

A Microsoft a Retail szoftverfejlesztői csomagján (SDK) keresztül rendelkezésre áll egy csatlakoztatómodell, amellyel lekérdezhetők és elküldhetők egy külső e-mail marketingszolgáltatónak. Ez a csatlakoztató kezeli a kapcsolatot a Retail Server kiszolgálóval, az Azure kulcshoz, a biztonságért, a bevásárlókocsik beolvasásának ütemezését kezeli egy adott időablakban, majd beolvassa a rendelési és a termékadatokat. Ezenkívül minta megvalósítást biztosít egy külső e-mail marketingszolgáltatóval való integrációhoz. A csatlakoztató úgy épül fel, hogy a [dobozon kívüli emarsyokkal](https://emarsys.com) kommunikáljon. Ugyanakkor egyszerűen testreszabható más megoldásokkal, például a Constant Contact, a Mailamp és a SendGrid megoldással való integrációra.

Az alábbi ábra az összeeső bevásárlókocsi csatlakoztató mintaalkalmazásának összetevőit mutatja be.

![Az összeeső bevásárlókocsi csatlakoztató mintaalkalmazásának összetevői](media/AbandonedCartConnector.png)

> [!IMPORTANT]
> Egyes régiókban szükség van arra, hogy a vevők választva át tudják-e küldeni a bevásárlókocsijuk adatait egy e-mail marketingszolgáltatónak, vagy kérhetik az adatok eltávolítását. A Microsoft azonban nem adja meg ezeket a beállításokat az ügyfelek számára. Ezért ha üzleti kapcsolatban áll a számukra előírt régiókban, meg kell adnia a vevői preferenciák nyomon követéséhez szükséges infrastruktúrát és testreszabásokat, és ezek alapján meg kell akadályozni, hogy a vevő adatai át tudjanak adni az e-mail platformra. A vevő kérése alapján meg kell határoznia a vevőadatoknak az e-mail marketingszolgáltatótól történő végleges kiürítését is.

## <a name="obtain-the-code-sample"></a>A kód minta beszerzése

Az a bevásárlókocsi-csatlakoztató mintaalkalmazás, amely a 10.0.16-os verziónak megfelelő Retail SDK készletbe tartozik. A kód a **\\ RetailSDKCodeSampleExtensionsRetailServerExtensions.ServerExtensions.AtlanCartSample\\\\\\\\ alatt található.** A Retail SDK készletről és annak beszerzéséről a [Retail szoftverfejlesztői csomag (SDK) nyújt további tájékoztatást](retail-sdk/retail-sdk-overview.md).

> [!NOTE]
> Bár a mintakódot először a 10.0.16-os verzióban készítették el, kompatibilis a Retail Server 10.0.13-as verziójával és későbbi buildekkel.

## <a name="prerequisites-and-dependencies"></a>Előfeltételek és függőségek

Az összeeső bevásárlókocsi csatlakoztató mintakódja csak akkor telepíthető és konfigurálható, ha teljesülnek a következő előfeltételek.

### <a name="access-to-commerce-resources"></a>Hozzáférés a Commerce-erőforrásokhoz

Az elhagyó cart Connector alkalmazás konfigurálása és telepítése a következő Commerce-erőforrásokhoz szükséges:

- Rendszergazdai hozzáférés a Commerce Headquarters for Your Environment alkalmazáshoz
- Hozzáférés a környezet Microsoft Dynamics Lifecycle Services (LCS) projektjéhez

### <a name="azure-cosmos-db"></a>Azure Cosmos DB

Az autóskocsi csatlakoztató alkalmazás az Azure Cosmos DB segítségével követi nyomon a korábban lekért bevásárlókocsikhoz kapcsolódó adatokat és időbélyegzőket. Az Azure segítségével Cosmos DB továbbra is megőrzheti ezeket az adatokat, vagy egy másik adattárolási beállítással való integrációra testreszabhatja a kód mintakódját. Az Azure szolgáltatásról az Üdvözli Cosmos DB a [Azure Cosmos DB](/azure/cosmos-db/introduction) szolgáltatásban !

Az Azure használata esetén Cosmos DB a minta futtatása előtt teljesülnie kell a következő előfeltételeknek:

- Aktív Azure-fiókkal kell lennie Cosmos DB. Ha nem ad meg fiókot, lásd Adatbázisfiók [létrehozása](/azure/cosmos-db/create-sql-api-dotnet#create-a-database-account).
- Az Azure-fiók **kulcsértékeiből be kellolvasnia az URI** **és** az ELSŐDLEGES KULCS (**vagy** MÁSODLAGOS KULCS) **·** Cosmos DB értékeit az Azure-portálon. A végpontok és az Azure-fiók Cosmos DB [kulcsinformációinak beolvasását a hozzáférési kulcsok és jelszavak megtekintése,](/azure/cosmos-db/manage-account#keys) másolása és újragenerálása tartalmazza.

### <a name="azure-key-vault"></a>Azure Key Vault

Az összeomlott cart connector alkalmazás a Key Cart Connector segítségével tárolja a biztonságos hozzáférést igénylő különféle összetevők nevét és adatbázisát.

A következő lépések szerint állíthatja be a kulcskulcsokat.

1. Kövesse az Azure Veremközpont [kulcsának kezelése a portál használatával útmutatót](/azure-stack/user/azure-stack-key-vault-manage-portal?view=azs-2002&preserve-view=true).
2. Létrehozás a következő információk alapján:

    - Az Emarsys alkalmazásprogramozási felület (API) felhasználóneve és API-titka
    - Leomlott kosár alkalmazásazonosítója és titkos azonosítója

Az a bevásárlókocsi-csatlakoztató mintakódja, amely Az Azure alapértelmezett hitelesítő adatait használja a kulcs elérése érdekében. Lista- **és** olvasási **engedélyeket** kell adnia ahhoz az identitáshoz, amely a Kulcsok eléréséhez használni fog.

Az Azure alapértelmezett hitelesítő adataival kapcsolatos további tudnivalókat [lásd DefaultAzureCredential Class](/dotnet/api/azure.identity.defaultazurecredential?view=azure-dotnet&preserve-view=true).

## <a name="create-an-abandoned-cart-connector-sample-app-application-id-for-the-azure-ad-tenant"></a>Leomlott bevásárlókocsi csatlakoztató mintaalkalmazás-azonosítójának létrehozása a bérlőhöz Azure AD

A (AD) bérlőhöz egy leomlott bevásárlókocsi csatlakoztató mintaalkalmazás-azonosítóját Azure Active Directory kell létrehozni. Az alkalmazásazonosítók létrehozásáról az [erőforrások elérésére használható alkalmazás és szolgáltatásnév létrehozásához használja a Azure AD portált](/azure/active-directory/develop/howto-create-service-principal-portal).

## <a name="add-the-abandoned-cart-connector-sample-app-application-id-to-the-allow-list-for-the-retail-server-api"></a>Az összeomlott bevásárlókocsi csatlakoztató mintaalkalmazás-azonosítójának hozzáadása a Retail Server API-ja allow listához

Ezután fel kell vennie az önkiszolgálókiszolgálói mintaalkalmazás-azonosítót a Retail Server API-ja allow listájára. Az Alkalmazásazonosítók Azure-beli engedélyezések listájához való hozzáadásáról a Retail [Server szolgáltatás-hitelesítés támogatása nyújt tájékoztatást](https://community.dynamics.com/ax/b/axforretail/posts/support-for-service-to-service-authentication-in-retail-server).

## <a name="configure-the-abandoned-cart-connector-sample-app"></a>Az leomlott bevásárlókocsi csatlakoztató mintaalkalmazásának konfigurálása

Ha konfigurálni szeretné az leomlott cart connector mintaalkalmazást, **módosítsa az appSettings.json** **konfigurációs fájlt, amely a A VánycartDetectionSample** könyvtár gyökerében található. A következő táblázatok leírják a konfigurációs fájl tulajdonságait.

### <a name="keyvaultoptions"></a>KeyVaultOptions

| Tulajdonság    | Leírás |
| ----------- | ----------- |
| KeyVaultURI | Az Azure-portálon használt kulcskulcs tartománynév-rendszere (DNS). |

### <a name="retailserverclientoptions"></a>RetailServerClientOptions

| Tulajdonság                                      | Leírás |
| --------------------------------------------- | ----------- |
| Bérlőazonosító                                      | Az Azure AD Azure-bérlő bérlőazonosítója |
| RetailServerAudienceId                        | A Retail Server célközönség-azonosítója Az alapértelmezett értéket itt hagyhatja. |
| AppIdKeyVaultSecretName                       | Annak a titkos névnek a neve, amit az leomlott cart connector mintaalkalmazás-alkalmazás azonosítójához hozott létre. |
| AppSecretKeyVaultSecretName                   | Annak a titkos helynek a neve, amely az leomlott bevásárlókocsi csatlakoztató mintaalkalmazás-azonosítójának alkalmazásnevét tárolja. |
| RetailServerUrl                               | A Retail Server-példány URL-címe Ez az érték az LCS-n található. |
| OperatingUnitNumber                           | Az üzemi egység száma (OUN). Ez az érték a Commerce Headquartersben található. |
| IncludeAbanoldedCartsModifiedSinceLastMinutes | A lekérdezni kívánt, le nem hagyott bevásárlókocsik időablakának kezdete. Az érték az aktuális idő előtti percek számában van kifejezve. **Állítsa például 120-ra** ezt a tulajdonságot, hogy beolvassa az összes olyan bevásárlókocsit, amelyet utoljára módosítottak 120 **perccel ezelőtt és az ExcludeAbanoldedCartsModifiedSinceLastMinutes** tulajdonság által meghatározott időablakban. |
| KizárásAbanoldedCartsModifiedSinceLastMinutes | A lekérdezni kívánt, le nem hagyott bevásárlókocsik időablakának vége. Az érték az aktuális idő előtti percek számában van kifejezve. **Ha például az IncludeAbanoldedCartsModifiedSinceLastMinutes** **tulajdonság 120-ra** van állítva, **állítsa 30-ra** ezt a tulajdonságot, hogy beolvassa az összes olyan bevásárlókocsit, amely 120 perccel és 30 perccel ezelőtt módosult. A gyakorlatban ez a tulajdonság azt az időt határozza meg, amíg a bevásárlókocsit érvénytelennek nem jelentették. |
| ReturnToCartUrl                               | A bevásárlókocsi URL-címe az e-commerce webhelyen, **az app.config fájlban használt formátumban**. |

### <a name="azurecosmosoptions"></a>AzureCoscosOptions

Az önrólott kocsi lekérési feladatának állapota, a bevásárlókocsi-idok és a módosított időbélyegzők az Azure szolgáltatásban tárolódnak Cosmos DB. Alapértelmezés szerint a konfigurációs fájl beállításai az Azure helyi emulátorpéldányra mutatnak Cosmos DB. Ha a csatlakoztató termelésre való telepítése történik, frissítenie kell ezeket a beállításokat, hogy az Azure-előfizetés Azure-példányára Cosmos DB mutasson. Helyi vagy üzenetkészlet-teszteléshez használhatja az [Azure Előfizetések emulátort](/azure/cosmos-db/local-emulator).

| Tulajdonság    | Leírás |
| ----------- | ----------- |
| EndPointUri | Az Azure vagy az emulátor által biztosított végponti URI. |
| PrimaryKey  | Az Azure vagy az emulátor által biztosított elsődleges kulcs. |
| DatabaseId  | Az adatbázis azonosítója. Az alapértelmezett értéket meghagyhatja, vagy saját értéket is biztosíthat. |
| Tárolóazonosító | A tároló azonosítója. Az alapértelmezett értéket meghagyhatja, vagy saját értéket is biztosíthat. |

### <a name="emarsysclientoptions"></a>EmarsysClientOptions

> [!NOTE]
> Ha az Emarsys szolgáltatástól kívüli e-mail marketingszolgáltatóval integrál, az IEmailProvider **felületet ki kell bővítenie ahhoz,** hogy kommunikáljon azzal a szolgáltatóval.

| Tulajdonság                      | Leírás |
| ----------------------------- | ----------- |
| ApiUrl                        | `https://api.emarsys.net/api/v2/event/{0}/trigger` |
| ExternalEventId               | Az Emarsys-ban létrehozott külső eseményrekord azonosítója. Az érték az Eseményindító beállítások **alatt** található abban a kampányban, amely az leomlott bevásárlókocsiról küldött e-mail értesítések küldését hozta létre. |
| ApiUserNameKeyVaultSecretName | Annak a kulcsnak a neve, ahol az Emarsys API-felhasználónév tárolva van. |
| ApiSecretKeyVaultSecretName   | Annak a kulcsnak a neve, ahol az Emarsys API-titkos kulcsot tárolják. |
| EmarsysContactKeyId           | Az Emarsys kapcsolattartó-adatbázis e-mail oszlopának azonosítója Az alapértelmezett érték **3**, ezért nem kell módosítani. |

### <a name="mediaoptions"></a>MediaOptions

Ha a Commerce rendszer e-commerce lehetőségeit használja, a Commerce digitális eszközkezelés segítségével termékképek lekérésére használhatja azt. A digitális eszközkezelés képméretező lehetőségeiről az [ImageSettings nézetport-konfigurációban található további tájékoztatás](../e-commerce-extensibility/image-component.md#imagesettings-viewport-configuration).

| Tulajdonság                             | Leírás |
| ------------------------------------ | ----------- |
| ImageServerUrl                       | A webhely digitáliseszköz-kezelőjének gyökér URL-címe. Az értéket a **Commerce Headquarters Retail és Commerce** Csatornabeállítási **\> csatornaprofiljai kulcsában találja meg a Médiakiszolgáló Alap URL-tulajdonság \>** kulcsában. |
| ImageViewPorts                       | Az egyes nézetport-konfigurációk tárolócsomópontja |
| ImageViewPorts/viewport              | A nézetport-definíció. Ezzel a tulajdonságtal képpontban megadhatja a nézet szélességi tartományát. A tulajdonság használatával kapcsolatos **példát lásd az appSettings.json konfigurációs** fájlban. |
| ImageViewPorts/imageWidth            | A nézetport képszélessége képpontban. |
| imageViewPorts/imageHetükrök           | A nézet nézetének kép magassága képpontban. |
| imageViewPorts/useForDefaultImageTag | **Truefalse**/**·**`<picture>` érték, amely jelzi, hogy a nézetport által definiált képdimenziókat kell-e használni, ha a HTML-címke nem támogatott webböngésző vagy e-mail ügyfél esetén. |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
