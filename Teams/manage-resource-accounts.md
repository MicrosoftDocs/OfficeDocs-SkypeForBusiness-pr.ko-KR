---
title: Teams에서 리소스 계정 관리
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
- seo-marvel-apr2020
description: 이 문서에서는 Microsoft Teams에서 리소스 계정을 만들고, 편집하고, 관리하는 방법을 배웠습니다.
ms.openlocfilehash: 2a043b608dfe311003dea26acc8a0c236460fad5
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031024"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Microsoft Teams에서 리소스 계정 관리

리소스 계정은 Azure AD에서 사용할 수 없는 사용자 개체로, 일반적으로 리소스를 나타내는 데 사용할 수 있습니다. 예를 들어 Exchange에서 리소스 계정을 사용하여 회의실을 나타내고 전화 번호와 일정을 사용할 수 있습니다. 리소스 계정은 비즈니스용 Skype Server 2019를 사용하여 Microsoft 365 또는 프레미스에 있을 수 있습니다.

Microsoft Teams에서 각 자동 전화 회의 또는 통화 큐에 리소스 계정이 필요합니다. 리소스 계정에 서비스 전화 번호가 할당될 수도 있습니다. 자동 전화 걸기 및 통화 큐에 전화 번호를 지정하여 Teams 외부의 발신자가 자동 전화 걸기 또는 통화 큐에 도달할 수 있도록 하는 방식입니다.

이 문서에서는 리소스 계정을 만들고 자동 전화 회의 및 통화 큐에 사용할 수 있도록 준비하는 방법을 다 제공합니다.

이 문서의 절차를 시작하기 전에 다음을 완료해야 합니다.

- [가상 사용자 라이선스 얻기](#obtain-virtual-user-licenses)
- [서비스 번호 얻기](#obtain-service-numbers)

### <a name="obtain-virtual-user-licenses"></a>가상 사용자 라이선스 얻기

각 리소스 계정에는 자동 전화 회의 및 통화 큐를 사용하려면 라이선스가 필요합니다. 무료 *Microsoft 365 Phone System - 가상 사용자 라이선스를 사용할 수* 있습니다. 이러한 라이선스를 얻은 경우 [가상 사용자 라이선스를 참조합니다.](teams-add-on-licensing/virtual-user.md)

이 문서의 후반부에서 리소스 계정에 라이선스를 할당하는 방법을 다합니다.

가상 사용자 라이선스를 다운로드하려면 Microsoft 365 관리 센터에서 청구 구매 서비스 추가 기능 구독으로 이동하여 끝까지 스크롤합니다. 전화 시스템 - 가상 사용자 라이선스가  >    >   표시됩니다.  지금 **구입을 선택합니다.** 비용은 0이지만 라이선스를 획득하려면 다음 단계를 따라야 합니다.

### <a name="obtain-service-numbers"></a>서비스 번호 얻기

서비스 번호는 자동 전화 걸기 및 통화 큐에 선택 사항이지만 발신자가 자동 전화 걸기 및 통화 큐 구성에 도달하려면 서비스 번호가 하나 이상 필요합니다. 서비스 번호로 직접 연결하려는 자동 전화 연결 또는 통화 큐의 경우 연결된 서비스 번호가 있는 리소스 계정이 있어야 합니다.

리소스 계정은 무료 또는 무료 서비스 번호를 사용할 수 있습니다. 다른 운송업체에서 새 번호 또는 포트 기존 번호를 요청할 수 있습니다.

새 서비스 번호를 얻은 경우 서비스 전화 번호 [보기를 참조합니다.](getting-service-phone-numbers.md)

다른 통신 사업자에서 번호를 포터를 이동하는 경우 Teams로 전화 [번호 이전을 참조합니다.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)

## <a name="create-a-resource-account"></a>리소스 계정 만들기

Teams 관리 센터에서 리소스 계정을 만들 수 있습니다.

![리소스 계정 사용자 인터페이스 추가 스크린샷](media/resource-account-add.png)

1. Teams 관리 센터에서 **전체 설정을** 확장한 다음 리소스 **계정을 클릭합니다.**

2. **추가** 를 클릭합니다.

3. 리소스 계정 **추가 창에서** 표시 **이름,** 사용자 이름 및 리소스 계정 유형을 **입력합니다.**  리소스 계정 유형은 이  리소스 계정을 사용하는 방법에 따라 자동 전화 걸기 또는 통화 큐일 수 있습니다.

4. **저장** 을 클릭합니다.

![리소스 계정 목록의 스크린샷](media/resource-accounts-page.png)

## <a name="assign-a-license"></a>라이선스 할당

각 리소스 계정에 대해 *Microsoft 365* 전화 시스템 ( 가상 사용자 라이선스 또는 전화 시스템 라이선스)을 *할당해야* 합니다.

![Microsoft 365 관리 센터의 라이선스 사용자 인터페이스 할당 스크린샷](media/resource-account-assign-virtual-user-license.png)

1. Microsoft 365 관리 센터에서 라이선스를 할당하려는 리소스 계정을 클릭합니다.

2. 라이선스 **및** 앱 탭의 **라이선스** **아래에서 Microsoft 365 Phone System - Virtual User를 선택합니다.**

3. 변경 **내용 저장을 클릭합니다.**

## <a name="assign-a-service-number"></a>서비스 번호 할당

서비스 번호가 필요한 자동 전화 번호 또는 통화 큐에서 리소스 계정을 사용하려면 리소스 계정에 번호를 할당합니다.

![서비스 번호 사용자 인터페이스 할당 스크린샷](media/resource-account-assign-phone-number.png)

1. Teams 관리 센터의 리소스  계정 페이지에서 서비스 번호를 할당할 리소스 계정을 선택한 다음 **할당/할당을 클릭합니다.**

2. 전화 번호 **유형 드롭다운에서** 사용할 번호 유형을 선택 합니다.

3. 할당된 **전화 번호** 상자에서 사용할 번호를 검색하고 추가를 **클릭합니다.**

4. **저장** 을 클릭합니다.


리소스 계정에 직접 라우팅 또는 하이브리드 번호를 할당하려면 PowerShell을 사용해야 합니다.

`Set-CsOnlineApplicationInstance -Identity aa-contoso_main@contoso64.net -OnpremPhoneNumber +19295550150`

## <a name="next-steps"></a>다음 단계

리소스 계정 설정 및 필요한 경우 서비스 번호 할당을 완료하면 자동 전화 회의 또는 통화 큐에서 리소스 계정을 사용할 준비가 된 것입니다.

다음 참조를 참조합니다.

 - [클라우드 자동 참석자](create-a-phone-system-auto-attendant.md)

 - [클라우드 호출 큐](create-a-phone-system-call-queue.md)

편집 옵션을 사용하여  리소스 계정 표시 이름 및 **리소스** 계정 유형을 **편집할 수** 있습니다. 완료되면 **저장을** 클릭합니다.

## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a>가상 사용자 라이선스를 사용하여 기존 리소스 계정 변경

기존 리소스 계정의 라이선스를 전화 시스템 라이선스에서 가상 사용자 라이선스로 전환하려면 무료 가상 사용자 라이선스를 획득한 다음 Microsoft 365 관리 센터의 단계에 따라 사용자를 다른 구독으로 이동해야 [합니다.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription) 

> [!WARNING]
> 항상 전체 전화 시스템 라이선스를 제거하고 동일한 라이선스 활동에서 가상 사용자 라이선스를 할당합니다. 이전 라이선스를 제거하고, 계정 변경 내용을 저장하고, 새 라이선스를 추가한 다음, 계정 설정을 다시 저장하면 리소스 계정이 더 이상 예상대로 작동하지 않을 수 있습니다. 이 경우 가상 사용자 라이선스에 대한 새 리소스 계정을 만들고 손상된 리소스 계정을 제거하는 것이 좋습니다.

## <a name="skype-for-business-server-2019"></a>비즈니스용 Skype Server 2019

클라우드 통화 큐 및 클라우드 자동 전화 걸기에서 사용할 수 있는 비즈니스용 Skype Server [](/SkypeforBusiness/hybrid/plan-call-queue) 2019에 있는 리소스 계정의 경우 클라우드 통화 큐 계획 또는 클라우드 자동 전화 걸기 계획을 참조하세요. [](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant) 하이브리드 구현(직접 라우팅에 있는 숫자)은 비즈니스용 Skype Server 2019 서버에서 [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint) cmdlet을 사용하여 구성됩니다.

애플리케이션 인스턴스를 만드는 동안 사용해야 하는 애플리케이션 ID는 다음입니다.

- **자동 전화 교환:** ce933385-9390-45d1-9512-c8d228074e07
- **호출 큐:** 11cd3e2e-fccb-42ad-ad00-878b93575e07

> [!NOTE]
> 비즈니스용 Skype Server 2019 사용자가 통화 큐 또는 자동 전화 걸기 기능을 검색할 수 있도록 하려는 경우 온라인 리소스 계정이 Active Directory와 동기화되지 않는 비즈니스용 Skype Server 2019에서 리소스 계정을 만들어야 합니다. sipfederationtls에 대한 DNS SRV 레코드가 비즈니스용 Skype Server 2019로 확인되면 SfB 관리 셸을 사용하여 비즈니스용 Skype Server 2019에서 리소스 계정을 생성하고 Azure AD에 동기화해야 합니다. 

비즈니스용 Skype Server와 하이브리드인 구현의 경우:

   [클라우드 자동 전화 교환 계획](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [클라우드 통화 큐 계획](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [프레미스 리소스 계정 구성](/SkypeForBusiness/hybrid/configure-onprem-ra)


## <a name="delete-a-resource-account"></a>리소스 계정 삭제

서비스 번호가 보류 중인 모드에서 빨라지지 않도록 삭제하기 전에 리소스 계정에서 전화 번호를 연결하지 않도록 합니다.

그런 다음 Microsoft 365 관리 센터의 사용자 탭에서 리소스 계정을 삭제할 수 있습니다.

리소스 계정에서 직접 라우팅 전화 번호를 연결하지하려면 다음 cmdlet을 사용하세요.

```powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```
