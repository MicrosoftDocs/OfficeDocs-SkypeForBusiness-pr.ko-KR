---
title: 비즈니스용 Skype 클라이언트에서 스마트 연락처 목록 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: '요약: 비즈니스용 Skype 클라이언트에서 Smart contacts list 기능을 설정 하는 방법을 알아봅니다.'
ms.openlocfilehash: d99008cde28b834f77a2935ffd7882162aa05e95
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776693"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a>비즈니스용 Skype 클라이언트에서 스마트 연락처 목록 구성

**요약:** 비즈니스용 Skype 클라이언트에서 Smart contacts list 기능을 설정 하는 방법을 알아봅니다.

스마트 연락처 목록 기능을 사용 하면 최종 사용자에 게 연락처 목록을 자동으로 채울 수 있습니다. 처음 비즈니스용 Skype를 사용 하면 사용자가 자신의 관리자 및 다른 사용자를 팀에서 자동으로 볼 수 있습니다. 이 기능은 Microsoft 365 및 Office 365 사용자에 대해 기본적으로 설정 되지만 클라이언트 정책 설정을 구성 하 여 온-프레미스 사용자에 대해이 기능을 명시적으로 사용 하도록 설정 해야 합니다.

이 기능을 구성할 때는 다음 사항에 유의 하세요.

- 사용자가 최대 13 명까지 다음 순서 대로 Smart contacts 목록에 자동으로 추가 됩니다.

  1. 관리자

  2. 사전순으로 지시

  3. 사전순으로 피어

- 사용자가 처음 로그인 할 때 내 그룹 이라는 새 그룹이 만들어집니다. 관리자 필드에 입력 한 사용자 별칭에 따라 사용자의 AD 그룹 관계에 있는 사용자로 그룹이 자동으로 채워집니다. AD 그룹 구성원을 변경 해도 처음에는 그룹에 대 한 업데이트를 수행 하지 않습니다. 사용자가 연락처 또는 그룹을 삭제 하면 해당 대화 상대 또는 그룹도 다시 만들어지지 않습니다. 

- 자동 태그 지정이 설정 된 경우에는 현재 상태 변경에 대 한 태그를 목록의 대화 상대에 게 표시 합니다. 자동 태그 지정은 기본적으로 설정 되어 있지만 해제 하도록 선택할 수 있습니다. 

- 그룹의 모든 새 사용자에 게 대화 상대 목록에 추가 되었음을 알리는 메시지가 표시 됩니다. 사용자는 자신의 내 그룹 또는 선택한 다른 그룹에 새 구성원을 수동으로 추가할 수 있습니다.

- 이 기능은 처음 로그인 한 사용자에 대해서만 작동 합니다. 사용자가 모바일 장치 또는 Mac과 같은 모든 장치에서 이전에 로그인 한 경우--해당 사용자에 게 해당 기능이 사용 하도록 설정 되어 있지 않은 것입니다.

## <a name="configure-smart-contacts-list"></a>스마트 연락처 목록 구성

사용자에 대해 스마트 연락처 목록 기능을 사용 하도록 설정 하려면 다음 단계를 수행 해야 합니다. 

- 새 CsClientPolicy 항목을 만들고 전역 클라이언트 정책에 추가 합니다. 

- 주소록 검색이 웹 검색 전용으로 구성 되어 있는지 확인 합니다.

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a>스마트 연락처 목록을 사용 하도록 설정 하는 정책 항목 만들기

정책 항목을 만들어 Smart contacts 목록 기능을 사용 하도록 설정 하려면 다음과 같이 EnableClientAutoPopulateWithTeam 옵션을 사용 하 여 [새-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) cmdlet을 사용 합니다.

```powershell
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

다음으로, [설정-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet을 사용 하 여 변경 내용을 글로벌 정책에 다음과 같이 기록 합니다.

```powershell
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

다음과 같이 자동 태그 지정 기능을 해제 하는 정책을 만들 수도 있습니다.

```powershell
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

또한 해당 정책에 대 한 AddressBookAvailability 매개 변수도 WebSearchOnly로 설정 해야 합니다. 자세한 내용은 [설정-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps)를 참조 하십시오. 

### <a name="troubleshoot"></a>문제 해결

Smart contacts 목록이 정상적으로 작동 하지 않는 경우 다음을 확인 합니다.

- 구성의 유효성을 검사 합니다. 

- AD 조직 정보가 채워졌는지 확인 합니다.

- 추가 분석을 위해 새 사용자에 게 비즈니스용 Skype 클라이언트 로그를 수집 합니다.

- 비즈니스용 Skype 클라이언트 UI가 주소록에 연결할 수 없다는 메시지를 표시 하지 않는지 확인 합니다. 주소록 연결을 확인 하려면 비즈니스용 Skype 클라이언트 검색 표시줄에서 사용자 검색을 수행 합니다.

- AD DS 복제 문제로 인해 사용자가 비즈니스용 Skype에 처음 로그인 할 때 연락처가 확인 되지 않을 수 있습니다.


