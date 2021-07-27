---
title: 'Teams Contoso 사례 연구: 자동 참석자 및 통화 큐'
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: 'Teams 회사에 대한 음성 사례 연구: 자동 참석자 및 통화 큐'
appliesto:
- Microsoft Teams
ms.openlocfilehash: a0251c4baa9aca86f871b7c1dc1af44695bd1585
ms.sourcegitcommit: b387296c043fcf10fba7b9ef416328383e54a565
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/26/2021
ms.locfileid: "53587167"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a>Contoso 사례 연구: 자동 참석자 및 통화 큐

Contoso는 자동 참석자 및 프레미스 배포에서 큐를 호출하는 비즈니스용 Skype 익숙했습니다. 클라우드 자동 참석자 및 호출 큐를 설정하고 큐를 호출하는 방법을 이해하기 위해 자동 참석자 및 호출 Teams 계획을 [검토했습니다.](plan-auto-attendant-call-queue.md)

## <a name="requirements-depending-on-site-type"></a>사이트 유형에 따라 요구 사항

사이트 유형에 따라 Contoso에는 다음과 같은 요구가 있습니다.

- 사이트 유형 A: 기존 레거시 전화 통신 시스템 

  사이트 유형 A는 수신 직원과 연결된 전화 번호를 자동 참석자 번호와 동일한 전화 번호를 유지해야 합니다. 이러한 각 사이트의 주요 부서에는 팀 구성원으로 라우팅하는 자체 호출 큐가 있습니다. 직접 라우팅 및 통화 전화 시스템 사용하는 사이트가 전화 시스템 혼합되었습니다.  

- 사이트 유형 B: 비즈니스용 Skype Enterprise Voice 

  Site Type B에는 기존 자동 참석자 및 호출 큐가 있으며, 이 큐는 사용자로 마이그레이션해야 Teams. Contoso는 자동 전화 번호와 연결된 전화 번호를 유지해야 합니다. Contoso는 이러한 대부분의 사이트를 호출 계획으로 전화 시스템 이동했습니다. 그러나 통화 계획을 사용할 수 없는 몇 가지 위치에서 Contoso는 이러한 사이트를 직접 라우팅 구성으로 이동했습니다.  

- 사이트 유형 C: 비즈니스용 Skype Enterprise Voice & 레거시 전화 통신 시스템 

  Site Type C에는 기존 레거시 전화 통신 시스템에 있는 기존 자동 참석자가 있습니다. 이 사이트에 대한 결정과 구성은 사이트 유형 A와 동일합니다.   

- 모든 사이트 유형에 대해 Contoso는 다음 질문을 던졌다.

  - Q: 새 번호 또는 기존 번호를 사용하나요? 
    A: Contoso는 기존 전화 번호를 사용하여 자동 참석자에 대한 서비스 계정에 할당하기로 결정했습니다. 

  - Q: 수신 통화를 수락할 수 있는 자동 참석자는 언제 사용할 수 있나요? 
    A: Contoso는 업무 시간을 설정하기로 결정하고 업무 시간 후에 "시간 이후" 자동 참석자로 리디렉션된 후 전화를 수신했습니다.  

  - Q: 호출이 호출 큐의 구성원(참석자, 직렬 또는 라운드 로빈 라우팅)으로 라우팅될까요? 
    A: Contoso는 참석자 라우팅을 사용하기로 결정했다. 

  - Q: 사용자가 통화를 받을지 안 하나요? 
    A: Contoso는 호출 처리 옵션을 사용하여 에이전트를 사용할 수 있는지 여부를 결정했습니다. 현재 상태 기반 라우팅입니다. 


## <a name="configuration"></a>구성

자동 참석자 및 호출 큐를 설정하는 단계는 리소스 계정 관리에 설명된 [다음을 포함합니다.](manage-resource-accounts.md) 

1. 서비스 번호를 구합니다. 

2. 리소스 계정 또는 전화 시스템 사용할 가상 사용자 라이선스 또는 유료 전화 시스템 라이선스를 전화 시스템.

3. 리소스 계정을 만들 수 있습니다. 연결된 리소스 계정을 사용하려면 자동 참석자 또는 호출 큐가 필요합니다. 

4. 리소스 계정에 전화 시스템 또는 전화 시스템 - 가상 사용자 라이선스를 할당합니다. 자세한 내용은 가상 [Microsoft 365 전화 시스템 - 가상 사용자 라이선스를 참조하세요.](./teams-add-on-licensing/virtual-user.md)

5. 라이선스를 할당한 리소스 계정에 서비스 전화 번호를 할당합니다. 

6. 전화 전화 시스템 또는 자동 참석자 만들기 

7. 리소스 계정을 호출 큐 또는 자동 참석자와 연결합니다. 


### <a name="sites-with-phone-system-with-direct-routing"></a>직접 전화 시스템 있는 사이트 

Contoso는 로컬 통신사가 제공한 전화 번호를 서비스 번호로 설정해야 Office 365. 

- 직접 라우팅을 통해 사용할 수 있는 전화 번호를 설정하기 위해 Contoso는 리소스 계정 관리 에 있는 지침을 [따릅니다.](manage-resource-accounts.md) Office 365 전화 번호를 인식하지 못하기 때문에 Contoso는 PowerShell을 사용하여 설정을 완료했습니다.   

- 클라우드 자동 수행자 구성을 위해 Contoso는 클라우드 자동 수행자 설정에 설명된 단계를 [따릅니다.](create-a-phone-system-auto-attendant.md) 

- 클라우드 호출 큐를 설정하기 위해 Contoso는 클라우드 호출 큐 만들기에 설명된 [단계를 따릅니다.](create-a-phone-system-call-queue.md)  


### <a name="sites-with-phone-system-with-calling-plan"></a>통화 전화 시스템 있는 사이트

Contoso는 자동 비즈니스용 Skype Enterprise Voice 전화 번호를 Office 365 전화 시스템. 이렇게 하면 자동 참석자로 사용할 서비스 번호로 동일한 번호를 할당할 수 있습니다. 

- 전화 번호를 포트하기 위해 Contoso는 [](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 전화 번호 전송의 지침을 따라 Teams 조직의 전화 번호 관리에서 추가 지침을 [얻습니다.](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

- Cloud 자동 수행자 구성을 위해 Contoso는 클라우드 자동 수행자 설정에 설명된 단계를 [따릅니다.](create-a-phone-system-auto-attendant.md)

-  클라우드 호출 큐를 설정하기 위해 Contoso는 클라우드 호출 큐 만들기에 설명된 [단계를 따릅니다.](create-a-phone-system-call-queue.md)  

