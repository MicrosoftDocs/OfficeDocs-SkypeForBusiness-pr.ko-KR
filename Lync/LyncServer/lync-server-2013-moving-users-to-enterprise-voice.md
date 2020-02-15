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
ms.openlocfilehash: b0320cb10e4122e5f5c42a659ad8de54ce3ae5b6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42039162"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-users-to-enterprise-voice-in-lync-server-2013"></a>Lync Server 2013에서 Enterprise Voice로 사용자 이동

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-18_

기존 PBX 전화 통신 인프라에서 Enterprise Voice로 사용자를 이동 하는 경우 배포 프로세스에 [Lync Server 2013의 Enterprise Voice 계획](lync-server-2013-planning-for-enterprise-voice.md)에서 이미 설명한 계획 프로세스의 일부가 아닌 몇 가지 단계가 포함 되어 있습니다. 이전 Enterprise Voice 배포에서 사용자를 마이그레이션하는 방법에 대한 자세한 내용은 설치 미디어에 포함된 마이그레이션 문서를 참조하십시오.

사용자를 기존 전화 통신 인프라에서 Enterprise Voice로 이동하는 프로세스는 다음 단계로 구성됩니다.

1.  기본 전화 번호 지정

2.  사용자가 Enterprise Voice를 사용할 수 있도록 설정

3.  사용자에 대한 다이얼 플랜 준비

4.  사용자 음성 정책 계획

5.  통화 경로 계획

6.  Enterprise Voice를 사용할 수 있는 사용자에 대한 통화를 다시 라우팅하도록 PBX 또는 SIP 트렁크 구성

7.  사용자를 Exchange UM (통합 메시징)으로 이동 합니다 (권장).

이 항목에서는 각 단계에 필요한 계획에 대해 설명합니다.

<div>

## <a name="step-1-designate-primary-phone-numbers"></a>1단계. 기본 전화 번호 지정

Enterprise Voice는 음성을 다른 메시징 미디어와 통합하며, 걸려오는 전화가 서버에 도착하면 서버에서 번호를 사용자의 SIP-URI에 매핑한 다음 통화를 해당 SIP-URI에 연결된 모든 클라이언트 끝점으로 분기합니다. 이 프로세스에서는 각 사용자가 기본 전화 번호와 연결되어야 합니다.

기본 전화 번호는 다음 사항을 충족해야 합니다.

  - 전역적으로 고유하거나 내부 내선 번호의 경우 엔터프라이즈 내에서 고유해야 합니다.

  - 엔터프라이즈에서 소유하고 라우팅할 수 있어야 합니다. 개인 번호는 사용하면 안 됩니다.

엔터프라이즈 사용자는 Active Directory 도메인 서비스에서 두 개 이상의 전화 번호를 나열할 수 있습니다. 특정 사용자와 연결된 모든 전화 번호는 Active Directory 사용자 및 컴퓨터 스냅인의 해당 사용자에 대한 속성 시트에서 보거나 변경할 수 있습니다.

**사용자 속성** 대화 상자의 **일반** 탭에 있는 **전화 번호** 상자에는 사용자의 기본 회사 전화 번호가 포함되어야 합니다. 일반적으로 이 번호가 사용자의 기본 전화 번호로 지정됩니다.

일부 사용자에게 특별한 요구 사항이 있을 수도 있지만(예: 걸려오는 모든 전화가 비서를 통해 라우팅되기를 원하는 중역) 이러한 예외는 요구가 분명하고 중요한 경우로만 제한되어야 합니다.

기본 전화 번호를 선택한 후 다음 작업을 수행해야 합니다.

  - 가능한 경우 기본 전화 번호를 E.164 형식으로 정규화해야 합니다.

  - 기본 전화 번호를 Active Directory **msRTCSIP-line** 특성에 복사해야 합니다.
    
    <div>
    

    > [!NOTE]  
    > <STRONG>RCC(원격 통화 제어)와 동시 사용</STRONG><BR>RCC는 Lync Server를 사용 하 여 데스크톱 PBX 전화를 모니터링 하 고 제어 하는 기능입니다. 제어는 PBX에 대한 게이트웨이 역할을 하는 서버를 통해 라우팅됩니다. 사용자가 RCC 및 Enterprise Voice 둘 다를 사용할 수 있도록 구성할 수 없지만 줄 URI 설정은 어느 경우든 사용자의 기본 전화 번호를 지정합니다.<BR>선택한 사용자가 기존 PBX 인프라를 계속 사용하도록 하려면 조직에 단계적으로 Enterprise Voice를 도입할 수 있습니다. 이 배포 시나리오에 대 한 자세한 내용은 계획 설명서의 <A href="lync-server-2013-direct-sip-deployment-options.md">Lync Server 2013에서 DIRECT SIP 배포 옵션</A> 을 참조 하십시오.<BR>이전 릴리스에서는 사용자에 대해 RCC 및 Enterprise Voice를 모두 사용 하도록 설정할 수 있지만 이중 포크를 위해 사용자를 구성한 경우에만 들어오는 호출이 사용자의 PBX 전화 및 Communicator에 연결 되는 기능입니다. Lync Server 2010에서는 이중 포크는 지원 되지 않습니다.

    
    </div>

**msRTCSIP-line** 특성을 채우는 세 가지 방법은 다음과 같습니다.

  - Microsoft Identity Integration Server(권장)

  - Lync Server 제어판의 **사용자** 페이지

다양 한 전화 번호를 처리 해야 하는 경우 조직에서 개발한 스크립트 사용자 지정이 더 좋습니다. 조직이 AD DS(Active Directory 도메인 서비스)에 전화 번호를 표시하는 조직의 방식에 따라 스크립트에서 기본 전화 번호를 **msRTCSIP-line** 특성으로 복사하기 전에 E.164 형식으로 정규화해야 할 수 있습니다.

  - 조직이 AD DS(Active Directory 도메인 서비스)에서 모든 전화 번호를 단일 형식으로 유지 관리하고 해당 형식이 E.164이면 스크립트에서는 각 기본 전화 번호를 **msRTCSIP-line** 특성에 쓰기만 하면 됩니다.

  - 반면 조직이 AD DS(Active Directory 도메인 서비스)에서 모든 전화 번호를 단일 형식으로 유지 관리하지만 해당 형식이 E.164가 아니면 스크립트에서 기본 전화 번호를 **msRTCSIP-line** 특성에 쓰기 전에 기존 형식에서 E.164로 변환하는 정규화 규칙을 정의해야 합니다.

  - 조직이 AD DS(Active Directory 도메인 서비스)에서 전화 번호에 대해 표준 형식을 적용하지 않는 경우 스크립트에서 기본 전화 번호를 **msRTCSIP-line** 특성에 쓰기 전에 다양한 형식의 기본 전화 번호를 E.164 준수로 변환하는 적합한 정규화 규칙을 정의해야 합니다.

또한 스크립트에서 접두사 **Tel:** 을 **msRTCSIP-line** 특성에 각 기본 전화 번호를 쓰기 전에 기본 전화 번호 앞에 삽입해야 합니다.

이 특성에 지정된 번호의 예상 형식은 다음과 같습니다.

  - Tel: + 14255550100으로; ext = 50100.

  - Tel:5550100(엔터프라이즈 전체의 고유 내선)
    
    <div>
    

    > [!IMPORTANT]  
    > ABS에서는 Active Directory 도메인 서비스에 액세스할 수 없어 기본 전화 번호를 <STRONG>msRTCSIP-line</STRONG> 특성에 복사할 수 없으므로 ABS(주소록 서비스)에서 정규화를 수행하는 경우에도 Active Directory 도메인 서비스에 있는 각 사용자의 기본 전화 번호를 정규화해야 합니다.

    
    </div>

</div>

<div>

## <a name="step-2-enable-users-for-enterprise-voice"></a>2단계. 사용자가 Enterprise Voice를 사용할 수 있도록 설정

사용할 수 있도록 설정할 사용자를 식별하기만 하면 이 단계를 완료하는 데 다른 특별한 계획은 필요하지 않습니다.

</div>

<div>

## <a name="step-3-prepare-dial-plans-for-users"></a>3단계. 사용자에 대해 다이얼 플랜 준비

Enterprise Voice를 사용할 수 있도록 설정된 사용자는 적절한 다이얼 플랜이 있어야 PSTN에 전화를 걸 수 있습니다. 다이얼 플랜은 전화 인증 및 통화 라우팅을 위해 명명된 위치, 개별 사용자 또는 연락처 개체의 전화 번호를 하나의 표준(E.164) 형식으로 변환하는 명명된 정규화 규칙 집합입니다. 정규화 규칙은 다양한 형식으로 표현된 전화 번호를 지정된 각 위치, 사용자 또는 연락처 개체에 대해 라우팅하는 방법을 정의합니다.

다이얼 플랜을 준비 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 다이얼 플랜 및 정규화 규칙](lync-server-2013-dial-plans-and-normalization-rules.md)을 참조 하십시오.

</div>

<div>

## <a name="step-4-plan-user-voice-policies"></a>4단계. 사용자 음성 정책 계획

회사 전화에서 장거리 또는 국제 전화를 걸 수 있는 권한 등 기존 PBX에 대한 사용자의 서비스 클래스 설정은 사용자에 대한 VoIP 정책이 Enterprise Voice로 이동함에 따라 다시 구성되어야 합니다. Enterprise Voice에 대 한 정책 계획 및 만들기에 대 한 자세한 내용은 [Lync Server 2013의 음성 정책을](lync-server-2013-voice-policies.md)참조 하세요.

</div>

<div>

## <a name="step-5-plan-outbound-call-routes"></a>5단계. 아웃바운드 통화 경로 계획

Call 경로 Lync Server가 Enterprise Voice 사용자가 설정한 아웃 바운드 호출을 처리 하는 방법을 지정 합니다. 사용자가 전화를 걸면 서버는 필요한 경우 전화 걸기 문자열을 E.164 형식으로 정규화하고 SIP URI에 일치시키려고 합니다. 일치시킬 수 없는 경우 서버는 해당 번호에 기초하여 아웃바운드 통화 라우팅 논리를 적용합니다. 해당 논리를 정의하는 마지막 단계는 각 다이얼 플랜에 나열된 각 대상 전화 번호 집합에 대한 별도의 명명된 통화 경로를 만드는 것입니다.

통화 경로를 계획 하는 방법에 대 한 자세한 내용은 [Lync Server 2013의 음성 경로](lync-server-2013-voice-routes.md)를 참조 하십시오.

</div>

<div>

## <a name="step-6-configure-pbx-or-sip-trunk-to-reroute-calls-for-enterprise-voice-users"></a>6단계. Enterprise Voice 사용자에 대한 통화를 다시 라우팅하도록 PBX 또는 SIP 트렁크 구성

ITSP(인터넷 전화 통신 서비스 공급자)에 연결된 일반 PBX 또는 SIP 트렁크 연결에서 이전에 호스팅된 사용자는 이동 후에도 전화 번호가 유지됩니다. 이러한 요구 사항은 이동 후에도 기업 음성 사용자에 대 한 수신 전화를 중재 서버로 라우팅하기 위해 PBX 또는 SIP 트렁크를 다시 구성 해야 한다는 것입니다.

</div>

<div>

## <a name="step-7-move-users-to-exchange-unified-messaging-recommended"></a>7단계. Exchange 통합 메시징으로 사용자 이동(권장)

사용자를 Exchange 통합 메시징으로 이동하는 과정은 다음 작업으로 구성됩니다.

  - Exchange 통합 메시징과 Lync Server가 함께 작동 하도록 구성 합니다.

  - 사용자가 Exchange 통합 메시징 통화 응답 및 Outlook Voice Access를 사용할 수 있도록 설정합니다. 이 작업은 Exchange 통합 메시징 서버에서 수행됩니다. 자세한 내용은에서 [http://go.microsoft.com/fwlink/p/?linkID=139372](http://go.microsoft.com/fwlink/p/?linkid=139372)Exchange Server 2010 TechNet 라이브러리를 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

