---
title: 'Lync Server 2013: 프런트 엔드 서버 VoIP 구성 요소'
description: 'Lync Server 2013: 프런트 엔드 서버 VoIP 구성 요소'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End Server VoIP components
ms:assetid: 310e81a7-da45-47d4-95d0-92837e386502
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425812(v=OCS.15)
ms:contentKeyID: 48183765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9390d06cf6277ef79ec2ec785bad4b497bc04a7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567095"
---
# <a name="front-end-server-voip-components-for-lync-server-2013"></a>Lync Server 2013의 프런트 엔드 서버 VoIP 구성 요소

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-01_

프런트 엔드 서버에 있는 VoIP 구성 요소는 다음과 같습니다.

  - 변환 서비스

  - 인바운드 라우팅 구성 요소

  - 아웃바운드 라우팅 구성 요소

  - Exchange UM 라우팅 구성 요소

  - Intercluster 라우팅 구성 요소

  - [Lync Server 2013의 중재 서버 구성 요소](lync-server-2013-mediation-server-component.md)

<div>

## <a name="translation-service"></a>변환 서비스

변환 서비스는 관리자가 정의한 정규화 규칙에 따라 전화 건 번호를 E.164 형식 또는 다른 형식으로 변환하는 역할을 수행하는 서버 구성 요소입니다. 조직에서 사설 번호 시스템을 사용하거나 E.164 형식을 지원하지 않는 게이트웨이나 PBX를 사용할 경우에는 변환 서비스가 E.164 이외의 다른 형식으로 변환할 수 있습니다.

</div>

<div>

## <a name="inbound-routing-component"></a>인바운드 라우팅 구성 요소

인바운드 라우팅 구성 요소는 Enterprise Voice 클라이언트에서 사용자가 지정한 기본 설정에 따라 수신 전화를 대규모로 처리합니다. 또한 사용자가 구성한 경우 대리인 신호 울림 및 동시 신호 울림도 쉽게 사용할 수 있도록 합니다. 예를 들어 사용자는 응답하지 않는 전화를 착신 전환할지 알림을 위해 기록만 할지를 지정합니다. 착신 전환 기능을 사용 하도록 설정 하면 사용자는 응답 하지 않은 통화를 다른 번호 또는 전화 응답을 제공 하도록 구성 된 Exchange UM 서버로 전달할지 여부를 지정할 수 있습니다. 인바운드 라우팅 구성 요소는 모든 Standard Edition 서버 및 프런트 엔드 서버에 기본적으로 설치 됩니다.

</div>

<div>

## <a name="outbound-routing-component"></a>아웃바운드 라우팅 구성 요소

아웃바운드 라우팅 구성 요소는 전화를 PBX 또는 PSTN 대상으로 라우팅합니다. 이 구성 요소는 사용자 음성 정책에 의해 정의된 통화 권한 부여 규칙을 발신자에게 적용하고 각 전화를 라우팅하는 데 사용할 최적의 PSTN 게이트웨이를 결정합니다. 아웃 바운드 라우팅 구성 요소는 모든 Standard Edition 서버 및 프런트 엔드 서버에 기본적으로 설치 됩니다.

아웃바운드 라우팅 구성 요소에 사용되는 라우팅 논리는 대부분 네트워크 또는 전화 통신 관리자가 해당 조직의 요구 사항에 따라 구성합니다.

</div>

<div>

## <a name="exchange-um-routing-component"></a>Exchange UM 라우팅 구성 요소

Exchange UM 라우팅 구성 요소는 lync Server와 Exchange UM (통합 메시징)을 실행 하는 서버 간의 라우팅을 처리 하 여 Lync Server를 통합 메시징 기능과 통합 합니다.

Exchange um 서버를 사용할 수 없는 경우에도 PSTN을 통해 음성 메일을 다시 라우팅하는 것을 처리 합니다. 중앙 사이트에 대 한 복구 가능한 WAN 링크가 없는 분기 사이트에 Enterprise Voice users가 있는 경우 분기 사이트에서 배포 하는 Sba (survivable 분기 기기는 WAN 중단 시 분기 사용자에 게 음성 메일 지 속성 제공 합니다. WAN 연결을 사용할 수 없는 경우 SBA는 다음을 수행합니다.

  - PSTN을 통해 응답하지 않은 전화를 중앙 사이트의 Exchange 통합 메시징 서버로 다시 라우팅합니다.

  - PSTN을 통해 음성 메일 메시지를 검색하는 기능을 사용자에게 제공합니다.

  - 부재 중 전화 알림을 큐에 넣은 다음 WAN 링크가 복원되면 Exchange UN 서버로 해당 알림을 업로드합니다.

음성 메일 경로를 다시 라우팅하도록 설정 하려면 Exchange 관리자가 메시지를 수락 하도록 Exchange UM 자동 전화 교환 (AA)을 구성 하는 것이 좋습니다.

이러한 기능에 대 한 자세한 내용은 [Lync server 2013의 Exchange 통합 메시징 통합 계획](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) 및 [lync Server 2013의 Enterprise Voice 복구 계획](lync-server-2013-planning-for-enterprise-voice-resiliency.md)을 참조 하십시오.

</div>

<div>

## <a name="intercluster-routing-component"></a>Intercluster 라우팅 구성 요소

Intercluster 라우팅 구성 요소는 통화를 수신자의 기본 등록자 풀로 라우팅합니다. 이렇게 할 수 없는 경우 이 구성 요소는 통화를 수신자의 백업 등록자 풀로 라우팅합니다. IP 네트워크를 통해 수신자의 기본 및 백업 등록자 풀에 연결할 수 없으면 Intercluster 라우팅 구성 요소는 PSTN을 통해 통화를 사용자 전화 번호로 다시 라우팅합니다.

</div>

<div>

## <a name="other-front-end-server-components-required-for-voip"></a>VoIP에 필요한 기타 프런트 엔드 서버 구성 요소

VoIP에 필수적인 지원을 제공 하지만 자체 VoIP 구성 요소가 아니라 프런트 엔드 서버 또는 디렉터에 있는 기타 구성 요소에는 다음이 포함 됩니다.

  - **사용자 서비스.** 각 수신 전화의 대상 전화 번호에 대해 역방향 번호 조회를 수행하고 대상 사용자의 SIP URI에 해당 번호를 일치시킵니다. 이 정보를 사용하여 인바운드 라우팅 구성 요소가 사용자의 등록된 SIP 끝점으로 전화를 분산시킵니다. 사용자 서비스는 모든 프런트 엔드 서버 및 디렉터의 핵심 구성 요소입니다.

  - **User Replicator.** Active Directory 도메인 서비스에서 사용자 전화 번호를 추출 하 여 사용자 서비스 및 주소록 서버에서 사용할 수 있는 RTC 데이터베이스의 테이블에 씁니다. 사용자 복제기는 모든 프런트 엔드 서버의 핵심 구성 요소입니다.

  - **주소록 서버.** Active Directory 도메인 서비스의 전체 주소 목록 정보를 Lync Server 클라이언트에 제공 합니다. 또한 RTC 데이터베이스에서 사용자 및 연락처 정보를 검색 하 고, 정보를 주소록 파일에 쓴 다음 Lync 클라이언트에서 다운로드 한 공유 폴더에 파일을 저장 합니다. 주소록 서버는 주소록 웹 쿼리 서비스에서 Microsoft Lync 2010 Mobile의 사용자 검색 쿼리에 응답 하기 위해 사용 하는 RTCAb 데이터베이스에 정보를 기록 합니다. 선택적으로 Lync에서 사용자 연락처를 프로 비전 하기 위해 RTC 데이터베이스에 기록 되는 엔터프라이즈 사용자 전화 번호를 정규화 합니다. 주소록 서비스는 모든 프런트 엔드 서버에 기본적으로 설치 됩니다. 주소록 웹 쿼리 서비스는 각 프런트 엔드 서버의 웹 서비스와 함께 기본적으로 설치 됩니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

