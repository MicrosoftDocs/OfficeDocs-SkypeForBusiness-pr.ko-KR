---
title: 전화 번호 및 라이선스 변경
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: ''
description: 라이선스 변경이 전화 번호 관리에 미치는 영향을 알아봅니다.
ms.openlocfilehash: 58821f950baf68474a637a8d76acaab9a088f31e
ms.sourcegitcommit: f5d784df59a8010b390691bbb20c4ea66c46280b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/26/2022
ms.locfileid: "67005471"
---
# <a name="how-licensing-affects-phone-number-management"></a>라이선스가 전화 번호 관리에 미치는 영향

사용자에게 라이선스를 제거하고 할당하는 방법은 Microsoft Teams에서 PSTN(공중 전화망) 통화를 만들고 받는 사용자의 기능에 영향을 미칠 수 있습니다. 이 문서에서는 사용자가 PSTN 호출을 수행하고 받을 수 있는 기능이 영향을 받지 않도록 라이선스 변경 내용을 관리하는 방법을 설명합니다.

전화 번호 관리에 대한 일반적인 내용은 [조직의 전화 번호 관리를 참조하세요](manage-phone-numbers-landing-page.md). Teams 추가 기능 라이선스에 대한 일반적인 내용은 [Microsoft Teams 추가 기능 라이선스를 참조하세요](/teams-add-on-licensing/microsoft-teams-add-on-licensing.md).



## <a name="remove-a-license"></a>라이선스 제거

할당된 전화 번호가 있는 사용자가 있고 하나 이상의 필수 구성 요소 라이선스를 제거하는 경우 라이선스를 제거하면 사용자의 전화 번호도 할당 취소됩니다. 할당된 전화 번호가 없으면 Microsoft Teams에서 PSTN 통화를 하고 받을 수 있는 사용자의 기능이 영향을 받습니다.

사용자의 [PSTN 연결 옵션](pstn-connectivity.md)에 따라 라이선스를 제거하면 전화 통신 매개 변수에 다음과 같은 영향을 미칩니다.

- **통화 플랜 전화 번호가 있는 사용자로부터 Microsoft 365 통화 플랜 라이선스를 제거** 하면 다음이 수행됩니다.
  - OnPremLineUri의 모든 값을 LineUri에 복사
  - EnterpriseVoiceEnabled를 False로 설정
  - 전화 번호 데이터베이스에서 전화 번호 할당 상태를 할당되지 않음으로 설정


- **운영자 연결 전화 번호가 있는 사용자로부터 Microsoft 365 Phone System 라이선스를 제거** 하면 다음이 수행됩니다.
  - LineUri 지우기
  - EnterpriseVoiceEnabled를 False로 설정
  - 전화 번호 데이터베이스에서 전화 번호의 할당 상태를 할당되지 않음으로 설정


- **직접 라우팅 전화 번호가 있는 사용자로부터 Microsoft 365 Phone System 라이선스를 제거** 하면 다음이 수행됩니다.
  - LineUri 지우기
  - EnterpriseVoiceEnabled를 False로 설정
  - 전화 번호 데이터베이스에서 전화 번호 제거


## <a name="change-a-license"></a>라이선스 변경

필수 구성 요소 라이선스 중 하나가 포함된 사용자에 대한 라이선스를 변경해야 하는 경우 라이선스 변경 내용이 동시에 적용되고 저장되었는지 확인해야 합니다. 이 방법을 사용하면 사용자가 할당된 전화 번호를 유지하고 Microsoft Teams에서 PSTN 통화를 계속 만들고 받을 수 있습니다. 

예를 들어 현재 Microsoft 365 E3 라이선스가 있는 사용자에게 Microsoft 365 E5 라이선스를 할당하려는 경우를 가정합니다. 

- Teams 관리 센터를 사용하는 경우 사용자 세부 정보 **라이선스 및 앱** 탭에서 **변경 내용 저장** 을 클릭하기 전에 이전 라이선스가 제거되고 새 라이선스가 추가되었는지 확인합니다. 

- PowerShell cmdlet, [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense) 또는 [Set-MgUserLicense](/powershell/module/microsoft.graph.users.actions/set-mguserlicense)를 사용하는 경우 cmdlet을 한 번 실행하고 -AddLicenses 및 -RemoveLicenses 매개 변수를 모두 사용합니다.

(이전 라이선스를 제거하고 변경 사항을 저장한 다음 새 라이선스를 추가하고 변경 사항을 저장하면 전화 번호가 할당되지 않고 사용자가 Microsoft Teams에서 PSTN 통화를 만들고 받을 수 있는 기능이 손실될 수 있습니다. 새 라이선스를 할당한 후에는 사용자에게 전화 번호를 다시 할당해야 합니다.)










