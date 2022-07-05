---
title: 'Teams 음성 Contoso 사례 연구: 자동 전화 교환 및 통화 큐'
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
description: '다국적 기업을 위한 Teams 음성 사례 연구: 자동 전화 교환 및 통화 큐'
appliesto:
- Microsoft Teams
ms.openlocfilehash: 50d1ee2d384b200aeab6eefd6ca2de623015b6f2
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615844"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a>Contoso 사례 연구: 자동 전화 교환 및 통화 큐

Contoso는 온-프레미스 비즈니스용 Skype 배포에서 자동 전화 교환 및 통화 큐에 익숙했습니다. 클라우드 자동 전화 교환을 설정하고 큐를 호출하는 방법을 이해하기 [위해 Teams 자동 전화 교환 및 통화 큐에 대한 계획을 검토했습니다](plan-auto-attendant-call-queue.md).

## <a name="requirements-depending-on-site-type"></a>사이트 유형에 따른 요구 사항

Contoso는 사이트 유형에 따라 다음과 같은 요구 사항이 있었습니다.

- 사이트 유형 A: 기존 레거시 전화 통신 시스템 

  사이트 유형 A는 자동 전화 교환 번호와 동일한 전화 번호를 접수원과 연결해야 했습니다. 이러한 각 사이트의 주요 부서에는 팀 구성원에게 라우팅되는 자체 통화 큐가 있습니다. 직접 라우팅과 전화 시스템과 통화 플랜 전화 시스템을 사용하는 사이트의 혼합이 있었다.  

- 사이트 유형 B: 비즈니스용 Skype Enterprise Voice 

  사이트 유형 B에는 Teams로 마이그레이션하는 데 필요한 기존 자동 전화 교환 및 통화 큐가 있었습니다. Contoso는 전화 번호를 자동 전화 교환과 연결된 상태로 유지해야 했습니다. Contoso는 이러한 사이트의 대부분을 통화 플랜이 있는 전화 시스템으로 이동했습니다. 그러나 통화 플랜을 사용할 수 없는 몇 가지 위치에서 Contoso는 이러한 사이트를 직접 라우팅 구성으로 이동했습니다.  

- 사이트 유형 C: 기존 레거시 전화 통신 시스템 비즈니스용 Skype Enterprise Voice & 

  사이트 유형 C에는 기존의 레거시 전화 통신 시스템에 상주하는 기존 자동 전화 교환이 있었습니다. 이 사이트의 결정 및 구성은 사이트 유형 A와 동일했습니다.   

- Contoso는 모든 사이트 유형에 대해 다음과 같은 질문을 했습니다.

  - Q: 새 숫자나 기존 숫자를 사용할 수 있나요? 
    A: Contoso는 자동 전화 교환을 위해 서비스 계정에 할당할 기존 전화 번호를 사용하기로 결정했습니다. 

  - Q: 자동 전화 교환을 언제 수신 전화를 수락할 수 있나요? 
    A: Contoso는 업무 시간을 설정하기로 결정하고 업무 시간 이후에 "근무 시간 후" 자동 전화 교환으로 리디렉션된 전화를 받기로 결정했습니다.  

  - Q: 호출 큐의 멤버(전화 교환, 직렬 또는 라운드 로빈 라우팅)로 호출을 라우팅하려면 어떻게 해야 합니까? 
    A: Contoso는 전화 교환 라우팅을 사용하기로 결정했습니다. 

  - Q: 사용자가 전화를 받아야 하거나 전화를 받지 않아야 하는 시기는 어떻게 결정하나요? 
    A: Contoso는 호출 처리 옵션을 사용하여 에이전트를 사용할 수 있는지 확인하기로 결정했습니다( 현재 상태 기반 라우팅). 

## <a name="configuration"></a>구성

자동 전화 교환 및 통화 큐를 설정하는 단계는 [리소스 계정 관리에](manage-resource-accounts.md) 설명된 다음을 포함합니다.

1. 서비스 번호를 가져옵니다.

2. **리소스 계정** 또는 전화 시스템 라이선스와 함께 사용할 무료 Microsoft Teams 전화 리소스 계정 라이선스 또는 유료 전화 시스템 라이선스를 얻습니다.

3. 리소스 계정을 만듭니다. 연결된 리소스 계정을 사용하려면 자동 전화 교환 또는 통화 큐가 필요합니다.

4. 리소스 계정에 **Teams 전화 표준 요금제** 또는 **Microsoft Teams 전화 리소스 계정** 라이선스를 할당합니다. 자세한 내용은 [Microsoft Teams 전화 Resource Account 라이선스](./teams-add-on-licensing/virtual-user.md)를 참조하세요.

5. 라이선스를 할당한 리소스 계정에 서비스 전화 번호를 할당합니다.

6. 전화 시스템 통화 큐 또는 자동 전화 교환을 만듭니다.

7. 리소스 계정을 통화 큐 또는 자동 전화 교환에 연결합니다.

### <a name="sites-with-phone-system-with-direct-routing"></a>직접 라우팅이 있는 전화 시스템이 있는 사이트

Contoso는 Office 365 서비스 번호로 로컬 통신 사업자가 제공하는 전화 번호를 설정해야 했습니다.

- 직접 라우팅을 통해 사용할 수 있는 전화 번호를 설정하기 위해 Contoso는 [리소스 계정 관리에](manage-resource-accounts.md) 있는 지침을 따랐습니다. Office 365 온-프레미스 전화 번호를 인식하지 못하기 때문에 Contoso는 PowerShell을 사용하여 설정을 완료했습니다.   

- Contoso는 클라우드 자동 전화 교환을 구성하기 위해 [클라우드 자동 전화 교환 설정](create-a-phone-system-auto-attendant.md)에 설명된 단계를 수행했습니다. 

- Contoso는 클라우드 호출 큐를 설정하기 위해 [클라우드 호출 큐 만들기](create-a-phone-system-call-queue.md)에 설명된 단계를 수행했습니다.  


### <a name="sites-with-phone-system-with-calling-plan"></a>통화 플랜이 있는 전화 시스템이 있는 사이트

Contoso는 자동 전화 교환을 Office 365 전화 시스템 비즈니스용 Skype Enterprise Voice 데 사용된 전화 번호를 이식해야 했습니다. 이렇게 하면 자동 전화 교환으로 사용할 서비스 번호로 동일한 번호를 할당할 수 있습니다. 

- 전화 번호를 이식하기 위해 Contoso는 [Teams로 전화 번호 전송](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 의 지침을 따르고 [조직의 전화 번호 관리](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)에서 추가 지침을 얻었습니다.

- Contoso는 클라우드 자동 전화 교환을 구성하기 위해 [클라우드 자동 전화 교환 설정](create-a-phone-system-auto-attendant.md)에 설명된 단계를 수행했습니다.

-  Contoso는 클라우드 호출 큐를 설정하기 위해 [클라우드 호출 큐 만들기](create-a-phone-system-call-queue.md)에 설명된 단계를 수행했습니다.  

