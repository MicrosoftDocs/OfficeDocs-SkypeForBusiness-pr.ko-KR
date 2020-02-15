---
title: 다양 한 정책 구성
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configuring the Various Policies
ms:assetid: e3b3cbda-7c17-470b-acb0-82fdcc473184
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945610(v=OCS.15)
ms:contentKeyID: 51541436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 134535f904b7394d5335b2a3252eba2a8de9341e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049220"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-various-policies"></a>다양 한 정책 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-24_

<div>

## <a name="configuring-the-various-policies"></a>다양 한 정책 구성

Lync server 2013 스트레스 및 성능 도구를 실행 하기 전에 Lync Server 2013 토폴로지에서 구성할 수 있는 다양 한 정책이 나와 있습니다.

<div>

## <a name="configuring-the-archiving-policy"></a>보관 정책 구성

예제 스크립트 ArchivingPolicy를 참조 하세요. 이 스크립트는 토폴로지에 보관 서버를 배포한 경우에만 사용 해야 합니다. 자세한 내용은 lync server 2013 설명서 및 [Lync server 2013의 보관 및 모니터링 cmdlet](https://technet.microsoft.com/library/gg415629\(v=ocs.15\))에 대 한 cmdlet 도움말을 참조 하십시오.

</div>

<div>

## <a name="configuring-the-conferencing-policy"></a>회의 정책 구성

예제 스크립트 Microsoft.rtc.management.writableconfig.policy.meeting.meetingpolicy를 참조 하세요. 자세한 내용은 Lync Server 2013 설명서 및 [Lync server 2013의 웹 회의 cmdlet](https://technet.microsoft.com/library/gg415675\(v=ocs.15\))에 대 한 cmdlet 도움말을 참조 하십시오.

</div>

<div>

## <a name="configuring-the-contacts-policy"></a>연락처 정책 구성

예: 연락처 이름 Spolicy. 자세한 내용은 Lync Server 2013 설명서 및 [Lync server 2013의 IM 및 현재 상태 cmdlet](https://technet.microsoft.com/library/gg398611\(v=ocs.15\))에 대 한 cmdlet 도움말을 참조 하십시오.

</div>

<div>

## <a name="configuring-the-federation-policy"></a>페더레이션 정책 구성

예제 FederationPolicy를 참조 하세요. 자세한 내용은 lync server 2013 설명서 및 lync server 2013 및 [페더레이션 및 외부 액세스 2013 cmdlet](https://technet.microsoft.com/library/gg415651\(v=ocs.15\))의 [Edge server cmdlet](https://technet.microsoft.com/library/gg415635\(v=ocs.15\)) 에 대 한 cmdlet 도움말을 참조 하십시오.

</div>

<div>

## <a name="configuring-the-call-admission-control-policy"></a>통화 허용 제어 정책 구성

예제 BandwidthPolicy를 참조 하세요. 자세한 내용은 lync server 2013 설명서에서 lync server [2013의 통화 허용 제어 개요](https://technet.microsoft.com/library/gg398529\(v=ocs.15\)) 및 [lync Server 2013의 통화 허용 제어 cmdlet](https://technet.microsoft.com/library/gg415676\(v=ocs.15\))에 대 한 cmdlet 도움말을 참조 하십시오.

</div>

<div>

## <a name="configuring-the-voice-routing-rules"></a>음성 라우팅 규칙 구성

예제 RoutingRules를 참조 하세요. 음성 라우팅 규칙을 구성할 때는 사용자를 만들 때 및 LyncPerfTool 구성 (특히 PSTN-UC 및 UC PSTN 용)을 사용할 때 전화 컨텍스트 (예:/Location,/Dinename)와 내부/외부 지역 코드를 기록해 둡니다. 예를 들어 Userprofilegenerator.exe 공용의 다음 그림에서 LocationProfile 값에 대해 RoutingRules의 **새 CsDialPlan 플랜** cmdlet에 대 한 호출의 simplename 매개 변수를 사용 해야 합니다.

![샘플 음성 라우팅 규칙입니다.](images/JJ945610.9f34d971-4ed0-4a4c-b101-086a91c4578c(OCS.15).jpg "샘플 음성 라우팅 규칙입니다.")

자세한 내용은 Lync Server 2013 설명서 및 [Lync server 2013의 Enterprise Voice cmdlet](https://technet.microsoft.com/library/gg415658\(v=ocs.15\))에 대 한 cmdlet 도움말을 참조 하십시오.

</div>

<div>

## <a name="configuring-conferencing-attendant-application"></a>회의 전화 교환 응용 프로그램 구성

예제 ConferenceAutoAttendantConfiguration를 참조 하세요. 구성 생성을 위해 LyncPerf 도구 구성 도구에 입력할 수 있도록 ConferencingAutoAttendant 전화 번호 (기본적으로 1121111111)를 기록해 둡니다.

![회의 전화 교환 응용 프로그램 구성](images/JJ945610.0618a22f-27a9-423a-9085-d2bf71e82db6(OCS.15).jpg "회의 전화 교환 응용 프로그램 구성")

자세한 내용은 lync server 2013 설명서 및 lync server 2013 및 [전화 접속 회의 2013 cmdlet](https://technet.microsoft.com/library/gg415630\(v=ocs.15\))의 [웹 회의 cmdlet](https://technet.microsoft.com/library/gg415675\(v=ocs.15\)) 에 대 한 cmdlet 도움말을 참조 하십시오.

</div>

<div>

## <a name="configuring-lync-server-call-park-service"></a>Lync Server 통화 대기 서비스 구성

통화 대기는 기본적으로 사용 하지 않도록 설정 됩니다. 예제 CallParkConfiguration를 참조 하세요. 자세한 내용은 Lync Server 2013 설명서 및 [Lync server 2013의 통화 대기 응용 프로그램 cmdlet](https://technet.microsoft.com/library/gg415639\(v=ocs.15\))에 대 한 cmdlet 도움말을 참조 하십시오.

</div>

<div>

## <a name="configuring-emergency-calls"></a>긴급 통화 구성

긴급 통화에 대 한 스트레스 및 성능 테스트를 구성 하려면 다음 단계를 수행 합니다.

1.  비상 전화를 위해 음성 경로를 설정 합니다. 이 음성 경로를 설정 하는 예제를 보려면 "Route E911 to PSTN" 설명에 나오는 RoutingRules 스크립트를 참조 하십시오.
    
    <div>
    

    > [!WARNING]  
    > RoutingRules의 예제 명령에 911가 아닌 119 수를 포함 하는 숫자 패턴이 있습니다. 부하 테스트 중에 로컬 응급 운영자에 게 실수로 전화를 걸 수 없도록 911 (또는 실제 로컬 비상 번호)를 사용 하지 않도록 해야 합니다. 이 구성은 시뮬레이션 목적 으로만 사용 됩니다.

    
    </div>

2.  다음 그림에 표시 된 것 처럼 UserProvisioningTool의 **LIS** 탭에 있는 값을 채워서 주소를 구성 합니다.
    
    ![위치 정보 서비스 구성](images/JJ945610.8ac1faa1-e9f9-40d0-b8b7-b159f4f459f7(OCS.15).jpg "위치 정보 서비스 구성")  

3.  **LIS 구성 파일 생성**을 클릭 합니다.

4.  포트, 서브넷, 스위치 및 Wap (무선 액세스 지점)에 대 한 CSV 파일 및 Lync Server 2013 스트레스 및 성능 도구인 XML 파일이 생성 됩니다. 이 CSV 파일은 LisConfiguration. ps1 스크립트를 사용 하 여 LIS (위치 정보 서비스)를 구성할 때 동일한 폴더에서 입력으로 사용 됩니다. 생성 된 Locations0 파일을 Lync Server 2013 스트레스 및 성능 도구 실행 파일 (여기서는 위치 프로필 (다이얼 플랜) 시나리오를 실행 하는 LyncPerfTool)과 동일한 폴더로 이동 합니다.

</div>

<div>

## <a name="creating-enabling-configuring-and-disabling-users"></a>사용자 만들기, 설정, 구성 및 해제

다음 스크립트를 실행 하기 전에 모든 사용자를 만들어야 합니다. 사용자 만들기 [및 연락처 만들기](create-users-and-contacts.md) 의 지침을 따릅니다. 자세한 내용은 [css\user](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)), [Set-Csuser](https://technet.microsoft.com/library/gg398510\(v=ocs.15\))및 [Disable-Csuser](https://technet.microsoft.com/library/gg398747\(v=ocs.15\)) cmdlet에 대 한 Lync Server 2013 cmdlet 설명서를 참조 하십시오.

</div>

<div>

## <a name="configuring-response-group-application"></a>응답 그룹 응용 프로그램 구성

ResponseGroupConfiguration. p 예를 참조 하십시오. 자세한 내용은 Lync Server 2013 설명서 및 [Lync server 2013의 응답 그룹 응용 프로그램 cmdlet](https://technet.microsoft.com/library/gg415654\(v=ocs.15\))에 대 한 cmdlet 도움말을 참조 하십시오. 응답 그룹 응용 프로그램 구성을 검토 하려면 다음 그림 `https://<poolfqdn>/RgsConfig/`에 표시 된 것 처럼를 참조 하십시오.

![응답 그룹 구성 도구](images/JJ945610.480a9440-2283-4533-98f8-86daaab4781c(OCS.15).jpg "응답 그룹 구성 도구")

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

