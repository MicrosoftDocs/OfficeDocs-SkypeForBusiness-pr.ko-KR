---
title: 회의실 및 공유 Teams 디바이스에 대한 리소스 계정 만들기
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Microsoft Teams 룸, Surface Hub의 Teams 룸, Teams 디스플레이의 핫 데스크 등 회의실 및 공유 디바이스에 대한 리소스 계정을 만드는 방법에 대한 자세한 내용은 이 문서를 참조하세요.
ms.openlocfilehash: 1448496137088ce04dc087825e67f7d8b31afd80
ms.sourcegitcommit: 3ad7b46e31890fba7abe739138cd49527d5ca6b7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/05/2022
ms.locfileid: "68475500"
---
# <a name="create-and-configure-resource-accounts-for-rooms-and-shared-teams-devices"></a>회의실 및 공유 Teams 디바이스에 대한 리소스 계정 만들기 및 구성

이 문서에서는 공유 공간 및 디바이스에 대한 리소스 계정을 만드는 단계를 제공하며 Windows의 Microsoft Teams 룸, Android의 Teams 룸, Surface Hub의 Teams 룸, Teams 디스플레이의 핫 데스크에 대한 리소스 계정을 구성하는 단계를 포함합니다.

Microsoft 365 리소스 계정은 회의실 또는 프로젝터와 같은 특정 리소스 전용 사서함 및 Teams 계정입니다. 이러한 리소스 계정은 만들 때 정의하는 규칙을 사용하여 모임 초대에 자동으로 응답할 수 있습니다. 예를 들어 회의실과 같은 공통 리소스가 있는 경우 일정 가용성에 따라 모임 초대를 자동으로 수락하거나 거절하는 해당 회의실에 대한 리소스 계정을 설정할 수 있습니다. 

모든 리소스 계정은 단일 Microsoft Teams 룸 설치에 고유하거나 Teams에서 핫 데스크 구현을 표시합니다.

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

> [!NOTE]
> Microsoft Teams 패널을 사용하는 경우 Teams 룸 리소스 계정이 Teams 룸 및 연결된 Teams 패널 모두에 로그인합니다.

> [!NOTE]
> **비즈니스용 Skype** <br><br>
> 리소스 계정이 비즈니스용 Skype 작동하도록 설정해야 하는 경우 비즈니스용 Skype 서버 사용하여 [Microsoft Teams 룸 배포](with-skype-for-business-server-2015.md)를 참조하세요.

## <a name="before-you-begin"></a>시작하기 전에

### <a name="requirements"></a>요구 사항

사용자 환경에 따라 리소스 계정을 만들려면 하나 이상의 역할이 필요합니다.

|**환경**|**필수 역할**|
|-----|-----|
|Azure Active Directory Domain Services  <br/> |전역 관리자 또는 사용자 관리자  <br/> |
|Active Directory  <br/> |Active Directory Enterprise Admins, Domain Admins 또는 사용자를 만들기 위한 위임된 권한이 있습니다. Azure Active Directory Connect 동기화 권한.  <br/> |
|Exchange Online  <br/> |전역 관리자 또는 Exchange 관리자   <br/> |
|Exchange Server  <br/> |Exchange 조직 관리 또는 받는 사람 관리   <br/> |

Teams 룸 대한 리소스 계정을 만드는 경우 UPN은 리소스 계정의 SMTP 주소와 일치해야 합니다. Teams 룸 배포하기 전에 [Microsoft Teams 룸 요구 사항을](requirements.md) 참조하세요.

### <a name="what-license-do-you-need"></a>어떤 라이선스가 필요한가요?

[!INCLUDE [mtr-device-config-license-include](../includes/mtr-device-config-license-include.md)]

## <a name="create-a-resource-account"></a>리소스 계정 만들기

[!INCLUDE [mtr-device-config-account-include](../includes/mtr-device-config-account-include.md)]

## <a name="configure-mailbox-properties"></a>사서함 속성 구성

[!INCLUDE [mtr-device-config-mailbox-include](../includes/mtr-device-config-mailbox-include.md)]

## <a name="turn-off-password-expiration"></a>암호 만료 끄기

[!INCLUDE [mtr-device-config-password-include](../includes/mtr-device-config-password-include.md)]

## <a name="assign-a-meeting-room-license"></a>회의실 라이선스 할당

[!INCLUDE [mtr-device-config-assign-include](../includes/mtr-device-config-assign-include.md)]

## <a name="next-steps"></a>다음 단계

### <a name="meeting-policies"></a>모임 정책

[!INCLUDE [mtr-device-config-policies-include](../includes/mtr-device-config-policies-include.md)]

### <a name="calling"></a>통화

리소스 계정으로 통화를 사용하도록 설정하는 고유한 요구 사항은 없습니다. 일반 사용자를 사용하도록 설정하는 것과 동일한 방식으로 호출에 리소스 계정을 사용하도록 설정합니다.

> [!NOTE]
> 디바이스 리소스 계정에 통화 정책을 할당하여 공유 디바이스에 대한 음성 메일을 해제하는 것이 좋습니다. 자세한 내용은 [Teams에서 통화 및 착신 전환(Call and call-forwarding](../teams-calling-policy.md) )을 참조하세요.

[!INCLUDE [mtr-device-config-calendar-include](../includes/mtr-device-config-calendar-include.md)]

## <a name="related-articles"></a>관련 기사

[Microsoft Teams 룸 대한 계정 구성](rooms-configure-accounts.md)

[Microsoft Teams 룸 계획](rooms-plan.md)

[Microsoft Teams 룸 배포](rooms-deploy.md)

[Microsoft Teams 룸 관리](rooms-manage.md)

[Microsoft Teams 룸 라이선스](rooms-licensing.md)
