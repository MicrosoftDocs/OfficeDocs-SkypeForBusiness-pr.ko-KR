---
title: 비즈니스용 Skype 서버용 프런트 엔드 서버 VoIP 구성 요소
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 310e81a7-da45-47d4-95d0-92837e386502
description: 번역 서비스와 다양 한 라우팅 구성 요소를 포함 하 여 비즈니스용 Skype 서버의 프런트 엔드 서버에 있는 Enterprise Voice 구성 요소에 대해 알아봅니다.
ms.openlocfilehash: d28beb809e172ea5d778e0cf8273cb232b7cf67c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187689"
---
# <a name="front-end-server-voip-components-for-skype-for-business-server"></a>비즈니스용 Skype 서버용 프런트 엔드 서버 VoIP 구성 요소

번역 서비스와 다양 한 라우팅 구성 요소를 포함 하 여 비즈니스용 Skype 서버의 프런트 엔드 서버에 있는 Enterprise Voice 구성 요소에 대해 알아봅니다.

프런트 엔드 서버에 있는 VoIP 구성 요소는 다음과 같습니다.

- 번역 서비스

- 인바운드 라우팅 구성 요소

- 아웃 바운드 라우팅 구성 요소

- Exchange UM 라우팅 구성 요소

- Intercluster 라우팅 구성 요소

- [비즈니스용 Skype 서버의 중재 서버 구성 요소](mediation-server.md)

## <a name="translation-service"></a>번역 서비스

번역 서비스는 관리자가 정의한 정규화 규칙에 따라, 전화를 통해 번호를 E 164 형식 또는 다른 형식으로 번역 하는 역할을 하는 서버 구성 요소입니다. 조직에서 개인 번호 매기기 시스템을 사용 하거나 E. f 2를 지원 하지 않는 게이트웨이나 PBX를 사용 하는 경우 번역 서비스는 E가 아닌 형식으로 변환할 수 있습니다.

## <a name="inbound-routing-component"></a>인바운드 라우팅 구성 요소

인바운드 라우팅 구성 요소는 해당 엔터프라이즈 음성 클라이언트에서 사용자가 지정한 환경 설정에 따라 들어오는 전화를 처리 합니다. 또한 사용자가 구성한 경우 대리인의 신호음 울림 및 동시 벨 울림이 용이해 집니다. 예를 들어 사용자는 응답 하지 않은 통화가 전달 되는지, 아니면 간단히 알림만 로깅할지를 지정 합니다. 착신 통화 전환 기능을 사용 하는 경우 사용자는 응답 하지 않은 전화를 다른 번호로 전달할지 또는 통화 응답을 제공 하도록 구성 된 Exchange UM 서버로 보낼지 여부를 지정할 수 있습니다. 인바운드 라우팅 구성 요소는 모든 스탠더드 버전 서버와 프런트 엔드 서버에 기본적으로 설치 됩니다.

## <a name="outbound-routing-component"></a>아웃 바운드 라우팅 구성 요소

아웃 바운드 라우팅 구성 요소는 PBX 또는 PSTN 대상으로 통화를 라우팅합니다. 이는 사용자의 음성 정책에 의해 정의 된 대로 통화 권한 부여 규칙을 호출자에 적용 하 고 각 호출을 라우팅하기 위한 최적의 PSTN 게이트웨이를 결정 합니다. 아웃 바운드 라우팅 구성 요소는 모든 스탠더드 버전 서버와 프런트 엔드 서버에 기본적으로 설치 됩니다.

아웃 바운드 라우팅 구성 요소에서 사용 하는 라우팅 논리는 조직의 요구 사항에 따라 네트워크 또는 전화 통신 관리자가 구성한 대규모 측정값입니다.

## <a name="exchange-um-routing-component"></a>Exchange UM 라우팅 구성 요소

Exchange UM 라우팅 구성 요소는 비즈니스용 Skype 서버와 UM (통합 메시징)를 실행 하는 서버 간의 라우팅을 처리 하 여 비즈니스용 Skype 서버를 통합 메시징 기능과 통합 합니다.

Exchange um 라우팅 구성 요소는 또한 Exchange UM 서버를 사용할 수 없는 경우 PSTN을 통해 음성 메일을 다시 라우팅하도록 처리 합니다. 중앙 사이트에 대 한 탄성 WAN 링크가 없는 지점 사이트에서 엔터프라이즈 음성 사용자를 사용 하는 경우 지점 사이트에서 배포 하는 Survivable Branch 기기는 WAN을 중단 하는 동안 분기 사용자를 위해 음성 메일 survivability을 제공 합니다. WAN 링크를 사용할 수 없는 경우 Survivable Branch 기기는 다음을 수행 합니다.

- 중앙 사이트의 Exchange 통합 메시징 서버에 대 한 PSTN을 통해 응답 하지 않은 통화를 다시 라우팅합니다.

- 사용자가 PSTN을 통해 음성 메일 메시지를 검색할 수 있는 기능을 제공 합니다.

- 부재 중 전화 알림을 큐에 대기 시키고 WAN 링크가 복원 되 면 Exchange UM 서버에 업로드 합니다.

음성 메일 전환 기능을 사용 하도록 설정 하려면 Exchange 관리자가 메시지를 수락 하도록 Exchange UM 자동 전화 교환 (AA)을 구성 하는 것이 좋습니다.

이러한 기능에 대 한 자세한 내용은 각각 [엔터프라이즈 음성 복구에 대 한](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)온 [-프레미스 Exchange 통합 메시징 통합](https://technet.microsoft.com/library/e7c63a71-2d99-4aa9-b649-36c1a431bdf1.aspx) 및 계획을 참조 하세요.

## <a name="intercluster-routing-component"></a>Intercluster 라우팅 구성 요소

Intercluster routing component는 피호출자의 기본 등록자 풀로의 호출을 라우팅하는 역할을 합니다. 이 기능을 사용할 수 없는 경우이 구성 요소는 호출을 피호출자의 백업 등록자 풀로 라우팅합니다. 호출 수신자의 기본 및 백업 등록자 풀에 IP 네트워크를 통해 연결할 수 없는 경우 Intercluster routing component는 PSTN을 통해 통화를 사용자의 전화 번호로 다시 라우팅합니다.

## <a name="other-front-end-server-components-required-for-voip"></a>VoIP에 필요한 다른 프런트 엔드 서버 구성 요소

VoIP에 대 한 필수 지원을 제공 하는 프런트 엔드 서버 또는 디렉터에 있는 다른 구성 요소는 자신의 VoIP 구성 요소가 아니라 다음을 포함 합니다.

- **사용자 서비스.** 들어오는 각 호출의 대상 전화 번호에 대 한 역방향 번호 조회를 수행 하 고 해당 번호와 대상 사용자의 SIP URI를 일치 시킵니다. 인바운드 라우팅 구성 요소는이 정보를 사용 하 여 해당 사용자의 등록 된 SIP 끝점으로 통화를 배포 합니다. 사용자 서비스는 모든 프런트 엔드 서버 및 디렉터의 핵심 구성 요소입니다.

- **사용자 복제기.** Active Directory 도메인 서비스에서 사용자의 전화 번호를 추출 하 고이를 사용자 서비스 및 주소록 서버에서 사용할 수 있는 RTC 데이터베이스의 테이블에 씁니다. 사용자 복제기는 모든 프런트 엔드 서버의 핵심 구성 요소입니다.

- **주소록 서버.** Active Directory 도메인 서비스에서 비즈니스용 Skype 서버 클라이언트에 게 전역 주소 목록 정보를 제공 합니다. 또한 RTC 데이터베이스에서 사용자 및 연락처 정보를 검색 하 고, 정보를 주소록 파일에 쓴 다음 비즈니스용 Skype 클라이언트에서 다운로드 한 공유 폴더에 파일을 저장 합니다. 주소록 서버는 주소록 웹 쿼리 서비스에서 비즈니스용 Skype의 사용자 검색 쿼리에 응답 하는 데 사용 하는 RTCAb 데이터베이스에 정보를 기록 합니다. 비즈니스용 Skype에서 사용자 연락처를 프로 비전 할 목적으로 RTC 데이터베이스에 기록 되는 엔터프라이즈 사용자 전화 번호를 선택적으로 표준화 합니다. 주소록 서비스는 모든 프런트 엔드 서버에 기본적으로 설치 됩니다. 주소록 웹 쿼리 서비스는 기본적으로 각 프런트 엔드 서버의 웹 서비스와 함께 설치 됩니다.


