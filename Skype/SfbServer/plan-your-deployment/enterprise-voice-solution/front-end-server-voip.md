---
title: 비즈니스용 Skype 서버의 프런트 엔드 서버 VoIP 구성 요소
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 310e81a7-da45-47d4-95d0-92837e386502
description: 번역 Enterprise Voice 다양한 라우팅 구성 요소를 포함하여 비즈니스용 Skype 서버의 프런트 엔드 서버에 있는 구성 요소에 대해 자세히 알아보습니다.
ms.openlocfilehash: 830f54e59e0d2135e3748fd03474b19e22741136
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101494"
---
# <a name="front-end-server-voip-components-for-skype-for-business-server"></a>비즈니스용 Skype 서버의 프런트 엔드 서버 VoIP 구성 요소

번역 Enterprise Voice 다양한 라우팅 구성 요소를 포함하여 비즈니스용 Skype 서버의 프런트 엔드 서버에 있는 구성 요소에 대해 자세히 알아보습니다.

프런트 엔드 서버에 있는 VoIP 구성 요소는 다음과 같습니다.

- 변환 서비스

- 인바운드 라우팅 구성 요소

- 아웃바운드 라우팅 구성 요소

- Exchange UM 라우팅 구성 요소

- Intercluster 라우팅 구성 요소

- [비즈니스용 Skype 서버의 중재 서버 구성 요소](mediation-server.md)

## <a name="translation-service"></a>변환 서비스

변환 서비스는 관리자가 정의한 정규화 규칙에 따라 전화 건 번호를 E.164 형식 또는 다른 형식으로 변환하는 역할을 수행하는 서버 구성 요소입니다. 조직에서 사설 번호 시스템을 사용하거나 E.164 형식을 지원하지 않는 게이트웨이나 PBX를 사용할 경우에는 변환 서비스가 E.164 이외의 다른 형식으로 변환할 수 있습니다.

## <a name="inbound-routing-component"></a>인바운드 라우팅 구성 요소

인바운드 라우팅 구성 요소는 Enterprise Voice 클라이언트에서 사용자가 지정한 기본 설정에 따라 수신 전화를 대규모로 처리합니다. 또한 사용자가 구성한 경우 대리인 신호 울림 및 동시 신호 울림도 쉽게 사용할 수 있도록 합니다. 예를 들어 사용자는 응답하지 않는 전화를 착신 전환할지 알림을 위해 기록만 할지를 지정합니다. 통화 전달을 사용하도록 설정한 경우 사용자는 응답하지 않은 통화를 다른 번호로 전달할지 또는 전화 응답을 제공하도록 구성된 Exchange UM 서버로 전달할지 여부를 지정할 수 있습니다. 인바운드 라우팅 구성 요소는 기본적으로 모든 Standard Edition 서버 및 프런트 엔드 서버에 설치됩니다.

## <a name="outbound-routing-component"></a>아웃바운드 라우팅 구성 요소

아웃바운드 라우팅 구성 요소는 전화를 PBX 또는 PSTN 대상으로 라우팅합니다. 사용자의 음성 정책에 정의된 통화 권한 부여 규칙을 발신자에 적용하고 각 통화를 라우팅하기 위한 최적의 PSTN 게이트웨이를 파악합니다. 아웃바운드 라우팅 구성 요소는 기본적으로 모든 Standard Edition 서버 및 프런트 엔드 서버에 설치됩니다.

아웃바운드 라우팅 구성 요소에 사용되는 라우팅 논리는 대부분 네트워크 또는 전화 통신 관리자가 해당 조직의 요구 사항에 따라 구성합니다.

## <a name="exchange-um-routing-component"></a>Exchange UM 라우팅 구성 요소

Exchange UM 라우팅 구성 요소는 비즈니스용 Skype 서버와 Exchange UM(통합 메시징)을 실행하는 서버 간의 라우팅을 처리하여 비즈니스용 Skype 서버를 통합 메시징 기능과 통합합니다.

Exchange UM 라우팅 구성 요소는 Exchange UM 서버를 사용할 수 없는 경우 PSTN을 통해 음성 메일의 다시 라우팅도 처리합니다. 중앙 사이트에 Enterprise Voice WAN 링크가 없는 분기 사이트의 사용자가 있는 경우 분기 사이트에서 배포하는 Survivable Branch Appliance는 WAN이 정전되는 동안 분기 사용자에게 음성 메일 지속성을 제공합니다. WAN 연결을 사용할 수 없는 경우 SBA는 다음을 수행합니다.

- PSTN을 통해 응답하지 않은 전화를 중앙 사이트의 Exchange 통합 메시징 서버로 다시 라우팅합니다.

- PSTN을 통해 음성 메일 메시지를 검색하는 기능을 사용자에게 제공합니다.

- 부재 중 전화 알림을 큐에 넣은 다음 WAN 링크가 복원되면 Exchange UN 서버로 해당 알림을 업로드합니다.

음성 메일 다시 로우트를 사용하도록 설정하려면 Exchange 관리자가 메시지만 수락하도록 AA(Exchange UM 자동 전화 교환)를 구성하는 것이 좋습니다.

이러한 기능에 대한 자세한 내용은 [On-Premises Exchange Unified Messaging Integration](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-exchange-unified-messaging-integration) 및 [Planning for Enterprise Voice Resiliency](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-enterprise-voice-resiliency)을 각각 참조하십시오.

## <a name="intercluster-routing-component"></a>Intercluster 라우팅 구성 요소

Intercluster 라우팅 구성 요소는 통화를 발신자 기본 등록자 풀로 라우팅합니다. 이 기능을 사용할 수 없는 경우 구성 요소는 통화를 발신자 백업 등록자 풀로 라우팅합니다. IP 네트워크를 통해 발신자 기본 및 백업 등록자 풀에 연결되지 않는 경우 Intercluster 라우팅 구성 요소는 PSTN을 통해 통화를 사용자의 전화 번호로 다시 라우팅합니다.

## <a name="other-front-end-server-components-required-for-voip"></a>VoIP에 필요한 기타 프런트 엔드 서버 구성 요소

VoIP에 대한 필수 지원을 제공하지만 자체 VoIP 구성 요소는 아닌 프런트 엔드 서버 또는 Director에 있는 다른 구성 요소에는 다음이 포함됩니다.

- **사용자 서비스.** 각 수신 전화의 대상 전화 번호에 대해 역방향 번호 조회를 수행하고 대상 사용자의 SIP URI에 해당 번호를 일치시킵니다. 이 정보를 사용하여 인바운드 라우팅 구성 요소는 통화를 해당 사용자의 등록된 SIP 끝점으로 분산합니다. User Services는 모든 프런트 엔드 서버 및 Director의 핵심 구성 요소입니다.

- **User Replicator.** Active Directory 도메인 서비스에서 사용자 전화 번호를 추출하여 RTC 데이터베이스의 테이블에 써서 사용자 서비스 및 주소 예약 서버에서 사용할 수 있습니다. User Replicator는 모든 프런트 엔드 서버의 핵심 구성 요소입니다.

- **주소록 서버.** Active Directory 도메인 서비스에서 비즈니스용 Skype 서버 클라이언트로의 전체 주소 목록 정보를 제공합니다. 또한 RTC 데이터베이스에서 사용자 및 연락처 정보를 검색하고 주소 기록 파일에 정보를 쓴 다음 비즈니스용 Skype 클라이언트에서 다운로드하는 공유 폴더에 파일을 저장합니다. 주소 기록 서버는 비즈니스용 Skype 모바일에서 사용자 검색 쿼리에 응답하는 데 사용되는 RTCAb 데이터베이스에 정보를 쓴다. 선택적으로 비즈니스용 Skype에서 사용자 연락처를 프로비전하기 위해 RTC 데이터베이스에 기록된 엔터프라이즈 사용자 전화 번호를 정규화합니다. 주소장 서비스는 기본적으로 모든 프런트 엔드 서버에 설치됩니다. 주소부 웹 쿼리 서비스는 기본적으로 각 프런트 엔드 서버에 웹 서비스와 함께 설치됩니다.