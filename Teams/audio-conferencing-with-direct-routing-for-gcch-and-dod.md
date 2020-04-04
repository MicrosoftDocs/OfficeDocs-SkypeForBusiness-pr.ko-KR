---
title: 직접 라우팅이 있는 오디오 회의, GCCH 및 DoD
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
description: GCCH 및 DoD 환경에서 직접 라우팅이 있는 오디오 회의를 사용 하는 방법에 대해 알아봅니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6b8077e2bf376976c9906a8703ebd59a1d1cc23f
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43141171"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>GCC High 및 DoD를 위해 직접 라우팅으로 오디오 회의

GCC High 및 DoD에 대 한 직접 라우팅이 있는 오디오 회의는 참가자가 휴대폰 장치를 사용 하 여 GCC High 또는 DoD 조직의 팀 모임에 참가할 수 있도록 합니다. 모임 참가자는 전화 장치를 사용 하 여 인터넷 연결이 제한 되어 있거나 사용자가 이동 중이 고 팀에 액세스할 수 없는 경우와 같은 시나리오에서 팀 모임에 참가 하는 것이 좋습니다. 참가자는 조직의 전화 접속 전화 번호로 전화를 걸고 전화 장치에 모임 전화를 걸도록 하 여 모임에 참가 하도록 선택할 수 있습니다.

GCC High 및 DoD에 대 한 직접 라우팅이 있는 오디오 회의를 사용 하는 경우 조직에서 전화 접속 전화 번호로 자체 번호를 사용 하 고 전화 장치에 대 한 모든 모임 전화 접속은 직접 라우팅을 통해 라우팅됩니다. 서비스를 사용 하도록 설정 하려면 조직에서 직접 라우팅과 전화 접속 전화 번호로 사용할 수 있는 전화 번호를 구성 해야 합니다. 직접 라우팅을 사용 해야 하는 요구 사항은 Microsoft에서 전화 접속 전화 번호를 제공 하는 비 GCC 높음이나 비 DoD 조직에 제공 되는 오디오 회의 서비스와 다릅니다.

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>GCC High 및 DoD에 대 한 직접 라우팅을 사용 하 여 오디오 회의 배포

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a>1 단계: GCC High 또는 DoD 라이선스에 대 한 직접 라우팅이 있는 오디오 회의를 가져옵니다. 

GCC High 또는 DoD에서 오디오 회의를 사용 하려면 조직 및 조직의 사용자가 직접 라우팅 라이선스를 할당 한 오디오 회의를 거쳐야 합니다. 다음은 GCC High 또는 DoD에 대 한 직접 라우팅이 오디오 회의를 사용 하도록 설정 하는 데 필요한 라이선스입니다.

- GCC 최고: 사용자의 조직 및 오디오 회의-gcc 상위 라이선스에 대 한 오디오 회의-GCC 고용량 테 넌 트 라이선스입니다.

- DoD: 조직 및 오디오 회의용 사용자의 DoD 라이선스에 대 한 오디오 회의-DoD 테 넌 트 라이선스

서비스를 사용 하도록 설정 하려면 테 넌 트 라이선스 및 하나 이상의 사용자 라이선스가 필요 합니다. 테 넌 트 라이선스 또는 사용자 라이선스만 사용 하 여 서비스를 사용 하도록 설정할 수 없습니다. 테 넌 트 및 조직의 사용자에 대 한 서비스 라이선스를 가져오려면 계정 팀에 문의 하세요.

> [!IMPORTANT]
> 전화 접속 전화 번호가 설정 될 때까지 직접 라우팅이 있는 오디오 회의는 사용자가 활성화할 수 없습니다. 이 문서에 설명 된 대로 전화 접속 전화 번호를 설정할 때까지 사용자에 게 GCC High 또는 DoD 라이선스에 대 한 직접 라우팅이 있는 오디오 회의를 할당 하지 않는 것이 좋습니다.

### <a name="step-2-set-up-direct-routing"></a>2 단계: 직접 라우팅 설정

직접 라우팅을 설정 하려면 다음 문서를 참조 하세요.

- [직접 라우팅 계획](direct-routing-plan.md)

- [직접 라우팅 구성](direct-routing-configure.md)

> [!NOTE]
> 직접 라우팅을 설정할 때는이 두 문서에서 설명 하는 GCC High 또는 DoD 관련 Fqdn 및 포트를 사용 해야 합니다.

### <a name="step-3-set-up-dial-in-phone-numbers"></a>3 단계: 전화 접속 전화 번호 설정

전화 접속 전화 번호는 오디오 회의 브리지에 연결 된 전화 번호입니다. 이러한 번호는 참가자가 조직의 사용자가 예약한 모임에 참가 하는 데 사용 됩니다. 이러한 번호는 조직의 모임을 예약 하는 사용자와 "로컬 번호 찾기" 페이지의 모임 초대에도 포함 됩니다.

#### <a name="define-service-phone-numbers-in-your-tenant"></a>테 넌 트에서 서비스 전화 번호 정의

CsHybridTelephoneNumber PowerShell cmdlet을 사용 하 여 테 넌 트에서 직접 라우팅을 통해 오디오 회의 서비스에 대 한 통화를 라우팅하는 데 사용할 수 있는 서비스 전화 번호를 정의할 수 있습니다. 

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

예를 들면 다음과 같습니다.
  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a>조직의 오디오 회의 브리지에 서비스 전화 번호 할당

CsOnlineDialInConferencingServiceNumber PowerShell cmdlet을 사용 하 여 조직의 오디오 회의 브리지에 서비스 전화 번호를 할당할 수 있습니다.

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

CsOnlineDialInConferencingBridge를 사용 하 여 오디오 회의 브리지의 ID를 볼 수 있습니다. 예를 들면 다음과 같습니다.

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```

### <a name="step-4-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a>4 단계: 사용자에 게 GCC High 또는 DoD 라이선스에 대 한 직접 라우팅이 있는 오디오 회의 할당

사용자에 게 GCC High 또는 DoD 라이선스에 대 한 직접 라우팅이 있는 오디오 회의를 할당 하려면 [비즈니스용 Office 365에서 사용자에 게 라이선스 할당](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users)을 참조 하세요.

### <a name="step-5-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a>5 단계: (선택 사항) 팀의 오디오 회의 번호 목록 보기

조직의 오디오 회의 번호 목록을 보려면 [Microsoft 팀에서 오디오 회의 번호 목록 보기를 참조](see-a-list-of-audio-conferencing-numbers-in-teams.md) 하세요.

### <a name="step-6-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a>6 단계: (선택 사항) 사용자 조직의 오디오 회의 전화 접속 번호에 대 한 자동 전화 교환 언어 설정

조직의 오디오 회의 전화 접속 번호 언어를 변경 하려면 [Microsoft 팀에서 오디오 회의를 위한 자동 전화 교환 언어 설정을](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) 참조 하세요.

### <a name="step-7-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a>7 단계: (선택 사항) 조직의 오디오 회의 브리지에 대 한 설정 변경

조직의 오디오 회의 브리지 설정을 변경 하려면 [오디오 회의 브리지에 대 한 설정 변경을](change-the-settings-for-an-audio-conferencing-bridge.md) 참조 하세요.

### <a name="step-8-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a>8 단계: (선택 사항) 조직의 사용자에 대 한 모임 초대에 포함 된 전화 번호 설정

사용자의 모임 초대에 포함 되는 전화 번호 집합을 변경 하려면 [Microsoft 팀의 초대에 포함 된 전화 번호 설정을](set-the-phone-numbers-included-on-invites-in-teams.md) 참조 하세요.

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>GCC High 및 DoD에 대 한 직접 라우팅이 있는 오디오 회의에서는 오디오 회의 기능이 지원 되지 않습니다.

다음은 GCC High 및 DoD에 대 한 직접 라우팅이 오디오 회의에서 지원 되지 않는 오디오 회의 기능입니다.

- 이름 기록을 사용 하 여 입력 및 종료 알림 직접 라우팅이 있는 오디오 회의의 경우 입력 및 종료 알림이 모임에서 톤으로 재생 됩니다.

- 오디오 회의에 대 한 아웃 바운드 통화 제한 정책 아웃 바운드 통화를 제한 하는 사용자 수준 컨트롤은 직접 라우팅을 통해 라우팅되는 모임 전화 접속 통화에는 적용 되지 않습니다.

- 특정 모임 이끌이가 사용할 수 있는 무료 전화 번호를 사용 하지 않도록 설정 합니다. 무료 번호 사용을 조직의 모임에 참가 하도록 제한 하는 사용자 수준 컨트롤은 직접 라우팅을 통해 라우팅되는 통화에는 적용 되지 않습니다.

- 설정이 변경 될 때 알림 전자 메일을 사용자에 게 보내기 오디오 회의 알림 전자 메일은 GCC High 및 DoD에 대 한 직접 라우팅이 있는 오디오 회의에서 지원 되지 않습니다.
