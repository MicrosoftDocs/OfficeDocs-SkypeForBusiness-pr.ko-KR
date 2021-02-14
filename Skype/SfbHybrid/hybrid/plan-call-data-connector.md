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
description: 하이브리드 시나리오에서 비즈니스용 Skype Online 원격 분석 도구를 사용하여 프레미스 구현을 모니터링하는 개요
ms.openlocfilehash: 30ff8aebc739e0602f9700cbe9120d230845a023
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221318"
---
# <a name="plan-call-data-connector"></a>호출 데이터 커넥터 계획

## <a name="overview"></a>개요

이 항목에서는 비즈니스용 Skype 서버 통화 데이터 커넥터를 구현하기 위한 이점, 계획 고려 사항 및 요구 사항에 대해 설명합니다. 통화 데이터 커넥터 구성에 대한 자세한 내용은 통화 데이터 커넥터 [구성을 참조하십시오.](configure-call-data-connector.md)


통화 데이터 커넥터는 더 이상 여러 가지 설정의 On-premises 및 Online 도구 집합을 사용하여 모든 사용자의 통화 품질을 모니터링할 필요가 아니기 때문에 하이브리드 환경에서 통화 모니터링을 크게 간소화합니다. 사용자가 온-프레미스에 있는지 온라인에 있는지에 따라 전체 조직에 대한 통화 품질을 온라인으로 볼 수 있습니다.

Call Data Connector를 사용하면 단일 도구 집합을 사용하여 다음 작업을 수행할 수 있습니다.

- Microsoft Teams, 비즈니스용 Skype Online 및 비즈니스용 Skype 서버에서 사용자 환경을 모니터링합니다.

- 네트워크 전체에서 문제를 보고 해결합니다.

- 기술 지원 팀 작업자가 자신의 책임 영역을 보고 문제를 해결할 수 있도록 Call Analytics에 대한 지원 데스크 및 관리자 역할을 할당합니다.

통화 데이터 커넥터를 사용하면 비즈니스용 Skype 서버는 다음 다이어그램과 같이 비즈니스용 Skype 온라인 통화 분석(CA) 및 CQD(통화 품질 대시보드) 도구를 활용할 수 있도록 통화 데이터를 클라우드 서비스에 푸시합니다.

![SfB 클라우드 음성메일](../../sfbserver2019/media/call-data-connector-plan-1.png)

서버는 QoE(QoE) 및 CDR(통화 정보 기록) 데이터를 모두 온라인 서비스에 푸시합니다.

Call Analytics 및 CQD 도구를 사용하면 다음과 같이 통화 품질을 모니터링하고 Microsoft Teams 및 비즈니스용 Skype 서비스의 연결 문제를 해결할 수 있습니다.

- Call Analytics는 특정 통화의 품질 문제에 초점을 맞추고 있습니다. 비즈니스용 Skype 계정의 각 사용자에 대한 통화 및 모임에 대한 자세한 정보가 표시됩니다.  Call Analytics를 사용하면 기술 지원 센터 운영자에게 사용 권한을 할당할 수 있습니다. 그러면 나머지 비즈니스용 Skype 관리 센터에 액세스하지 않고도 통화를 모니터링할 수 있습니다.

- 통화 품질 대시보드는 조직 전체의 네트워크 성능 및 문제에 중점을 안합니다. 비즈니스용 Skype 관리자 및 네트워크 엔지니어는 이 도구를 사용하여 네트워크 성능을 문제 해결하고 최적화합니다.

자세한 내용은 통화 분석 및 [통화 품질 대시보드를 참조하세요.](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard)

물론 일부 통화 품질 데이터를 프레미스에 유지할 수도 있습니다. 예를 들어 사용자 지정된 보고서 및 워크플로가 있는 타사 솔루션을 사용하는 경우를 예로 들 수 있습니다.  통화 데이터 커넥터를 사용하면 다음 다이어그램과 같이 온라인 서비스로 데이터 전송을 구성하는 동시에 데이터 복사본을 온라인 서버에 보관할 수 있습니다.

![SfB 클라우드 음성메일](../../sfbserver2019/media/call-data-connector-plan-2.png)

## <a name="requirements"></a>요구 사항

다음 요구 사항은 지원되는 토폴로지에서 비즈니스용 Skype 서버가 이미 배포된 것으로 가정합니다.  비즈니스용 Skype 서버 및 지원되는 토폴로지 배포에 대한 자세한 내용은 토폴로지 [기본을 참조하세요.](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/topology-basics/topology-basics) 통화 데이터 커넥터를 구성하려면 다음을 실행해야 합니다.

- 하이브리드 연결을 사용하도록 설정 비즈니스용 Skype 서버가 이미 배포되어 있으며 통화 데이터 커넥터를 사용하도록 설정하려는 경우, 하이브리드 연결이 온라인 환경과 온라인 환경 간에 설정되어 있는지를 확인해야 합니다. 이를 분할 도메인 구성이라고도 합니다.

   자세한 내용은 비즈니스용 Skype 서버와 [Microsoft 365 또는 Office 365](plan-hybrid-connectivity.md) 간의 하이브리드 연결 계획과 비즈니스용 [Skype 서버와 Microsoft 365 또는 Office 365](configure-hybrid-connectivity.md)간의 하이브리드 연결 구성을 참조하세요.

- Microsoft 365 또는 Office 365 조직에 인증하고 다음 역할을 사용하도록 설정해야 합니다.

  - 비즈니스용 Skype 서버 관리자
  - Microsoft 365 또는 Office 365 전역 관리자

- 아직 설정하지 않은 경우 Microsoft Teams 및 비즈니스용 Skype Online에 대한 통화 품질 대시보드 켜기 및 사용에 설명된 통화 품질 대시보드를 [켜야 합니다.](/microsoftteams/turning-on-and-using-call-quality-dashboard)

- 로컬 LCSCdr 및 QoEMetrics 데이터베이스를 사용하여 모니터링에 프런트 엔드 풀을 사용하도록 설정 이렇게 하지 않으면 Call Data Connector에 사용할 메트릭 데이터가 없습니다.

> [!IMPORTANT]
> 프런트 엔드 풀에서 모니터링을 사용하도록 설정하지 않은 경우 통화 데이터 커넥터가 작동하지 않습니다.

- 제대로 구성된 [서버-서버 인증.](https://docs.microsoft.com/skypeforbusiness/manage/authentication/server-to-server-and-partner-applications) 

## <a name="comparison-of-on-premises-and-online-call-quality-dashboard-cqd-reports"></a>온-프레미스 및 온라인 CQD(통화 품질 대시보드) 보고서 비교

| 기능 보고서 | 비즈니스용 Skype 온라인 | 비즈니스용 Skype 서버   |
|:---------------------------|:---------------------|:---------------------|:------------------|
| 응용 프로그램 공유 메트릭 |예 | 제한 |
| 고객 구축 정보| 예 | 예 |
| 드릴다운 분석 | 예 | 아니요 |
| 미디어 안정성 메트릭 | 예 | 제한 |
| 첫 사용 보고서 | 예 | 예 |
| 개요 보고서 | 예 | 아니요 |
| 사용자당 보고서 | 예 | 예 |
| 보고서 집합 사용자 지정 <br> (보고서 추가, 삭제, 수정) | 예 | 예 |
| 비디오 기반 화면 공유 메트릭 | 예 | 아니요 |
| 프로그래밍식 액세스를 위한 데이터 API <br> 에서 CQD로 | 아니요 | 예 |
||||
