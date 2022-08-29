---
title: 교육용 Microsoft Teams 라이선스 할당
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: 교육용 Microsoft Teams 라이선스를 할당하는 방법을 알아봅니다.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom:
- admindeeplinkMAC
ms.openlocfilehash: e57780436167e3a872e78a717d12cd3acc35a6e9
ms.sourcegitcommit: c19ac3be42cc4b8409c8d512bbe3156736af0309
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2022
ms.locfileid: "67426805"
---
# <a name="assign-microsoft-teams-licenses-for-education"></a>교육용 Microsoft Teams 라이선스 할당

이 문서는 교직원, 교직원 및 학생에게 팀 라이선스를 할당해야 하는 교육 분야의 IT 관리자를 위한 것입니다.

사용자가 Teams를 준비할 수 있도록 하려면 다음을 수행해야 합니다.

1. [Microsoft 365 관리 센터 학교에서 Microsoft Teams를 사용하도록 설정합니다](/microsoft-365/education/intune-edu-trial/enable-microsoft-teams).
2. Teams를 포함하여 Microsoft 365 서비스에 액세스할 수 있도록 사용자 계정에 라이선스를 할당합니다.

## <a name="ways-to-assign-teams-licenses"></a>Teams 라이선스를 할당하는 방법

사용자 계정에 라이선스를 할당할 수 있습니다.

- 개별적으로 또는 Microsoft 365 관리 센터 있는 소규모 사용자 그룹에 연결합니다.
- [PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell) 또는 [Active Directory 그룹 기반 라이선스](/azure/active-directory/users-groups-roles/licensing-groups-assign)를 사용하여 그룹 멤버 자격을 통해 자동으로 수행됩니다.

이 문서에서는 Microsoft 365 관리 센터 라이선스를 할당하는 방법을 안내합니다.

Microsoft 365 관리 센터 다음 중 하나에서 사용자에게 라이선스를 할당할 수 있습니다.

- 특정 사용자에게 제품 라이선스를 할당하는 **라이선스** 페이지입니다.
- 특정 제품에 사용자 라이선스를 할당하는 **활성** 사용자 페이지입니다.

> [!NOTE]
> 전역 관리자, 청구 관리자, 라이선스 관리자 또는 사용자 관리 관리자 권한을 갖고 있어야 합니다. 자세한 내용은 [Office 365 관리자 역할 정보](/microsoft-365/admin/add-users/about-admin-roles)를 참조하세요.

## <a name="assign-licenses-to-users-on-the-licenses-page"></a>라이선스 페이지에서 사용자에게 라이선스 할당

**라이선스** 페이지에는 구독이 있는 모든 제품의 목록, 각 제품에 대한 총 라이선스 수, 할당된 라이선스 수 및 사용 가능한 라이선스 수가 표시됩니다.

1. [관리 센터에서](https://go.microsoft.com/fwlink/p/?linkid=2024339) **청구** > [라이선스](https://go.microsoft.com/fwlink/p/?linkid=842264) 페이지로 이동합니다.

2. 라이선스를 할당하려는 제품을 선택합니다. Microsoft Teams는 학생용 무료 Microsoft 365 A1 SKU의 일부입니다.

3. **라이선스 할당** 을 선택합니다.

4. **사용자에 게 라이선스 할당** 창에서 이름을 입력하기 시작합니다. 이 경우 이름 목록이 생성됩니다.

5. 검색 결과에서 찾으려는 이름을 선택하여 목록에 추가합니다. 한 번에 최대 20명의 사용자를 추가할 수 있습니다.

6. **앱 및 서비스를 설정 또는 해제** 를 선택하여 Microsoft Teams와 같은 특정 항목에 대한 액세스 권한을 할당하거나 제거합니다. **Microsoft Teams** 및 **웹용 Office(교육)** 가 선택되어 있는지 확인합니다.

7. 작업을 마치면 **할당** 을 선택한 다음 **닫기** 를 선택합니다.

### <a name="change-the-apps-and-services-a-user-has-access-to"></a>사용자가 액세스할 수 있는 앱 및 서비스 변경

1. 사용자가 포함된 행을 선택합니다.

2. 오른쪽 창에서 액세스 권한을 부여 또는 제거할 앱과 서비스를 선택하거나 선택 취소합니다.

3. 작업을 마치면 **저장** 을 선택한 다음 **닫기** 를 선택합니다.

## <a name="assign-licenses-to-users-on-the-active-users-page"></a>활성 사용자 페이지에서 사용자에게 라이선스 할당

1. [관리 센터에서](https://go.microsoft.com/fwlink/p/?linkid=2024339) **사용자 활성 사용자** >  페이지 [로](https://go.microsoft.com/fwlink/p/?linkid=834822) 이동합니다.

2. 라이선스를 할당하려는 사용자의 이름 옆의 원을 선택합니다.

3. 맨 위에서 **제품 라이선스 관리를** 선택합니다.

4. **제품 라이선스 관리** 창에서 **기존 제품 라이선스 할당에 추가** > **다음** 을 선택합니다.

5. **기존 제품에 추가** 창에서 선택한 사용자에게 제공하려는 라이선스의 **설정** 위치로 토글합니다. **Microsoft Teams** 및 **웹용 Office(교육)** 가 선택되어 있는지 확인합니다.

   기본적으로 이들 라이선스와 연결된 모든 서비스가 사용자에게 자동으로 할당됩니다. 사용자가 이용할 수 있는 서비스를 제한할 수 있습니다. 사용자에게 제공하지 않으려는 서비스의 **해제** 위치로 토글을 전환합니다.

6. 창 아래쪽에서 **닫기** **추가** > 를 선택합니다.
