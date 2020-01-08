---
title: 'Lync Server 2013:  Active Directory 도메인 서비스 준비'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing Active Directory Domain Services
ms:assetid: 7b0d9aa4-f1ab-4578-b22f-b802b6ed1530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398607(v=OCS.15)
ms:contentKeyID: 48184583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7deb5594c0d3c009ee4b10565bc4dbe12f56d2c4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-active-directory-domain-services-in-lync-server-2013"></a>Lync Server 2013에서 Active Directory 도메인 서비스 준비

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-02-19_

Lync Server 2013에서 Lync Server 배포 마법사를 사용 하 여 Active Directory 도메인 서비스를 준비 하거나 Lync Server 관리 셸 cmdlet을 직접 사용할 수 있습니다. 이 항목의 뒷부분에 설명 된 대로 도메인 컨트롤러에서 ldifde 명령줄 도구를 직접 사용할 수도 있습니다.

Lync Server 배포 마법사가 각 Active Directory 준비 작업을 안내 합니다. 배포 마법사는 Lync Server Management Shell cmdlet을 실행 합니다. 이 도구는 단일 도메인 및 단일 포리스트 토폴로지 또는 기타 유사한 토폴로지가 있는 환경에 유용 합니다.

<div>


> [!IMPORTANT]  
> 도메인 컨트롤러가 일부 운영 체제의 32 비트 버전을 실행 하는 포리스트나 도메인에 Lync Server를 배포할 수 있습니다 (자세한 내용은 <A href="lync-server-2013-active-directory-infrastructure-requirements.md">Lync server 2013에 대 한 Active Directory 인프라 요구 사항</A>참조). 그러나 배포 마법사와 지원 파일이 64 비트 전용 이므로 이러한 환경에서 Lync Server 배포 마법사를 사용 하 여 스키마, 포리스트 및 도메인 준비를 실행할 수 없습니다. 대신, ldifde와 32 비트 도메인 컨트롤러의 연결 된 .ldf 파일을 사용 하 여 스키마, 포리스트 및 도메인을 준비할 수 있습니다. 이 항목의 뒷부분에 있는 "Cmdlet 및 Ldifde 사용" 섹션을 참조 하세요.



</div>

Lync Server Management Shell cmdlet을 사용 하 여 작업을 원격으로 실행 하거나 복잡 한 환경을 만들 수 있습니다.

<div>

## <a name="active-directory-preparation-prerequisites"></a>Active Directory 준비 필수 조건

Windows Server 2012, Windows Server 2012 R2 또는 Windows Server 2008 R2 SP1 (64 비트)을 실행 하는 컴퓨터에서 Active Directory 준비 단계를 실행 해야 합니다. Active Directory 준비에는 Lync Server Management Shell 및 OCSCore 필요 합니다.

Active Directory 준비 작업을 실행 하려면 다음 구성 요소가 필요 합니다.

  - Lync Server Core 구성 요소 (Ocx 점수. msi)
    
    <div>
    

    > [!NOTE]  
    > Active Directory 준비를 위해 Lync Server Management Shell을 사용할 계획 이라면 먼저 Lync Server 배포 마법사를 실행 하 여 핵심 구성 요소를 설치 해야 합니다.

    
    </div>

  - Microsoft .NET Framework 4.5
    
    <div>
    

    > [!NOTE]  
    > Windows Server 2012 및 Windows Server 2012 R2의 경우 서버 관리자를 사용 하 여 .NET Framework 4.5을 설치 하 고 정품 인증 합니다. 자세한 내용은 <A href="lync-server-2013-additional-software-requirements.md">Lync Server 2013에 대 한 추가 소프트웨어 요구 사항</A>에서 "Microsoft .net Framework 4.5"을 참조 하세요. Windows Server&nbsp;2008&nbsp;R2의 경우 Microsoft 웹 사이트에서 <A href="http://www.microsoft.com/en-us/download/details.aspx?id=30653">.net Framework 4.5</A> 을 다운로드 하 여 설치 합니다.

    
    </div>

  - RSAT (원격 서버 관리 도구)
    
    <div>
    

    > [!NOTE]  
    > 도메인 컨트롤러가 아닌 구성원 서버에서 Active Directory 준비 단계를 실행 하는 경우 일부 RSAT 도구가 필요 합니다. 서버 관리자의 AD DS 및 AD LDS 도구 노드에서 AD DS 스냅인 및 명령줄 도구와 Windows PowerShell 용 Active Directory 모듈을 설치 합니다.

    
    </div>

  - Microsoft Visual c + + 11 재배포 가능 패키지
    
    <div>
    

    > [!NOTE]  
    > 설치 프로그램이 컴퓨터에 아직 설치 되어 있지 않은 경우이 필수 구성 요소를 설치 하 라는 메시지가 표시 됩니다. 패키지는 사용자에 게 제공 되며 별도로 구입 하지 않아도 됩니다.

    
    </div>

  - Windows PowerShell 3.0 (64 비트)
    
    Windows Server 2012 및 Windows Server 2012 R2의 경우 Windows PowerShell 3.0을 Lync Server 2013 설치에 포함 해야 합니다. Windows Server 2008 R2의 경우 Windows PowerShell 3.0을 설치 하거나 업그레이드 해야 합니다. 자세한 내용은 [Lync Server 2013 용 Windows PowerShell 3.0 설치](lync-server-2013-installing-windows-powershell-3-0.md) 를 참조 하세요.

</div>

<div>

## <a name="administrator-rights-and-roles"></a>관리자 권한 및 역할

다음 표에서는 각 Active Directory 준비 작업에 필요한 관리 권한 및 역할을 보여 줍니다.

### <a name="user-rights-required-for-active-directory-preparation"></a>Active Directory 준비에 필요한 사용자 권한

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>절차</th>
<th>권한 또는 역할</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>스키마 준비</p></td>
<td><p>포리스트 루트 도메인 및 스키마 마스터의 관리자 권한에 대 한 스키마 관리자 그룹의 구성원</p></td>
</tr>
<tr class="even">
<td><p>포리스트 준비</p></td>
<td><p>포리스트에 대 한 Enterprise Admins 그룹의 구성원</p></td>
</tr>
<tr class="odd">
<td><p>도메인 준비</p></td>
<td><p>지정 된 도메인에 대 한 엔터프라이즈 관리자 또는 Domain Admins 그룹의 구성원</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="active-directory-preparation-cmdlets"></a>Active Directory 준비 Cmdlet

다음 표에서는 AD DS를 준비 하는 데 사용 되는 Lync Server Management Shell cmdlet을 Microsoft Office Communications Server 2007 R2에서 AD DS를 준비 하는 데 사용 되는 LcsCmd 명령으로 비교 합니다.

### <a name="cmdlets-compared-to-lcscmd"></a>LcsCmd와 비교 되는 cmdlet

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Cmdlet</th>
<th>LcsCmd</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Install-CsAdServerSchema</p></td>
<td><p>Lcscmd/forest/action: SchemaPrep/SchemaType: 서버</p></td>
</tr>
<tr class="even">
<td><p>Get-CsAdServerSchema</p></td>
<td><p>Lcscmd /forest /action:CheckSchemaPrepState</p></td>
</tr>
<tr class="odd">
<td><p>Enable-CsAdForest</p></td>
<td><p>Lcscmd/forest/action: ForestPrep</p></td>
</tr>
<tr class="even">
<td><p>사용 안 함-CsAdForest</p></td>
<td><p>Lcscmd /forest /action:ForestUnprep</p></td>
</tr>
<tr class="odd">
<td><p>Get-CsAdForest</p></td>
<td><p>Lcscmd /forest /action:CheckForestPrepState</p></td>
</tr>
<tr class="even">
<td><p>Enable-CsAdDomain</p></td>
<td><p>Lcscmd/domain/action: DomainPrep</p></td>
</tr>
<tr class="odd">
<td><p>Disable-CsAdDomain</p></td>
<td><p>Lcscmd/domain/action: DomainUnprep</p></td>
</tr>
<tr class="even">
<td><p>Get-CsAdDomain</p></td>
<td><p>Lcscmd/domain/action: CheckDomainPrepState</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="locked-down-active-directory-requirements"></a>Active Directory 요구 사항 잠금

권한 상속을 사용 하지 않거나 인증 된 사용자 권한을 조직에서 사용 하지 않도록 설정 해야 하는 경우 도메인 준비 중에 추가 단계를 수행 해야 합니다. 자세한 내용은 [Lync Server 2013에서 잠겨진 Active Directory 도메인 서비스 준비](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)를 참조 하세요.

</div>

<div>

## <a name="custom-container-permissions"></a>사용자 지정 컨테이너 사용 권한

조직에서 세 가지 기본 제공 컨테이너 (즉, 사용자, 컴퓨터 및 도메인 컨트롤러) 대신 사용자 지정 컨테이너를 사용 하는 경우 인증 된 사용자 그룹에 대 한 사용자 지정 컨테이너에 대 한 읽기 권한을 부여 해야 합니다. 도메인 준비에는 컨테이너에 대 한 읽기 권한이 필요 합니다. 자세한 내용은 [Lync Server 2013에 대 한 도메인 준비](lync-server-2013-preparing-domains.md)를 참조 하세요.

</div>

<div>

## <a name="using-cmdlets-and-ldifdeexe"></a>Cmdlet 및 Ldifde 사용

Lync Server 배포 마법사의 **스키마 준비** 단계와 **설치-CsAdServerSchema** cmdlet은 64 비트 운영 체제를 실행 하는 도메인 컨트롤러에서 Active Directory 스키마를 확장 합니다. 32 비트 운영 체제를 실행 하는 도메인 컨트롤러에서 Active Directory 스키마를 확장 해야 하는 경우 구성원 서버에서 원격으로 **설치-CsAdServerSchema** cmdlet을 실행할 수 있습니다 (권장 되는 방법). 그러나 도메인 컨트롤러에서 직접 스키마 준비를 실행 해야 하는 경우에는 Ldifde 도구를 사용 하 여 스키마 파일을 가져올 수 있습니다. Ldifde 도구에는 대부분의 Windows 운영 체제 버전이 함께 제공 됩니다.

Ldifde를 사용 하 여 스키마 파일을 가져오는 경우 이전 버전에서 마이그레이션하는 지 또는 새로 설치를 수행 하 든 관계 없이 네 개의 파일을 모두 가져와야 합니다. 다음 순서 대로 가져와야 합니다.

1.  ExternalSchema. .ldf

2.  ServerSchema. .ldf

3.  BackCompatSchema

4.  VersionSchema. .ldf

<div>


> [!NOTE]  
> 4 .ldf 파일은 설치 미디어의 \Support\Schema 디렉터리 또는 다운로드에 있습니다.



</div>

Ldifde를 사용 하 여 스키마 마스터인 도메인 컨트롤러에 있는 네 개의 스키마 파일을 가져오려면 다음 형식을 사용 합니다.

    ldifde -i -v -k -s <DCName> -f <Schema filename> -c DC=X <defaultNamingContext> -j logFilePath -b <administrator account> <logon domain> <password>

예를 들면 다음과 같습니다.

    ldifde -i -v -k -s DC1 -f ServerSchema.ldf -c DC=X "DC=contoso,DC=com" -j C:\BatchImportLogFile -b Administrator contoso password

<div>


> [!NOTE]  
> 다른 사용자로 로그인 한 경우에만 b 매개 변수를 사용 합니다. 필요한 사용자 권한에 대 한 자세한 내용은이 항목의 앞부분에 있는 "관리자 권한 및 역할" 섹션을 참조 하세요.



</div>

Ldifde를 사용 하 여 스키마 마스터가 아닌 도메인 컨트롤러에서 네 개의 스키마 파일을 가져오려면 다음 형식을 사용 합니다.

    ldifde -i -v -k -s <SchemaMasterFQDN> -f <Schema filename> -c DC=X <rootDomainNamingContext> -j logFilePath -b <administrator account> <domain> <password>

Ldifde를 사용 하는 방법에 대 한 자세한 내용은 Microsoft 기술 자료 문서 237677, "LDIFDE를 사용 하 여 Active Directory로 디렉터리 개체 [http://go.microsoft.com/fwlink/p/?linkId=132204](http://go.microsoft.com/fwlink/p/?linkid=132204)가져오기 및 내보내기"를 참조 하세요.

</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 Active Directory 스키마 준비](lync-server-2013-preparing-the-active-directory-schema.md)

  - [Lync Server 2013에 대한 포리스트 준비](lync-server-2013-preparing-the-forest.md)

  - [Lync Server 2013에 대한 도메인 준비](lync-server-2013-preparing-domains.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

