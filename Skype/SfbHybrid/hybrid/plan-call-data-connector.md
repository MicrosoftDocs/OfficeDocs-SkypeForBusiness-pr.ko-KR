---
title: 통화 데이터 커넥터 계획 | 통화 품질 대시보드 모니터링 하이브리드 분석
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 비즈니스용 Skype 온라인 원격 분석 도구를 사용 하 여 하이브리드 시나리오에서 온-프레미스 구현을 모니터링 하는 방법에 대해 간략하게 설명 합니다.
ms.openlocfilehash: ad4d7ddb270bc4e4227eea7d33c37411ea96fa8c
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779664"
---
# <a name="plan-call-data-connector"></a>통화 데이터 커넥터 계획

## <a name="overview"></a>개요

이 항목에서는 비즈니스용 Skype 서버 통화 데이터 커넥터를 구현 하기 위한 혜택, 계획 고려 사항 및 요구 사항에 대해 설명 합니다. 통화 데이터 커넥터를 구성 하는 방법에 대 한 자세한 내용은 [Configure Call Data connector](configure-call-data-connector.md)을 참조 하십시오.


통화 데이터 커넥터는 서로 다른 온-프레미스 및 온라인 도구 집합을 사용 하 여 모든 사용자 통화 품질을 모니터링할 필요가 없기 때문에 하이브리드 환경에서 호출 모니터링이 매우 간단해 집니다. 사용자가 온-프레미스에 있거나 온라인 상태 인지 여부에 관계 없이 전체 조직에 대 한 통화 품질을 온라인으로 볼 수 있습니다.

Call Data Connector에서는 단일 도구 집합을 사용 하 여 다음 작업을 수행할 수 있습니다.

- Microsoft 팀원, 비즈니스용 Skype Online 및 비즈니스용 Skype 서버에서 사용자 환경을 모니터링 합니다.

- 네트워크에서 문제를 확인 하 고 문제를 해결 합니다.

- 헬프데스크 및 관리자 역할을 할당 하 여 지원 자가 해당 분야를 확인 하 고 문제를 해결할 수 있도록 합니다.

Call Data Connector를 사용 하는 경우 비즈니스용 Skype 서버는 다음 다이어그램에 나와 있는 것 처럼 비즈니스용 Skype (온라인 통화 분석) 및 CQD (통화 품질 대시보드) 도구를 활용할 수 있도록 통화 데이터를 클라우드 서비스에 푸시합니다.

![SfB Cloud 음성 메일](../../sfbserver2019/media/call-data-connector-plan-1.png)

서버는 QoE (서비스 품질) 및 CDR (통화 정보 기록) 데이터를 온라인 서비스에 푸시합니다.

통화 분석 및 CQD 도구를 사용 하면 다음과 같이 통화 품질을 모니터링 하 고 Microsoft 팀 및 비즈니스용 Skype 서비스와의 연결 문제를 해결할 수 있습니다.

- 통화 분석은 특정 통화의 품질 문제에 초점을 맞춥니다. 비즈니스용 Skype 계정의 각 사용자에 대 한 통화 및 모임에 대 한 자세한 정보를 표시 합니다.  통화 분석을 사용 하 여 헬프데스크 운영자에 게 사용 권한을 할당 한 다음 비즈니스용 Skype 관리 센터의 나머지에 대 한 액세스 권한이 없어도 통화를 모니터링할 수 있습니다.

- 통화 품질 대시보드는 조직 전반의 네트워크 성능 및 문제에 중점을 둔 것입니다. 비즈니스용 Skype 관리자 및 네트워크 엔지니어는이 도구를 사용 하 여 네트워크 성능 문제를 해결 하 고 최적화 합니다.

자세한 내용은 [통화 분석 및 통화 품질 대시보드](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard)를 참조 하세요.

물론 일부 통화 품질 데이터는 온-프레미스로 유지 해야 할 수 있습니다. 예를 들어 사용자 지정 된 보고서 및 워크플로와 함께 타사 솔루션을 사용 하는 경우이 문제가 발생할 수 있습니다.  Call Data Connector를 사용 하면 다음 다이어그램과 같이 온-프레미스 서버에 데이터 복사본을 보관 하면서 온라인 서비스에 대 한 데이터 전송도 구성할 수 있습니다.

![SfB Cloud 음성 메일](../../sfbserver2019/media/call-data-connector-plan-2.png)

## <a name="requirements"></a>요구 사항

다음 요구 사항에 따라 지원 되는 토폴로지에서 비즈니스용 Skype 서버를 이미 배포 했다고 가정 합니다.  비즈니스용 Skype 서버 및 지원 되는 토폴로지를 배포 하는 방법에 대 한 자세한 내용은 [토폴로지 기본 사항을](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/topology-basics/topology-basics)참조 하세요. Call Data Connector를 구성 하려면 다음을 수행 해야 합니다.

- 하이브리드 연결을 사용 합니다. 비즈니스용 Skype 서버가 이미 배포 되어 있고 통화 데이터 커넥터를 사용 하도록 설정 하려는 경우 온-프레미스 및 온라인 환경 간에 하이브리드 연결이 설정 되어 있는지 확인 해야 합니다. 이를 분할 도메인 구성 이라고 합니다.

   자세한 내용은 비즈니스용 [Skype 서버 및 office 365의 하이브리드 연결 계획](plan-hybrid-connectivity.md) 및 [비즈니스용 Skype 서버 및 office 365 간의 하이브리드 연결 구성을](configure-hybrid-connectivity.md)참조 하세요.

- Office 365 조직에 인증 하 고 다음 역할을 사용 하도록 설정 했는지 확인 합니다.

  - 비즈니스용 Skype 서버 관리자
  - 전역 관리자

- 아직 수행 하지 않은 경우 [Microsoft 팀 및 비즈니스용 Skype Online에 대 한 통화 품질 대시보드 켜기 및 사용](/microsoftteams/turning-on-and-using-call-quality-dashboard)에 설명 된 대로 통화 품질 대시보드를 켜십시오.

- 로컬 LCSCdr 및 QoEMetrics 데이터베이스를 사용 하 여 모니터링을 위해 프런트 엔드 풀을 사용 하도록 설정 합니다. 이를 제외 하 고는 Call Data Connector에 사용할 메트릭 데이터가 없습니다.

> [!IMPORTANT]
> 프런트 엔드 풀에서 모니터링을 사용 하지 않는 경우에는 Call Data Connector가 작동 하지 않습니다.

- 적절 하 [게 구성 된 서버 간 인증](https://docs.microsoft.com/skypeforbusiness/manage/authentication/server-to-server-and-partner-applications) 

## <a name="comparison-of-on-premises-and-online-call-quality-dashboard-cqd-reports"></a>온-프레미스 및 CQD (온라인 통화 품질 대시보드) 보고서 비교

| 기능 보고서 | 비즈니스용 Skype 온라인 | 비즈니스용 Skype 서버   |
|:---------------------------|:---------------------|:---------------------|:------------------|
| 응용 프로그램 공유 메트릭 |예 | 되며 |
| 고객 건물 정보| 예 | 예 |
| 드릴 다운 분석 | 예 | 아니요 |
| 미디어 안정성 메트릭 | 예 | 되며 |
| 기본 보고서입니다. | 예 | 예 |
| 개요 보고서 | 예 | 아니요 |
| 사용자 단위 보고서 | 예 | 예 |
| 보고서 집합 사용자 지정 <br> (보고서 추가, 삭제, 수정) | 예 | 예 |
| 비디오 기반 화면 공유 메트릭 | 예 | 아니요 |
| 프로그래밍 액세스용 데이터 Api <br> CQD | 아니요 | 예 |
||||
