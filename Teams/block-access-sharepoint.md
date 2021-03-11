---
title: 특정 사용자의 SharePoint 액세스 차단하기
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: Nigolc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 특정 사용자의 SharePoint 액세스를 차단하는 방법 알아보기
ms.openlocfilehash: e3cda9d6443c41abc7dfa736be03555690a3b0f1
ms.sourcegitcommit: 31a585cc0fe6350efacf3a7771d1e590d5e4233c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/10/2021
ms.locfileid: "50615084"
---
# <a name="block-access-to-sharepoint-for-specific-users"></a>특정 사용자의 SharePoint 액세스 차단하기

Microsoft 365의 SharePoint에 모든 조건부 액세스(CA) 정책을 적용하는 것이 Teams에서도 적용됩니다. 그러나 일부 조직의 경우, SharePoint 파일 액세스(업로드, 다운로드, 보기, 편집, 만들기)를 차단하면서도 직원들이 관리되지 않는 장치에서 Teams 데스크톱, 모바일 및 웹 클라이언트를 사용할 수 있도록 허용하고자 할 수 있습니다. CA 정책 하에서 Sharepoint를 차단하면 Teams도 차단됩니다. 이 문서에서는 어떻게 이 한계를 피하고, SharePoint에 저장된 파일 액세스를 완전히 차단하면서도 직원들이 Teams를 계속 사용할 수 있도록 허용할 수 있는지에 대해 설명합니다.

> [!Note]
> 관리되지 않는 장치에서 액세스를 차단하거나 제한하는 기능은 Azure AD 조건부 액세스 정책을 따르고 있습니다. [Azure AD 라이선싱](https://azure.microsoft.com/pricing/details/active-directory/)에 대해 알아보세요. Azure AD의 조건부 액세스에 대한 개요는 [Azure Active Directory의 조건부 액세스](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)를 참조하세요. 권장하는 SharePoint Online 액세스 정책에 대한 자세한 내용은 [SharePoint 사이트 및 파일 보호를 위한 정책 권장 사항](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies)을 참조하세요. 관리되지 않는 장치에서 액세스를 제한하는 경우, 관리되는 장치의 사용자는 [지원되는 OS 및 브라우저 조합](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#client-apps-condition) 중 하나를 사용해야 합니다. 그렇지 않으면 액세스가 제한될 수 있습니다.

다음의 경우 액세스를 차단하거나 제한할 수 있습니다.

- 조직의 모든 사용자 또는 일부 사용자 또는 보안 그룹

- 조직의 모든 사이트 또는 일부 사이트

액세스가 차단되면 사용자에게 오류 메시지가 표시됩니다. 액세스를 차단하면 보안이 보장되고 기밀 데이터를 보호하는 데 도움이 됩니다. 액세스가 차단되면 사용자에게 오류 메시지가 표시됩니다.

1. SharePoint 관리 센터를 엽니다.

2. **정책** > **액세스 정책** 을 확장합니다.

3. **관리 되지 않은 장치** 구역에서 **액세스 차단** 을 선택하고 **저장** 을 선택합니다.

   ![정책에 대한 관리 되지 않은 장치 섹션](media/no-sharepoint-access1.png)

4. [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) 포털을 열고 **조건부 액세스 정책** 을 탐색합니다.

    SharePoint에서 다음 예와 유사한 새 정책이 생성된 것을 볼 수 있습니다.

    ![브라우저 액세스를 위해 앱 적용 제한 사용이라는 새 정책](media/no-sharepoint-access2.png)

5. 정책을 업데이트하여 특정 사용자나 그룹만을 대상으로 지정합니다.

    ![사용자 선택 섹션이 강조 표시된 Sharepoint 관리 센터](media/no-sharepoint-access2b.png)

  > [!Note]
> 이 정책을 설정하면 SharePoint 관리 포털에 대한 액세스를 차단할 수 있습니다. 제외 정책을 구성하고 전역 및 SharePoint 관리자를 선택하는 것이 좋습니다.

6. 대상 클라우드 앱으로 SharePoint만 선택했는지 확인합니다.

    ![Sharepoint가 대상 앱으로 선택되었습니다.](media/no-sharepoint-access3.png)

7. 데스크톱 클라이언트 또한 포함하도록 **조건** 을 업데이트합니다.

    ![강조 표시된 데스크톱 및 모바일 앱](media/no-sharepoint-access4.png)

8. **액세스 권한 부여** 가 설정되어 있는지 확인합니다.

    ![액세스 권한 부여가 설정되었습니다.](media/no-sharepoint-access5.png)

9. **앱 적용 제한 사용** 이 설정되어 있는지 확인합니다.

10. 정책 사용을 설정하고 **저장** 을 선택합니다.

    ![앱 적용 제한 사용이 설정되었습니다.](media/no-sharepoint-access6.png)

정책을 테스트하려면 Teams 데스크톱 앱 또는 비즈니스용 OneDrive 동기화 클라이언트와 같은 클라이언트에서 로그아웃한 다음 다시 로그인하여 정책이 적용되었는지 확인해야 합니다. 액세스가 차단된 경우 Teams에서 항목이 존재하지 않을 수 있음을 알리는 메시지가 표시됩니다.

 ![항목 없음 메시지](media/access-denied-sharepoint.png)

Sharepoint에서 액세스 거부 메시지를 받게 됩니다.

![액세스 거부 메시지](media/blocked-access-warning.png)

## <a name="related-topics"></a>관련 주제

[SharePoint에서 관리 되지 않은 장치에 대한 액세스 제어](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)
