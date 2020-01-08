---
title: 'Lync Server 2013: 보관 된 Lync Server 2013 데이터를 검색 하도록 Microsoft SharePoint Server 2013 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring SharePoint Server 2013 to search for archived Lync Server 2013 data
ms:assetid: 17f49365-8778-4962-a41b-f96faf6902f1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687978(v=OCS.15)
ms:contentKeyID: 49733566
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 381db352aae635358dfd62cc1965ea238960bf8a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976209"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-sharepoint-server-2013-to-search-for-archived-microsoft-lync-server-2013-data"></a>Microsoft SharePoint Server 2013에서 보관 된 Microsoft Lync Server 2013 데이터를 검색 하도록 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-02-04_

Microsoft Lync Server 2013 대신 Microsoft Exchange Server 2013에서 인스턴트 메시징 및 웹 회의 레코드를 저장 하는 주요 이점 중 하나는 데이터를 동일한 위치에 저장 하면 관리자가 단일 도구를 사용 하 여 보관 된 Exchange 데이터 및/또는 아카이브된 Lync Server 데이터를 검색할 수 있다는 점입니다. 모든 데이터는 같은 위치에 저장 되므로 (Exchange) 보관 된 Exchange 데이터를 검색할 수 있는 도구를 사용할 수도 있습니다.

보관 된 데이터를 쉽게 검색할 수 있는 한 가지 도구는 Microsoft SharePoint Server 2013입니다. SharePoint를 사용 하 여 Lync Server 데이터를 검색 하려면 먼저 Lync Server에서 Exchange 보관을 구성 하는 것과 관련 된 모든 단계를 완료 해야 합니다. Exchange 2013 및 Lync Server 2013이 성공적으로 통합 된 후에는 SharePoint 서버에서 Exchange Web Services 관리 API 버전 2.0을 설치 해야 합니다. 해당 API의 설치 프로그램은 Microsoft 다운로드 센터 ([http://go.microsoft.com/fwlink/p/?LinkId=258305](http://go.microsoft.com/fwlink/p/?linkid=258305))에서 다운로드할 수 있습니다. 다운로드 한 파일 (EWSManagedAPI)을 SharePoint 서버의 모든 폴더에 저장할 수 있습니다.

파일을 다운로드 한 후 SharePoint 서버에서 다음 절차를 완료 합니다.

1.  **시작**을 클릭 하 고 **모든 프로그램**을 클릭 한 다음 **보조 프로그램**을 클릭 하 고 **명령 프롬프트**를 마우스 오른쪽 단추로 클릭 한 다음 **관리자 권한으로 실행**을 클릭 하 여 명령 창을 엽니다.

2.  명령 창에서 **cd** 명령을 사용 하 여 현재 디렉터리를 EWSManagedAPI 파일이 저장 된 폴더로 변경 합니다. 예를 들어 C:\\다운로드에 파일을 저장 한 경우 명령 창에 다음 명령을 입력 하 고 enter 키를 누릅니다.
    
        cd C:\Downloads

3.  API를 설치 하려면 다음 명령을 입력 한 다음 enter 키를 누릅니다.
    
        msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"

4.  API가 설치 되 면 다음 명령을 입력 하 고 ENTER 키를 눌러 IIS를 다시 설정 합니다.
    
        iisreset

Exchange Web Services가 설치 된 후 SharePoint Server 2013 및 Exchange 2013 간에 서버 간 인증을 구성 해야 합니다. 이렇게 하려면 먼저 SharePoint 2013 관리 셸을 열고 다음 명령 집합을 실행 합니다.

    New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
    $service = Get-SPSecurityTokenServiceConfig
    $service.HybridStsSelectionEnabled = $True
    $service.AllowMetadataOverHttp = $False
    $service.AllowOAuthOverHttp = $False
    $service.Update()

<div>


> [!NOTE]  
> 자동 검색 서비스에 대 한 URI를 사용 해야 합니다. 샘플 URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1를 사용 하지 마세요.



</div>

토큰 발급자를 만들고 토큰 서비스를 구성한 후에는이 명령을 실행 하 여 샘플 URL에 대 한 SharePoint 사이트의 URL을 대체 하세요.http://atl-sharepoint-001:

    $exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
    $app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
    $site = Get-SPSite  "https://atl-sharepoint-001"
    Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy

Exchange 2013에 대해 서버 간 인증을 구성 하려면 Exchange 관리 셸을 열고 다음과 같은 명령을 실행 합니다 (C: 드라이브에 Exchange가 설치 되어 있고 기본 폴더 경로를 사용 하 고 있다고 가정).

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"

파트너 응용 프로그램을 구성한 후에는 모든 Exchange 사서함 및 클라이언트 액세스 서버에서 IIS (인터넷 정보 서비스)를 중지 하 고 다시 시작 하는 것이 좋습니다. 컴퓨터 atl-exchange-001에서 서비스를 다시 시작 하는 다음과 같은 명령을 사용 하 여 IIS를 다시 시작할 수 있습니다.

    iisreset atl-exchange-001

이 명령은 Exchange 관리 셸 또는 다른 명령 창 내에서 실행할 수 있습니다.

다음으로, 다음과 비슷한 명령을 실행 하 여 Exchange에서 검색을 수행할 수 있는 권한을 지정 된 사용자 (이 예제에서는 kenmyer)에 게 부여 합니다.

    Add-RoleGroupMember "Discovery Management" -Member "kenmyer"

Exchange와 SharePoint 간에 서버 간 인증이 설정 된 후 다음 단계는 SharePoint에서 eDiscovery 사이트를 만드는 것입니다. 이 작업은 SharePoint 관리 셸에서와 비슷한 명령으로 실행할 수 있습니다.

    $template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
    New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"

<div>


> [!NOTE]  
> "eDiscovery"은 "전자적 검색"에 대해 짧고 일반적으로 "admissible 증명을 받을 수 있는 항목"이 법률의 법정에서 "적절 하 게 계산 되어"는 것을 의미 합니다.



</div>

새 사이트를 사용할 준비가 되 면 다음 단계는 SharePoint의 결과 원본 역할을 하도록 Exchange 2013를 구성 하는 것입니다. SharePoint 2013 중앙 관리 페이지에서 다음 절차를 완료 하 여이 작업을 수행할 수 있습니다.

1.  중앙 관리 페이지에서 **서비스 응용 프로그램 관리** 를 클릭 한 다음 **검색 서비스 응용 프로그램**을 클릭 합니다.

2.  Search Service 응용 프로그램: 관리 페이지 검색 **결과 원본을** 클릭 한 다음 **새 결과 원본을**클릭 합니다.

3.  **새 결과 원본** 창에서 **이름** 상자에 새 결과 원본 (예: **Microsoft Exchange**)의 이름을 입력 합니다. **Exchange** 를 결과 원본 **프로토콜로**선택한 다음 exchange **원본 url** 상자에 EXCHANGE server의 웹 서비스 원본 url을 입력 합니다. 원본 URL은 다음과 유사 합니다.
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx

4.  **자동 검색 사용** 이 선택 되어 있지 않은지 확인 한 다음 **확인**을 클릭 합니다.

마지막으로, SharePoint 검색 사이트에서 다음 절차를 완료 하 여 새 eDiscovery 사례와 새 eDiscovery 집합을 만듭니다 (예:https://atl-sharepoint-001/sites/discovery):

1.  사이트 콘텐츠 페이지에서 **새 사례 만들기를**클릭 합니다.

2.  사이트 콘텐츠: 새 SharePoint 사이트 페이지에서 **제목** 상자에 사용자의 전자 메일 별칭 (예: **kenmyer**)을 입력 한 다음 같은 URL을 **웹 사이트 주소** 상자에 추가 합니다. 그러면 다음과 같은 URL이 생성 됩니다.
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer

3.  **만들기**를 클릭 합니다.

4.  EDiscovery 설정 페이지가 나타나면 Id 아래에서 **새 항목** 을 클릭 **하 고 유지: 검색 집합**을 선택 합니다.

5.  새: 검색 집합 페이지의 **검색 집합 이름** 상자에 사용자의 전자 메일 별칭을 입력 합니다. **필터** 상자에 **eDiscovery Lync\* ** 를 입력 한 다음 **추가 & 원본 관리**를 클릭 합니다.

6.  원본 관리 & 추가 페이지의 **사서함**아래 첫 번째 텍스트 상자에 사용자의 전자 메일 별칭을 입력 합니다. 교재 옆에 있는 사서함 확인 아이콘을 클릭 하 여 SharePoint가 지정 된 사서함에 연결할 수 있는지 확인 합니다.

7.  **확인**을 클릭합니다.

8.  EDiscovery 설정 페이지에서 **저장** 을 클릭 하 여 새 ediscovery 집합을 저장 합니다.

이 시점에서 다른 SharePoint 콘텐츠 또는 결과 원본에 대해 사용 하는 것과 동일한 방법으로 지정 된 사서함 (kenmyer) 및/또는 In 위치 유지를 검색할 수 있습니다.

</div>

<span> </span>

</div>

</div>

</div>

