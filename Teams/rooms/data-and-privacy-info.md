---
title: 데이터 및 개인 정보
author: altsou
ms.author: altsou
manager: serdars
ms.date: 06/01/2022
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 데이터 및 개인 정보
f1keywords: Microsoft Teams Rooms Managed Service Data and Privacy Information
ms.openlocfilehash: ec28dcafa7825e7f754d3631d2c21400a08c9b83
ms.sourcegitcommit: baf29d244b428712052553f9e4484e72e727247e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2022
ms.locfileid: "69046787"
---
# <a name="approach"></a>접근

Microsoft Teams 룸 Managed Services를 사용하는 고객은 Microsoft에 가장 가치 있는 자산인 데이터를 위임합니다. 그들은 개인 정보 보호가 보호되고 자신의 기대와 일치하는 방식으로만 사용될 것이라고 신뢰합니다.

이 기술은 개인 정보 처리 프로세스를 따라 서비스를 효과적으로 실행하는 데이터를 수집하고 사용하는 고객의 약속을 준수하는지 확인합니다.
## <a name="data-collection-and-privacy"></a>데이터 수집 및 개인 정보

 Microsoft Teams 룸 Managed Services는 디바이스를 모니터링하고, 고객 콘텐츠 데이터를 수집하며, 원격으로 디바이스에 액세스하고 관리자 권한으로 관리합니다. 수집되는 데이터는 등록된 회의실에서 식별된 상태, 근본 원인 및 완화 문제를 모니터링하는 데 필요한 정보로 제한됩니다. 수집된 특정 데이터는 개별 사용자가 아닌 회의실 계정에만 적용됩니다.

> [!Note]
> 개별 사용자에 대한 부수적 참조는 디바이스를 사용하는 동안 활동 로그에 있을 수 있습니다.

## <a name="who-can-access-data"></a>데이터에 액세스할 수 있는 사용자

Managed Services는 권한이 없는 사용자가 부적절한 액세스 또는 사용으로부터 고객 데이터를 보호하는 데 도움이 되는 강력한 조치를 취합니다. 이러한 조치에는 Microsoft 직원 및 하청업체의 액세스 제한이 포함됩니다.

## <a name="zero-standing-access-data-storage"></a>제로 스탠딩 액세스 데이터 스토리지

Managed Services는 제로 스탠딩 액세스 원칙을 통해 조직 내부 및 외부의 악의적인 행위자로부터 권한 있는 액세스 권한이 있는 계정과 관련된 위험을 완화합니다. 이 원칙을 통해 Managed Services는 기본적으로 모든 사용자가 사용할 수 있는 권한 없이 작동할 수 있습니다. Just-In-Time 및 Just-Enough-Access의 원칙과 결합되어 기본적으로 안전하고 규정을 준수할 수 있는 강력한 프레임워크를 제공합니다. 진단 데이터는 내부 포털을 통해 Microsoft 서비스 운영 팀에서 사용할 수 있습니다.

## <a name="data-handling"></a>데이터 처리

Microsoft는 데이터 전송, 스토리지, 사용 및 보존에 대한 엄격한 표준의 적용을 받습니다. Microsoft에는 데이터 분류에 따라 데이터를 처리하는 방법을 규제하는 데이터 처리 표준 정책이 있습니다.

## <a name="technology-description"></a>기술 설명

Managed Services는 배포의 문제를 모니터링, 진단 및 완화하기 위해 Microsoft에 데이터를 보냅니다. 예를 들면 다음과 같습니다.

- 디바이스가 최신 상태인지 확인(앱, OS, 드라이버, F/W 포함)
- 디바이스를 사용할 준비가 되도록(로그인, 정상 상태를 보고하는 모든 주변 장치 등)
- 환경 준비(계정 프로비저닝, 네트워크 속도 충분히 빠름 등)
- 하드웨어 문제 또는 설치 문제(예: 느슨한 케이블 연결)가 있을 수 있는지 확인
- 문제를 확인하기 위한 추론(과도한 재부팅 등)

Managed Services는 다음 작업을 사용하여 디바이스를 관리합니다.

- 소프트웨어 업데이트
- 다시 부팅을 통해 문제를 완화하고 USB 연결 & 상태를 다시 설정합니다.
- 문제를 진단하는 데 도움이 되는 특정 로그 수집

Managed Services는 솔루션 키트의 오디오, 비디오, 미디어 또는 모임 콘텐츠를 모니터링하거나 기록하지 않습니다.

### <a name="service-collected-data-categories"></a>서비스 수집 데이터 범주
 
|범주|세부 정보|쿼리 이유|
| :- | :- | :- |
|지속적인 데이터 수집 및 관리|IP 주소, 회의실 계정의 ID(Exchange, 비즈니스용 Skype 및/또는 Teams), Microsoft 또는 소프트웨어와 포털 내의 위치 좌표, 전자 메일 및 통신|관리 중인 시스템을 식별하고 연결합니다. 오류를 식별, 진단 및 완화합니다. 사용량, 분석 및 인사이트를 추적합니다. 연결 상태 쿼리 및 복구|
|임시 데이터 수집 및 관리|이벤트 로그 정보, 진단 정보, Windows 시스템 쿼리와 함께 로그 파일에 로그인한 회의실 사용자의 사용자 활동/ID(예: USB 디바이스 목록, 전원 상태 등)|사용량, 분석 및 인사이트에 대한 오류 식별, 진단 및 완화|

디바이스 활동 로그의 특정 중요한 데이터는 로컬에서 수정됩니다(관리되는 서비스에서 수집하지 않음).

- 모임 제목 및 본문
- 모임 참석자에 대한 연락처 카드 정보(예: 제목, 전화 번호 등)
- 모임 메신저 메시지 콘텐츠에서

> [!NOTE]
> Microsoft가 Managed Services를 발전함에 따라 특정 데이터는 변경될 수 있습니다.

### <a name="enrollment"></a>등록

관리되는 서비스는 진단 및 보고를 비롯한 자동화된 모니터링 및 지원 서비스를 위해 온라인 포털에 등록됩니다. 등록은 디바이스의 TPM(신뢰할 수 있는 플랫폼 모듈) 기반 공개 키를 사용하여 암호화된 네트워크 통신을 통해 수행됩니다.

### <a name="unenrollment"></a>등록 취소

관리되는 서비스를 제거하여 디바이스를 등록 취소할 수 있습니다. 또한 Microsoft는 서비스 해제 중에 백 엔드 모니터링에서 디바이스를 제거하고 요청 시 수집된 데이터를 삭제할 수 있습니다.
## <a name="compliance"></a>규정 준수

제품을 작업하는 모든 엔지니어는 보안 및 개인 정보 보호 인식 교육을 받아야 합니다. Microsoft는 또한 모든 직원이 개인 정보 요구 사항에 대한 책임 수용을 인증하도록 보장합니다.

Managed Services는 유럽(EU), APAC(아시아 태평양) 및 미국(미국)의 데이터 센터를 통해 지역 데이터 상주 지원을 제공합니다. 서비스 고객은 선택한 지역의 데이터 센터에 저장된 조직과 관련된 데이터를 갖게 됩니다.

## <a name="more-resources"></a>추가 리소스

Windows 보안용 Microsoft Teams 룸: [[Microsoft Teams for Windows 보안](/microsoftteams/rooms/security-windows) \
Android 보안용 Microsoft Teams 룸: [Android 보안용 Microsoft Teams](/microsoftteams/rooms/security-android) \
Microsoft 개인정보처리방침: https://aka.ms/privacy \
Microsoft의 데이터 관리: https://www.microsoft.com/trust-center/privacy/data-management \
관리 서비스 서비스 설명: [Microsoft Teams 룸 관리 서비스](rooms-pro-management.md)
