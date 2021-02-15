---
title: Teams 음성 Contoso 사례 연구
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
description: 다국적 기업에 대한 Teams 음성 사례 연구
appliesto:
- Microsoft Teams
ms.openlocfilehash: a6ee08fa7bdeb1ded6bda384115a08048021cb67
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918734"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a>Contoso 사례 연구: 자동 전화 회의 및 통화 큐

Contoso는 자동 전화 회의 및 비즈니스용 Skype 배포의 통화 큐에 익숙했습니다. 클라우드 자동 전화 회의 및 통화 큐를 설정하는 방법을 이해하기 위해 Teams 자동 전화 회의 및 통화 큐에 대한 계획을 [검토했습니다.](plan-auto-attendant-call-queue.md)

## <a name="requirements-depending-on-site-type"></a>사이트 유형에 따라 요구 사항

사이트 유형에 따라 Contoso에는 다음과 같은 요구가 있습니다.

- 사이트 유형 A: 기존 레거시 전화 통신 시스템 

  사이트 유형 A는 수신 직원과 연결된 전화 번호를 자동 전화 번호로 유지하는 데 필요합니다. 이러한 각 사이트의 주요 부서에는 팀 구성원에게 라우팅하는 자체 호출 큐가 있습니다. 전화 시스템을 직접 라우팅과 전화 시스템과 통화 요금제에 사용한 사이트가 혼합되었습니다.  

- 사이트 유형 B: 비즈니스용 Skype Enterprise Voice 

  사이트 유형 B에는 Teams로 마이그레이션해야 하는 기존 자동 전화 회의 및 통화 큐가 있습니다. Contoso는 자동 전화 번호와 연결된 전화 번호를 유지해야 합니다. Contoso는 대부분의 사이트를 통화 요금제가 있는 전화 시스템으로 이동했습니다. 그러나 통화 계획을 사용할 수 없는 몇 가지 위치에서 Contoso는 이러한 사이트를 직접 라우팅 구성으로 이동했습니다.  

- 사이트 유형 C: 비즈니스용 Skype Enterprise Voice & 레거시 전화 통신 시스템 

  사이트 유형 C에는 기존 레거시 전화 통신 시스템에 있는 기존 자동 전화 회의가 있습니다. 이 사이트에 대한 결정 및 구성은 사이트 유형 A와 동일합니다.   

- Contoso는 모든 사이트 유형에 대해 다음과 같은 질문을 합니다.

  - Q: 새 번호나 기존 번호를 사용하나요? 
    A: Contoso는 기존 전화 번호를 자동 전화 연결에 대한 서비스 계정에 할당하기로 결정했습니다. 

  - Q: 자동 전화 회의는 언제 수신 전화를 수락할 수 있나요? 
    A: Contoso는 업무 시간을 설정하고 업무 시간 이후에 "시간 후" 자동 전화 회의로 리디렉션된 후 전화를 수신하기로 결정했습니다.  

  - Q: 통화는 전화 대기열의 구성원에게 어떻게 라우팅하나요? 전화 번호, 직렬 또는 라운드 로빈 라우팅은 어떻게 하나요? 
    A: Contoso는 Attendant 라우팅을 사용하기로 결정 

  - Q: 사용자가 통화를 해야 하는 경우를 어떻게 결정하나요? 
    A: Contoso는 통화 처리 옵션을 사용하여 에이전트를 사용할 수 있는지 여부를 결정했습니다. 현재 상태 기반 라우팅입니다. 


## <a name="configuration"></a>구성

자동 전화 회의 및 통화 큐를 설정하는 단계는 리소스 계정 관리에 설명된 [다음을 포함합니다.](manage-resource-accounts.md) 

1. 서비스 번호를 얻습니다. 

2. 리소스 계정 또는 전화 시스템 라이선스와 함께 사용할 무료 전화 시스템 - 가상 사용자 라이선스 또는 유료 전화 시스템 라이선스를 얻습니다.

3. 리소스 계정을 생성합니다. 연결된 리소스 계정이 있는 경우 자동 전화 연결 또는 통화 큐가 필요합니다. 

4. 전화 시스템 또는 전화 시스템 - 가상 사용자 라이선스를 리소스 계정에 할당합니다. 자세한 내용은 [Microsoft 365 Phone System – 가상 사용자 라이선스를 참조하세요.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user)

5. 라이선스를 할당한 리소스 계정에 서비스 전화 번호를 할당합니다. 

6. 전화 시스템 통화 큐 또는 자동 전화 번호 만들기 

7. 리소스 계정을 통화 큐 또는 자동 전화 연결에 연결합니다. 


### <a name="sites-with-phone-system-with-direct-routing"></a>직접 라우팅이 있는 전화 시스템이 있는 사이트 

Contoso는 로컬 통신 사업자에서 제공하는 전화 번호를 Office 365의 서비스 번호로 설정해야 합니다. 

- Contoso는 직접 라우팅을 통해 사용할 수 있는 전화 번호를 설정하기 위해 리소스 계정 관리에 있는 지침을 [따릅니다.](manage-resource-accounts.md) Office 365는 Office 365에서 프레미스 전화 번호를 인식하지 못하기 때문에 Contoso는 PowerShell을 사용하여 설정을 완료했습니다.   

- Contoso는 클라우드 자동 연결 기능을 구성하기 위해 클라우드 자동 연결 설정에 설명된 [단계를 수행했습니다.](create-a-phone-system-auto-attendant.md) 

- 클라우드 호출 큐를 설정하기 위해 Contoso는 클라우드 호출 큐 만들기에 설명된 [단계를 수행했습니다.](create-a-phone-system-call-queue.md)  


### <a name="sites-with-phone-system-with-calling-plan"></a>통화 요금제가 있는 전화 시스템이 있는 사이트

Contoso는 Office 365 전화 시스템으로 자동 전화 Enterprise Voice 비즈니스용 Skype에 사용된 전화 번호를 포터 이동해야 합니다. 이렇게 하면 자동 전화 번호로 사용할 수 있도록 동일한 번호를 서비스 번호로 할당할 수 있습니다. 

- Contoso는 전화 번호를 포식하기 위해 [](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) Teams로 전화 번호 이전의 지침을 따르고 조직의 전화 번호 관리에서 추가 지침을 [얻습니다.](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

- Contoso는 클라우드 자동 연결 기능을 구성하기 위해 클라우드 자동 연결 설정에 설명된 [단계를 수행했습니다.](create-a-phone-system-auto-attendant.md)

-  클라우드 호출 큐를 설정하기 위해 Contoso는 클라우드 호출 큐 만들기에 설명된 [단계를 수행했습니다.](create-a-phone-system-call-queue.md)  

 