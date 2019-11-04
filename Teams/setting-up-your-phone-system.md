---
title: 조직에서 전화 시스템 설정
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: '조직의 전화 시스템 (클라우드 PBX)을 설정 하는 방법에 대해 알아봅니다. '
ms.openlocfilehash: 402ae5f92e72cd1bc7ab759d3706108480a27a7e
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2019
ms.locfileid: "37925299"
---
# <a name="setting-up-phone-system-in-your-organization"></a>조직에서 전화 시스템 설정

다음은 Office 365에서 전화 시스템을 설정 하는 단계별 지침입니다. 자세한 정보에 대 한 링크는 각 단계의 마지막에 나와 있습니다.

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a>1 단계: 전화 시스템을 해당 국가 또는 지역에서 사용할 수 있는지 확인

1.  먼저 [오디오 회의 및 통화 요금제의 국가 및 지역 사용 가능성](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)으로 이동 하 고 페이지 위쪽에 있는 목록에서 국가 또는 지역을 선택 합니다. 
2.  **전화 시스템**에서 기능 목록과 세부 정보를 검토 합니다. 
3.  전화 시스템을 사용할 수 있는 경우 2 단계로 이동 합니다. 

**전화 시스템 및 오디오 회의의 국가별 사용 가능성에 대 한 자세한 내용은 [오디오 회의 및 통화 요금제의 국가 및 지역 사용 가능성](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)을 참조 하세요.**

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a>2 단계: 전화 시스템 및 통화 계획 라이선스 구입 및 할당

전화 시스템 및 통화 계획 라이선스를 단일 사용자에 게 할당 하려면 Office 365 라이선스를 할당 하는 것과 같은 단계를 수행 합니다. [Microsoft 팀 라이선스 할당](assign-teams-licenses.md)을 참조 하세요. 대량으로 여러 사용자를 할당 하려는 경우 [Microsoft 팀 라이선스 할당](assign-teams-licenses.md)을 참조 하세요.

## <a name="step-3-get-phone-numbers-for-your-users"></a>3 단계: 사용자의 전화 번호 가져오기

전화를 걸고 받을 수 있도록 조직에 사용자를 설정 하려면 먼저 전화 번호를 받아야 합니다.

다음과 같은 세 가지 방법으로 사용자에 대 한 번호를 얻을 수 있습니다.
- 비즈니스용 Skype 관리 센터를 사용 하 여 새로운 번호를 받으세요.
- 비즈니스용 Skype 관리 센터에서 사용할 수 없는 새로운 번호를 받으세요.
- 현재 서비스 공급자 또는 전화 통신 회사의 기존 번호를 Office 365으로 이식 하거나 이전 합니다.

이러한 번호를 보고, 검색 하 고, 가져오고, 예약 하려면 **새 사용자 번호 추가** 페이지를 사용 해야 합니다. 국가/지역, 시/도, 시/도를 기준으로 검색할 수 있으며, 사용자에 게 필요한 전화 번호 수를 입력 합니다.

### <a name="get-new-user-phone-numbers"></a>새 사용자 전화 번호 받기 
 
![비즈니스용 skype](media/sfb-logo-30x30.png) **관리 센터를 사용 하 여** 비즈니스용 skype 로고를 표시 하는 아이콘

1. 회사 또는 학교 계정으로 Microsoft 365에 로그인 합니다.

2. **Microsoft 365 관리 센터** > **비즈니스용 Skype**로 이동 합니다.
    
3. 왼쪽 탐색 창에서 **음성** > **전화 번호로**이동 하 고, **새 번호** ![추가 단추를 클릭 하 고 더하기 기호로](media/c224fbd0-f0f5-46ce-a1a7-73adf4540ef7.png)표시 한 다음 **새 사용자 번호**를 클릭 합니다.
    
### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a>비즈니스용 Skype 관리 센터에서 사용할 수 없는 새로운 번호 가져오기
  
때로는 (국가/지역에 따라) 비즈니스용 Skype 관리 센터를 사용 하 여 새 번호를 받을 수 없습니다. 이 경우 양식을 다운로드 하 여 다시 전송 해야 합니다. 새 사용자 번호를 요청 하는 방법을 알아보려면 [조직의 전화 번호 관리](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 를 참조 하세요.   
  
### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>서비스 공급자 또는 전화 통신 회사의 전화 번호를 이식 하거나 전송 합니다.
  
- 사용자에 게 999 이하의 전화 번호가 필요한 경우 비즈니스용 Skype 관리 센터의 **새 로컬 번호 포트 주문** 마법사를 사용할 수 있습니다. 전화 [번호를 팀에 게 전송](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 에 나와 있는 단계를 따라 전화 번호를 전송 합니다.
    
- 999 개 이상의 전화 번호를 이식 해야 하는 경우에는 [조직의 전화 번호 관리](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 를 참조 하 여 이러한 전화 번호를 모두 Office 365로 전송 하는 방법으로 포트 주문 서비스 요청 또는 주문을 제출 해 보세요. 

**새 전화 번호를 받고 있거나 기존 번호를 전송 하는 방법에 대 한 자세한 내용은 [조직의 전화 번호 관리](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)를 참조 하세요.**

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>4 단계: 서비스 전화 번호 가져오기 (오디오 회의, 통화 대기열, 자동 전화 교환)

Office 365에서 사용자의 전화 번호를 가져올 수 있을 뿐만 아니라 오디오 회의 (컨퍼런스), 자동 전화 교환, 통화 대기열 (서비스 번호 라고도 함) 등의 서비스에 대 한 유료 또는 무료 전화 번호를 검색 하 고 받을 수도 있습니다. 서비스 전화 번호는 사용자 또는 구독자 전화 번호 보다 높은 동시 통화 용량을가지고 있습니다. 예를 들어 서비스 번호는 통화를 동시에 한 번만 처리할 수 있지만, 사용자의 전화 번호는 일부 통화를 동시에 처리할 수 있습니다.

### <a name="get-new-service-numbers"></a>새 서비스 번호 가져오기

![비즈니스용 skype](media/sfb-logo-30x30.png) **관리 센터를 사용 하 여** 비즈니스용 skype 로고를 표시 하는 아이콘


1. 회사 또는 학교 계정으로 Office 365에 로그인 합니다.

2. **Microsoft 365 관리 센터** > **비즈니스용 Skype**로 이동 합니다.

3. 왼쪽 탐색 창에서 **음성** > **전화 번호로** > 이동한 다음 새**번호를 추가**하 고 **새 서비스 번호**를 클릭 합니다.

    > [!IMPORTANT]
    > 비즈니스용 Skype 관리 센터의 왼쪽 탐색 창에서 **음성** 옵션을 보려면 먼저 하나 이상의 **Enterprise E5 라이선스**, 하나의 **전화 시스템** 추가 기능 라이선스 또는 하나의 **오디오 회의** 추가 기능 라이선스를 구입 해야 합니다.

### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a>비즈니스용 Skype 관리 센터에서 사용할 수 없는 새로운 번호 가져오기
  
때로는 (국가/지역에 따라) 비즈니스용 Skype 관리 센터를 사용 하 여 새 번호를 받을 수 없습니다. 이 경우 양식을 다운로드 하 여 다시 전송 해야 합니다. 새 번호를 요청 하는 방법을 알아보려면 [조직의 전화 번호 관리](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 를 참조 하세요. 

### <a name="port-or-transfer-existing-service-numbers"></a>기존 서비스 번호 포트 또는 전송

현재 서비스 공급자 또는 통신 회사에서 서비스 번호를 전송 하려면 Microsoft에 수동으로 포트 순서를 제출 해야 합니다. 각 서비스 번호 유형 (유료 및 무료)에 대해 별도의 포트 주문을 제출 하 여 승인 문자 (LOA)를 사용 하 여 전송 하 게 됩니다. 인증 문자 (LOA)에서 올바른 서비스 번호 유형을 선택 해야 합니다. Microsoft support에 문의 하는 경우*사용자 또는 구독자 번호가 아닌*서비스 번호를 전송 하 고 있는지, 아니면 동시 호출 용량이 통화 볼륨을 처리 하는 데 충분 하지 않을 수 있다는 것을 지정 하십시오. 전화 번호를 전송 하거나 전화 번호를 사용 하 여 다른 작업을 수행 하려는 경우 [조직의 전화 번호 관리](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)를 참조 하세요.

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a>5 단계: 통화 계획을 설정 하려는 경우

위의 단계를 수행한 후에는 이미 전화 시스템 및 라이선스와 통화 요금제 (2 단계)를 구입 하 고 할당 하 고 사용자에 게 확보 한 전화 번호 (3 단계)를 사용 하 여 통화 계획이 부분적으로 설정 되어 있습니다. 다음 세 절차에 따라 통화 요금제 설정을 완료 합니다.

### <a name="add-emergency-addresses-and-locations-for-your-organization"></a>조직의 긴급 주소 및 위치 추가

1. **음성** 페이지에서 **응급 위치** > 에서**새 주소 추가**를 선택 합니다.

2. **새 주소** 창에서 주소의 이름을 입력 한 다음 나머지 상자를 완료 합니다.
    
     ![새 주소 창 스크린샷](media/dc1c5ef3-0554-4fb7-9ab1-5ea3ac9e5eb5.png)
  
    > [!TIP]
    > 영어 고객의 경우, 해당 하는 이름이 숫자 이면 위의 그림에 표시 된 대로 끝에 "st" 또는 "th"를 포함 해야 합니다.

3. **유효성 검사**를 선택 합니다.

    필요한 경우 주소를 수정 하 라는 메시지가 표시 됩니다.

    > [!CAUTION]
    > 주소 또는 도심 주소의 유효성을 검사 하는 경우 정확 하 게 서식이 지정 된 상태 인지 확인 해야 합니다. 구/군/시 이름을 잘못 입력 하는 등 부분적으로 올바른 긴급 주소를 입력 해도 여전히 유효성 검사를 통과할 수 있습니다. 철자가 잘못 입력 되어 있고 유효성 검사를 통과 한 경우에는 주소의 다른 올바른 부분과 함께 철자가 틀린 이름을 조합 하 여 통화를 적절 한 긴급 파견 센터로 라우팅할 수 있는 충분 한 정보가 있습니다.

    > [!TIP]
    > 긴급 응답을 위해 주소를 수정 해야 하는 경우 녹색 배너에 주소가 업데이트 되었음을 알리는 메시지가 표시 됩니다.

4. 주소의 유효성을 검사 한 후 **저장**을 선택 합니다.

### <a name="assign-phone-numbers-and-emergency-addresses-to-users"></a>사용자에 게 전화 번호 및 긴급 주소 할당

> [!TIP]
> 이 단계를 수행 하기 전에 비즈니스에 더 많은 사람을 추가 하는 경우 **음성 사용자** 페이지에 표시 되는 데 **몇 시간이** 걸릴 수 있습니다. 대기 시간이 있습니다.

1. **음성 사용자** 페이지에서 전화 번호와 긴급 주소를 할당 하려는 사용자를 선택 합니다.

2. 작업 창에서 **번호 지정**을 클릭 합니다.

3. **번호 할당** 페이지의 **배정할 번호 선택** 목록에서 사용자의 전화 번호를 선택 합니다.

4. 긴급 주소를 선택 하려면 상자에 구/군/시의 이름을 입력 하 고 **검색**을 선택 합니다.

    > [!IMPORTANT]
    > 미국 이외의 지역에 거주 하는 사용자에 게는 이미 긴급 한 주소가 있지만, 지금이 번호를 변경할 수 있습니다. [사용자에 대 한 긴급 주소 할당 또는 변경을](/skypeforbusiness/what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user)참조 하세요. 
  
5. 전화 번호와 긴급 주소를 모두 할당 한 후 **저장**을 선택 합니다.

### <a name="tell-your-users-about-their-new-phone-numbers"></a>사용자에 게 새로운 전화 번호에 대해 알아보기


메일을 보내거나 비즈니스의 선호 하는 통신 방법을 사용 하 여 새 전화 번호에 대 한 정보를 제공 하는 것이 좋습니다.

**Skype For Business** 앱에서 해당 전화 번호를 볼 수 있는 방법은 다음과 같습니다.

1. 데스크톱에서 비즈니스용 Skype에 로그인 합니다.
    
2. **설정** > **** 도구 > **옵션**을 선택 합니다. 
    
     ![도구 메뉴의 옵션 스크린샷](media/20637117-91d7-4a7e-9f06-7abc634a9211.png)
  
3. 그런 다음 **전화**를 선택 합니다. 
    
    ![비즈니스용 Skype 전화 옵션 스크린샷](media/0128d667-2bf8-4165-b703-e9b78a15b63c.png)
 
**Microsoft 팀**에서 사용자는 왼쪽 탐색 창에서 **통화** 를 클릭 하 여 전화 번호를 볼 수 있습니다. 전화 번호가 다이얼 패드 위에 표시 됩니다.

![통화를 클릭 한 후 사용할 수 있는 옵션의 스크린샷](media/teams-phone-number.png)

**통화 요금제 설정에 관련 된 모든 단계에 대 한 자세한 내용은 [통화 계획](set-up-calling-plans.md)설정을 참조 하세요.**


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a>6 단계: 오디오 회의를 설정 하려는 경우

조직의 사용자가 모임에 전화를 걸 때 휴대폰을 사용 해야 하는 경우가 있습니다. 비즈니스용 Skype 및 Microsoft 팀에는 이러한 상황에 대 한 오디오 회의 기능이 포함 되어 있습니다. 모바일 장치 또는 PC에서 비즈니스용 Skype 또는 Microsoft 팀 앱을 사용 하는 대신 휴대폰을 사용 하 여 비즈니스용 Skype 또는 Microsoft 팀 모임으로 통화할 수 있습니다.

일정을 예약 하거나 리드 회의를 하는 사용자를 위해 오디오 회의를 설정 하기만 하면 됩니다. 전화를 걸 수 있는 모임 참석자는 해당 사용자 또는 다른 설정에 할당 된 라이선스가 필요 하지 않습니다.
  
오디오 회의에 대 한 질문과 대답은 [오디오 회의 일반적인 질문](audio-conferencing-common-questions.md)을 참조 하세요.
    
1. **오디오 회의** 추가 기능 라이선스 및 통신 크레딧 라이선스를 구입한 경우에는 할당 합니다. 지침은 [Microsoft 팀 라이선스 할당](assign-teams-licenses.md)을 참조 하세요.

    오디오 회의 공급자를 결정 합니다. 오디오 회의 공급자가 오디오 회의 브리지를 제공 합니다. 회의 브리지는 모임에 대 한 전화 접속 전화 번호, Pin 및 회의 Id를 설정 합니다. Microsoft 또는 타사 오디오 회의 공급자를 사용할지 여부를 결정 합니다.

    > [!NOTE]
    > Microsoft 팀 사용자는 타사 오디오 회의 공급자를 사용자가 사용할 수 없습니다.

    - **Microsoft의 오디오 회의 공급자**: 오디오 회의를 위한 가장 쉬운 솔루션을 원하는 경우 오디오 회의 공급자로 Microsoft를 선택 합니다.
    
    - 타사 **오디오 회의 공급자**: Office 365의 오디오 회의를 사용할 수 없는 국가의 경우 해당 위치 때문에 서비스 품질은 좋지 않거나 기존 계약이 있으므로 타사 오디오를 선택 합니다. 회의 공급자. 공급자를 찾으려면 [Microsoft](https://go.microsoft.com/fwlink/?LinkId=797530)로 이동 하세요.
 
2. 모임을 진행 하거나 예약 하는 사람에 게 오디오 회의 공급자를 할당 합니다. [Microsoft를 오디오 회의 공급자로 지정](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)을 참조 하세요.

3. 모임 초대를 설정 합니다. 다음 단계는 선택 사항 이지만, 다음과 같은 관리자가 많습니다. 
  
   1. [비즈니스용 Skype에서 모임 초대를 사용자 지정](/skypeforbusiness/set-up-skype-for-business-online/customize-meeting-invitations)합니다. 사용자에 대해 설정 된 전화 접속 번호가 참석자에 게 전송 되는 모임 초대에 자동으로 추가 됩니다. 그러나 고유한 도움말 및 법률 링크, 문자 메시지 및 작은 회사 그래픽을 추가할 수 있습니다.
    
   2. [비즈니스용 Skype](/skypeforbusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites) 또는 [Microsoft 팀](set-the-phone-numbers-included-on-invites-in-teams.md)의 초대에 포함 된 모임 이끌이의 오디오 회의 전화 번호를 설정 합니다. 사용자가 예약한 모임에 표시 되는 전화 번호입니다.
    
   3. 비즈니스용 [Skype](/skypeforbusiness/audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing) 또는 [Microsoft 팀](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) 에서 오디오 회의에 대 한 자동 전화 교환 언어를 설정 합니다. 오디오 회의 자동 전화 교환은 음성 회의 전화 번호로 전화를 걸 때 발신자에 게이를 인사 하는 데 사용 됩니다. 이 단계는 Microsoft를 오디오 공급자로 사용 중인 경우에만 적용 됩니다.
    
   4. [Microsoft 팀에서](set-the-pin-length-for-audio-conferencing-meetings-in-teams.md)오디오 회의 모임에 대 한 PIN 길이를 설정 합니다.
    
      > [!NOTE]
      > 중국에서 21Vianet이 운영 하는 Office 365를 사용 하는 고객은이 기능을 아직 사용할 수 없습니다. 자세한 내용은 [21vianet에서 운영 하는 Office 365에 대 한](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE)자세한 내용을 알아보세요.

**오디오 회의에 대 한 자세한 내용은 [Microsoft 팀을 위한 오디오 회의 설정을](set-up-audio-conferencing-in-teams.md)참조 하세요.**

## <a name="step-7-if-you-want-to-set-up-a-cloud-call-queue"></a>7 단계: 클라우드 통화 큐를 설정 하려면

클라우드 통화 큐에는 사용자가 조직의 전화 번호를 호출할 때 사용 되는 인사말, 통화 대기를 자동으로 전환 하는 기능, 전화를 거는 사용자가 통화를 처리 하기 위해 사용할 수 있는 다음 통화 에이전트 검색 기능 등이 포함 됩니다. 대기 중인 음악 듣기. 조직에 대 한 단일 또는 복수 통화 대기열을 만들 수 있습니다.

통화 대기열을 만들고 설정 하기 전에 기존의 유료 또는 무료 서비스 번호를 가져오거나 이전 해야 합니다. 무료 또는 무료 서비스 전화 번호를 얻은 후에는 **비즈니스용 Skype 관리 센터** > **음성** > **전화 번호**에 표시 되며 나열 된 **번호 종류가** 서비스로 표시 됩니다 **-무료입니다. **. 서비스 번호를 얻으려면 [비즈니스용 Skype 및 Microsoft 팀에 대 한 서비스 전화 번호 가져오기를](/microsoftteams/getting-service-phone-numbers) 참조 하거나, 기존 서비스 번호를 전송 하 고 싶다면 [전화 번호를 팀에 게 양도](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)를 참조 하세요.
  
> [!NOTE]
> 미국 이외의 지역에 거주 하는 경우 비즈니스용 Skype 관리 센터를 사용 하 여 서비스 번호를 얻을 수 없습니다. 미국 이외의 지역에서이를 수행 하는 방법을 확인 하려면 [조직의 전화 번호 관리](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 로 이동 하세요.

새 통화 대기열을 만들려면 **비즈니스용 Skype 관리 센터**에서 **통화 라우팅** > **통화 대기열**을 클릭 하 고 **새로 추가**를 클릭 한 다음 [클라우드 통화 대기열 만들기](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue#step-3---create-a-new-call-queue)의 **3 단계** 에 나오는 지침을 따릅니다.

**통화 대기열에 대 한 자세한 내용은 [클라우드 통화 대기열 만들기](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)를 참조 하세요.**

## <a name="step-8-if-you-want-to-set-up-a-cloud-auto-attendant"></a>8 단계: 클라우드 자동 전화 교환을 설정 하려면

자동 전화 교환을 통해 조직에 전화를 걸고 메뉴 시스템을 탐색 하 여 올바른 부서, 통화 대기열, 사람, 교환원에 게 얻을 수 있습니다. 비즈니스용 Skype 관리 센터를 사용 하 여 조직의 자동 전화 교환을 만들 수 있습니다.

새 자동 전화 교환을 만들려면 비즈니스용 Skype 관리 센터에서 **통화 라우팅** > **자동 전화 교환을**클릭 하 고 **새로 추가**를 클릭 한 다음 클라우드 자동 전화 교환 만들기의 **2 단계** 에서 각 페이지에 대 한 지침을 따릅니다. [ ](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant#step-2---create-a-new-auto-attendant).


**클라우드 자동 전화 교환에 대 한 자세한 내용은 [클라우드 자동 전화 교환 설정을](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant)참조 하세요.**

## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>9 단계: 서비스 전화 번호 지정 (오디오 회의, 통화 대기열, 자동 전화 교환)

**위의 4 단계**에서 서비스 번호를 찾았으면 원하는 각 서비스 유형에 할당 해야 합니다. 예를 들어 유료 또는 무료 서비스 전화 번호를 원할 경우 회의 브리지에 해당 번호를 할당 해야 합니다.

- 오디오 회의의 경우 **Microsoft 365 관리 센터** > **관리 센터** > 에서**비즈니스용 Skype** > **오디오 회의** 로 이동 하 여 회의 브리지에 전용 번호를 할당 하 고 다음을 클릭 합니다. 회의 브리지를 사용 하거나 [오디오 회의 브리지에서 유료 또는 무료 전화 번호 변경을](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)볼 수 있습니다.

- 자동 전화 교환의 경우 **Microsoft 365 관리 센터** > **관리 센터** > (비즈니스용**Skype** > **통화 라우팅** > **자동 전화 교환)로 이동 하 여 자동 전화 교환에 전용 번호를 할당할 수 있습니다. **자동 전화 교환 단추를 클릭 합니다. **일반** 페이지에서 이미 존재 하는 서비스 번호가 **전화 번호** 드롭다운에 나열 됩니다. 자세한 내용은 [클라우드 자동 전화 교환 설정을](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant)참조 하세요.
- 통화 대기열의 경우 **Microsoft 365 관리 센터** > **관리 센터** > **비즈니스용 Skype** > **통화 라우팅** > **통화 전담팀** 으로 이동 하 여 통화 대기열에 전용 번호를 할당할 수 있으며, 다음을 클릭 합니다. 통화 대기열 **일반** 페이지에서 이미 존재 하는 서비스 번호가 **전화 번호** 드롭다운에 나열 됩니다. 자세한 내용은 [클라우드 통화 대기열 만들기](https://docs.microsoft.com/microsoftteams/create-a-phone-system-call-queue)를 참조 하세요.

**새 서비스 번호를 받고 기존 서비스 번호를 포팅 하는 방법에 대 한 자세한 내용은 [서비스 전화 번호 가져오기를](/microsoftteams/getting-service-phone-numbers)참조 하세요.**

## <a name="step-10-set-up-communications-credits-for-your-organization"></a>10 단계: 조직의 통신 크레딧을 설정

비즈니스용 Skype 및 Microsoft 팀에 무료 전화 번호를 사용 하려는 경우에는 통신 크레딧을 설정 해야 합니다. 또한 통화 요금제 (국내 또는 국제) 및 오디오 회의 사용자에 게 통신 크레딧을 설정 하 고 **목적지**로 전화를 걸 수 있는 기능이 필요한 경우이 좋습니다. 여러 국가/지역이 포함 되어 있지만 일부 대상은 통화 요금제 또는 오디오 회의 구독에 포함 되지 않을 수 있습니다. 통신 크레딧 청구를 설정 하지 않고 사용자에 게 **통신 크레딧** 라이선스를 할당 하지 않은 경우 (해당 국가/지역의 통화 요금제 또는 오디오 회의 계획에 따라 다름) 해당 사용자는 오디오 회의 모임에서 통화 하거나 전화를 걸 수 없습니다. [통신 크레딧을 확인](what-are-communications-credits.md) 하 여 권장 자금을 포함 하 여 더 많은 정보를 얻을 수 있습니다.
  
> [!NOTE]
> 비용을 확인 하려면 [여기에서 요금](https://go.microsoft.com/fwlink/p/?LinkId=799523 )을 보세요.

### <a name="to-set-up-communications-credits"></a>통신 크레딧을 설정 하려면

1. 회사 또는 학교 계정으로 Microsoft 365에 로그인 합니다.

2. 관리 센터의 왼쪽 탐색 모음에서 **청구** > **구독** > **추가** > 기능으로 이동 하 여 추가 기능을**구매한**다음, 지금 **통신 크레딧** > **구매**를 선택 합니다.

3. **커뮤니케이션 크레딧** 신청 페이지에서 정보를 입력 하 고 **다음**을 클릭 합니다.

4. 결제 정보를 입력 하 고 **주문을**클릭 합니다.
    >[!IMPORTANT]
    >볼륨 라이선스 고객 인 경우 결제를 위해 엔터프라이즈 계약 번호를 선택할 수 있습니다. 여러 엔터프라이즈 계약 번호를 사용 하는 경우 결제에 사용할 엔터프라이즈 계약을 선택할 수 있습니다. 또한 회사 계약 번호와 연결할 구매 주문 번호를 지정할 기회가 주어 집니다 (해당 하는 경우).
    
**통신 크레딧을 설정 하는 방법에 대 한 자세한 내용은 [조직의 통신 크레딧을 설정](set-up-communications-credits-for-your-organization.md)을 참조 하세요.**
  
### <a name="assign-a-communications-credits-license-to-users"></a>사용자에 게 통신 크레딧 라이선스 할당

1. 회사 또는 학교 계정으로 Office 365에 로그인 합니다.

2. Microsoft 365 관리 센터의 왼쪽 탐색 창에서 **사용자** > **활성 사용자**로 이동한 다음 목록에서 한 명 또는 몇 명의 사용자를 선택 합니다.

3. 작업 창의 **제품 라이선스**에서 **편집**을 클릭 합니다.

4. **제품 라이선스** 페이지에서이 **라이선스를 할당 하도록** **통신 크레딧을** 설정/해제 한 다음 **저장**을 클릭 합니다.

    > [!NOTE]
    > **Enterprise E5** 라이선스를 할당 받은 사용자가 있는 경우에도이 작업을 수행 하는 것이 좋습니다.

**통신 제작진 라이선스를 할당 하는 방법에 대 한 자세한 내용은 [조직의 통신 크레딧 설정을](set-up-communications-credits-for-your-organization.md)참조 하세요.**

## <a name="related-topics"></a>관련 항목
[Office 365에서 전화 시스템을 사용 하 여 얻을 수 있는 기능](here-s-what-you-get-with-phone-system.md)

[비즈니스용 Skype 및 Microsoft 팀에 대 한 서비스 전화 번호 가져오기](/microsoftteams/getting-service-phone-numbers)

[오디오 회의 및 통화 플랜의 국가 및 지역 가용성](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 
