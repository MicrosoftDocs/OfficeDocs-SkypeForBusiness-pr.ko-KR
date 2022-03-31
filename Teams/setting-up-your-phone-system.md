---
title: 조직에서 전화 시스템 설정
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-apr2020
- intro-get-started
description: 조직에서 조직에 대한 Teams 전화 시스템 방법을 자세히 설명하는 단계별 Microsoft 365.
ms.openlocfilehash: 6b56c68e7316c78c7c1881d6e9d6ca39b13823b1
ms.sourcegitcommit: cbdc80c302e97d18a923ef57bb5d4b6cf7676d00
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/30/2022
ms.locfileid: "64556299"
---
# <a name="set-up-phone-system-in-your-organization"></a>조직에서 전화 시스템 설정

이 문서에서는 클라우드에서 통화 제어 및 PBX(Private Branch Exchange)를 사용하도록 설정하기 위한 microsoft의 기술 전화 시스템 콘텐츠에 대한 로드맵을 Microsoft 365 제공합니다. 자세한 정보에 대한 링크는 각 단계의 끝에서 사용할 수 있습니다. 

이 문서를 읽기 전에 이 문서의 내용을 전화 시스템 내용을 읽어 [](what-is-phone-system-in-office-365.md) 보면 다음과 같은 내용을 [전화 시스템.](here-s-what-you-get-with-phone-system.md) 후자의 두 문서에서는 요구 사항 및 전화 시스템 설명합니다.    

이 문서에서는 다음 단계를 설명합니다. 

- [1단계: 라이선스 전화 시스템 할당](#step-1-buy-and-assign-a-phone-system-license)  
- [2단계: PSTN 연결 옵션 선택](#step-2-choose-a-pstn-connectivity-option) 
- [3단계: 사용자에 대한 전화 번호 확인](#step-3-get-phone-numbers-for-your-users)
- [4단계: 서비스에 대한 전화 번호 얻기](#step-4-get-phone-numbers-for-services-call-queues-auto-attendants)
- [5단계: 통화 큐를 설정하려는 경우](#step-5-if-you-want-to-set-up-a-call-queue) 
- [6단계: 자동 참석자 설정](#step-6-if-you-want-to-set-up-an-auto-attendant) 
- [7단계: 무료 번호에 대한 통신 크레딧 설정](#step-7-set-up-communications-credits-for-toll-free-numbers)
 

## <a name="step-1-buy-and-assign-a-phone-system-license"></a>1단계: 라이선스 전화 시스템 할당

단일 사용자에게 전화 시스템 라이선스를 할당하기 위해 단계는 단일 라이선스를 할당하는 Microsoft 365 동일합니다. 여러 사용자에게 일괄적으로 라이선스를 할당할 수도 있습니다. 사용 가능한 라이선스에 대한 전화 시스템 및 라이선스를 획득하고 할당하는 방법에 대한 자세한 내용은 추가 Teams 추가 기능 [](/microsoftteams//teams-add-on-licensing/microsoft-teams-add-on-licensing) 라이선스 및 추가 Microsoft Teams 할당을 [참조하세요](/microsoftteams/teams-add-on-licensing/assign-teams-add-on-licenses).

## <a name="step-2-choose-a-pstn-connectivity-option"></a>2단계. PSTN 연결 옵션 선택 
 
사용자가 외부 통화를 걸고 받을 수 있도록 설정하려면 PSTN(공용 전화 시스템 전화 네트워크)에 연결해야 합니다. Microsoft는 다음을 포함하여 PSTN에 연결하는 여러 옵션을 제공합니다. 

- 요금제 호출. PSTN 통신사로 Microsoft를 사용할 수 있는 올인원 클라우드 솔루션입니다. 

- 운영자 연결. 기존 통신사가 Microsoft 운영자 연결 프로그램에 참여하는 경우 PSTN 호출 및 SBC(세션 테두리 컨트롤러)를 관리할 수 있습니다. 

- 직접 라우팅. SBC를 연결하여 사용자 자신의 PSTN 캐리어를 전화 시스템. 

모든 연결 옵션에 대한 자세한 내용은 [PSTN 연결 옵션을 참조하세요](pstn-connectivity.md).   

## <a name="step-3-get-phone-numbers-for-your-users"></a>3단계: 사용자에 대한 전화 번호 확인

전화 통화를 걸고 받을 수 있도록 조직에서 사용자를 설정하려면 먼저 해당 사용자에 대한 전화 번호를 받아야 합니다.

사용자의 전화 번호를 관리하는 방법에 대한 자세한 내용은 다음 문서를 참조하세요. 사용자에 대한 숫자를 관리하는 방법은 선택한 PSTN 연결 옵션에 따라 다를 수 있습니다.   

- [조직의 전화](manage-phone-numbers-landing-page.md) 번호 관리 - PSTN 연결 옵션에 따라 숫자를 구하고 관리할 수 있는 특정 문서에 대한 링크가 있는 전화 번호 유형 개요를 제공합니다. 두 가지 유형의 사용자 전화 [번호를 설명합니다](manage-phone-numbers-landing-page.md#user-telephone-numbers). 
 
- [사용자에 대한](assign-change-or-remove-a-phone-number-for-a-user.md) 전화 번호를 할당, 변경 또는 제거 - 획득한 전화 번호를 할당하고 관리하는 방법을 설명합니다. 
 
- [받을 수 있는 전화](how-many-phone-numbers-can-you-get.md) 번호 수 – 구입하고 할당한 라이선스의 유형 및 전화 번호 유형에 따라 얻을 수 있는 전화 번호 수를 설명합니다. 


## <a name="step-4-get-phone-numbers-for-services-call-queues-auto-attendants"></a>4단계: 서비스에 대한 전화 번호 보기(통화 큐, 자동 참석자)

사용자에 대한 전화 번호를 획득하는 것 외에도 자동 참석자 및 통화 큐와 같은 서비스에 대한 무료 전화 번호를 획득할 수 있습니다. 서비스 번호는 수백 개의 통화를 동시에 처리할 수 있는 반면, 사용자의 전화 번호는 몇 개의 호출만 동시에 처리할 수 있습니다.   

라이선스에 포함된 Microsoft의 서비스 번호를 얻을 수 있습니다. 연결 또는 직접 라우팅을 통해 PSTN 운영자 연결 경우 자체 통신사 또는 운영자가 제공하는 서비스 번호를 사용할 수 있습니다. 

자세한 내용은 다음을 참조하세요.

- [조직의 전화](manage-phone-numbers-landing-page.md) 번호 관리 - PSTN 연결 옵션에 따라 숫자를 구하고 관리할 수 있는 특정 문서에 대한 링크가 있는 전화 번호 유형 개요를 제공합니다.  
라이선스 [에](manage-phone-numbers-landing-page.md#service-telephone-numbers) 포함된 Microsoft에서 사용할 수 있는 서비스 전화 번호를 설명합니다. 서비스 번호 또는 직접 라우팅에서 제공하는 서비스 운영자 연결 자세한 내용은 공급자에 문의하세요. 

- [받을 수 있는 전화](how-many-phone-numbers-can-you-get.md) 번호 수 – 구입하고 할당한 라이선스의 유형 및 전화 번호 유형에 따라 얻을 수 있는 전화 번호 수를 설명합니다. 

## <a name="step-5-if-you-want-to-set-up-a-call-queue"></a>5단계: 통화 큐를 설정하려는 경우

통화 큐에는 다른 사용자가 조직의 전화 번호로 전화를 걸 때 사용되는 인사말, 자동으로 통화를 보류할 수 있는 능력, 통화를 처리하기 위해 사용할 수 있는 다음 통화 에이전트를 검색하는 기능을 포함합니다. 조직에 대해 단일 또는 여러 개의 호출 큐를 만들 수 있습니다. 

호출 큐에 대한 자세한 내용은 호출 큐 [만들기를 참조하세요](create-a-phone-system-call-queue.md).

## <a name="step-6-if-you-want-to-set-up-an-auto-attendant"></a>6단계: 자동 참석자 설정

자동 참석자는 조직에 전화하는 사람들이 메뉴 시스템을 탐색하여 올바른 부서로 이동하고, 큐, 사람 또는 연산자를 호출할 수 있도록 합니다.  

자동 참석자 설정에 대한 자세한 내용은 자동 참석자 설정  [을 참조하세요](create-a-phone-system-auto-attendant.md).

## <a name="step-7-set-up-communications-credits-for-toll-free-numbers"></a>7단계: 무료 번호에 대한 통신 크레딧 설정

무료 전화 번호와 함께 사용하려면 Microsoft Teams 크레딧을 설정해야 합니다. 무료 통화는 분당 청구하며 양수의 통신 크레딧 잔액이 요구됩니다. 

통신 크레딧은 다음과 같이 사용할 무료 번호를 추가하는 편리한 방법입니다. 

- 음성 앱에 대한 서비스 번호(예: 자동 참석자 또는 통화 큐)를 사용할 수 있습니다. 

- 국내 통화 요금제 구독이 있는 경우 또는 국내 및 국제 통화 요금제 구독에 포함된 범위를 초과하는 경우 국제 전화 번호로 전화를 걸 수 있습니다. 

- 월별 분 배분을 소진한 후 전화를 걸고 분당 요금을 지불합니다. 

자세한 내용은 통신 크레딧이 있나요 [?](what-are-communications-credits.md) 및 조직에 대한 통신 크레딧 설정 을 [참조하세요](set-up-communications-credits-for-your-organization.md).
  

## <a name="related-topics"></a>관련 항목

- [전화 시스템이란?](what-is-phone-system-in-office-365.md)

- [다음은 전화 시스템 기능입니다.](here-s-what-you-get-with-phone-system.md)

- [조직의 전화 번호 관리](manage-phone-numbers-landing-page.md)


    
  
 
