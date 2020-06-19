---
title: 팀 음성 Contoso 사례 연구
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
description: 여러 국가의 기업에 대 한 팀 음성 사례 연구
appliesto:
- Microsoft Teams
ms.openlocfilehash: 780d812b4e6e56b28b867ace14dbf1d5f6170302
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786094"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a>Contoso 사례 연구: 자동 전화 교환 및 통화 대기열

Contoso는 온-프레미스 비즈니스용 Skype 배포의 자동 전화 교환 및 통화 대기열에 익숙합니다. 클라우드 자동 전화 교환을 설정 하는 방법에 대 한 자세한 내용은 [클라우드 자동 전화 교환 기능](what-are-phone-system-auto-attendants.md) 을 검토 하는 방법을 이해 하는 데, 그리고 [자동 전화 교환 자습서를 설치 하는 소규모 비즈니스 예-](tutorial-org-aa.yml) 통화 대기열을 설정 하는 데 사용할 수 있는 옵션에 대 한 자세한 내용은 Contoso가 [클라우드 통화 대기열 만들기](create-a-phone-system-call-queue.md)를 검토 했습니다.  

## <a name="requirements-depending-on-site-type"></a>사이트 종류에 따라 요구 사항

사이트 유형에 따라 Contoso에는 다음과 같은 요구 사항이 있습니다.

- 사이트 종류 A: 기존 레거시 전화 통신 시스템 

  사이트 receptionist와 연결 된 동일한 전화 번호를 자동 전화 교환 번호로 유지 하는 데 필요한 시간을 입력 합니다. 이러한 각 사이트의 주요 부서에는 팀 구성원에 게 라우팅할 수 있는 고유한 통화 대기열이 있습니다. 전화 시스템을 사용 하 여 다이렉트 라우팅 및 전화 시스템을 사용한 통화 요금제와 혼합 된 사이트 들이 섞여 있습니다.  

- 사이트 종류 B: 비즈니스용 Skype Enterprise Voice 

  사이트 유형 B에 팀으로 마이그레이션하는 데 필요한 기존 자동 전화 교환 및 통화 대기열이 있습니다. Contoso는 자동 전화 교환에 연결 된 전화 번호를 유지 해야 합니다. Contoso는 이러한 사이트의 대부분을 전화 시스템으로 통화 요금제로 이동 했습니다. 그러나 전화 요금제를 사용할 수 없는 몇 가지 경우에는 Contoso가 이러한 사이트를 직접 라우팅 구성으로 이동 했습니다.  

- 사이트 종류 C: 비즈니스용 Skype Enterprise Voice & 기존 레거시 전화 통신 시스템 

  사이트 유형 C에 기존의 레거시 전화 통신 시스템에 있던 자동 전화 교환이 있습니다. 이 사이트에 대 한 결정과 구성은 사이트 종류 A와 동일 합니다.   

- 모든 사이트 유형에 대해 Contoso는 다음 질문을 요청 했습니다.

  - Q: 새로운 숫자나 기존 번호를 사용 합니까? 
    A: Contoso는 기존 전화 번호를 사용 하 여 자동 전화 교환의 서비스 계정에 할당 하기로 결정 했습니다. 

  - Q: 자동 전화 교환은 걸려오는 전화를 수락 하는 데 언제 제공 되나요? 
    A: Contoso는 업무 시간을 설정 하 고 업무 시간이 "시간 경과 후" 자동 전화 교환으로 리디렉션되는 전화를 받을 수 있도록 결정 했습니다.  

  - Q: 통화 대기열의 구성원에 게 전화를 거는 방법: 전화 교환, 직렬 또는 라운드 로빈 라우팅 
    A: Contoso는 전화 교환 라우팅을 사용 하기로 결정 했습니다. 

  - Q: 사용자가 전화를 받을 수 있는 시간을 결정 하는 방법은 무엇 인가요? 
    A: Contoso는 통화 처리 옵션을 사용 하 여 에이전트를 사용할 수 있는지 여부를 결정 합니다 (현재 상태 기반 라우팅). 


## <a name="configuration"></a>구성

자동 전화 교환 및 통화 대기열을 설정 하는 단계에는 [리소스 계정 관리](manage-resource-accounts.md)에 설명 된 다음이 포함 됩니다. 

1. 서비스 번호를 가져옵니다. 

2. 무료 전화 시스템-가상 사용자 라이선스 또는 리소스 계정이 나 전화 시스템 라이선스와 함께 사용 하는 유료 전화 시스템 라이선스를 취득 하세요.

3. 자원 계정을 만듭니다. 연결 된 리소스 계정이 있는 경우 자동 전화 교환 또는 통화 대기열이 필요 합니다. 

4. 전화 시스템 또는 전화 시스템-가상 사용자 라이선스를 리소스 계정에 할당 합니다. 자세한 내용은 [Microsoft 365 전화 시스템-가상 사용자 라이선스](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user)를 참조 하세요.

5. 라이선스를 할당 한 리소스 계정에 서비스 전화 번호를 할당 합니다. 

6. 전화 시스템 통화 대기열 또는 자동 전화 교환 만들기 

7. 통화 대기열 또는 자동 전화 교환과 함께 리소스 계정을 연결 합니다. 


### <a name="sites-with-phone-system-with-direct-routing"></a>직접 라우팅이 있는 전화 시스템이 있는 사이트 

Contoso는 로컬 통신 업체가 제공 하는 전화 번호를 Office 365의 서비스 번호로 설정 했습니다. 

- 직접 라우팅을 통해 사용할 수 있는 전화 번호를 설정 하려면 Contoso는 [리소스 계정 관리](manage-resource-accounts.md)에 있는 지침을 따릅니다. Office 365이 온-프레미스 전화 번호를 인식 하지 못하기 때문에 Contoso는 PowerShell을 사용 하 여 설정을 완료 합니다.   

- 클라우드 자동 전화 교환을 구성 하기 위해 Contoso는 [클라우드 자동 전화 교환 설정](create-a-phone-system-auto-attendant.md)에 설명 된 단계를 수행 합니다. 

- 클라우드 통화 대기열을 설정 하기 위해 Contoso는 [구름 통화 대기열 만들기](create-a-phone-system-call-queue.md)에 명시 된 단계를 팔 로우 합니다.  


### <a name="sites-with-phone-system-with-calling-plan"></a>전화 시스템이 있는 사이트 (통화 요금제 포함)

Contoso는 비즈니스용 Skype Enterprise Voice 자동 전화 교환에 사용 된 전화 번호를 Office 365 전화 시스템에 이식 해야 했습니다. 이렇게 하면 자동 전화 교환으로 사용할 수 있는 것과 동일한 번호가 서비스 번호로 할당 될 수 있습니다. 

- 전화 번호를 이식 하기 위해 Contoso는 [전화 번호를 팀으로 전송](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) 하는 지침을 팔 로우 하 고 [조직의 전화 번호 관리에 대 한](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)추가 지침을 얻었습니다.

- 클라우드 자동 전화 교환을 구성 하기 위해 Contoso는 [클라우드 자동 전화 교환 설정](create-a-phone-system-auto-attendant.md)에 설명 된 단계를 수행 합니다.

-  클라우드 통화 대기열을 설정 하기 위해 Contoso는 [구름 통화 대기열 만들기](create-a-phone-system-call-queue.md)에 명시 된 단계를 팔 로우 합니다.  

 