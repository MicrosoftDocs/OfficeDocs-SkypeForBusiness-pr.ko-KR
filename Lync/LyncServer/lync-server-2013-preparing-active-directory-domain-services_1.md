---
title: 'Lync Server 2013: Active Directory 도메인 서비스 준비'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing Active Directory Domain Services
ms:assetid: 7b0d9aa4-f1ab-4578-b22f-b802b6ed1530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398607(v=OCS.15)
ms:contentKeyID: 48184583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b3af3ce7940b8d0fb58a74b4a8f7bb0a21c5e2d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506995"
---
# <a name="preparing-active-directory-domain-services-in-lync-server-2013"></a>Lync Server 2013에서 Active Directory 도메인 서비스 준비

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-02-19_

Lync Server 2013에서는 Lync Server 배포 마법사를 사용 하 여 Active Directory 도메인 서비스를 준비 하거나 Lync Server 관리 셸 cmdlet을 직접 사용할 수 있습니다. 또한 이 항목의 뒷부분에 설명된 대로 도메인 컨트롤러에서 ldifde.exe 명령줄 도구를 직접 사용할 수 있습니다.

Lync Server 배포 마법사가 각 Active Directory 준비 작업을 안내 합니다. 배포 마법사는 Lync Server 관리 셸 cmdlet을 실행 합니다. 이 도구는 단일 도메인 및 단일 포리스트 토폴로지 또는 이와 유사한 토폴로지 환경에 유용합니다.

<div>


> [!IMPORTANT]  
> 도메인 컨트롤러에서 32 비트 버전의 운영 체제를 실행 하는 포리스트 또는 도메인에 Lync Server를 배포할 수 있습니다 (자세한 내용은 <A href="lync-server-2013-active-directory-infrastructure-requirements.md">Active Directory 인프라 요구 사항 (Lync Server 2013의</A>경우). 그러나 배포 마법사와 지원 파일이 64 비트 전용 이므로 이러한 환경에서는 Lync Server 배포 마법사를 사용 하 여 스키마, 포리스트 및 도메인 준비를 실행할 수 없습니다. 대신, ldifde.exe 및 연결 된 .ldf 파일을 32 비트 도메인 컨트롤러에 사용 하 여 스키마, 포리스트 및 도메인을 준비할 수 있습니다. 이 항목의 뒷부분에 나오는 "Cmdlet 및 Ldifde.exe 사용" 섹션을 참조 하십시오.



</div>

Lync Server 관리 셸 cmdlet을 사용 하 여 원격으로 또는 좀 더 복잡 한 환경에 대해 작업을 실행할 수 있습니다.

<div>

## <a name="active-directory-preparation-prerequisites"></a>Active Directory 준비를 위한 필수 구성 요소

Windows Server 2012, Windows Server 2012 R2 또는 Windows Server 2008 R2 SP1 (64 비트)을 실행 하는 컴퓨터에서 Active Directory 준비 단계를 실행 해야 합니다. Active Directory 준비에는 Lync Server 관리 셸 및 OCSCore 필요 합니다.

Active Directory 준비 작업을 실행하려면 다음 구성 요소가 필요합니다.

  - Lync Server Core 구성 요소 (OCScore.msi)
    
    <div>
    

    > [!NOTE]  
    > Active Directory 준비를 위해 Lync Server 관리 셸을 사용 하려는 경우 먼저 Lync Server 배포 마법사를 실행 하 여 핵심 구성 요소를 설치 해야 합니다.

    
    </div>

  - Microsoft .NET Framework 4.5
    
    <div>
    

    > [!NOTE]  
    > Windows Server 2012 및 Windows Server 2012 r 2의 경우 서버 관리자를 사용 하 여 .NET Framework 4.5을 설치 하 고 정품 인증 합니다. 자세한 내용은 <A href="lync-server-2013-additional-software-requirements.md">Lync Server 2013에 대 한 추가 소프트웨어 요구 사항</A>에서 "Microsoft .net Framework 4.5"를 참조 하세요. Windows Server 2008 r 2의 경우 &nbsp; &nbsp; Microsoft 웹 사이트에서 <A href="https://www.microsoft.com/download/details.aspx?id=30653">.net Framework 4.5</A> 를 다운로드 하 여 설치 합니다.

    
    </div>

  - RSAT(원격 서버 관리 도구)
    
    <div>
    

    > [!NOTE]  
    > 도메인 컨트롤러 대신 구성원 서버에서 Active Directory 준비 단계를 실행하려면 몇 가지 RSAT 도구가 필요합니다. 서버 관리자의 ad DS 및 AD LDS 도구 노드에서 AD DS 스냅인 및 명령줄 도구와 Windows PowerShell 용 Active Directory 모듈을 설치 합니다.

    
    </div>

  - Microsoft Visual c + + 11 재배포 가능 패키지
    
    <div>
    

    > [!NOTE]  
    > 설치 시 이 필수 구성 요소를 설치할지 묻는 메시지가 나타납니다(컴퓨터에 이미 설치되지 않은 경우). 이 패키지는 자동으로 제공되므로 별도로 구입할 필요가 없습니다.

    
    </div>

  - Windows PowerShell 3.0 (64 비트)
    
    Windows Server 2012 및 Windows Server 2012 r 2의 경우 Lync Server 2013 설치에 Windows PowerShell 3.0이 포함 되어 있어야 합니다. Windows Server 2008 r 2의 경우 Windows PowerShell 3.0을 설치 하거나 업그레이드 해야 합니다. 자세한 내용은 [Windows PowerShell 3.0 For Lync Server 2013을](lync-server-2013-installing-windows-powershell-3-0.md) 참조 하십시오.

</div>

<div>

## <a name="administrator-rights-and-roles"></a>관리자 권한 및 역할

다음 표에서는 Active Directory 준비 작업에 필요한 관리자 권한 및 역할을 보여 줍니다.

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
<td><p>Schema Admins 그룹의 구성원(포리스트 루트 도메인) 및 관리자 권한(스키마 마스터)</p></td>
</tr>
<tr class="even">
<td><p>포리스트 준비</p></td>
<td><p>Enterprise Admins 그룹의 구성원(포리스트)</p></td>
</tr>
<tr class="odd">
<td><p>도메인 준비</p></td>
<td><p>Enterprise Admins 또는 Domain Admins 그룹의 구성원(지정된 도메인)</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="active-directory-preparation-cmdlets"></a>Active Directory 준비 Cmdlet

다음 표에서는 AD ds를 준비 하는 데 사용 되는 Lync Server 관리 셸 cmdlet과 Microsoft Office Communications Server 2007 r 2에서 AD DS를 준비 하는 데 사용 되는 LcsCmd 명령에 대해 비교 합니다.

### <a name="cmdlets-compared-to-lcscmd"></a>Cmdlet와 LcsCmd 비교

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
<td><p>Lcscmd /forest /action:SchemaPrep /SchemaType:Server</p></td>
</tr>
<tr class="even">
<td><p>Get-CsAdServerSchema</p></td>
<td><p>Lcscmd /forest /action:CheckSchemaPrepState</p></td>
</tr>
<tr class="odd">
<td><p>Enable-CsAdForest</p></td>
<td><p>Lcscmd /forest /action:ForestPrep</p></td>
</tr>
<tr class="even">
<td><p>Disable-CsAdForest</p></td>
<td><p>Lcscmd /forest /action:ForestUnprep</p></td>
</tr>
<tr class="odd">
<td><p>Get-CsAdForest</p></td>
<td><p>Lcscmd /forest /action:CheckForestPrepState</p></td>
</tr>
<tr class="even">
<td><p>Enable-CsAdDomain</p></td>
<td><p>Lcscmd /domain /action:DomainPrep</p></td>
</tr>
<tr class="odd">
<td><p>Disable-CsAdDomain</p></td>
<td><p>Lcscmd /domain /action: DomainUnprep</p></td>
</tr>
<tr class="even">
<td><p>Get-CsAdDomain</p></td>
<td><p>Lcscmd /domain /action:CheckDomainPrepState</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="locked-down-active-directory-requirements"></a>잠긴 Active Directory 요구 사항

조직에서 권한 상속이 비활성화되어 있거나 인증된 사용자 권한을 비활성화해야 하는 경우 도메인 준비 작업 중에 추가 단계를 수행해야 합니다. 자세한 내용은 [Lync Server 2013에서 잠긴 Active Directory 도메인 서비스 준비](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)를 참조 하세요.

</div>

<div>

## <a name="custom-container-permissions"></a>사용자 지정 컨테이너 권한

조직에서 세 가지 기본 제공 컨테이너(사용자, 컴퓨터 및 도메인 컨트롤러) 대신 사용자 지정 컨테이너를 사용하는 경우 Authenticated Users 그룹에 대해 사용자 지정 컨테이너에 대한 읽기 권한을 부여해야 합니다. 컨테이너에 대한 읽기 권한은 도메인을 준비하는 데 필요합니다. 자세한 내용은 [Lync Server 2013에 대 한 도메인 준비](lync-server-2013-preparing-domains.md)를 참조 하십시오.

</div>

<div>

## <a name="using-cmdlets-and-ldifdeexe"></a>Cmdlet 및 Ldifde.exe 사용

Lync Server 배포 마법사의 **스키마 준비** 단계와 **Install-csadserverschema** cmdlet은 64 비트 운영 체제를 실행 하는 도메인 컨트롤러에서 Active Directory 스키마를 확장 합니다. 32비트 운영 체제를 실행하는 도메인 컨트롤러에서 Active Directory 스키마를 확장해야 하는 경우 구성원 서버에서 원격으로 **Install-CsAdServerSchema** cmdlet를 실행할 수 있습니다(권장 방법). 그러나 도메인 컨트롤러에서 스키마 준비를 직접 실행해야 하는 경우에는 Ldifde.exe 도구를 사용하여 스키마 파일을 가져올 수 있습니다. Ldifde.exe 도구는 대부분의 Windows 운영 체제 버전에 포함되어 있습니다.

Ldifde.exe를 사용하여 스키마 파일을 가져오는 경우 이전 버전에서 마이그레이션 중인지 또는 새로 설치하는 중인지에 관계없이 네 개 파일을 모두 가져와야 합니다. 가져와야 하는 파일의 순서는 다음과 같습니다.

1.  ExternalSchema .ldf

2.  ServerSchema .ldf

3.  Backcompatschema.ldf-이전

4.  VersionSchema .ldf

<div>


> [!NOTE]  
> 이 네 개의 .ldf 파일은 설치 미디어 또는 다운로드의 \Support\Schema 디렉터리에 있습니다.



</div>

Ldifde.exe를 사용하여 스키마 마스터인 도메인 컨트롤러에서 스키마 파일 네 개를 가져오려면 다음 형식을 사용합니다.

    ldifde -i -v -k -s <DCName> -f <Schema filename> -c DC=X <defaultNamingContext> -j logFilePath -b <administrator account> <logon domain> <password>

예:

    ldifde -i -v -k -s DC1 -f ServerSchema.ldf -c DC=X "DC=contoso,DC=com" -j C:\BatchImportLogFile -b Administrator contoso password

<div>


> [!NOTE]  
> b 매개 변수는 다른 사용자로 로그인한 경우에만 사용합니다. 필요한 사용자 권한에 대한 자세한 내용은 이 항목의 앞부분에 있는 "관리자 권한 및 역할" 섹션을 참조하십시오.



</div>

Ldifde.exe를 사용하여 스키마 마스터가 아닌 도메인 컨트롤러에서 스키마 파일 네 개를 가져오려면 다음 형식을 사용합니다.

    ldifde -i -v -k -s <SchemaMasterFQDN> -f <Schema filename> -c DC=X <rootDomainNamingContext> -j logFilePath -b <administrator account> <domain> <password>

Ldifde를 사용 하는 방법에 대 한 자세한 내용은 Microsoft 기술 자료 문서 237677, "LDIFDE를 사용 하 여 Active Directory로 디렉터리 개체 가져오기 및 내보내기"를 참조 하세요 [https://go.microsoft.com/fwlink/p/?linkId=132204](https://go.microsoft.com/fwlink/p/?linkid=132204) .

</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 Active Directory 스키마 준비](lync-server-2013-preparing-the-active-directory-schema.md)

  - [Lync Server 2013에 대 한 포리스트 준비](lync-server-2013-preparing-the-forest.md)

  - [Lync Server 2013에 대 한 도메인 준비](lync-server-2013-preparing-domains.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

