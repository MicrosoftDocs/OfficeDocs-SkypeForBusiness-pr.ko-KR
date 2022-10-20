---
title: Microsoft Teams에서 통화 대기 및 검색
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.callparkpolicies.overview
- seo-marvel-apr2020
description: 통화 대기를 사용하고 검색하여 Microsoft Teams에서 통화를 보류하는 방법에 대해 알아봅니다.
ms.openlocfilehash: c541f92b265d5794df4513eb0cda5d2ff2969f20
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614241"
---
# <a name="configure-call-park-and-retrieve"></a>통화 대기 구성 및 검색

통화 대기 및 검색을 통해 사용자가 통화를 보류할 수 있습니다. 호출이 대기되면 서비스는 호출 검색을 위한 고유한 코드를 생성합니다. 전화를 대기한 사용자 또는 다른 사용자가 지원되는 앱 또는 디바이스에서 해당 코드를 사용하여 통화를 검색할 수 있습니다. (자세한 내용은 [Teams에서 통화 대기를 참조하세요](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).)

콜파크 사용에 대한 일반적인 시나리오는 다음과 같습니다.

- 접수원은 공장에서 일하는 사람을 위해 전화를 주차합니다. 그러면 접수원은 공용 주소 시스템을 통해 통화 및 코드 번호를 알려 줍니다. 그런 다음 통화 대상 사용자는 공장 바닥에서 Teams 전화를 선택하고 코드를 입력하여 통화를 검색할 수 있습니다.

- 디바이스 배터리의 전원이 부족하여 사용자가 모바일 디바이스에서 통화를 대기합니다. 그런 다음, 사용자가 코드를 입력하여 Teams 책상 전화에서 통화를 검색할 수 있습니다.

- 지원 담당자가 고객 전화를 대기하고 Teams 채널에 발표를 보내 전문가가 통화를 검색하고 고객을 도와줍니다. 전문가가 Teams 클라이언트에 코드를 입력하여 통화를 검색합니다.

통화를 대기하고 검색하려면 사용자가 Enterprise Voice 사용자여야 하며 통화 대기 정책에 포함되어야 합니다.

기본적으로 호출 픽업 번호의 범위는 10-99입니다. 10-9999 사이의 고유한 사용자 지정 범위를 만들 수도 있습니다. 첫 번째 주차된 호출은 범위 시작의 픽업 코드(예: 10)로 렌더링됩니다. 다음 주차된 호출은 1씩 증가된 픽업 코드로 렌더링됩니다. 즉, 11 등, 범위의 끝까지 픽업 코드로 렌더링됩니다. 그 후 렌더링된 픽업 코드는 범위의 시작부터 다시 시작됩니다. 

시간 제한을 대기된 통화가 선택되지 않은 경우 다시 울리기 전에 대기할 시간(초)으로 지정할 수 있습니다. 허용되는 범위는 120-1800초이고 기본값은 300초입니다.

통화 대기를 구성하고 검색하려면 Teams 관리자여야 합니다. 기본적으로 사용하지 않도록 설정됩니다. 통화 대기 정책을 사용하여 사용자에 대해 사용하도록 설정하고 사용자 그룹을 만들 수 있습니다. 사용자 집합에 동일한 정책을 적용하는 경우 사용자 간에 통화를 대기하고 검색할 수 있습니다.

> [!NOTE]
> 통화 대기 및 검색은 [Teams 전용 배포 모드](teams-and-skypeforbusiness-coexistence-and-interoperability.md)에서만 사용할 수 있습니다. 비즈니스용 Skype IP 휴대폰에서는 지원되지 않습니다.

Teams 관리 센터를 사용하거나 PowerShell을 사용하여 통화 대기를 구성하고 검색할 수 있습니다.

## <a name="use-teams-admin-center"></a>Teams 관리 센터 사용

새 통화 대기 정책 인스턴스를 만들려면 다음을 수행합니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **음성** > **통화 대기 정책** 으로 이동합니다.

2. **정책 관리** 탭에서 **추가** 를 클릭합니다.

3. 정책 이름을 지정한 다음 **통화 대기 허용** 을 켜기로 전환 **합니다**.

4. 필요에 따라 범위를 변경하고 시간 제한을 주차합니다.

5. **저장** 을 선택합니다.

목록에서 정책을 선택하고 편집을 클릭하여 정책을 **편집** 할 수 있습니다.

정책이 작동하려면 사용자에게 할당해야 합니다. [사용자에게 개별적으로 정책을 할당](assign-policies-users-and-groups.md)하거나 그룹에 할당할 수 있습니다.

그룹에 통화 대기 정책을 할당하려면 다음을 수행합니다.

1. **통화 대기 정책** 페이지의 **그룹 정책 할당** 탭에서 **그룹 추가** 를 클릭합니다.

2. 사용할 그룹을 검색한 다음 **추가** 를 클릭합니다.

3. 다른 그룹 할당과 비교하여 순위를 선택합니다.

4. **정책 선택에서** 이 그룹을 할당할 정책을 선택합니다.

5. **적용** 을 선택합니다.

## <a name="use-powershell"></a>PowerShell 사용

PowerShell을 사용하여 통화 대기를 관리하고 정책을 검색하려면 다음 Teams PowerShell 모듈 cmdlet을 사용합니다.

- [New-CsTeamsCallParkPolicy](/powershell/module/skype/new-csteamscallparkpolicy)

- [Set-CsTeamsCallParkPolicy](/powershell/module/skype/set-csteamscallparkpolicy)

- [Get-CsTeamsCallParkPolicy](/powershell/module/skype/get-csteamscallparkpolicy)

- [Remove-CsTeamsCallParkPolicy](/powershell/module/skype/remove-csteamscallparkpolicy)

- [Grant-CsTeamsCallParkPolicy](/powershell/module/skype/grant-csteamscallparkpolicy)

### <a name="examples"></a>예제

#### <a name="new-custom-call-park-policy"></a>새 사용자 지정 통화 대기 정책

다음 예제에서는 500에서 1500 사이의 픽업 번호를 생성하고 주차된 호출이 응답하지 않으면 600초 후에 파커를 다시 울리는 사용자 지정 통화 공원 정책을 만듭니다.

```powershell
PS C:\> New-CsTeamsCallParkPolicy -Identity "SalesPolicy" -AllowCallPark $true -PickupRangeStart 500 -PickupRangeEnd 1500 -ParkTimeoutSeconds 600
```

#### <a name="change-a-call-park-policy"></a>통화 대기 정책 변경

다음 예제에서는 통화 대기 정책을 사용하지 않도록 설정합니다.

```powershell
PS C:\> Set-CsTeamsCallParkPolicy -Identity "SalesPolicy" -AllowCallPark $false
```

#### <a name="grant-a-call-park-policy-to-a-user"></a>사용자에게 통화 대기 정책 부여

다음 예제에서는 사용자에게 통화 대기 정책을 부여합니다.

```powershell
PS C:\> Grant-CsTeamsCallParkPolicy -PolicyName "SalesPolicy" -Identity Ken.Myer@contoso.com
```

#### <a name="remove-a-call-park-policy"></a>통화 대기 정책 제거

다음 예제에서는 통화 대기 정책을 제거합니다.

```powershell
PS C:\> Remove-CsTeamsCallParkPolicy -Identity "SalesPolicy"
```

## <a name="related-topics"></a>관련 주제

[Teams에서 통화 대기](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[Teams에서 사용자에게 정책 할당](policy-assignment-overview.md)

