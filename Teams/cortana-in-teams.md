---
title: Microsoft 팀의 Cortana 음성 도우미
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: 팀에서 Cortana 음성 도우미를 사용 하는 방법 알아보기
localization_priority: Normal
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f820bf6c44eae2cfbdb13a683d017be2f93d6756
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255552"
---
# <a name="cortana-voice-assistance-in-teams"></a>팀의 Cortana 음성 지원

> [!Note]
> Cortana 음성 지원은 미국 사용자 용 Microsoft 팀 iOS 및 Android 모바일 앱에서 지원 됩니다. 현재 GCC, GCC-High, DoD, .EDU 테 넌 트에는 사용할 수 없습니다. 이후 릴리스의 일부로 추가 언어 및 지역으로 확장이 수행 됩니다.

팀 모바일 앱의 Cortana 음성 지원은 Microsoft 365 Enterprise 사용자가 음성 자연어를 사용 하 여 통신, 공동 작업 및 모임 관련 작업을 간소화할 수 있도록 합니다. 사용자는 팀 모바일 앱의 오른쪽 위에 있는 마이크 단추를 클릭 하 여 Cortana에 말할 수 있습니다. 이동 중에 팀과 빠르게 연결 하기 위해 사용자는 &#8220;call Megan&#8221; 또는 &#8220;다음 모임&#8221;에 메시지를 보낼 수 있습니다. 또한 사용자는 다음 모임&#8221; 참가 &#8220;하 여 모임에 참가 하 고, 음성 도우미를 사용 하 여 파일을 공유 하 고, 일정을 확인할 수 있습니다. 이러한 음성 지원 환경은 [OST (온라인 서비스 사용 약관)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)에 반영 된 Office 365의 개인 정보 취급, 보안 및 준수 약속을 완벽 하 게 준수 하는 [Cortana 엔터프라이즈 등급 서비스](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) 를 사용 하 여 제공 됩니다.

이 이미지는 모바일 장치에서 Cortana에 채팅을 전송 하는 방법을 보여 줍니다.

![이미지는 Cortana 채팅 세션을 보여 주는 모바일 화면 순서를 표시 합니다.](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a>관리 제어 및 제한 사항

팀의 Cortana 음성 지원은 OST (온라인 서비스 사용 약관)에 반영 된 Office 365 엔터프라이즈 수준의 개인 정보, 보안 및 준수 약속을 완벽 하 게 준수 하는 서비스를 사용 하 여 제공 됩니다. 이 기능은 테 넌 트에 대해 기본적으로 사용 하도록 설정 됩니다.

테 넌 트 관리자는 정책 (TeamsCortanaPolicy)을 사용 하 여 팀에서 Cortana 음성 지원을 사용할 수 있는 테 넌 트의 사용자를 제어할 수 있습니다. 이 정책은 사용자 계정 수준 또는 테 넌 트 수준 중 하나로 설정할 수 있습니다. 관리자는이 정책 컨트롤 내에서 CortanaVoiceInvocationMode 필드를 사용 하 여 Cortana를 사용 하지 않도록 설정할지, 푸시 단추 호출을 사용 하거나, 절전 모드 종료 단어를 지원 하도록 (이 기능을 지 원하는 장치에 해당)를 결정할 수 있습니다.

관리자는 다음 PowerShell cmdlet을 사용 하 여이 정책을 관리할 수 있습니다 (현재 Microsoft 팀 관리 센터에서는 정책을 사용할 수 없음).

- [새로운 CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [부여-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [제거-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

예를 들어 아래 명령은 Microsoft 팀에서 Cortana 음성 도우미를 사용할 수 없도록 설정 된 이름 &#8220;EmployeeCortanaPolicy&#8221;를 사용 하 여 새 정책을 만듭니다.  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

이 예제에서는 이름 &#8220;EmployeeCortanaPolicy&#8221;를 사용 하 여 기존 정책을 업데이트 하 고, 푸시 단추 호출만 있는 Microsoft 팀에서 Cortana 음성 도우미를 사용 하도록 설정 하는 방법을 보여 줍니다. 사용자는 팀에서 Cortana 마이크 단추를 탭 하 여 Cortana를 호출할 수 있습니다. 깨우기 (&#8220;안녕 코타&#8221;) 호출은 사용할 수 없게 됩니다.  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

이 예제에서는 푸시 단추와 깨우기 단어 호출을 모두 사용 하 여 정책을 업데이트 하 고 Cortana 음성 도우미를 사용 하는 방법을 보여 줍니다.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

> [!Note]
> 미국에서 Microsoft 365 Enterprise 사용자를 처음 릴리스할 때 팀 모바일 앱은 깨우기 단어 활성화를 지원 하지 않지만 향후 지원 됩니다.

## <a name="user-control"></a>사용자 제어

개별 사용자는 마이크 단추를 클릭 하 여 팀 모바일 앱에서 Cortana 음성 지원을 시도할 수 있습니다. 팀 모바일 앱의 설정을 사용 하 여 디바이스에 대해 팀의 Cortana를 사용할 수 있는지 여부를 제어할 수도 있습니다.

1. 팀 모바일 앱을 엽니다.

2. **설정**으로 이동 합니다.

3. **Cortana**를 선택 합니다.

4. 장치에서 Cortana 음성 지원이 필요한 지 여부에 따라 설정/ **해제** **로 이동** 합니다.
