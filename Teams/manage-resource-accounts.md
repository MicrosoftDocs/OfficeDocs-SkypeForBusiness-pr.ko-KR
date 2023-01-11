---
title: Teams에서 리소스 계정 관리
author: DaniEASmith
ms.author: danismith
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
ms.openlocfilehash: 2bc0642f20341b9818b1c407fa0294127ee44d6a
ms.sourcegitcommit: ae687f530d5505b96df7cb7ef4da3a36bd9afd29
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2023
ms.locfileid: "69763579"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Microsoft Teams에서 리소스 계정 관리

[!INCLUDE [set-up-resource-account-steps](./includes/set-up-resource-account-steps.md)]

## <a name="next-steps"></a>다음 단계

리소스 계정 설정을 완료하고 필요한 경우 전화 번호를 할당하면 자동 전화 교환 또는 통화 큐와 함께 리소스 계정을 사용할 준비가 된 것입니다.

자세한 내용은 다음 참조를 참조하세요.

- [클라우드 자동 전화 교환](create-a-phone-system-auto-attendant.md)
- [클라우드 호출 큐](create-a-phone-system-call-queue.md)

편집 옵션을 사용하여 리소스 계정 **표시 이름** 및 **리소스 계정** 유형을 **편집** 할 수 있습니다. 완료되면 **저장** 을 선택합니다.

## <a name="change-an-existing-resource-account-to-use-a-microsoft-teams-phone-resource-account-license"></a>Microsoft Teams 전화 리소스 계정 라이선스를 사용하도록 기존 리소스 계정 변경

기존 리소스 계정의 라이선스를 **Teams 전화 표준 요금제** 라이선스에서 **Microsoft Teams 전화 Resource Account** 라이선스로 전환하려면 **Microsoft Teams 전화 Resource Account** 라이선스를 취득한 다음 다음의 단계를 따라야 합니다. 사용자를 [다른 구독으로 이동하는 Microsoft 365 관리 센터](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).

> [!WARNING]
> 항상 **Teams 전화 표준 요금제** 라이선스를 제거하고 동일한 라이선스 활동에서 **Microsoft Teams 전화 Resource Account** 라이선스를 할당합니다. 이전 라이선스를 제거한 경우 계정 변경 내용을 저장하고 새 라이선스를 추가한 다음 계정 설정을 다시 저장하면 리소스 계정이 더 이상 예상대로 작동하지 않을 수 있습니다. 이 경우 Microsoft Teams 전화 리소스 계정 라이선스에 대한 새 **리소스 계정을** 만들고 손상된 리소스 계정을 제거하는 것이 좋습니다.

## <a name="skype-for-business-server-2019"></a>비즈니스용 Skype Server 2019

클라우드 통화 큐 및 클라우드 자동 전화 교환과 함께 사용할 수 있는 비즈니스용 Skype Server 2019에 있는 리소스 계정은 [클라우드 통화 큐 계획](/SkypeforBusiness/hybrid/plan-call-queue) 또는 [클라우드 자동 전화 교환 계획을 참조하세요](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant). 하이브리드 구현(직접 라우팅에 포함되는 숫자)은 온-프레미스 비즈니스용 Skype 서버 2019 서버의 [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint) cmdlet을 사용하여 구성됩니다.

애플리케이션 인스턴스를 만드는 동안 사용해야 하는 애플리케이션 ID는 다음과 같습니다.

- **자동 전화 교환:** ce933385-9390-45d1-9512-c8d228074e07
- **통화 큐:** 11cd3e2e-fccb-42ad-ad00-878b93575e07

> [!NOTE]
> Skype For Business Server 2019 사용자가 통화 큐 또는 자동 전화 교환을 검색하려면 온라인 리소스 계정이 Active Directory로 동기화되지 않으므로 비즈니스용 Skype Server 2019에서 리소스 계정을 만들어야 합니다. sipfederationtls에 대한 DNS SRV 레코드가 비즈니스용 Skype 서버 2019로 확인되면 SfB Management 셸을 사용하여 비즈니스용 Skype Server 2019에서 리소스 계정을 만들고 Azure AD 동기화 **해야 합니다**.

비즈니스용 Skype 서버 사용하는 하이브리드 구현의 경우:

- [클라우드 자동 전화 교환을 계획합니다](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant).
- [클라우드 호출 큐를 계획합니다](/SkypeforBusiness/hybrid/plan-call-queue).
- [온-프레미스 리소스 계정을 구성합니다](/SkypeForBusiness/hybrid/configure-onprem-ra).

## <a name="delete-a-resource-account"></a>리소스 계정 삭제

보류 중인 모드에서 전화 번호가 중단되는 것을 방지하려면 삭제하기 전에 리소스 계정에서 전화 번호를 분리해야 합니다.

이렇게 하면 **사용자** 탭 아래의 Microsoft 365 관리 센터 리소스 계정을 삭제할 수 있습니다.

리소스 계정에서 직접 라우팅 전화 번호를 연결 해제하려면 다음 cmdlet을 사용합니다.

```powershell
Remove-CsPhoneNumberAssignment -Identity <Resource Account Object ID> -PhoneNumber <assigned phone number> -PhoneNumberType DirectRouting
```

## <a name="hide-resource-accounts-from-teams-users"></a>Teams 사용자로부터 리소스 계정 숨기기

Teams 사용자로부터 특정 리소스 계정을 숨길 수 있습니다. 예를 들어 Teams 사용자가 통화 큐를 직접 호출하고 작업 시간이 구성된 자동 전화 교환을 우회하지 못하도록 방지할 수 있습니다.

[정보 장벽은](information-barriers-in-teams.md) 리소스 계정을 숨기는 데 사용됩니다.  아래 단계를 진행하기 전에 정보 장벽 설명서를 검토하여 가능한 영향을 이해합니다.

### <a name="required-subscriptions-and-permissions"></a>필수 구독 및 권한 

정보 장벽에 액세스하고 사용하려면 조직에 다음 구독 중 하나 또는 추가 기능이 있어야 합니다. 

-   Microsoft 365 E5/A5 구독(유료 또는 평가판 버전).
-   Office 365 E5/A5/A3/A1 구독(유료 또는 평가판 버전).
-   추가 기능을 Office 365 Advanced Compliance.
-   Microsoft 365 E3/A3/A1 구독 + Microsoft 365 E5/A5 규정 준수 추가 기능.
- Microsoft 365 E3/A3/A1 구독 + Microsoft 365 E5/A5 참가자 위험 관리 추가 기능.

> [!NOTE]
> [이미 Exchange Online](/exchange/address-books/address-book-policies/address-book-policies) 주소록 정책을 구성한 경우 아래 단계를 진행하기 전에 제거해야 합니다.   
> 
> 아래의 모든 단계는 테넌트 전역 관리자가 수행합니다. 
>   
> 이러한 지침에서는 구성된 다른 정보 장벽이 없다고 가정합니다.

#### <a name="teams-admin-center"></a>Teams 관리 센터

1. [Teams 관리 센터에 로그인합니다](https://go.microsoft.com/fwlink/p/?linkid=2066851).
2. 왼쪽 레일 메뉴에서 Teams를 확장 **합니다**.
3. **Teams 설정을** 선택합니다. 
4. **이름으로 검색** 까지 아래로 스크롤합니다.
5. 토글을 켜고 변경 사항을 저장합니다.

이 옵션에 대한 자세한 내용은 [Teams에서 디렉터리를 검색할 때 사용자가 볼 수 있는 사용자 제한을 참조하세요](teams-scoped-directory-search.md).

#### <a name="compliance---auditing"></a>규정 준수 - 감사

1. [Microsoft Purview 규정 준수 포털](https://compliance.microsoft.com/) 로그인합니다.
2. 왼쪽 탐색 창에서 **감사를** 선택합니다.
3. 감사가 꺼져 있으면 다음 배너가 표시됩니다. 
 
     :::image type="content" source="/microsoft-365/media/AuditingBanner.png" alt-text="감사가 사용하도록 설정되지 않은 경우 감사 배너를 보여 주는 스크린샷":::
  
4. **기록 시작 사용자 및 관리자 활동을** 선택합니다. 

감사에 대한 자세한 내용은 [Microsoft 365에서 감사(표준) 설정을 참조하세요](/microsoft-365/compliance/audit-standard-setup).

#### <a name="segmenting-data"></a>데이터 분할

직접 호출해서는 안 되는 리소스 계정을 세분화하고 쉽게 식별할 수 있어야 합니다.  이 작업은 특정 그룹의 구성원으로 만들거나 사용자 프로필의 고유한 정보(예: )를 통해 수행할 수 있습니다. 

-   회사
-   사용자 계정 이름
-   위치
-   부서
-   사용 위치
-   메일 애칭(별칭)
-   실제 배달 사무실 이름(Office)
-   우편 번호
-   프록시 주소(Email 주소)
-   주소
-   대상 주소(ExternalEmailAddress)
-   메일(WindowsEmailAddress)
-   설명

아래 예제 단계에서는 필드가 `Department` 사용됩니다. 

사용자 분할에 대한 자세한 내용은  [세그먼트 식별을 참조하세요](/microsoft-365/compliance/information-barriers-policies).

#### <a name="microsoft-admin-center"></a>Microsoft 관리 센터

1. [Microsoft 365 관리 센터에 로그인합니다](https://go.microsoft.com/fwlink/p/?linkid=2024339).
2. 왼쪽 탐색 창에서 **활성 사용자를** 선택합니다.
3. 직접 호출을 차단할 첫 번째 리소스 계정을 선택합니다.
4. 오른쪽 창에서 **연락처 정보 관리를** 선택합니다.
5. 필드의 `Department` 내용을 부서 이름으로 사용되지 않는 고유한 단어 또는 머리글자어로 바꿉니다. 예를 들어 입니다 `DNC`.
6. 변경 내용을 저장합니다.
7. 직접 전화를 받지 못하도록 차단해야 하는 각 리소스 계정에 대해 반복합니다.

#### <a name="compliance---information-barriers"></a>규정 준수 - 정보 장벽

1. [Microsoft Purview 규정 준수 포털](https://compliance.microsoft.com/) 로그인합니다.
2. 왼쪽 탐색 창에서 **정보 장벽****세그먼트를** >  선택합니다.
3. **새 세그먼트를** 선택합니다.
4. 세그먼트의 이름을 입력하고 **다음** 을 선택합니다. 예를 들어 입니다 `Uncallable Resource Accounts`.
5. **+ 추가** 를 선택한 다음 **부서** 를 선택합니다.
6. 위의 Microsoft 관리 센터 5단계에서 사용되는 고유한 단어 또는 머리글자어를 입력합니다. 예를 들어 입니다 `DNC`.
7. **다음** 을 선택한 다음 **제출** 을 선택합니다.
8. **새 세그먼트를** 선택합니다.
9. 세그먼트의 이름을 입력하고 **다음** 을 선택합니다. 예를 들어 입니다 `Callable Users`.
10. **+ 추가** 를 선택한 다음 **부서** 를 선택합니다.
11. **등** 수 드롭다운을 선택하고 같지 **않음을** 선택합니다.
12. 위의 Microsoft 관리 센터 5단계에서 사용되는 고유한 단어 또는 머리글자어를 입력합니다. 예를 들어 입니다 `DNC`.
13. **다음** 을 선택한 다음 **제출** 을 선택합니다. 
14. 왼쪽 탐색 창에서 **정보 장벽** > **정책을** 선택합니다.
15. **정책 만들기** 를 선택합니다.
16. 정책 이름을 입력하고 **다음** 을 선택합니다. 예를 들어 입니다 `Uncallable Resource Accounts`.
17. **+ 세그먼트 선택을 선택하고** 위의 9단계에서 만든 세그먼트를 추가하고 **다음** 을 선택합니다. 예를 들어 입니다 `Callable Users`.
18. **통신 및 공동 작업** 드롭다운에서 **차단을** 선택합니다.
19. **+ 세그먼트 선택을 선택하고** 위의 4단계에서 만든 세그먼트를 추가하고 **다음** 을 선택합니다. 예를 들어 입니다 `Uncallable Resource Accounts`.
20. 정책을 **켜** 기로 설정하고 **다음** 을 선택한 다음 **제출** 을 선택합니다.
21. **정책 만들기** 를 선택합니다.
22. 정책 이름을 입력하고 **다음** 을 선택합니다. 예를 들어 입니다 `Callable Users`.
23. **+ 세그먼트 선택을 선택하고**, 4단계에서 만든 세그먼트를 추가하고, **다음** 을 선택합니다.
24. **통신 및 공동 작업** 드롭다운에서 **차단을** 선택합니다. 
25. **+ 세그먼트 선택을 선택하고** 위의 9단계에서 만든 세그먼트를 추가하고 **다음** 을 선택합니다.
26. 정책을 **켜** 기로 설정하고 **다음** 을 선택한 다음 **제출** 을 선택합니다.
27. 왼쪽 탐색 창에서 **정보 장벽****정책 애플리케이션** 을  >  선택합니다.
28. **모든 정책 적용을** 선택합니다.

> [!NOTE]
> 정책을 적용하는 데 30분 이상이 걸릴 수 있습니다.  
> 
> 상태가 완료된 것으로 표시되면 Teams 클라이언트로 이동하여 차단된 리소스 계정을 검색합니다. Teams 캐시를 지워야 할 수도 있습니다.  
> 
> Teams 사용자가 리소스 계정을 연락처로 저장한 경우 더 이상 전화를 걸 수 없습니다.
