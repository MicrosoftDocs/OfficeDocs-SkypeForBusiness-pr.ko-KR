---
title: Microsoft Teams용 오디오 회의 설정하기
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
- highpri
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- LIL_Placement
description: '전화를 사용하여 전화 회의에 참여해야 하는 회사의 사용자를 위해 전화 접속 또는 오디오 회의를 설정하는 방법을 알아봅니다. '
ms.openlocfilehash: 5f9912b005061461aa2309fb0faa54b4455214ea
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2022
ms.locfileid: "68584159"
---
# <a name="set-up-audio-conferencing-for-microsoft-teams"></a>Microsoft Teams용 오디오 회의 설정하기

경우에 따라 조직의 사용자가 전화를 사용하여 모임에 전화해야 하는 경우가 있습니다. Microsoft Teams에는 이런 상황에 대한 오디오 회의 기능이 포함되어 있습니다. 사용자는 모바일 장치 또는 PC에서 Microsoft Teams 앱을 사용하는 대신 전화를 사용하여 모임에 전화를 걸 수 있습니다.
  
모임 일정을 계획하거나 주도하는 사용자들을 위해 오디오 회의를 설정하기만 하면 됩니다. 전화를 거는 모임 참석자는 자신에게 할당된 라이선스 혹은 그 외 설정이 필요하지 않습니다.
  
오디오 회의에 대한 질문과 대답을 확인하려면 [오디오 회의에 대한 일반적인 질문](audio-conferencing-common-questions.md)을 참조하세요.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>1단계: 사용자의 국가/지역에서 오디오 회의를 사용할 수 있는지 확인하기

[오디오 회의 및 통화 플랜의 국가 및 지역 가용성](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)으로 이동하고 해당 국가나 지역을 선택하여 전화 시스템, 통화 플랜, 유료 및 무료 전화번호, 통신 크레딧에 대한 정보뿐만 아니라 오디오 회의에 대한 가용성 정보를 얻을 수 있습니다.

## <a name="step-2-get-and-assign-licenses"></a>2단계: 라이선스 받기 및 할당하기

1. 오디오 회의를 위해서는 전화 접속 모임을 설정할 각 사용자에 대한 라이선스가 필요합니다. 오디오 회의를 위해 구입해야 하는 라이선스와 비용에 대한 자세한 내용은 [Microsoft Teams 추가 기능 라이선스](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)를 참조하세요.

    >[!NOTE]
    > 오디오 회의는 Office 365 Enterprise E5 라이선스에 추가 기능으로 포함되어 있습니다.

2. 오디오 회의 라이선스를 구입한 후에는 모임을 예약하거나 진행할 조직의 사용자에게 라이선스를 할당해야 합니다. 모임을 예약하거나 이끌 조직의 사용자에게 구매한 [비즈니스용 microsoft 365 또는 Office 365 사용자에게 라이선스 할당](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)을 참조하세요.

3. 또한 이전 단계에서 라이선스를 할당한 동일한 사용자에게 통신 크레딧 라이선스(비용 없음)를 할당하는 것이 좋습니다. 통신 크레딧을 설정하는 방법을 확인하려면 [조직에 대한 통신 크레딧 설정하기](set-up-communications-credits-for-your-organization.md)를 참조하세요.

   > [!NOTE]
   > [오디오 회의(분 단위 요금)](audio-conferencing-pay-per-minute.md)를 설정할 수도 있습니다.

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>3단계: 회의 브리지에 대한 서비스 전화번호 받기

오디오 회의의 경우 사용자의 전화번호를 사용할 수 없습니다. 서비스 전화번호를 받아야 합니다. 회의 브리지에 대한 유료 또는 무료 서비스 전화번호를 받을 수 있습니다. 유료 및 무료 서비스 전화번호를 받는 방법에는 세 가지가 있습니다.
  
- **Microsoft Teams 관리 센터 사용하기** 일부 국가/지역의 경우 Microsoft Teams 관리 센터를 사용하여 회의 브리지의 서비스 전화번호를 받을 수 있습니다. [서비스 전화번호 받기](./getting-service-phone-numbers.md)를 참조하세요.

- **기존 서비스 전화번호 포팅하기** 현재 서비스 공급자 또는 전화 통신 사업자에서 Microsoft 365 또는 Office 365 기존 번호를 포팅하거나 전송합니다. 이 작업을 수행 하는 데 도움이 되는 자세한 내용은 [Teams로 전화번호 전송](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 또는 [조직에 대한 전화번호 관리하기](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)를 참조하세요.  
  
- **새 전화 번호를 위한 요청 양식 사용하기** 경우에 따라(국가/지역에 따라) Microsoft Teams 관리 센터를 사용하여 새 서비스 전화번호를 받을 수 없거나 특정 전화번호 또는 지역 코드가 필요합니다. 그럴 경우 양식을 다운로드하여 다시 보내주세요. 자세한 내용은 [조직에서 전화번호 관리하기](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)를 참조하세요.

## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>4단계: 회의 브리지에 서비스 전화번호 할당하기

회의 브리지에 대한 유료 및/또는 무료 전화번호를 받으면 모임 초대에 사용할 수 있도록 번호를 할당해야 합니다.  

다음 단계에 따라 오디오 회의 브리지에 새 전화번호를 할당하세요.

 **Microsoft Teams 관리 센터 사용**:

 1. 집에서 **음성** > **전화 번호** 로 이동합니다.
 2. 전화번호를 선택하고, **할당** 을 클릭합니다.

자세한 내용은 [오디오 회의 브리지에서 전화번호 변경하기](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)를 참조하세요.

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>5단계: 회의 브리지의 기본 및 대체 언어 설정하기

 다음으로, [Microsoft Teams에서 오디오 회의에 대한 자동 전화 교환 언어를 설정](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)하려고 합니다. 이는 회의 자동 전화 교환에서 오디오 회의를 위해 전화번호로 전화를 걸 때 발신자에게 인사하는 데 사용하는 언어입니다.

 **Microsoft Teams 관리 센터 사용**:

1. 집에서 모임 **컨퍼런스 브리지****로** >  이동합니다.
2. 회의 브리지 전화번호를 선택하고 **편집** 을 클릭한 다음 기본 언어를 선택합니다.

## <a name="step-6-set-your-conferencing-bridge-settings"></a>6단계: 회의 브리지 설정 확인하기

회의 브리지를 설정한 후에는 입력/종료 알림과 PIN 길이와 같은 기본 설정이 사용하려는 설정인지 확인합니다. 사용하려는 설정이 아니라면 설정을 변경할 수 있습니다.

 **Microsoft Teams 관리 센터 사용**:

1. 집에서 모임 **컨퍼런스 브리지****로** >  이동합니다.
2. **브리지 설정** 을 선택합니다. 그러면 **브리지 설정** 창이 열립니다.

자세한 내용은 [오디오 회의 브리지의 설정 변경하기](change-the-settings-for-an-audio-conferencing-bridge.md)를 참조하세요.

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>7단계: 모임을 진행하는 사용자에게 전화 접속 번호 할당하기

[Microsoft Teams의 초대에 포함된 전화 번호 설정을 참조하세요](set-the-phone-numbers-included-on-invites-in-teams.md).

> [!NOTE]
> *TeamsAudioconferencingpolicy* 에 전화 번호를 추가하고 사용자에게 정책을 할당하여 전화 번호를 설정할 수도 있습니다. 정책에 추가된 수신자 및 무료 전화 번호는 오디오 회의 설정 창을 통해 사용자에게 개별적으로 설정된 전화 번호보다 우선합니다. *Teamsaudioconferencingpolicy* 에 전화 번호가 추가되지 않으면 오디오 회의 설정 창을 통해 사용자에 대해 개별적으로 설정된 전화 번호가 Microsoft Teams 모임 요청에 표시됩니다. [유료 및 무료 번호에 대한 오디오 회의 정책 설정에는](audio-conferencing-toll-free-numbers-policy.md) 자세한 정보가 있습니다.

> [!IMPORTANT]
> 할당된 전화 번호가 모임 초대에 표시되는 데 최대 24시간이 걸릴 수 있습니다. 업데이트된 번호가 표시되지 않는 경우 지원에 문의하기 전에 최소 24시간 동안 기다려 주세요.

## <a name="step-8-set-up-meeting-invitations-optional"></a>8단계: 모임 초대 설정하기(선택 사항)

사용자에게 설정되는 전화 접속 번호는 모임 참석자에게 보내지는 모임 초대에 자동으로 추가됩니다. 그러나 원하는 경우 자체 도움말 및 법적인 링크, 문자 메시지 및 작은 회사 그래픽을 추가할 수 있습니다. [모임 초대 사용자 지정하기](meeting-settings-in-teams.md#customize-meeting-invitations)를 참조하세요.

## <a name="related-topics"></a>관련 항목

[오디오 회의 일반적인 질문](audio-conferencing-common-questions.md)
  
[Microsoft Teams에서 오디오 회의를 위한 전화번호](phone-numbers-for-audio-conferencing-in-teams.md)
  
[온라인 모임 및 전화 회의에 대한 옵션 설정하기](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
