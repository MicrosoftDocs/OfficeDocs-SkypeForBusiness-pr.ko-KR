---
title: 통화 데이터 커넥터 계획 | 통화 품질 대시보드 하이브리드 분석 모니터링
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 비즈니스용 Skype Online 원격 분석 도구를 사용 하 여 하이브리드 시나리오에서 온-프레미스 구현을 모니터링 하는 방법에 대해 간략하게 설명 합니다.
ms.openlocfilehash: dc129ed99e1ed69e3faf5d2a7b6923f818c482eb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36185514"
---
# <a name="plan-call-data-connector"></a>통화 데이터 커넥터 계획

## <a name="overview"></a>개요

이 항목에서는 비즈니스용 Skype Server Call Data Connector를 구현 하기 위한 이점, 계획 고려 사항, 요구 사항에 대해 설명 합니다. 통화 데이터 커넥터를 구성 하는 방법에 대 한 자세한 내용은 [Call Data Connector 구성을](configure-call-data-connector.md)참조 하세요.

> [!NOTE]
> 공용 preview 릴리스에서는 통화 분석 대시보드만 사용할 수 있습니다.

호출 데이터 커넥터는 더 이상 다른 온-프레미스 및 온라인 도구 집합을 사용 하 여 모든 사용자 통화 품질을 모니터링할 필요가 없기 때문에 하이브리드 환경에서 호출 모니터링을 간소화 합니다. 사용자가 구내 또는 온라인으로 설정 되어 있는지 여부에 관계 없이 전체 조직의 통화 품질을 온라인으로 볼 수 있습니다.

통화 데이터 커넥터를 사용 하 여 단일 도구 집합을 사용 하 여 다음 작업을 수행할 수 있습니다.

- Microsoft 팀, 비즈니스용 Skype Online, 비즈니스용 Skype 서버에서 사용자 환경을 모니터링 하세요.

- 네트워크에서 문제를 보고 해결 합니다.

- 헬프 데스크 직원의 책임 영역을 보고 문제를 해결할 수 있도록 통화 분석에 대 한 헬프데스크 및 관리자 역할을 할당 합니다.

통화 데이터 커넥터를 사용 하는 경우 비즈니스용 Skype Server는 다음 다이어그램에 표시 된 것 처럼 비즈니스용 Skype Online Call 분석 (CA) 및 CQD (비즈니스 지원) 도구를 활용할 수 있도록 클라우드 서비스에 대 한 통화 데이터를 푸시합니다.

![SfB 구름 보이스 메일](../../sfbserver2019/media/call-data-connector-plan-1.png)

서버는 체감 품질 (환경 품질) 및 CDR (통화 정보 기록) 데이터를 온라인 서비스에 푸시합니다.

통화 분석 및 CQD 도구를 사용 하 여 통화 품질을 모니터링 하 고 다음과 같이 Microsoft 팀 및 비즈니스용 Skype 서비스의 연결 문제를 해결할 수 있습니다.

- 통화 분석은 특정 통화에 대 한 품질 문제를 중점적으로 다룹니다. 비즈니스용 Skype 계정에서 각 사용자의 통화 및 모임에 대 한 자세한 정보를 보여 줍니다.  통화 분석을 사용 하면 비즈니스용 Skype 관리 센터의 나머지에 대 한 액세스 권한 없이 통화를 모니터링할 수 있는 헬프데스크 운영자에 게 권한을 할당할 수 있습니다.

- 통화 품질 대시보드는 조직의 네트워크 성능 및 문제에 중점을 둘 것입니다. 비즈니스용 Skype 관리자 및 네트워크 엔지니어는이 도구를 사용 하 여 네트워크 성능 문제를 해결 하 고 최적화 합니다.

자세한 내용은 [통화 분석 및 통화 품질 대시보드](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard)를 참조 하세요.

물론 일부 통화 품질 데이터는 구내에 유지할 수 있습니다. 예를 들어 사용자 지정 보고서 및 워크플로와 함께 타사 솔루션을 사용 하는 경우이 문제가 나타날 수 있습니다.  통화 데이터 커넥터를 사용 하면 다음 다이어그램과 같이 온-프레미스 서버에 데이터 복사본을 유지 하면서 온라인 서비스에 대 한 데이터 전송도 구성할 수 있습니다.

![SfB 구름 보이스 메일](../../sfbserver2019/media/call-data-connector-plan-2.png)

## <a name="requirements"></a>요구 사항

다음 요구 사항은 지원 되는 토폴로지에서 이미 비즈니스용 Skype 서버를 배포 하는 것으로 가정 합니다.  비즈니스용 Skype 서버 및 지원 되는 토폴로지에 배포 하는 방법에 대 한 자세한 내용은 [토폴로지 기본 사항을](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/topology-basics/topology-basics)참조 하세요. 통화 데이터 커넥터를 구성 하려면 다음을 수행 해야 합니다.

- 하이브리드 연결을 사용 합니다. 비즈니스용 Skype 서버를 이미 배포 하 고 통화 데이터 커넥터를 사용 하도록 설정 하려면 온-프레미스 및 온라인 환경 간에 하이브리드 연결이 설정 되어 있는지 확인 해야 합니다. 이를 도메인 분할 구성이 라고도 합니다.

   자세한 내용은 비즈니스용 [Skype 서버 및 office 365 하이브리드 연결 계획](plan-hybrid-connectivity.md) 을 참조 하 고 비즈니스용 [Skype 서버와 office 365의 하이브리드 연결을 구성](configure-hybrid-connectivity.md)합니다.

- Office 365 테 넌 트에 인증 하 고 다음 역할을 사용 하도록 설정 했는지 확인 합니다.

  - 비즈니스용 Skype 서버 관리자
  - Office 365 전역 관리자

- 아직 수행 하지 않은 경우에는 [Microsoft 팀과 비즈니스용 Skype Online에 대 한 통화 품질 대시보드 켜기 및 사용](/microsoftteams/turning-on-and-using-call-quality-dashboard)에 설명 된 대로 통화 품질 대시보드를 설정 합니다.

- 로컬 LCSCdr 및 QoEMetrics 데이터베이스를 사용 하 여 모니터링을 위해 프런트 엔드 풀을 사용 하도록 설정 합니다. 이 없이는 Call Data Connector에 사용할 수 있는 메트릭 데이터가 없습니다.

> [!IMPORTANT]
> 프런트 엔드 풀에서 모니터링을 사용할 수 없는 경우에는 Call Data Connector가 작동 하지 않습니다.

## <a name="comparison-of-on-premises-and-online-call-quality-dashboard-cqd-reports"></a>온-프레미스 및 온라인 통화 품질 대시보드 (CQD) 보고서 비교

| 기능 보고서 | 비즈니스용 Skype Online | 비즈니스용 Skype 서버   |
|:---------------------------|:---------------------|:---------------------|:------------------|
| 응용 프로그램 공유 메트릭 |' | 받습니다 |
| 고객 건물 정보| ' | ' |
| 드릴 다운 분석 | ' | 아니요 |
| 미디어 안정성 메트릭 | ' | 받습니다 |
| 오래 된 보고서 | ' | ' |
| 개요 보고서 | ' | 아니요 |
| 사용자 단위 보고서 | ' | ' |
| 보고서 집합 사용자 지정 <br> (보고서 추가, 삭제, 수정) | ' | ' |
| 비디오 기반 화면 공유 메트릭 | ' | 아니요 |
| 프로그래밍 액세스용 데이터 Api <br> CQD에 | 아니요 | ' |
||||
