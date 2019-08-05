---
title: 클라우드 통화 대기열 계획
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 비즈니스용 Skype 서버 2019에서 클라우드 자동 전화 교환을 사용 하는 방법에 대해 간략하게 설명 합니다.
ms.openlocfilehash: bcb1f14ed9dfc3471b146a318a97700c362f115c
ms.sourcegitcommit: 868db85f0126e8f56d711ea590ad44acce8f96f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2019
ms.locfileid: "36185544"
---
# <a name="plan-cloud-call-queues"></a>클라우드 통화 대기열 계획

클라우드 통화 큐는 고객 전화를 수락 하 고, 인사말 메시지를 재생 한 다음, 미리 구성 된 에이전트 목록을 검색 하 여 이러한 통화에 응답 하는 동안 대기 대기열에 이러한 호출을 배치 하는 서비스입니다. 메일 사용이 가능한 메일 그룹이 나 보안 그룹의 에이전트 집합을 정의할 수 있습니다. 조직에는 하나 또는 여러 개의 통화 대기열이 있을 수 있습니다. 통화 대기열은 일반적으로 자동 전화 교환와 조합 하 여 사용 됩니다.

또한 클라우드 통화 대기열은 다음을 제공할 수 있습니다.

- 호출자가 대기 중인 동안 음악
- 통화 대기열에 대 한 사용자 지정 설정 최대 크기, 시간 제한 및 통화 처리 옵션

Microsoft 팀 관리 센터의 통화 대기열에 직접 연결 되는 비즈니스용 Skype Server 2019 시스템에서 각 통화 대기열에는 **리소스 계정** ( [리소스 계정 구성](configure-onprem-ra.md)참조)이 할당 됩니다. 통화 대기열에 대 한 자세한 내용 및 통화 대기열에 대해 존재 하는 옵션과 기능은 [클라우드 통화 대기열 만들기](/MicrosoftTeams/create-a-phone-system-call-queue) 를 참조 하세요.

> [!NOTE]
> 여러 전화 번호를 통화 대기열에 할당할 수 있지만, Microsoft 서비스 번호 또는 하이브리드 번호 여야 합니다.

## <a name="requirements"></a>요구 사항

다음 요구 사항은 지원 되는 토폴로지에서 비즈니스용 Skype 서버 2019이 이미 배포 되어 있다고 가정 합니다.  요구 사항은 시나리오에 따라 달라 집니다.

- 클라우드 통화 큐의 새로운 구성을 보려면 [리소스 계정 구성](configure-onprem-ra.md)에 설명 된 단계를 따릅니다. 온라인 또는 비즈니스용 Skype 서버 2019에 리소스 계정을 만들어야 하며 전화 번호를 통화 대기열과 연결 해야 할 수도 있습니다.

위의 요구 사항 외에도 다음 요구 사항을 Microsoft 클라우드 통화 대기열 서비스에 연결 하도록 구성 해야 합니다.

- 하이브리드 연결. 비즈니스용 Skype 서버를 이미 배포 하 고 온-프레미스 사용자에 대 한 클라우드 호출 큐를 사용 하도록 설정 하려면 온-프레미스 및 온라인 환경 간에 하이브리드 연결이 설정 되어 있는지 확인 해야 합니다. 이를 도메인 분할 구성이 라고도 합니다.

   자세한 내용은 비즈니스용 [Skype 서버 및 office 365 하이브리드 연결 계획](plan-hybrid-connectivity.md) 을 참조 하 고 비즈니스용 [Skype 서버와 office 365의 하이브리드 연결을 구성](configure-hybrid-connectivity.md)합니다.

- 리소스 계정에 전화 번호를 지정 하는 경우, 이제 비용 무료 전화 시스템 가상 사용자 라이선스를 사용할 수 있습니다. 이렇게 하면 조직 수준에서 전화 시스템 기능을 전화 번호에 제공 하 고 자동 전화 교환 및 통화 대기열 기능을 만들 수 있습니다.

- 각 통화 대기열에 대 한 온-프레미스 [리소스 계정을](configure-onprem-ra.md) 만들고 필요한 경우 라이선스 및 전화 번호를 할당 합니다.  

## <a name="additional-planning-resources"></a>추가 계획 리소스

사용자 요구에 대 한 정보를 수집 하는 프로세스, 자동 전화 교환 및 사용자의 구조 계획, 메뉴 프롬프트를 작성 하는 등의 간단한 비즈니스와 같은 자습서에서 [자동 전화 교환을 설정](/microsoftteams/tutorial-org-aa) 하면 온라인 관리 센터에서 계획을 구현 합니다. 자습서를 검토 하 고 여기에서 계획 수립 연습을 사용해 보세요.

사용자의 요구에 맞는 솔리드 구조와 고객을 효율적으로 안내 하는 스크립트를 사용 하는 경우 [리소스 계정 구성을](configure-onprem-ra.md)진행 합니다.

## <a name="see-also"></a>참고 항목

[자원 계정 구성](configure-onprem-ra.md)

[전화 사용자 인터페이스를 사용 하 여 사용자 지정 음성 안내 기록 사용](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[클라우드 자동 전화 교환 이란?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[클라우드 자동 전화 교환 설정](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[비즈니스용 Skype 서버와 Office 365 하이브리드 연결 계획](plan-hybrid-connectivity.md)

[비즈니스용 Skype 서버와 Office 365 하이브리드 연결 구성](configure-hybrid-connectivity.md)

[Microsoft 팀에서 자원 계정 관리](/MicrosoftTeams/manage-resource-accounts)
