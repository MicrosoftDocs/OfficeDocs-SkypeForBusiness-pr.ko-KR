---
title: Teams에서 리소스 계정 관리
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
- seo-marvel-apr2020
description: 이 문서에서는 Microsoft Teams에서 리소스 계정을 만들고, 편집하고, 관리하는 방법을 알아봅니다.
ms.openlocfilehash: ac3eb35894fa765dc44f46fcb489399b06adfa74
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2022
ms.locfileid: "68584029"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Microsoft Teams에서 리소스 계정 관리

[!INCLUDE [set-up-resource-account-steps](./includes/set-up-resource-account-steps.md)]

## <a name="next-steps"></a>다음 단계

리소스 계정 설정을 완료하고 필요한 경우 서비스 번호를 할당하면 자동 전화 교환 또는 통화 큐에서 리소스 계정을 사용할 준비가 된 것입니다.

자세한 내용은 다음 참조를 참조하세요.

- [클라우드 자동 전화 교환](create-a-phone-system-auto-attendant.md)
- [클라우드 호출 큐](create-a-phone-system-call-queue.md)

편집 옵션을 사용하여 리소스 계정 **표시 이름** 및 **리소스 계정** 유형을 **편집** 할 수 있습니다. 완료되면 **저장** 을 클릭합니다.

## <a name="change-an-existing-resource-account-to-use-a-teams-phone-resource-account-license"></a>Teams 전화 리소스 계정 라이선스를 사용하도록 기존 리소스 계정 변경

기존 리소스 계정의 라이선스를 **Teams 전화 표준 요금제** 라이선스에서 **Microsoft Teams 전화 Resource Account** 라이선스로 전환하려는 경우 무료 **Teams 전화 리소스 계정** 라이선스를 획득한 다음 Microsoft 365 관리 센터 단계를 [따라야 합니다. 사용자를 다른 구독으로 이동합니다](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).

> [!WARNING]
> 항상 전체 Teams 전화 표준 요금제 라이선스를 제거하고 동일한 라이선스 작업에서 **Microsoft Teams 전화 Resource Account** 라이선스를 할당합니다. 이전 라이선스를 제거하고 계정 변경 내용을 저장하고 새 라이선스를 추가한 다음 계정 설정을 다시 저장하면 리소스 계정이 더 이상 예상대로 작동하지 않을 수 있습니다. 이 경우 Microsoft Teams 전화 리소스 계정 라이선스에 대한 새 **리소스 계정을** 만들고 손상된 리소스 계정을 제거하는 것이 좋습니다.

## <a name="skype-for-business-server-2019"></a>비즈니스용 Skype 서버 2019

클라우드 통화 큐 및 클라우드 자동 전화 교환과 함께 사용할 수 있는 비즈니스용 Skype Server 2019에 있는 리소스 계정은 [클라우드 통화 큐 계획](/SkypeforBusiness/hybrid/plan-call-queue) 또는 [클라우드 자동 전화 교환 계획을 참조하세요](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant). 하이브리드 구현(직접 라우팅에 포함되는 숫자)은 온-프레미스 비즈니스용 Skype 서버 2019 서버의 [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint) cmdlet을 사용하여 구성됩니다.

애플리케이션 인스턴스를 만드는 동안 사용해야 하는 애플리케이션 ID는 다음과 같습니다.

- **자동 전화 교환:** ce933385-9390-45d1-9512-c8d228074e07
- **통화 큐:** 11cd3e2e-fccb-42ad-ad00-878b93575e07

> [!NOTE]
> 비즈니스용 Skype Server 2019 사용자가 통화 큐 또는 자동 전화 교환을 검색하도록 하려면 온라인 리소스 계정이 Active Directory로 동기화되지 않으므로 비즈니스용 Skype 서버 2019에서 리소스 계정을 만들어야 합니다. sipfederationtls에 대한 DNS SRV 레코드가 비즈니스용 Skype 서버 2019로 확인되면 SfB 관리 셸을 사용하여 비즈니스용 Skype Server 2019에서 리소스 계정을 만들고 Azure AD 동기화 **해야 합니다**.

비즈니스용 Skype 서버 하이브리드 구현의 경우:

   [클라우드 자동 전화 교환 계획](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

   [클라우드 통화 큐 계획](/SkypeforBusiness/hybrid/plan-call-queue)

   [온-프레미스 리소스 계정 구성](/SkypeForBusiness/hybrid/configure-onprem-ra)

## <a name="delete-a-resource-account"></a>리소스 계정 삭제

서비스 번호가 보류 중인 모드에서 중단되는 것을 방지하려면 삭제하기 전에 리소스 계정에서 전화 번호를 분리해야 합니다.

이렇게 하면 Microsoft 365 관리 센터 사용자 탭에서 리소스 계정을 삭제할 수 있습니다.

리소스 계정에서 직접 라우팅 전화 번호를 연결 해제하려면 다음 cmdlet을 사용합니다.

```powershell
Remove-CsPhoneNumberAssignment -Identity <Resource Account Object ID> -PhoneNumber <assigned phone number> -PhoneNumberType DirectRouting
```
