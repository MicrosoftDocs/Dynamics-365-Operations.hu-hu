---
title: "On-premises környezetek beállítása és telepítése"
description: "Ez a témakör tájékoztatja önt a helyszíni környezetek tervezéséről, beállításáról és telepítéséről."
author: kfend
manager: AnnBe
ms.date: 06/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core
ms.custom: 55651
ms.assetid: 
ms.search.region: Global
ms.author: sarvanisathish
ms.search.validFrom: 2016-08-30T00:00:00.000Z
ms.dyn365.ops.version: Platform update 8
ms.translationtype: HT
ms.sourcegitcommit: 3e9a2e33d9579769f6808b598f865d75f072c450
ms.openlocfilehash: 7caf033ab2de5afd6a2d88fa2d41631df4542cbe
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---

# <a name="set-up-and-deploy-on-premises-environments"></a>On-premises környezetek beállítása és telepítése

Ez a dokumentum megmutatja, hogyan tervezze meg a telepítést, állítsa fel az infrastruktúrát, és telepítse a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition-t (helyszíni).

## <a name="finance-and-operations-components"></a>Finance and Operations komponensek

A Finance and Operations alkalmazás három fő komponensből áll:

- AOS kiszolgáló
- Üzleti intelligencia (BI)
- Pénzügyi jelentéskészítés/Felügyeleti jelentéskészítő

Ezek a komponensek az alábbi rendszer szoftvertől függenek:

- Microsoft Windows Server 2016
- Microsoft SQL Server 2016 SP1, amely az alábbi szolgáltatásokkal rendelkezik:

    - A teljes szöveges index keresés engedélyezve van.
    - SQL Server Reporting Services (SSRS).
    - SQL Server Integration Services (SSIS).
    
     > [!NOTE]
     > Az alkalmazás nem fog futni, ha a teljes szöveges keresés nincs engedélyezve.

- SQL Server Management Studio
- Önálló Microsoft Azure Service Fabric
- Windows PowerShell 5.0 vagy újabb verziója
- Active Directory Federation Services (AD FS) a Windows Server 2016-on

  A tartományvezérlő Windows Server 2012 R2 vagy újabb kell, hogy legyen, illetve a tartomány működési szintjének el kell érnie a 2012 R2-t

  További információ a tartomány működési szintekről: 
  - [Active Directory működési szintjeinek fogalma](https://technet.microsoft.com/en-us/library/cc787290(v=ws.10).aspx)
  - [Az Active Directory Domain Services működési szintjeinek ismertetése](https://technet.microsoft.com/en-us/library/understanding-active-directory-functional-levels(v=ws.10).aspx)


## <a name="lifecycle-services"></a>Lifecycle Services

A Finance and Operations bitjeit a Microsoft Dynamics Lifecycle Services (LCS) osztja el. A telepítés előtt meg kell vásárolnia a licenckulcsokat a [vállalati megállapodások](https://www.microsoft.com/en-us/Licensing/licensing-programs/enterprise.aspx) csatornán keresztül, és be kell állítania egy helyszíni projektet az LCS-ben. A telepítéseket csak az LCS-en keresztül lehet elindítani. Helyszíni projektek LCS beállításával kapcsolatos információkért lásd: [helyszíni projekt létrehozása a Lifecycle Services szolgáltatásban](../lifecycle-services/lbd-create-lcs-on-prem-project.md).

## <a name="authentication"></a>Hitelesítés

A Helyszíni alkalmazás működik az AD FS-szel. Az LCS-szel való kommunikációhoz konfigurálnia kell az Azure Active Directory-t (Azure AD).

## <a name="standalone-service-fabric"></a>Önálló Service Fabric

A Finance and Operations az önálló Service Fabric-ot használja. További információkért lásd a [Service Fabric súgóját](/azure/service-fabric/).

## <a name="infrastructure"></a>Infrastruktúra

A Finance and Operations kompatibilis a hyper-konvergens architektúrákkal. A hardver konfiguráció a következő komponensekből áll:

- A Windows Server 2016 virtuális gépeire (VG-k) alapozott önálló Service Fabric fürt
- SQL Server (a fürtözött SQL és az Always-On is támogatott)
- AD FS hitelesítéshez
- Server Message Block (SMB) 3-as verzió fájlmegosztás tárolásra
- Választható: Microsoft Office Server 2017

További információkért lásd a [rendszerkövetelményeket](../get-started/system-requirements.md) és a méretezési irányelveket.

### <a name="hardware-layout"></a>Hardver elrendezése

Tervezze meg az infrastruktúráját és a Service Fabric fürtjét a [Hardver méretezés helyszíni környezetekben](../get-started/hardware-sizing-on-premises-environments.md) által ajánlott méretezés alapján. További információkért Service Fabric fürt tervezéséhez lásd: [Önálló Service Fabric fürt telepítésének tervezése és előkészítése](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation).

A következő táblázat egy hardver elrendezést ábrázol. A témakör többször is használja ezt a példát a beállítás illusztrálására.

> [!NOTE]
> A Service Fabric fürt fő csomópontjának legalább három csomóponttal kell rendelkeznie. Ebben a példában az **OrchestratorType** van kijelölve elsődleges csomóponttípusként.

| Gép célja                                 | Gép neve    | IP-cím    |
|-------------------------------------------------|-----------------|---------------|
| Tartományvezérlő                               | DAX7SQLAODC1    | 10.179.108.2  |
| AD FS                                           | DAX7SQLAOADFS1  | 10.179.108.3  |
| Fájlkiszolgáló                                     | DAX7SQLAOFILE1  | 10.179.108.4  |
| SQL Always-On fürt                           | DAX7SQLAOSQLA01 | 10.179.108.5  |
|                                                 | DAX7SQLAOSQLA02 | 10.179.108.6  |
|                                                 | DAX7SQLAOSQLA   | 10.179.108.9  |
| Ügyfél                                          | SQLAOCLIENT1    | 10.179.108.11 |
| Service Fabric fürt/AOS 1                    | SQLAOSF1AOS1    | 10.179.108.12 |
| Service Fabric fürt/AOS 2                    | SQLAOSF1AOS2    | 10.179.108.13 |
| Service Fabric fürt/AOS 3                    | SQLAOSF1AOS3    | 10.179.108.14 |
| Service Fabric fürt/Szervező 1           | SQLAOSF1ORCH1   | 10.179.108.15 |
| Service Fabric fürt/Szervező 2           | SQLAOSF1ORCH2   | 10.179.108.16 |
| Service Fabric fürt/Szervező 3           | SQLAOSF1ORCH3   | 10.179.108.17 |
| Service Fabric fürt/Felügyeleti jelentéskészítő csomópont | SQLAOSMR1       | 10.179.108.18 |
| Service Fabric fürt/SSRS csomópont                | SQLAOSFBIN1     | 10.179.108.10 |

## <a name="setup"></a>Beállítás

### <a name="prerequisites"></a>Előfeltételek

A telepítés előtt meg kell felelnie az alábbi előfeltételeknek. Ezen előfeltételek beállításának leírása nem található ebben a dokumentumban.

- Az Active Directory Domain Services (AD DS) telepítve és konfigurálva van a hálózaton.
- Az AD FS telepítve van.
- Az SQL Server, SSRS és Management Studio telepítve vannak.

### <a name="overview"></a>Áttekintés

A Finance and Operations infrastruktúrájának beállításához a következő lépéseket kell teljesíteni.

1. A tartománynév és a DNS-zónák tervezése
2. Tanúsítványok tervezése és beszerzése
3. A felhasználók és a szolgáltatásfiókok tervezése
4. DNS-zónák létrehozása és A rekordok hozzáadása
5. Virtuális gépek felvétele a tartományba
6. Előfeltételi szoftverek hozzáadása a virtuális gépekhez
7. Beállítási parancsfájlok letöltése az LCS-ből
8. Írja le a konfigurációját
9. Beállítási tanúsítványok
10. Önálló Service Fabric fürt beállítása
11. Konfigurálja a bérlő LCS-kapcsolatát
12. Állítsa be a fájl tárhelyet
13. Állítsa be az SQL Server-t
14. Konfigurálja az adatbázisokat
15. Titkosítsa a hitelesítő adatokat
16. SSRS beállítása
17. Konfigurálja az AD FS-t

### <a name="plan-your-domain-name-and-dns-zones"></a>A tartománynév és a DNS-zónák tervezése

Ajánlott egy nyilvánosan regisztrált tartománynév használata az AOS termelési beállításához. Így az elérhető lesz a hálózaton kívül is, ha szükség van külső hozzáférésre.

Például ha a vállalati tartomány contoso.com, akkor a Finance and Operations (helyszíni) lehet d365ffo.onprem.contoso.com, és az állomásnevek a következők lehetnek:

- ax.d365ffo.onprem.contoso.com az AOS gépek számára
- sf.d365ffo.onprem.contoso.com a Service Fabric fürt számára

### <a name="plan-and-acquire-your-certificates"></a>Tanúsítványok tervezése és beszerzése

Secure Sockets Layer (SSL) tanúsítványok szükségesek a Service Fabric fürt és a telepített alkalmazások védelmére. A termelési és védőfali terhelés esetén a tanúsítványokat ajánlott egy hitelesítésszolgáltatótól (CA) beszerezni, mint például a [DigiCert](https://www.digicert.com/ssl-certificate/), [Comodo](https://ssl.comodo.com/), a [Symantec](https://www.websecurity.symantec.com/ssl-certificate), a [GoDaddy](https://www.godaddy.com/web-security/ssl-certificate), vagy a [GlobalSign](https://www.globalsign.com/en/ssl/). Ha a tartomány [Active Directory Certificate Services-zel](https://technet.microsoft.com/en-us/library/cc772393(v=ws.10).aspx) (AD CS) van beállítva, akkor létrehozhat tanúsítványokat az AD CS-en keresztül. Minden tanúsítványnak tartalmaznia kell egy kulcs cserére létrehozott privát kulcsot ,ami exportálható személyes információcsere (.pfx) fájlba.

Önaláírt tanúsítványok csak tesztelésre használhatóak. Kényelmi szempontok miatt a beállítási tanúsítványok között vannak olyanok, amik önaláírt tanúsítványokat generálnak és exportálnak. Ahogy már említettük, ezek a tanúsítványok csak tesztelésre használhatóak.

| Cél                                      | Magyarázat | Kiegészítő követelmények |
|----------------------------------------------|-------------|-------------------------|
| SQL Server SSL tanúsítványa                   | Ez a tanúsítvány az SQL Server egy példánya és a kliens alkalmazás között, a hálózaton keresztül továbbított adatok titkosítására használható. | <p>A tanúsítvány tartománynevének meg kell egyeznie az SQL Server példány vagy figyelő teljesen minősített tartománynevével (FQDN).</p><p>Ha például az SQL figyelő a DAX7SQLAOSQLA gépen van tárolva , akkor a tanúsítvány DNS neve DAX7SQLAOSQLA.onprem.contoso.com.</p> |
| Service Fabric Server tanúsítvány            | Ez a tanúsítvány a Service Fabric csomópontok közti kommunikáció védelmére szolgál. Ez a tanúsítvány a fürthöz csatlakozó kliensnek megadott kiszolgálói tanúsítvány szerepét is betölti. | <p>A tanúsítvány tartománynevének meg kell egyeznie a DNS-zónával, ahol az AOS és a Service Fabric tárolva vannak.</p><p>A tanúsítvány tartományneve lehet például \*. onprem.contoso.com vagy \*. contoso.com.</p><p>Helyettesítő tanúsítvány használatakor a helyettesítő karakter csak egy szintre vonatkozik. Egy altartományt, a tulajdonos alternatív nevét (SAN) kell alkalmazni a tanúsítványon, ha több szintje is van, mint például a \*.contoso.com az előző példában.</p> |
| Service Fabric Client tanúsítvány            | Ezt a tanúsítványt a kliensek használják a Service Fabric fürt megtekintésére és kezelésére. | |
| Titkosítási tanúsítvány                     | Ez a tanúsítvány kényes adatok titkosítására szolgál, mint például az SQL Server jelszó és a felhasználói fiók jelszavak. | <p>A tanúsítvány kulcshasználatának tartalmaznia kell az adattitkosítást (10), és nem szabad tartalmaznia a kiszolgáló hitelesítést vagy a kliens hitelesítést.</p><p>További információkért lásd: [Titkok kezelése Service Fabric alkalmazásokban](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-application-secret-management).</p> |
| AOS SSL tanúsítvány                          | <p>Ez a tanúsítvány az AOS webhely kliensének megadott kiszolgálói tanúsítvány szerepét tölti be. A Windows Communication Foundation (WCF)/Simple Object Access Protocol (SOAP) tanúsítványok engedélyezésére is használatos.</p><p>A Service Fabric Server tanúsítvány akkor használható, ha helyettesítő tanúsítvány.</p> | <p>A tanúsítvány tartománynevének meg kell egyeznie a DNS-zónával, ahol az AOS és a Service Fabric tárolva vannak.</p><p>A tanúsítvány tartományneve lehet például \*.d365ffo.onprem.contoso.com, \*.onprem.contoso.com, vagy \*.contoso.com.</p><p>Helyettesítő tanúsítvány használatakor a helyettesítő karakter csak egy szintre vonatkozik. Egy altartományt, a SAN-t kell alkalmazni a tanúsítványon, ha több szintje is van, mint például a \*.contoso.com az előző példában.</p> |
| Munkamenet hitelesítési tanúsítvány           | Ezt a tanúsítványt az AOS használja a felhasználó munkamenet-adatainak védelmének biztosítására. | Ez egyben a **fájlmegosztás** tanúsítvány is, ami az LCS-től való telepítés közben használatos. |
| Adattitkosítási és adataláírási tanúsítvány | Ezeket a tanúsítványokat az AOS használja a bizalmas adatok titkosítására. | |
| Pénzügyi jelentéskészítő kliens tanúsítvány       | Ez a tanúsítvány a Financial Reporting szolgáltatások és az AOS közti kommunikáció védelmére szolgál. | |
| Jelentéskészítő tanúsítvány                        | Ez a tanúsítvány az SSRS és az AOS közti kommunikáció védelmére szolgál. | |
| Helyszíni ügynök tanúsítvány           | <p>Ez a tanúsítvány a helyszíni tárolású helyi ügynök és az LCS közti kommunikáció védelmére szolgál.</p><p>Ez a tanúsítvány lehetővé teszi, hogy a helyi ügynök az Azure AD bérlő nevében járhasson el, és hogy kommunikálhasson az LCS-szel a telepítések szervezése és megfigyelése miatt.</p> | |

### <a name="plan-your-users-and-service-accounts"></a>A felhasználók és a szolgáltatásfiókok tervezése

A Finance and Operations (helyszíni) működtetéséhez több felhasználót vagy szolgáltatásfiókot is létre kell hoznia. Egy kombinációját kell létrehoznia a csoport-felügyelt szolgáltatásfiókoknak (gMSA-k), tartományfiókoknak és SQL fiókoknak. Az alábbi táblázat bemutatja a felhasználói fiókokat, ezek rendeltetését, és a példaneveket, amelyek ebben a témakörben használatosak.

| Felhasználói fiók                                            | Típus           | Cél | Felhasználónév |
|---------------------------------------------------------|----------------|---------|-----------|
| Pénzügyi jelentéskészítő alkalmazás szolgáltatásfiókja         | gMSA           |         | Contoso\\svc-FRAS$ |
| Pénzügyi jelentéskészítő folyamat szolgáltatásfiókja             | gMSA           |         | Contoso\\svc-FRPS$ |
| Pénzügyi jelentéskészítő egykattintásos tervező szolgáltatásfiókja | gMSA           |         | Contoso\\svc-FRCO$ |
| AOS Szolgáltatásfiókja                                     | gMSA           | Ezt a felhasználót létre kell hozni a jövőbeli ellenőrzéshez Tervezzük engedélyezni az AOS gMSA-val való működését a jövőbeli kiadásokban. A beállítás során a felhasználó létrehozásával segít a gMSA-hoz való zökkenőmentes átmenet biztosításában. | Contoso\\svc-AXSF$ |
| AOS Szolgáltatásfiókja                                     | Tartomány fiókja | Az AOS ezt a felhasználót használja a GA kiadásban. | Contoso\\AXServiceUser |
| AOS SQL-adatbázis rendszergazdai felhasználó                                   | SQL Felhasználó       | A Finance and Operations ezt a felhasználót használja az SQL-lel való hitelesítésre\*. Ezt a felhasználót is felülírja majd a gMSA felhasználó a jövőbeli kiadásokban. | AXDBAdmin |
| Helyi telepítési ügynök szolgáltatásfiókja                  | gMSA           | A helyi ügynök ezt a fiókot használja a telepítés szervezésére különböző csomópontokon. | Contoso\\Svc-LocalAgent$ |

\* Az SQL hitelesítéshez tartozó SQL-felhasználónév és jelszó biztonságban vannak, mert titkosítottak és a fájlmegosztásban vannak tárolva.

### <a name="create-dns-zones-and-add-a-records"></a>DNS-zónák létrehozása és A rekordok hozzáadása

A DNS az AD DS-sel van integrálva, és lehetővé teszi az erőforrások rendezését, kezelését és keresését a hálózaton. Hozzon létre egy DNS címkeresési zónát és A rekordokat az AOS állomásnév és a Service Fabric fürt részére. Ezen példabeállítás esetén a DNS-zóna neve d365ffo.onprem.contoso.com, és az A rekordok/állomásnevek a következők:

- **ax**.d365ffo.onprem.contoso.com az AOS gépek számára
- **sf**.d365ffo.onprem.contoso.com a Service Fabric fürt számára

#### <a name="add-a-dns-zone"></a>Adjon hozzá egy DNS-zónát

DNS-zóna hozzáadásához használja az alábbi eljárást:

1. Jelentkezzen be a tartományvezérlő gépbe, kattintson a **kezdésre**, és indítsa el a DNS-kezelőt a **dnsmgmt.msc** beírásával.
2. Kattintson a jobb gombbal a tartományvezérlő nevére, kattintson az **Új zóna gombra** \> **majd a tovább gombra**.
3. Válassza ki az **elsődleges zónát**.
4. Hagyja a **tárolja a zónát az Active Directory-ban (csak akkor, ha a DNS-kiszolgáló egy írható tartományvezérlő)** jelölőnégyzetet bejelölve, és kattintson a **következő** gombra.
5. Válassza ki ezt: **Minden, tartományvezérlőn futó DNS-kiszolgálóra a tartományban: Contoso.com**, és kattintson a **következő** gombra.
6. Válassza ki ezt: **Címkeresési zóna**, és kattintson a **következő** gombra.
7. Adja meg a beállítás zónanevét , és kattintson a **következő** gombra. Példa a megadáshoz: **d365ffo.onprem.contoso.com**.
8. Válassza ki ezt: **Dinamikus frissítések tiltása**, és kattintson a **következő** gombra.

#### <a name="set-up-an-a-record-for-aos"></a>Hozzon létre egy A rekordot az AOS számára

Az új DNS-zónában hozzon létre egy **ax.d365ffo.onprem.contoso.com** nevű A rekordot **mindegyik** **AOSNodeType** típusú Service Fabric fürt csomópont számára. Más csomóponttípus számára ne hozzon létre A rekordot.

1. Kattintson jobb egérgombbal az új zónára, majd kattintson az **Új állomás** lehetőségre.
2. Adja meg a Service Fabric csomópont nevét és IP-címét (pl. 10.179.108.12), majd kattintson az **Állomás Hozzáadása** lehetőségre.

#### <a name="set-up-an-a-record-for-the-orchestrator"></a>Hozzon létre egy A rekordot a szervező számára

Az új DNS-zónában hozzon létre egy **sf.d365ffo.onprem.contoso.com** nevű A rekordot **mindegyik** **OrchestratorType** típusú Service Fabric fürt csomópont számára. Más csomóponttípus számára ne hozzon létre A rekordot.

1. Kattintson jobb egérgombbal az új zónára, majd kattintson az **Új állomás** lehetőségre.
2. Adja meg a Service Fabric csomópont nevét és IP-címét (pl. 10.179.108.15), majd kattintson az **Állomás Hozzáadása** lehetőségre.

#### <a name="join-vms-to-the-domain"></a>Virtuális gépek felvétele a tartományba

Vegye fel az összes virtuális gépet a tartományba az alábbi lépések végrehajtásával: [Windows Server 2016 felvétele egy Active Directory tartományba](http://www.tomsitpro.com/articles/join-windows-server-2016-to-ad-domain,2-1063.html). Másik lehetőségként használhatja a Windows PowerShell parancsfájlt is.

```
$domainName = Read-Host -Prompt 'Specify domain name (ex: contoso.com)'
Add-Computer -DomainName $domainName -Credential (Get-Credential -Message 'Enter domain credential')
Restart-Computer
```
Ha felvette a virtuális gépeket a tartományba, adja hozzá az AOS-szolgáltatásfiókokat (Contoso\svc-AXSF$, Contoso\svc-AXSF$ ) a helyi rendszergazdák csoporthoz. Megtekintheti a [Tag hozzáadása helyi csoporthoz](https://technet.microsoft.com/en-us/library/cc772524(v=ws.11).aspx) cikket ennek módjáról.

#### <a name="disable-user-access-control"></a>Felhasználói hozzáférés-szabályozás letiltása 

Hajtsa végre a következő parancsfájlt, ha le kívánja tiltani a felhasználói hozzáférés-szabályozást **mindegyik** Service Fabric csomóponton.
```
$RegPath = "HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System"
New-ItemProperty -Path $RegPath -Name "EnableLUA" -Value 0 -PropertyType "DWORD" -Force
New-ItemProperty -Path $RegPath -Name "ConsentPromptBehaviorAdmin" -Value 0 -PropertyType "DWORD" -Force
New-ItemProperty -Path $RegPath -Name "EnableUIADesktopToggle" -Value 0 -PropertyType "DWORD" -Force
New-ItemProperty -Path $RegPath -Name "LocalAccountTokenFilterPolicy" -Value 1 -PropertyType "DWORD" -Force
```
> [!IMPORTANT]
> A parancsfájl sikeres befejezése után újra kell indítani a csomópontot.

#### <a name="add-prerequisite-software-to-vms"></a>Előfeltételi szoftverek hozzáadása a virtuális gépekhez

Az alábbi táblázat felsorolja azokat az előfeltételi szoftvereket, amiket minden csomóponttípus gépén alkalmazni kell.

> [!NOTE]
> Az összetevők telepítése után újra kell indítani a számítógépet.

| Csomópont típusa | Összetevő | Parancs |
|-----------|-----------|---------|
| AOS       | SNAC - ODBC-illesztőprogram | Lásd: [Microsoft ODBC illesztőprogram 13.1 az SQL Server-hez - Windows + Linux](https://www.microsoft.com/en-us/download/details.aspx?id=53339). |
| AOS       | A Microsoft .NET keretrendszer 2.0-s – 3.5-ös verziója (CLR 2.0) | `Add-WindowsFeature -Name NET-Framework-Features, NET-Framework-Core, NET-HTTP-Activation, NET-Non-HTTP-Activ` |
| AOS       | A Microsoft .NET keretrendszer 4.0-s – 4.6-ös verziója (CLR 4.0) | `Add-WindowsFeature -Name NET-Framework-45-Features, NET-Framework-45-Core, NET-Framework-45-ASPNET, NET-WCF-Services45, NET-WCF-TCP-PortSharing45` |
| AOS       | Internet Information Services (IIS) | `Add-WindowsFeature WAS, WAS-Process-Model, WAS-NET-Environment, WAS-Config-APIs`<br>`# Windows Process Activation Service`<br>`Add-WindowsFeature Web-Server, Web-WebServer, Web-Security, Web-Filtering, Web-App-Dev, Web-Net-Ext, Web-Mgmt-Tools, Web-Mgmt-Console` |
| AOS       | Microsoft SQL Server Management Studio 2016 | |
| AOS       | Microsoft Visual C++ újraterjeszthető csomagok Microsoft Visual Studio 2013 számára | Lásd: [Microsoft Visual C++ újraterjeszthető csomagok Microsoft Visual Studio 2013 számára](https://support.microsoft.com/en-us/help/3179560). |
| AOS       | Microsoft Access adatbázismotor 2010 terjeszthető változata | Lásd: [Microsoft Access adatbázismotor 2010 terjeszthető változata](https://www.microsoft.com/en-us/download/details.aspx?id=13255) |
| AZ ÜZLETI INTELLIGENCIA        | A .NET keretrendszer 2.0-s – 3.5-ös verziója (CLR 2.0) | `Add-WindowsFeature -Name NET-Framework-Features, NET-Framework-Core, NET-HTTP-Activation, NET-Non-HTTP-Activ` |
| AZ ÜZLETI INTELLIGENCIA        | A .NET keretrendszer 4.0-s – 4.6-ös verziója (CLR 4.0) | `Add-WindowsFeature -Name NET-Framework-45-Features, NET-Framework-45-Core, NET-Framework-45-ASPNET, NET-WCF-Services45, NET-WCF-TCP-PortSharing45` |
| AZ ÜZLETI INTELLIGENCIA        | Microsoft SQL Server 2016 SP1 | |
| AZ ÜZLETI INTELLIGENCIA        | Management Studio 2016 | |
| AZ ÜZLETI INTELLIGENCIA        | SQL Server Reporting Services 2016 **Natív** módban | |
| MR        | A .NET keretrendszer 2.0-s – 3.5-ös verziója (CLR 2.0) | `Add-WindowsFeature -Name NET-Framework-Features, NET-Framework-Core, NET-HTTP-Activation, NET-Non-HTTP-Activ` |
| MR        | A .NET keretrendszer 4.0-s – 4.6-ös verziója (CLR 4.0) | `Add-WindowsFeature -Name NET-Framework-45-Features, NET-Framework-45-Core, NET-Framework-45-ASPNET, NET-WCF-Services45, NET-WCF-TCP-PortSharing45` |
| MR        | Visual C++ újraterjeszthető csomagok Visual Studio 2013 számára. | Lásd: [Microsoft Visual C++ újraterjeszthető csomagok Microsoft Visual Studio 2013 számára](https://support.microsoft.com/en-us/help/3179560). |

#### <a name="download-setup-scripts-from-lcs"></a>Beállítási parancsfájlok letöltése az LCS-ből

A telepítés folyamatának javítása érdekében több parancsfájlt mellékeltünk. Kövesse az alábbi lépéseket, ha le kívánja tölteni a telepítő parancsfájlokat az LCS-ből.

1. Bejelentkezés az LCS-be (<https://lcs.dynamics.com/v2>).
2. Az irányítópulton kattintson a **Közös eszköztár** csempére.
3. Kattintson a **Modell** fülre.
4. A rácson válassza ki a **Dynamics 365 for Operations - helyszíni telepítési parancsfájljai** sort.
5. Kattintson a **verziókra**, és töltse le a parancsfájlok legfrissebb verzióját.

### <a name="describe-your-configuration"></a>Írja le a konfigurációját

Ez a szakasz tájékoztatást tartalmaz azokról a parancsfájlokról, amelyeket önnek futtatnia kell. A szakasz abban a sorrendben tárgyalja a parancsfájlokat, ahogy önnek futtatnia kell őket. A parancsfájlok futtatásához töltse ki a $(downloadPath)\\ConfigTemplate.xml helyen található sablonfájlt. A ConfigTemplate.xml fájl bemutatja a Service Fabric fürtöket, az ezek konfigurálására használt tanúsítványokat, illetve azokat a fiókokat, amelyeknek hozzáférést kell biztosítani a szükséges tanúsítványokhoz. A megadott példában az ebben a témakörben leírt példa infrastruktúra értékei vannak kitöltve. A sablonfájlt a következő szakaszban használjuk.

#### <a name="create-the-domain-account-for-a-service-user"></a>Hozzon létre egy tartományfiókot a szolgáltatás felhasználójának

A contoso\\AXServiceUser tartományi felhasználói fiók létrehozásához futtassa a következő parancsot.

```
New-ADUser -Name 'AXServiceUser' `
    -AccountPassword (Read-Host -Prompt 'Specify User Password' -AsSecureString) `
    -PasswordNeverExpires $true -ChangePasswordAtLogon $false `
    -Enabled $true -UserPrincipalName 'AXServiceUser@contoso.com'
```

#### <a name="create-gmsas"></a>gMSA-k létrehozása

1. Módosítsa a könyvtárat a **$(DownloadPath)** helyre, és futtassa a következő Windows PowerShell parancsot.

    > [!NOTE]
    > Ez a parancsfájl nem hoz létre felhasználókat. Ehelyett kinyomtatja a parancsokat, amelyeket manuálisan kell futtatni a tartományvezérlő gépen.

    ```
    # Generate gMSA account creation script (shows in console):
    .\Get-NewGMSAInDomainScript.ps1 -InputXml .\ConfigTemplate.xml
    ```

2. Másolja a parancs kimenetét a Windows PowerShell ablakba. Győződjön meg arról, hogy a sortörések törlődnek, és futtassa a sorokat az Active Directory tartományvezérlő számítógépen magasabb szintű jogosultságok használatával (kattintson a jobb gombbal, majd kattintson a **Futtatás rendszergazdaként** lehetőségre).
3. A fiókok sikeres létrehozásának ellenőrzéséhez futtassa a következő parancsfájlt az Active Directory tartományvezérlőjén. Győződjön meg arról, hogy a parancsfájlt azután futtatja, hogy kicserélte azt a mintát, amely a szolgáltatásfiókok elnevezési szabályát használja.

    ```
    #Use this command to validate the gMSA accounts are added to AD.
    #Ensure to replace the Filter parameter with the pattern used to create your accounts.
    Get-ADServiceAccount -Filter { samAccountName -like "svc-*" }
    ```

4. Futtassa az Export-AddGMSAsONVMScript.ps1 parancsfájlt a kliens gépen. Ez a parancsfájl olyan parancsfájlokat hoz létre, amelyek minden Service Fabric virtuális gépen futnak, és hozzáadják őket a virtuális gép nevekhez tartozó mappákhoz.

    ```
    # Exports a script for installing gMSA on VM nodes into a directory VMs\<VMName>, again feed from XML
    .\Export-AddGMSAsOnVMScript.ps1 -InputXml .\ConfigTemplate.xml
    ```

#### <a name="stop-iis"></a>IIS Leállítása

Használja a távoli asztali protokollt (RDP) minden egyes Service Fabric virtuális géphez való kapcsolódáshoz, és teljesítse a kézi lépéseket: [Webkiszolgáló indítása és leállítása (IIS 7)](https://technet.microsoft.com/en-us/library/cc732317(v=ws.10).aspx). Másik lehetőségként használhatja a következő Windows PowerShell-parancsfájlt, ha az RDP segítségével csatlakozik mindegyik Service Fabric virtuális géphez.

```
$ServiceName = "WAS"
$wasService = Get-Service $ServiceName -ErrorAction SilentlyContinue
if($wasService)
{
    $wasService.DependentServices | Stop-Service -Force -ErrorAction Continue
    $wasService | Stop-Service -ErrorAction Continue
    Set-Service $ServiceName -StartupType Disabled
}

$ServiceName = 'W3SVC'
$w3svc = Get-Service $ServiceName -ErrorAction SilentlyContinue
if($w3svc)
{
    $w3svc.DependentServices | Stop-Service -Force -ErrorAction Continue
    $w3svc | Stop-Service -ErrorAction Continue
    Set-Service $ServiceName -StartupType Disabled
}
```
_Az IIS szolgáltatást telepíteni kell, de le kell tiltani, mivel függőségek találhatók a termékben lévő IIS dll-ektől._

### <a name="install-certificates"></a>Beállítási tanúsítványok

1. Ha a a témakörben korábban ismertetett tanúsítványokat érvényes hitelesítésszolgáltatótól vásárolta meg, akkor töltse ki a .pfx fájlnevet és ujjlenyomatot a ConfigTemplate.xml fájlban található tanúsítványok számára. Állítsa a **generateSelfSignedCert** attribútumot **hamis** értékre és az **exportálható** attribútumot szintén **hamis** értékre. Másolja a .pfx fájlokat a $(DownloadPath)\\InfrastructureScripts\\Certs mappába.
2. Ha önaláírt tanúsítványokat használ (csak tesztelésre), akkor futtassa a következő parancsfájlt. Önaláírt tanúsítványok létrehozásához győződjön meg arról, hogy a ConfigTemplate.xml fájlban a **generateSelfSignedCert** értéke **igaz** és **exportable** értéke szintén **igaz**. A parancsfájl módosítani fogja az XML-fájlt a tanúsítványok ujjlenyomataival.

    ```
    # Create self-signed certs (optionally, use -Display if you only want to see commands):
    # Note: this script is completely driven off ConfigTemplate.xml
    .\New-SelfSignedCertificates.ps1 -InputXml .\ConfigTemplate.xml
    ```

3. Exportálja az új tanúsítványokat a titkos kulccsal (a .pfx fájl). A következő parancsfájl segítségével állítsa elő és futtassa a Windows PowerShell exportálási parancsokat. A .pfx fájlok a Certs mappába kerülnek.

    ```
    # Exports Pfx files into a directory VMs\<VMName>, all the certs will reside in a folder named Certs\
    # Feeds from XML, if certs don't have passwords then you are prompted to enter one
    .\Export-PfxFiles.ps1 -InputXml .\ConfigTemplate.xml
    ```

    > [!NOTE]
    > A tanúsítványokat telepíteni kell, és jelen kell lenniük itt: cert:\\CurrentUser\\My. A tanúsítványoknak exportálhatóaknak kell lenniük.

    Ha önaláírt tanúsítványokat használ, ugorjon a következő szakaszra. Nem szükséges elvégeznie ezt az eljárást.

4. Miután átmásolta vagy exportálta a .pfx fájlokat a $(DownloadPath)\\InfrastructureScripts\\Certs mappába, futtassa a következő parancsokat, hogy létrehozza a parancsfájlokat, amik a virtuális gépekhez tartozó mappákba kerülnek.

    ```
    # Exports script for adding ACLs to certs into a directory VMs\<VMName>
    .\Export-CertificateAclsForVMs.ps1 -InputXml .\ConfigTemplate.xml
    
    # Exports Import-PfxFiles.ps1 script for importing PFXs on VM nodes into a directory VMS\<VMname>:
    .\Export-ImportPfxFilesScript.ps1 -InputXml .\ConfigTemplate.xml
    
    .\Export-UnblockStrongNameScript.ps1 -InputXml .\ConfigTemplate.xml
    ```

5. A parancsfájlokat másolja mindegyik mappából a mappa nevéhez tartozó virtuális gépre.
6. Futtassa a parancsfájlokat mindegyik virtuális gépen a megjelenés sorrendjében.

    ```
    #Run this script only if it exists
    .\Add-GMSAOnVM.ps1
    
    .\Import-PfxFiles.ps1
    
    .\Set-CertificateAcls.ps1
    
    #Run this script only if it exists
    .\Unblock-StrongName.ps1
    ```

### <a name="set-up-a-standalone-service-fabric-cluster"></a>Önálló Service Fabric fürt beállítása

1. A ClusterConfig.json fájl létrehozásához futtassa a következő parancsot.

    ```
    .\New-SFClusterConfig.ps1 -InputXml .\ConfigTemplate.xml
    ```

    További információkért lásd: [1B lépés: több gépes fürt létrehozása](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-cluster-creation-for-windows-server#create-the-cluster), [Önálló fürt védelme Windows-on X.509 tanúsítványokkal](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-windows-cluster-x509-security), és [Windows Server-en futó önálló fürt létrehozása](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-cluster-creation-for-windows-server#create-the-cluster).

2. Töltse le ezt: [Service Fabric önálló telepítőcsomag](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-cluster-creation-for-windows-server#download-the-service-fabric-standalone-package) a Service Fabric csomópontok egyikére. Miután letöltötte a zip fájlt, kattintson a jobb gombbal a zip fájlra és kattintson a **tulajdonságok** lehetőségre a feloldáshoz. A párbeszédpanelen jelölje be az **Unblock** jelölőnégyzetet a képernyő jobb alsó sarkában.
3. Másolja a zip fájlt a Service Fabric fürt egyik csomópontjára, és bontsa ki.
4. Futtassa az alábbi parancsokat bejövő tűzfal szabály létrehozásához mindegyik csomópont 443-as és 445-ös portjain.

    ```
    #Create inbound Rule
    New-NetFirewallRule -DisplayName "SFInbound443445" -LocalPort 135, 137, 138, 139, 445, 443 -Direction Inbound -Enabled True -Protocol TCP
    
    #Test inbound Rule
    Get-NetFirewallRule -DisplayName "SFInbound443445"
    ```

5. Futtassa az alábbi parancsokat bejövő tűzfal szabály létrehozásához csakis az SSRS csomópont 80-as portján.

    ```
    #Create inbound Rule
    New-NetFirewallRule -DisplayName "Reporting80" -LocalPort 80 -Direction Inbound -Enabled True -Protocol TCP
    
    #Test inbound Rule
    Get-NetFirewallRule -DisplayName "Reporting80"
    ```

6. Másolja a ClusterConfig.json fájlt az önálló Service Fabric kicsomagolatlan telepítési helyére.
7. A Windows PowerShellben keresse meg a kicsomagolatlan telepítési helyet a magasabb szintű jogosultságok használatával, majd futtassa a következő parancsot a ClusterConfig teszteléséhez.

    ```
    .\TestConfiguration.ps1 -ClusterConfigFilePath .\clusterConfig.json
    ```

8. Ha a teszt sikeres, futtassa a következő parancsot a fürt telepítéséhez.

    ```
    .\CreateServiceFabricCluster.ps1 -ClusterConfigFilePath .\ClusterConfig.json
    ```

9. A fürt létrehozása után nyissa meg a Service Fabric explorer-t bármelyik ügyfél gépen a telepítés ellenőrzéséhez:

    1. Ha még nem tette, telepítse a Service Fabric kliens tanúsítványt a CurrentUser\\My helyen.
    2. Keresse fel ezt: **IE beállítások** \> **kompatibilitási mód**, és törölje a jelet az **Intranethelyek megjelenítése kompatibilitás módban** jelölőnégyzetben.
    3. Keresse fel a `https://sf.d365ffo.onprem.contoso.com:19080`oldalt, ahol a sf.d365ffo.onprem.contoso.com a zónában megadott Service Fabric fürt állomásneve. Ha a DNS név feloldás nincs konfigurálva, akkor használja a gép IP-címét.
    4. Jelölje ki a kliens tanúsítványt. Megjelenik a **Service Fabric explorer** lap.

### <a name="configure-lcs-connectivity-for-the-tenant"></a>Konfigurálja a bérlő LCS-kapcsolatát

A Finance and Operations telepítésének és karbantartásának szervezése az LCS-en keresztül történik egy helyszíni ügynök használatával. Az LCS-től a Finance and Operations bérlőhöz való kapcsolat létrehozásához konfigurálnia kell egy tanúsítványt, ami engedélyt ad a helyi ügynöknek, hogy az ön Azure AD bérlője nevében járjon el (például Contoso.Onmicrosoft.com).

Használja a hitelesítésszolgáltatótól beszerzett helyi ügynök tanúsítványt vagy a parancsfájlok segítségével generált önaláírt tanúsítványt.

Csak a globális rendszergazdai könyvtár szerepkörrel rendelkező felhasználói fiókok adhatnak hozzá olyan tanúsítványokat, amelyek az LCS-t engedélyezik. Alapértelmezés szerint az a személy, aki a szervezet számára regisztrál a Microsoft Office 365-re, lesz a könyvtár globális rendszergazdája.

> [!NOTE]
> A tanúsítványt bérlőnként pontosan egyszer kell konfigurálnia. Minden helyszíni környezet ugyanazon tanúsítvány segítségével kapcsolódhat az LCS-hez.

1. Töltse le és telepítse az Azure PowerShell legfrissebb verzióját egy kliens gépre. További információkért lásd: [Azure PowerShell telepítése és konfigurálása](https://docs.microsoft.com/en-us/powershell/azure/install-azurerm-ps?view=azurermps-4.1.0&viewFallbackFrom=azurermps-4.0.0).
2. Jelentkezzen be ebbe: [vevők Azure portalja](https://portal.azure.com), hogy meggyőződjön róla, hogy globális rendszergazdai könyvtár szerepköre van.
3. Futtassa a következő parancsfájlt a $(DownloadPath)\\InfrastructureScripts helyről.

   ```
   .\AddCertToServicePrincipal.ps1 -CertificateThumbprint <OnPremLocalAgent Certificate Thumbprint>
   ```

### <a name="set-up-file-storage"></a>Állítsa be a fájl tárhelyet

Be kell állítania két magas rendelkezésre állású SMB 3.0 fájl megosztást. Az SMB 3.0 engedélyezésével kapcsolatos információkért lásd:[SMB biztonsági fejlesztések](https://technet.microsoft.com/en-us/library/dn551363(v=ws.11).aspx#BKMK_disablesmb1).
A biztonságos dialektus-egyeztetés nem észlelheti, és nem is akadályozhatja meg az SMB 1.0-ra való visszalépést SMB 2.0-ról vagy SMB 3.0-ról. Ennek következtében, és az SMB titkosítási lehetőségeinek teljes kihasználásához erősen ajánlott az SMB 1.0 kiszolgáló letiltása.

> [!NOTE]
> Az ön környezetében található alvó állapotú adatok védelmének érdekében a BitLocker Drive titkosítást minden gépen engedélyezni kell. A BitLocker engedélyezésével kapcsolatos további információkért lásd: [BitLocker: telepítés Windows Server 2012 vagy újabb verzión](https://docs.microsoft.com/en-us/windows/device-security/bitlocker/bitlocker-how-to-deploy-on-windows-server).

- Olyan fájlmegosztás, amely az AOS-re feltöltött felhasználói dokumentumokat tárolja (például \\\\DAX7SQLAOFILE1\\aos-storage).
- Olyan fájlmegosztás, ami a legújabb felépítési és konfigurációs fájlokat tárolja a telepítés szervezéséhez (például \\\\DAX7SQLAOFILE1\\agent))

    > [!NOTE]
    > Tartsa a fájlmegosztás elérési útvonalát a lehető legrövidebben a megosztásba helyezett fájlok maximális elérési útvonal-hosszának átlépésének elkerülése végett.

1. Futtassa a következő parancsot a fájlmegosztás gépén.

    ```
    Install-WindowsFeature -Name FS-FileServer -IncludeAllSubFeature -IncludeManagementTools
    ```
#### <a name="set-up-the-dax7sqlaofile1aos-storage-file-share"></a>Állítsa be a \\\\DAX7SQLAOFILE1\\aos-storage fájlmegosztást

2. Válassza ki a kiszolgálókezelőben ezt: **Fájl- és tárolási szolgáltatások** \> **Megosztások**.
3. Kattintson a **Tasks** \> **New Share** opcióra az **aos-storage** nevű új megosztás létrehozására.
4. Adjon meg **Modify** engedélyeket mindegyik gép számára a Service Fabric fürtben az **OrchestratorNodeType** kivételével.
5. Adjon meg **Modify** engedélyeket az AOS tartományi felhasználó (contoso\\AXServiceUser) és a gMSA felhasználó (contoso\\svc-AXSF) számára.

#### <a name="set-up-the-dax7sqlaofile1agent-file-share"></a>Állítsa be a \\\\DAX7SQLAOFILE1\\agent fájlmegosztást

6. Menjen vissza a kiszolgálókezelőbe, és válassza ezt: **Fájl- és tárolási szolgáltatások** \> **Megosztások**.
7. Kattintson a **Tasks** \> **New Share** opcióra az **agent** nevű új megosztás létrehozására.
8. Adjon meg **Full-Control** engedélyeket a gMSA felhasználó számára a helyi telepítési ügynökre vonatkozóan (contoso\\svc-LocalAgent$).

### <a name="set-up-sql-server"></a>Állítsa be az SQL Server-t

1. Telepítse az SQL Server 2016 SP1-et magas elérhetőséggel, vagy a tároló hálózatot (SAN) tartalmazó SQL fürtökként, vagy Always-On konfigurációban.  Ellenőrizze, hogy az **Adatbázismotor, jelentési szolgáltatások, teljes szöveges keresés**, és a **Kezelési eszközök** már telepítve vannak.
> [!NOTE]
> Győződjön meg arról, hogy az SQL mindig a következők szerint van beállítva: [Válassza ki a kezdeti adat-szinkronizálási lapot (Always-On elérhetőség csoport varázslók)](https://docs.microsoft.com/en-us/sql/database-engine/availability-groups/windows/select-initial-data-synchronization-page-always-on-availability-group-wizards), és kövesse ezt: [Másodlagos adatbázisok manuális előkészítése](https://docs.microsoft.com/en-us/sql/database-engine/availability-groups/windows/select-initial-data-synchronization-page-always-on-availability-group-wizards#PrepareSecondaryDbs)
2. Futtassa az SQL Service-t tartományi felhasználóként.
3. A Finance and Operations konfigurálásához szerezzen be egy SSL tanúsítványt egy hitelesítésszolgáltatótól. Tesztelési célokból létrehozhat és használhat egy önaláírt tanúsítványt.

**Önaláírt tanúsítvány fürtözött SQL-példányhoz**
   ```
   New-SelfSignedCertificate -CertStoreLocation "cert:\CurrentUser\My" -DnsName "DAX7SQLAOSQLA.contososqlao.com" -Provider "Microsoft Enhanced RSA and AES Cryptographic Provider" -Subject "DAX7SQLAOSQLA.contososqlao.com"
   ```
**Önaláírt tanúsítvány Always-On SQL-példányhoz**
```
#https://www.derekseaman.com/2014/11/sql-2014-alwayson-ag-pt-13-ssl.html

# Create certificate for each SQL Node (i.e. 2 nodes = 2 certificates)
# Run script on each node
$computerName = $env:COMPUTERNAME.ToLower() 
$domain = $env:USERDNSDOMAIN.ToLower()
$listenerName = 'dax7sqlaosqla' 
$cert = New-SelfSignedCertificate -Subject "$computerName.$domain" -DnsName "$listenerName.$domain", $listenerName, $computerName -Provider 'Microsoft Enhanced RSA and AES Cryptographic Provider'

```
4. A tanúsítvány használatával hajtsa végre ezeket a lépéseket: [SSL-titkosítás engedélyezése az SQL Server egy példányának a Microsoft Management Console használatával](https://support.microsoft.com/en-us/help/316898/how-to-enable-ssl-encryption-for-an-instance-of-sql-server-by-using-microsoft-management-console) SSL beállításához az SQL Server kiszolgálón.
5. Kövesse az alábbi lépéseket a fürt minden csomópontján. Győződjön meg arról, hogy a nem aktív csomóponton végezte el a módosításokat, és akkor adja át azokat, amikor a módosításokat már végrehajtotta.

    1. Importálja a tanúsítványokat a LocalMachine\\My helyre.
    2. Adjon tanúsítvány engedélyeket az SQL szolgáltatást futtató szolgáltatásfiók számára. A Microsoft Management Console-ban (MMC) kattintson a jobb gombbal a tanúsítványra (certlm.msc), majd kattintson a **Tasks** \> **Manage Private Keys** opcióra.
    3. Adja hozzá a tanúsítvány ujjlenyomatát ehhez: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Microsoft SQL Server\\*MSSQL.x*\\MSSQLServer\\SuperSocketNetLib\\Certificate.
    4. A Microsoft SQL Server Configuration Manager eszközben állítsa ezt: **ForceEncryption** erre: **Igen**.

6. Exportálja a tanúsítvány nyilvános kulcsát (a .cer fájlt), majd telepítse azt valamennyi Service Fabric csomópont megbízható gyökerébe.

### <a name="configure-the-orchestratordata-database"></a>Az OrchestratorData-adatbázis konfigurálása

1.  Hozzon létre egy üres adatbázist, és nevezze el így: **OrchestratorData**. Ezt az adatbázist a helyi ügynök használja a telepítések szervezéséhez.
2.  Adjon engedélyeket a gMSA helyi ügynöknek (svc-LocalAgent$) **db\_owner** a következő adatbázison:

    1. A fastrukúrában bontsa ki a kiszolgáló nevét, majd bontsa ki ezt: **Security** \> **Logins**, és ezután kattintson a jobb gombbal, majd kattintson erre **New Login**.

        ![Új bejelentkezési parancs](./media/OPSetup_01_NewLogin.png)


    2. Keresse meg a **svc-LocalAgent$** szolgáltatásfiókot. Kattintson erre: **Locations**, válassza ki ezt: **Entire Directory**, kattintson erre: **Object Types**, majd válassza ki ezt: **Service Account**.

        ![Felhasználó, szolgáltatásfiók vagy csoport párbeszédpanel kiválasztása](./media/OPSetup_02_SelectUserServiceAccountOrGroupDialogBox.png)

    3. Állítsa ezt: **ServerRole hozzárendelése** erre: **nyilvános**.
    4. Rendelje hozzá a **db\_owner** adatbázis szerepkör-engedélyt az OrchestratorData adatbázishoz.

### <a name="configure-the-finance-and-operations-database"></a>A Finance and Operations adatbázis konfigurálása

1. Bejelentkezés az LCS-be (<https://lcs.dynamics.com/v2>).
2. Az irányítópulton kattintson a **Közös eszköztár** csempére.
3. Kattintson a **Modell** fülre 
4. A rácsban kattintson a **Dynamics 365 for Operations helyszíni, vállalati kiadás - bemutató adatok** sorra a zip-fájl letöltéséhez.
5. A zip-fájl üres és bemutató adatos .bak fájlokat tartalmaz. Válassza ki a megfelelő .bak fájlt az ön igényei alapján. Ha például bemutató adatokra van szüksége, akkor állítsa vissza az AxBootstrapDB_Demodata.bak fájlt. 
6. Állítsa vissza az AxBootstrapDB_DemoData.bak adatbázist.
7. Nevezze át az **AXDBRAIN** adatbázist.
8. Futtassa a következő lekérdezéseket a visszaállított adatbázison.

    ```
    ALTER DATABASE AXDBRAIN
    SET READ_COMMITTED_SNAPSHOT ON
    GO
    
    ALTER DATABASE AXDBRAIN
    SET ALLOW_SNAPSHOT_ISOLATION ON
    GO
    ```

4. Az adatbázis-fájlok frissítése:

    1. Kattintson a jobb gombbal az adatbázisra, majd kattintson a **Tulajdonságok** lehetőségre.
    2. Kattintson erre: **fájlok** az adatbázis-fájl tulajdonságainak módosításához.
    3. A **Kezdeti méret (MB)** mezőbe írjon be egy értéket, amely több, mint 5,120.

        ![Adatbázis-tulajdonságok párbeszédpanel](./media/OPSetup_03_DatabasePropertiesDialogBox.png)

    4. Erre vonatkozóan: **AXDBBuild\_Data**, állítsa be a **Autogrowth/Maximize** mezőt **200** megabájtra (MB).
    5. Erre vonatkozóan: **AXDBBuild\_Log**, állítsa be a **Autogrowth/Maximize** mezőt **500** megabájtra (MB).

        ![Automatikus növekedési párbeszédpanel módosítása](./media/OPSetup_04_ChangeAutogrowthDialogBox.png)

5. Hozzon létre egy új felhasználót, ami számára az SQL-hitelesítés engedélyezett (axdbadmin).
6. Használja a következő táblázatban található információkat a felhasználók és az adatbázis-szerepkörök leképezésére.

    | Felhasználó             | Típus    | Adatbázis-szerepkör |
    |------------------|---------|---------------|
    | svc-AXSF$        | gMSA    | db\_owner     |
    | svc-LocalAgent$  | gMSA    | db\_owner     |
    | svc-FRPS$        | gMSA    | db\_owner     |
    | svc-FRAS$        | gMSA    | db\_owner     |
    | axdbadmin        | SqlUser | db\_owner     |

7. Adjon hozzáférést az svc-AXSF$ felhasználónak és az axdbadmin SQL-felhasználónak a tempdb adatbázisban a következő szerepkörökhöz:

    - db\_datareader
    - db\_datawriter
    - db\_ddladmin

8. A Management Studio programban futtassa a következő Transact SQL (T-SQL) parancsokat:

    ```
    GRANT VIEW SERVER STATE TO axdbadmin
    GRANT VIEW SERVER STATE TO [contososqlao\svc-AXSF$]
    ```
9. Futtassa a következő parancsot:
```
.\Reset-DatabaseUsers.ps1 -DatabaseServer ‘<FQDN of the SQL server>’ -DatabaseName '<AX database name>'
```

### <a name="configure-the-financial-reporting-database"></a>A pénzügyi jelentéskészítés adatbázis konfigurálása

1.  Hozzon létre egy üres adatbázist, és nevezze el így: **FinancialReporting**.
2.  Használja a következő táblázatban található információkat a felhasználók és az adatbázis-szerepkörök leképezésére.

    | Felhasználó             | Típus | Adatbázis-szerepkör |
    |------------------|------|---------------|
    | svc-LocalAgent$  | gMSA | db\_owner     |
    | svc-FRPS$        | gMSA | db\_owner     |
    | svc-FRAS$        | gMSA | db\_owner     |

### <a name="encrypt-credentials"></a>Titkosítsa a hitelesítő adatokat

1. Minden kliens gépen telepítse a LocalMachine\\My certificate tárolóban található titkosítási tanúsítványt.
2. Adjon olvasási engedélyt ezen tanúsítvány titkos kulcsához az aktuális felhasználónak.
3. Hozza létre a Credentials.json fájlt az itt látható módon.

    ```
    {
        "AosPrincipal": {
            "AccountPassword": "<encryptedDomainUserPassword>"
        },
        "AosSqlAuth": {
            "SqlUser": "<encryptedSqlUser>",
            "SqlPwd": "<encryptedSqlPassword>"
        }
    }
    ```

    - Az **AccountPassword** az AOS-tartomány felhasználójának titkosított tartomány felhasználó jelszava (contoso\\axserviceuser).
    - Az **SqlUser** az a titkosított SQL felhasználó (axdbadmin), amely hozzáféréssel rendelkezik a Finance and Operations adatbázishoz (AXDBRAIN), és a **SqlPassword** a titkosított SQL jelszó.

4. Másolja az alábbi .json fájlt az SMB fájlmegosztásba: \\\\AX7SQLAOFILE1\\ügynök\\hitelesítő adatok\\Credentials.json.
5. Frissítése a Credentials.json fájlt titkosított értékekkel.

    ```
    # Service fabric API to encrypt text and copy it to the clipboard.
    Invoke-ServiceFabricEncryptText -Text '<textToEncrypt>' -CertThumbprint '<DataEncipherment Thumbprint>' -CertStore -StoreLocation LocalMachine -StoreName My | clip
    ```

    1. A Credentials.json fájlban cserélje le ezt: **\<encryptedDomainUserPassword\>** a titkosított tartomány jelszóval.
    2. Cserélje le ezt: **\<encryptedSqlUser\>** a titkosított Finance and Operations SQL felhasználóval.
    3. Cserélje le ezt: **\<encryptedSqlPassword\>** a Finance and Operations SQL jelszóval.
    
### <a name="set-up-ssrs"></a>SSRS beállítása

1.  Mielőtt hozzálátna, győződjön meg róla, hogy a témakör elején felsorolt előfeltételek telepítve vannak-e.
2.  Kövesse ezeket a lépéseket: [Az SQL Server Reporting Services konfigurálása helyszíni telepítéshez](../analytics/configure-ssrs-on-premises.md)

### <a name="configure-ad-fs"></a>Konfigurálja az AD FS-t

Ahhoz, hogy végrehajthassa ezt az eljárást, telepítenie kell az AD FS-t a Windows Server 2016-on. További információkért az AD FS telepítéséről lásd: [Windows Server 2016 és 2012 R2 AD FS telepítési útmutató](https://docs.microsoft.com/en-us/windows-server/identity/ad-fs/deployment/windows-server-2012-r2-ad-fs-deployment-guide).

A Finance and Operations-nek szüksége van az AD SF alapértelmezett kulcsrakész konfigurációján túli konfigurációkra is. Az alábbi lépések bemutatásához tegyük fel, hogy a Windows PowerShell egy olyan gépen fut, amelyen telepítve van az AD SF szerepkör-szolgáltatás. A felhasználói fióknak az AD FS felügyeletéhez megfelelő engedélyekkel kell rendelkeznie. Például a felhasználónak tartomány rendszergazdai fiókkal kell rendelkeznie.

1. Úgy konfigurálja az AD FS azonosítót, hogy az megegyezzen az AD FS jogkivonat kibocsátójával.

    ```
    $adfsProperties = Get-AdfsProperties
    Set-AdfsProperties -Identifier $adfsProperties.IdTokenIssuer
    ```

2. Intranetes hitelesítési kapcsolatokhoz ajánlott letiltani a Windows integrált hitelesítést (WIA), kivéve, ha az AD FS-t vegyes környezetekhez konfigurálta. További információkért a WIA konfigurálásáról úgy, hogy használható legyen az AD FS-sel, lásd: [Böngészők konfigurálása a Windows integrált hitelesítés (WIA) AD FS-sel való használatához](https://docs.microsoft.com/en-us/windows-server/identity/ad-fs/operations/configure-ad-fs-browser-wia).

   ```
   Set-AdfsGlobalAuthenticationPolicy -PrimaryIntranetAuthenticationProvider FormsAuthentication, MicrosoftPassportAuthentication
   ```

3. A bejelentkezéshez a felhasználó e-mail címének egy elfogadható hitelesítési bemenetnek kell lennie.

   ```
   Add-Type -AssemblyName System.Net
   $fdqn = ([System.Net.Dns]::GetHostEntry('localhost').HostName).ToLower()
   $domainName = $fdqn.Substring($fdqn.IndexOf('.')+1)
   Set-AdfsClaimsProviderTrust -TargetIdentifier 'AD AUTHORITY' -AlternateLoginID mail -LookupForests $domainName
   ```

Ahhoz, hogy az AD FS megbízza a Finance and Operations-t a hitelesítésváltás érdekében, különböző alkalmazás-bejegyzéseket kell regisztrálni az AD FS-ben az AD FS alkalmazáscsoport alatt. A telepítési folyamat felgyorsítása és a hibák csökkentése érdekében használhatja a következő parancsfájlt a regisztrációhoz. Másolja a Publish-ADFSApplicationGroup.ps1 parancsfájlt és a D365FO-OP mappát egy olyan gépre, amire telepítve van az AD FS szerepkör-szolgáltatás. Futtassa a parancsfájlt egy olyan felhasználói fiók használatával, ami rendelkezik a megfelelő engedélyekkel az AD FS felügyeletéhez, mint például egy rendszergazdai fiók. További információkért a parancsfájl használatáról olvassa el a parancsfájlban található dokumentációt. Jegyezze fel a kimenetben meghatározott kliens azonosítókat, mivel ezeket az adatokat az LCS egy későbbi lépésben kéri.

```
# Host URL is your DNS record\host name for accessing the AOS
.\Publish-ADFSApplicationGroup.ps1 -HostUrl 'ax.d365ffo.onprem.contoso.com'
```

Az AD FS felügyeleti konzoljának az alábbi ábrára kell hasonlítania. A Kiszolgálókezelő megnyitásához kattintson erre: **Tools** \> **AD FS Management**, és a fa nézet bal alsó sarkában kattintson erre: **alkalmazás csoportok**. További részletekért kattintson kétszer az alkalmazás csoportra.

![Alkalmazás csoport tulajdonságai](./media/OPSetup_05_ApplicatioGroupProperties.png)

Végső megerősítésként győződjön meg arról, hogy hozzáférése van az AD FS OpenID konfigurációs URL-címéhez egy **AOSNodeType** típusú Service Fabric csomóponton. Ehhez nyissa meg a `https://<adfs-dns-name>/adfs/.well-known/openid-configuration` webhelyet egy böngészőben. Ha egy üzenetet kap, mely arról tájékoztatja, hogy a webhely nem biztonságos, akkor nem adta hozzá az AD FS SSL tanúsítványt a megbízható legfelső szintű hitelesítésszolgáltatók tárolóhoz. Ez a lépés le van írva az AD FS telepítési útmutatójában. Ha sikeresen hozzáfér az URL-címhez, akkor egy JavaScript Object Notation (JSON) fájl érkezik, ami tartalmazza az ön AD FS konfigurációját, és látni fogja, hogy az ön AD FS URL-címe megbízható.

Ezzel az infrastruktúra telepítése befejeződött. Az alábbi szakaszok leírják, hogy hogyan juthat el ehhez: [LCS](https://lcs.dynamics.com) a csatlakoztató beállításához és a Dynamics 365 for Finance and Operations környezet telepítéséhez.

## <a name="configure-connector-and-install-on-premises-local-agent"></a>Csatlakoztató konfigurálása és helyszíni ügynök telepítése

1. Jelentkezzen be ide: [LCS](https://lcs.dynamics.com/), és nyissa meg a helyszíni megvalósítás projektet.
2. A hamburger menüben kattintson erre: **Projektbeállítások**.

    ![Projektbeállítások parancs](./media/OPSetup_06_ProjectSettings.png)

3. Kattintson erre: **Helyszíni csatlakoztatók**.
4. Kattintson a **Hozzáadás** elemre új csatlakoztató létrehozásához.
5. Töltse le az ügynök telepítőprogramját az **Állomás infrastruktúra beállítása** lapon.

    ![Töltse le az ügynök telepítőprogram gombját az állomás infrastruktúra beállítása lapon.](./media/OPSetup_07_DownloadAgentInstaller.png)

6. Ellenőrizze, hogy a zip-fájl zárolatlan. Kattintson a jobb gombbal a fájlra, kattintson erre: **tulajdonságok**, majd válassza ki ezt: **Zárolás feloldása**.
7. Bontsa ki az ügynök telepítőprogramját az egyik **OrchestratorType** típusú Service Fabric csomóponton.
8. írja be a konfigurációs beállításokat az **Ügynök konfigurálása** mezőbe.
9. Mentse a konfigurációt, és kattintson erre: **Konfigurációk letöltése** a localagent-config.json konfigurációs fájl letöltéséhez.

    ![Töltse le az ügynök konfigurálása lapon a konfigurációk gombot](./media/OPSetup_08_DownloadConfigurations.png)

10. Másolja a localagent-config.json fájlt az ügynök telepítőcsomagját tartalmazó gépre.
11. Futtassa a következő parancsot egy parancssori képernyőn az ügynök telepítőprogramját tartalmazó mappa felkeresésével.

    ```
    LocalAgentCLI.exe Install <path to config.json>
    ```

    > [!NOTE]
    > A parancsot futtató felhasználónak rendelkeznie kell **db\_owner** engedélyekkel az OrchestratorData adatbázison.
    
12. A helyi ügynök sikeres telepítése után térjen vissza az LCS-en belüli helyszíni csatlakoztatójához.
13. A **Telepítés ellenőrzése** lapon kattintson az **Üzenet ügynök** gombra. Ezzel teszteli az LCS kapcsolatát az ön helyi ügynökéhez. A kapcsolat sikeres létrejötte után a lapnak az alábbi ábra által mutatott módon kell kinéznie.

     ![Az ügynök ellenőrzése](./media/ValidateAgent.PNG)

## <a name="deploy-your-dynamics-365-for-finance-and-operations-on-premises-environment"></a>Telepítse az ön Dynamics 365 for Finance and Operations (helyszíni) környezetét

1. Keresse meg az LCS-ben az ön helyszíni projektjét, ugorjon ide: **Környezet**, majd ide: **Védőfal**, és végül kattintson erre: **Konfigurálás**
2. Válassza ki ezt: **Környezet topológia**, és kövesse a varázsló lépéseit a telepítés elindításához.
3. A helyi ügynök felveszi a telepítési kérelmet, elindítja a telepítést, majd kapcsolatot teremt az LCS-szel, amikor készen áll.

