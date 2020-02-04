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
ms.openlocfilehash: 6316a1027de963cefea6c0c76051f09cb5d33538
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727688"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-various-policies"></a>다양 한 정책 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-24_

<div>

## <a name="configuring-the-various-policies"></a>다양 한 정책 구성

Lync server 2013 스트레스 및 성능 도구를 실행 하기 전에 Lync Server 2013 토폴로지에서 구성할 수 있는 다양 한 정책에 대해 알아보세요.

<div>

## <a name="configuring-the-archiving-policy"></a>보관 정책 구성

예제 스크립트 ArchivingPolicy을 참조 하세요. 이 스크립트는 토폴로지에 보관 서버가 배포 된 경우에만 사용 해야 합니다. 자세한 내용은 lync Server 2013 설명서 및 [Lync server 2013에서 cmdlet을 기록 하 고 모니터링](https://technet.microsoft.com/en-us/library/gg415629\(v=ocs.15\))하는 cmdlet 도움말을 참조 하세요.

</div>

<div>

## <a name="configuring-the-conferencing-policy"></a>회의 정책 구성

예제 스크립트 MeetingPolicy을 참조 하세요. 자세한 내용은 lync Server 2013 설명서 및 [Lync server 2013의 웹 회의 cmdlet](https://technet.microsoft.com/en-us/library/gg415675\(v=ocs.15\))에 대 한 cmdlet 도움말을 참조 하세요.

</div>

<div>

## <a name="configuring-the-contacts-policy"></a>연락처 정책 구성

예: 연락처 Spolicy. ps1을 참조 하세요. 자세한 내용은 lync Server 2013 설명서 및 [Lync server 2013의 IM 및 현재 상태 cmdlet](https://technet.microsoft.com/en-us/library/gg398611\(v=ocs.15\))에 대 한 cmdlet 도움말을 참조 하세요.

</div>

<div>

## <a name="configuring-the-federation-policy"></a>페더레이션 정책 구성

예제 FederationPolicy를 참조 하세요. 자세한 내용은 lync Server 2013 설명서 및 lync server [2013의 Edge server cmdlet](https://technet.microsoft.com/en-us/library/gg415635\(v=ocs.15\)) 에 대 한 cmdlet 도움말 및 [lync Server 2013의 페더레이션 및 외부 액세스 cmdlet](https://technet.microsoft.com/en-us/library/gg415651\(v=ocs.15\))을 참조 하세요.

</div>

<div>

## <a name="configuring-the-call-admission-control-policy"></a>통화 허용 제어 정책 구성

예제 BandwidthPolicy를 참조 하세요. 자세한 내용은 lync server 2013에서 lync server [2013의 통화 허용 제어](https://technet.microsoft.com/en-us/library/gg398529\(v=ocs.15\)) 에 대 한 개요 및 lync [Server 2013의 통화 허용 제어 cmdlet](https://technet.microsoft.com/en-us/library/gg415676\(v=ocs.15\))에 대 한 cmdlet 도움말을 참조 하세요.

</div>

<div>

## <a name="configuring-the-voice-routing-rules"></a>음성 라우팅 규칙 구성

예제 RoutingRules를 참조 하세요. 음성 라우팅 규칙을 구성할 때 전화 컨텍스트 (즉,/위치 프로필 또는/SimpleName) 및 내부/외부 지역 코드를 기록 하 여 사용자를 만들 때, 그리고 LyncPerfTool 구성 중에 (특히 PSTN-UC 및 UC-PSTN 용)를 지정할 수 있습니다. 예를 들어 RoutingRules의 **새-CsDialPlan 플랜** cmdlet에 대 한 호출의 simplename 매개 변수는 다음 UserProfileGenerator 그림의 locationprofile 값에 사용 해야 합니다.

![샘플 음성 라우팅 규칙.](images/JJ945610.9f34d971-4ed0-4a4c-b101-086a91c4578c(OCS.15).jpg "샘플 음성 라우팅 규칙.")

자세한 내용은 lync Server 2013 설명서 및 [Lync server 2013의 엔터프라이즈 음성 cmdlet](https://technet.microsoft.com/en-us/library/gg415658\(v=ocs.15\))에 대 한 cmdlet 도움말을 참조 하세요.

</div>

<div>

## <a name="configuring-conferencing-attendant-application"></a>회의 수행자 응용 프로그램 구성

예제 ConferenceAutoAttendantConfiguration를 참조 하세요. 구성 생성을 위해 LConferencingAutoAttendant Cperf Tool 구성 도구에 입력할 수 있도록 기본적으로 1121111111 등의 전화 번호를 기록 합니다.

![회의 길잡이 응용 프로그램 구성](images/JJ945610.0618a22f-27a9-423a-9085-d2bf71e82db6(OCS.15).jpg "회의 길잡이 응용 프로그램 구성")

자세한 내용은 lync Server 2013 설명서와 lync server [2013의 웹 회의](https://technet.microsoft.com/en-us/library/gg415675\(v=ocs.15\)) cmdlet에 대 한 cmdlet 도움말 및 [lync Server 2013의 전화 접속 회의 cmdlet](https://technet.microsoft.com/en-us/library/gg415630\(v=ocs.15\))을 참조 하세요.

</div>

<div>

## <a name="configuring-lync-server-call-park-service"></a>Lync Server 통화 공원 서비스 구성

통화 공원는 기본적으로 사용 되지 않습니다. 예제 CallParkConfiguration를 참조 하세요. 자세한 내용은 lync Server 2013 설명서 및 [Lync server 2013의 통화 공원 응용 프로그램 cmdlet](https://technet.microsoft.com/en-us/library/gg415639\(v=ocs.15\))에 대 한 cmdlet 도움말을 참조 하세요.

</div>

<div>

## <a name="configuring-emergency-calls"></a>비상 전화 구성

긴급 통화에 대 한 스트레스 및 성능 테스트를 구성 하려면 다음 단계를 수행 합니다.

1.  비상 전화에 대 한 음성 경로를 설정 합니다. 이 음성 경로 설정에 대 한 예는 "PSTN으로 E911 라우팅"의 "RoutingRules 스크립트"를 참조 하세요.
    
    <div>
    

    > [!WARNING]  
    > RoutingRules의 예제 명령에 911이 아닌 숫자 119를 포함 하는 숫자 패턴이 있습니다. 부하 테스트 중에 로컬 비상 운영자에 게 실수로 전화를 하지 않도록 911 (또는 실제 로컬 비상 번호)를 사용 하지 않아야 합니다. 이 구성은 시뮬레이션 용도로만 사용 됩니다.

    
    </div>

2.  다음 그림과 같이 UserProvisioningTool의 **LIS** 탭에 있는 값을 입력 하 여 주소를 구성 합니다.
    
    ![위치 정보 서비스 구성.](images/JJ945610.8ac1faa1-e9f9-40d0-b8b7-b159f4f459f7(OCS.15).jpg "위치 정보 서비스 구성.")  

3.  **LIS 구성 파일 생성**을 클릭 합니다.

4.  포트, 서브넷, 스위치 및 WAPs (무선 액세스 지점)의 CSV 파일과 Lync Server 2013 스트레스 및 성능 도구의 XML 파일이 생성 됩니다. CSV 파일은 LisConfiguration. ps1 스크립트를 사용 하 여 LIS (위치 정보 서비스)를 구성할 때 입력 (동일한 폴더에서)으로 사용 됩니다. 생성 된 Locations0 파일을 Lync Server 2013 스트레스 및 성능 도구 실행 파일과 동일한 폴더로 이동 합니다 (이 경우 위치 프로필 (다이얼 플랜) 시나리오를 실행 합니다.

</div>

<div>

## <a name="creating-enabling-configuring-and-disabling-users"></a>사용자 만들기, 설정, 구성, 사용 안 함

다음 스크립트를 실행 하기 전에 모든 사용자를 만들어야 합니다. 사용자 [및 연락처 만들기](create-users-and-contacts.md) 의 지침에 따라 사용자를 만듭니다. 자세한 내용은 온 [-csuser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)), [Set Csuser](https://technet.microsoft.com/en-us/library/gg398510\(v=ocs.15\))및 [Disable-Csuser](https://technet.microsoft.com/en-us/library/gg398747\(v=ocs.15\)) cmdlet에 대 한 Lync Server 2013 cmdlet 설명서를 참조 하세요.

</div>

<div>

## <a name="configuring-response-group-application"></a>응답 그룹 응용 프로그램 구성

예: ResponseGroupConfiguration. ps1을 참조 하세요. 자세한 내용은 Lync Server 2013 설명서 및 [Lync server 2013의 응답 그룹 응용 프로그램 cmdlet](https://technet.microsoft.com/en-us/library/gg415654\(v=ocs.15\))에 대 한 cmdlet 도움말을 참조 하세요. 응답 그룹 응용 프로그램 구성을 검토 하려면 다음 그림과 `https://<poolfqdn>/RgsConfig/`같이을 참조 하세요.

![응답 그룹 구성 도구.](images/JJ945610.480a9440-2283-4533-98f8-86daaab4781c(OCS.15).jpg "응답 그룹 구성 도구.")

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

