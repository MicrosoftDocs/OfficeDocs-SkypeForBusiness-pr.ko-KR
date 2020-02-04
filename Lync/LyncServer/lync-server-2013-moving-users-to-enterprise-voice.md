---
title: 'Lync Server 2013: Enterprise Voice로 사용자 이동'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving users to Enterprise Voice
ms:assetid: a2df6d51-5cf2-4d3e-8f97-496af5fd5e5e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412758(v=OCS.15)
ms:contentKeyID: 48184958
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e92f0a7d71d42d8551a51028afec209e795941d5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756692"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-users-to-enterprise-voice-in-lync-server-2013"></a>Lync Server 2013에서 Enterprise Voice로 사용자 이동

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-18_

기존 PBX 전화 통신 인프라에서 엔터프라이즈 음성으로 사용자를 이동 하는 경우 배포 프로세스에는 [Lync Server 2013의 Enterprise Voice 계획](lync-server-2013-planning-for-enterprise-voice.md)에서 이미 설명한 계획 프로세스의 일부가 아닌 몇 가지 단계가 포함 됩니다. 이전 엔터프라이즈 음성 배포에서 사용자를 마이그레이션하는 방법에 대 한 자세한 내용은 설치 미디어에 포함 된 마이그레이션 문서를 참조 하세요.

기존 전화 통신 인프라에서 엔터프라이즈 음성으로 사용자를 이동 하는 프로세스는 다음 단계로 구성 됩니다.

1.  기본 전화 번호를 지정 합니다.

2.  엔터프라이즈 음성에 대해 사용자를 사용 하도록 설정 합니다.

3.  사용자를 위한 다이얼 플랜을 준비 합니다.

4.  사용자 음성 정책 계획.

5.  통화 경로 계획

6.  PBX 또는 SIP 트렁크를 구성 하 여 엔터프라이즈 음성에 사용 하도록 설정 된 사용자에 대 한 경로를 전환 합니다.

7.  사용자를 Exchange UM (통합 메시징)로 이동 (권장)

이 항목에서는 각 단계에 필요한 계획에 대해 설명 합니다.

<div>

## <a name="step-1-designate-primary-phone-numbers"></a>1 단계. 기본 전화 번호 지정

엔터프라이즈 음성은 다른 메시징 미디어와 음성을 통합 하 여 들어오는 통화가 서버에 도착할 때 서버는 해당 번호를 사용자의 SIP URI에 매핑한 다음 해당 SIP URI와 연결 된 모든 클라이언트 끝점으로 호출을 포크 합니다. 이 프로세스에서는 각 사용자가 기본 전화 번호와 연결 되어 있어야 합니다.

기본 전화 번호는 다음과 같아야 합니다.

  - 전역적으로 고유 하거나, 내부 확장의 경우 엔터프라이즈에서 고유 합니다.

  - 엔터프라이즈에서 소유 하 고 라우팅할 수 있습니다. 개인 번호는 사용해 서는 안 됩니다.

엔터프라이즈 사용자는 Active Directory 도메인 서비스에서 두 개 이상의 전화 번호를 나열할 수 있습니다. 특정 사용자와 연결 된 모든 전화 번호는 Active Directory 사용자 및 컴퓨터 스냅인에서 해당 사용자의 속성 시트에서 보거나 변경할 수 있습니다.

**사용자 속성** 대화 상자의 **일반** 탭에 있는 **전화 번호** 상자에는 사용자의 기본 작업 번호가 포함 되어 있어야 합니다. 이 번호는 일반적으로 사용자의 기본 전화 번호로 지정 됩니다.

일부 사용자에 게 특별 한 요구 사항 (예: 관리 도우미를 통해 들어오는 모든 걸려오는 통화를 원하는 경우)이 있지만, 이러한 예외는 필요한 경우 명확 하 고 중요 한 경우에만 제한할 수 있습니다.

기본 번호를 선택한 후에는 다음을 수행 해야 합니다.

  - 가능한 경우 모두 E 164 형식으로 정규화 됩니다.

  - Active Directory **msRTCSIP** 특성에 복사 됩니다.
    
    <div>
    

    > [!NOTE]  
    > <STRONG>RCC (원격 통화 제어)로 동시 연결</STRONG><BR>RCC는 Lync Server를 사용 하 여 데스크톱 PBX 휴대폰을 모니터링 하 고 제어 하는 기능입니다. 제어가 PBX에 대 한 게이트웨이 역할을 하는 서버를 통해 라우트됩니다. RCC 및 Enterprise Voice 모두에 대해 사용자를 구성할 수는 없지만 회선 URI 설정은 두 경우 모두에 사용자의 기본 전화 번호를 지정 합니다.<BR>사용자가 계속 사용 하기 위해 기존 PBX 인프라를 보유 하 고 있는 경우 조직에 점진적으로 엔터프라이즈 음성을 도입할 수 있습니다. 이 배포 시나리오에 대 한 자세한 내용은 계획 설명서의 <A href="lync-server-2013-direct-sip-deployment-options.md">Lync Server 2013에서 다이렉트 SIP 배포 옵션</A> 을 참조 하세요.<BR>이전 릴리스에서는 사용자에 대 한 RCC 및 Enterprise Voice를 모두 사용할 수 있지만, 이중 포크를 위해 사용자를 구성한 경우에만 수신 전화를 통해 사용자의 PBX 휴대폰 및 Communicator가 동시에 연결 되는 기능이 있습니다. Lync Server 2010에서 듀얼 포크는 지원 되지 않습니다.

    
    </div>

다음과 같은 세 가지 방법으로 **msRTCSIP** 특성을 채울 수 있습니다.

  - Microsoft Id 통합 서버 (권장)

  - Lync Server 컨트롤 패널의 **사용자** 페이지

여러 개의 전화 번호를 처리 해야 하는 경우 조직에서 개발한 스크립트 사용자 지정이 더 나은 선택입니다. 조직에서 Active Directory 도메인 서비스에 전화 번호를 표시 하는 방법에 따라 스크립트에서 기본 전화 번호를 **msRTCSIP** 특성에 복사 하기 전에 해당 형식을 E 164로 정규화 해야 할 수 있습니다.

  - 조직에서 Active Directory 도메인 서비스의 모든 전화 번호를 단일 형식으로 유지 관리 하는 경우, 해당 형식이 E 자로 되어 있으면 스크립트는 각 기본 전화 번호를 **msRTCSIP line** 특성에만 써야 합니다.

  - 조직에서 Active Directory 도메인 서비스의 모든 전화 번호를 단일 형식으로 유지 관리 하지만 해당 형식이 E. c 1이 아닌 경우, 해당 스크립트는 **msRTCSIP line** 특성에 쓰기 전에 기본 전화 번호를 기존 형식에서 E로 변환 하는 적절 한 정규화 규칙을 정의 해야 합니다.

  - 조직에서 Active Directory 도메인 서비스에 전화 번호에 대 한 표준 형식을 적용 하지 않는 경우, 스크립트는 기본 전화 번호를 **msRTCSIP 명령줄** 특성에 기록 하기 전에 해당 하는 적절 한 정규화 규칙을 정의 하 여 해당 사용자가 기본 전화번호를 다양 한 형식에서 E. c 1 규격으로 변환 해야 합니다.

또한 스크립트는 **msRTCSIP** 특성에 쓰기 전에 각 주 번호 앞에 접두사 **Tel:** 을 삽입 해야 합니다.

이 특성에 지정 된 숫자의 예상 형식은 다음과 같습니다.

  - Tel: + 14255550100; ext = 50100.

  - Tel: 5550100 (고유한 엔터프라이즈 전체 확장의 경우)
    
    <div>
    

    > [!IMPORTANT]  
    > ABS에는 Active Directory 도메인 서비스에 대 한 액세스 권한이 없으므로 사용자의 기본 전화 번호를 정규화 할 필요가 없기 때문에 ABS (주소록 서비스)에서 정규화를 사용 해도 active directory 도메인 서비스에서 각 사용자의 주 전화번호를 표준화 하지 않아도 되므로 기본 번호를 <STRONG>msRTCSIP 줄</STRONG> 특성에 복사할 수 없습니다.

    
    </div>

</div>

<div>

## <a name="step-2-enable-users-for-enterprise-voice"></a>2 단계. 사용자가 Enterprise Voice를 사용할 수 있도록 설정

사용할 사용자를 식별 하는 것 외에는이 단계를 완료 하는 데 특별 한 계획이 필요 하지 않습니다.

</div>

<div>

## <a name="step-3-prepare-dial-plans-for-users"></a>3 단계. 사용자를 위한 다이얼 플랜을 준비 합니다.

엔터프라이즈 음성 기능을 사용 하도록 설정 된 사용자는 다이얼 플랜을 적절 하 게 설정 하지 않고 PSTN에 전화를 걸 수 없습니다. 다이얼 플랜은 전화 인증 및 통화 라우팅과 같은 목적으로 명명 된 위치, 개인 사용자 또는 연락처 개체의 전화 번호를 단일 표준 (E) 형식으로 변환 하는 정규화 규칙의 명명 된 집합입니다. 정규화 규칙은 다양 한 형식으로 표시 되는 전화 번호가 지정 된 각 위치, 사용자 또는 연락처 개체에 대해 라우팅되는 방법을 정의 합니다.

다이얼 플랜을 준비 하는 방법에 대 한 자세한 내용은 [Lync Server 2013의 다이얼 플랜 및 정규화 규칙](lync-server-2013-dial-plans-and-normalization-rules.md)을 참조 하세요.

</div>

<div>

## <a name="step-4-plan-user-voice-policies"></a>4 단계. 사용자 음성 정책 계획

회사 전화를 통해 장거리 전화를 거는 등의 기존 PBX의 사용자 클래스 서비스 설정은 Enterprise Voice로 이동한 사용자에 대 한 VoIP 정책으로 다시 구성 해야 합니다. 엔터프라이즈 음성에 대 한 정책 계획 및 만들기에 대 한 자세한 내용은 [Lync Server 2013의 음성 정책을](lync-server-2013-voice-policies.md)참조 하세요.

</div>

<div>

## <a name="step-5-plan-outbound-call-routes"></a>5 단계. 아웃 바운드 통화 경로 계획

통화 경로는 Lync Server가 엔터프라이즈 음성 사용자가 설정한 아웃 바운드 통화를 처리 하는 방법을 지정 합니다. 사용자가 번호를 사용 하는 경우, 서버는 필요한 경우이를 SIP URI와 일치 시 키도로 정규화 하 고이를 사용 하 여 다이얼 문자열을 지정 합니다. 서버에서 일치 하는 항목을 만들 수 없는 경우에는 해당 번호를 기반으로 나가는 호출 라우팅 논리를 적용 합니다. 해당 논리를 정의 하는 마지막 단계는 각 다이얼 플랜에 나열 된 각 대상 전화 번호 집합에 대해 별도의 명명 된 호출 경로를 만드는 것입니다.

통화 경로를 계획 하는 방법에 대 한 자세한 내용은 [Lync Server 2013의 음성 경로](lync-server-2013-voice-routes.md)를 참조 하세요.

</div>

<div>

## <a name="step-6-configure-pbx-or-sip-trunk-to-reroute-calls-for-enterprise-voice-users"></a>6 단계. 엔터프라이즈 음성 사용자의 경로를 바꾸려면 PBX 또는 SIP 트렁크 구성

이전에 기존 PBX에서 호스트 된 사용자 또는 인터넷 통신 서비스 공급자 (ITSP)에 대 한 SIP 트렁크 연결에는 이동 후에도 전화 번호가 유지 됩니다. 유일한 요구 사항은 이동 후에도 엔터프라이즈 음성 사용자에 대 한 걸려오는 전화를 중재 서버로 라우팅하기 위해 PBX 또는 SIP 트렁크를 다시 구성 해야 한다는 것입니다.

</div>

<div>

## <a name="step-7-move-users-to-exchange-unified-messaging-recommended"></a>7 단계. Exchange 통합 메시징으로 사용자 이동 (권장)

Exchange 통합 메시징으로 사용자를 이동 하는 작업은 다음과 같이 구성 됩니다.

  - Exchange 통합 메시징 및 Lync 서버가 함께 작동 하도록 구성 합니다.

  - Exchange 통합 메시징 통화 응답 및 Outlook Voice Access에 대해 사용자를 사용 하도록 설정 합니다. 이 작업은 Exchange 통합 메시징 서버에서 수행 됩니다. 자세한 내용은에서 [http://go.microsoft.com/fwlink/p/?linkID=139372](http://go.microsoft.com/fwlink/p/?linkid=139372)Exchange Server 2010 TechNet 라이브러리를 참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

