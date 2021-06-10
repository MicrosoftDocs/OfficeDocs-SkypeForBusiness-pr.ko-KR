---
title: 통화 데이터 커넥터 | 통화 품질 대시보드 모니터링 하이브리드 분석
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
description: 하이브리드 시나리오에서 비즈니스용 Skype 온라인 원격 분석 도구를 사용하여 프레미스 구현을 모니터링하는 방법을 간략하게 설명합니다.
ms.openlocfilehash: 7b6076224280446b7fc52c505fe5fc3ab8d41be4
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856357"
---
# <a name="plan-call-data-connector"></a>호출 데이터 커넥터 계획

## <a name="overview"></a>개요

이 항목에서는 Call Data Connector를 구현하기 위한 이점, 계획 고려 사항 및 비즈니스용 Skype 서버 설명합니다. 통화 데이터 커넥터 구성에 대한 자세한 내용은 [Configure Call Data Connector을 참조하십시오.](configure-call-data-connector.md)


통화 데이터 커넥터는 더 이상 서로 다른 On-프레미스 및 온라인 도구 집합을 사용하여 모든 사용자의 통화 품질을 모니터링할 필요가 없는 하이브리드 환경에서 통화 모니터링을 크게 간소화합니다. 사용자가 온-프레미스에 있는지 온라인에 있는지에 따라 전체 조직의 통화 품질을 온라인으로 볼 수 있습니다.

Call Data Connector를 사용하면 단일 도구 집합을 사용하여 다음 작업을 수행할 수 있습니다.

- 온라인, Microsoft Teams, 비즈니스용 Skype 사용자 환경을 비즈니스용 Skype 서버.

- 네트워크에서 문제를 보고 해결합니다.

- 기술 지원 팀 작업자가 책임 영역을 보고 문제를 해결할 수 있도록 Call Analytics에 대한 지원 팀 및 관리자 역할을 할당합니다.

통화 데이터 커넥터를 사용하면 비즈니스용 Skype 서버 다이어그램에 표시된 비즈니스용 Skype 온라인 통화 분석(CA) 및 CQD(통화 품질 대시보드) 도구를 활용할 수 있도록 통화 데이터가 클라우드 서비스에 푸시됩니다.

![SfB 클라우드 음성 사서함](../../sfbserver2019/media/call-data-connector-plan-1.png)

서버는 QoE(QoE) 및 CDR(통화 정보 기록) 데이터를 모두 온라인 서비스에 푸시합니다.

Call Analytics 및 CQD 도구를 사용하면 통화 품질을 모니터링하고 다음과 같이 Microsoft Teams 비즈니스용 Skype 문제를 해결할 수 있습니다.

- Call Analytics는 특정 통화의 품질 문제에 초점을 맞추고 있습니다. 계정의 각 사용자에 대한 통화 및 모임에 대한 자세한 비즈니스용 Skype 표시됩니다.  Call Analytics를 사용하면 기술 지원 센터 운영자에게 사용 권한을 할당할 수 있습니다. 그러면 지원 센터의 나머지 센터에 액세스하지 않고도 통화를 모니터링할 비즈니스용 Skype 있습니다.

- 통화 품질 대시보드는 조직 전체의 네트워크 성능 및 문제에 중점을 . 비즈니스용 Skype 네트워크 엔지니어는 이 도구를 사용하여 네트워크 성능 문제를 해결하고 최적화합니다.

자세한 내용은 통화 분석 및 통화 품질 [대시보드를 참조하세요.](/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard)

물론 일부 통화 품질 데이터를 프레미스에 유지할 수도 있습니다. 예를 들어 사용자 지정된 보고서 및 워크플로가 있는 타사 솔루션을 사용하는 경우를 예로 들 수 있습니다.  통화 데이터 커넥터를 사용하면 다음 다이어그램과 같이 온라인 서비스에 데이터 전송을 구성하는 동시에 데이터 복사본을 사내 서버에 유지할 수 있습니다.

![SfB 클라우드 음성 사서함](../../sfbserver2019/media/call-data-connector-plan-2.png)

## <a name="requirements"></a>요구 사항

다음 요구 사항은 지원되는 토폴로지에서 비즈니스용 Skype 서버 이미 배포했다고 가정합니다.  토폴로지 및 지원되는 비즈니스용 Skype 서버 배포하는 비즈니스용 Skype 서버 토폴로지 [기본 정보를 참조하세요.](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md) 통화 데이터 커넥터를 구성하려면 다음을 실행해야 합니다.

- 하이브리드 연결을 사용하도록 설정 이미 배포된 비즈니스용 Skype 서버 경우 통화 데이터 커넥터를 사용하도록 설정하려는 경우, 사내 환경과 온라인 환경 간에 하이브리드 연결을 설정해야 합니다. 이를 분할 도메인 구성이라고도 합니다.

   자세한 내용은 비즈니스용 Skype 서버 [](plan-hybrid-connectivity.md) 및 Microsoft 365 또는 Office 365 간의 하이브리드 연결 계획 및 비즈니스용 Skype 서버 및 Microsoft 365 또는 [Office 365.](configure-hybrid-connectivity.md)

- 조직 또는 Microsoft 365 Office 365 인증하고 다음 역할을 사용하도록 설정해야 합니다.

  - 비즈니스용 Skype 서버 관리자
  - Microsoft 365 또는 Office 365 관리자

- 아직 수행하지 않은 경우 통화 품질 대시보드 켜기 및 사용에 설명된 바와 같이 통화 품질 대시보드를 Microsoft Teams [비즈니스용 Skype 을 선택합니다.](/microsoftteams/turning-on-and-using-call-quality-dashboard)

- 로컬 LCSCdr 및 QoEMetrics 데이터베이스를 사용하여 모니터링에 프런트 엔드 풀을 사용하도록 설정할 수 있습니다. 이렇게 하지 않으면 Call Data Connector에 사용할 메트릭 데이터가 없습니다.

> [!IMPORTANT]
> 프런트 엔드 풀에서 모니터링을 사용하도록 설정하지 않은 경우 통화 데이터 커넥터가 작동하지 않습니다.

- 서버 대 서버 인증을 [올바르게 구성했습니다.](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md) 

## <a name="comparison-of-on-premises-and-online-call-quality-dashboard-cqd-reports"></a>프레미스 및 온라인 CQD(통화 품질 대시보드) 보고서 비교

| 기능 보고서 | 비즈니스용 Skype 온라인 | 비즈니스용 Skype 서버   |
|:---------------------------|:---------------------|:---------------------|:------------------|
| 응용 프로그램 공유 메트릭 |예 | 제한 |
| 고객 구축 정보| 예 | 예 |
| 드릴다운 분석 | 예 | 아니요 |
| 미디어 안정성 메트릭 | 예 | 제한 |
| Out-of-the-box reports | 예 | 예 |
| 개요 보고서 | 예 | 아니요 |
| 사용자당 보고서 | 예 | 예 |
| 보고서 집합 사용자 지정 <br> (보고서 추가, 삭제, 수정) | 예 | 예 |
| 비디오 기반 화면 공유 메트릭 | 예 | 아니요 |
| 프로그래밍식 액세스를 위한 데이터 API <br> 를 CQD로 | 아니요 | 예 |
||||