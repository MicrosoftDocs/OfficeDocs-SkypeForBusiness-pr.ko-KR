---
title: Microsoft Teams에서 게스트 액세스 권한 부여
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- SPO_Content
ms.reviewer: rafarhi
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
description: 네 가지 수준의 권한 부여를 통해 Microsoft Teams 게스트 액세스 기능을 관리합니다.
ms.openlocfilehash: e74152bc61bdf0bb793338b50ddcd5da62e9b2d0
ms.sourcegitcommit: 43e5a4aac11c20dd5a4c35b59695f309e1559e82
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/03/2020
ms.locfileid: "48346189"
---
# <a name="authorize-guest-access-in-microsoft-teams"></a>Microsoft Teams에서 게스트 액세스 권한 부여

조직의 요구 사항을 충족 하기 위해 네 가지 수준의 권한 부여를 통해 팀 게스트 액세스 기능 및 기능을 관리할 수 있습니다. 모든 권한 수준은 Microsoft 365 조직에 적용 됩니다. 각 권한 수준은 아래와 같이 게스트 경험을 제어합니다.

- **Azure Active Directory**: 팀의 게스트 액세스는 Azure AD BUSINESS (b2b) 플랫폼에 따라 달라 집니다. 이 권한 수준은 디렉터리, 테넌트 및 응용 프로그램 수준에서의 게스트 경험을 제어합니다.
- **팀**: 팀 에서만 게스트 환경을 제어 합니다.
- **Microsoft 365 그룹**: Microsoft 365 그룹 및 팀에서 게스트 환경을 제어 합니다.
- **Sharepoint 및 onedrive**: Sharepoint, Onedrive, Microsoft 365 그룹 및 팀에서 게스트 환경을 제어 합니다.

이러한 서로 다른 권한 수준은 조직에 게스트 액세스를 설정하는 방법에 유연성을 제공합니다. 예를 들어 팀에서 게스트 사용자를 허용 하 고 조직에서 전반적으로 허용 하려는 경우 팀에서 게스트 액세스를 해제 하면 됩니다. 또 다른 예로는 Azure AD, 팀 및 그룹 수준에서 게스트 액세스를 사용 하도록 설정할 수 있지만, [선택 된 팀에서 데이터 분류와 같은 하나 이상의 조건과 일치 하는 게스트 사용자 추가를 사용 하지 않도록 설정 합니다](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites). SharePoint 및 OneDrive에는 Microsoft 365 그룹에 의존 하지 않는 고유한 게스트 액세스 설정이 있습니다.

엔드 투 엔드 게스트 액세스 구성 지침은 [팀에서 게스트 공동 작업](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)을 참조 하세요.

> [!NOTE]
> 게스트는 [Microsoft 365 및 Office 365 서비스 설명](https://go.microsoft.com/fwlink/p/?linkid=282347) 및 [Azure AD B2B 공동 작업의 제한 사항](https://docs.microsoft.com/azure/active-directory/external-identities/current-limitations)에서 설명하는 서비스 제한의 적용을 받습니다. 

다음 다이어그램은 게스트 액세스 권한 부여 종속성이 Azure Active Directory, 팀 및 Microsoft 365 간에 부여 되 고 통합 되는 방법을 보여 줍니다.

![게스트 액세스에 대한 권한 종속성 다이어그램.](media/teams_dependencies_image1.png)

다음 다이어그램은 일반적인 게스트 액세스 초대 및 상환 흐름을 통해 사용자 경험이 권한 모델을 사용하는 방법을 개략적으로 보여줍니다.

![초대 및 상환 흐름 다이어그램](media/authorize-guest-image1.png)

앱, 인공 지능 및 커넥터에는 고유한 사용 권한 집합 및/또는 사용자 계정에 대 한 동의가 필요 하다는 점에 유의 해야 합니다. 이들은 별도로 부여해야 할 수도 있습니다. 마찬가지로 SharePoint는 특정 사용자, 사용자 그룹 또는 사이트 수준에 대해 추가 외부 공유 경계를 부과할 수 있습니다.

앞의 두 다이어그램은 [Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/media/teams_dependencies.vsdx?raw=true)에서도 사용할 수 있습니다.

## <a name="control-guest-access-in-azure-active-directory"></a>Azure Active Directory에서 게스트 액세스 제어

Azure AD를 사용하여 외부 협력자를 게스트로 초대할지와 초대 방식을 결정할 수 있습니다. Azure B2B 게스트 액세스에 대한 자세한 내용은 [Azure Active Directory B2B의 게스트 사용자 액세스란](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b)을 참조하세요. Azure AD 역할에 대한 자세한 내용은 [Azure Active Directory 테넌트에서 파트너 조직의 사용자에게 권한 부여](https://docs.microsoft.com/azure/active-directory/b2b/add-guest-to-role)를 참조하세요.

초대에 대 한 설정은 조직 수준에서 적용 되며 디렉터리 및 응용 프로그램 수준에서 게스트 환경을 제어 합니다. [외부 공동 작업 설정](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/CompanyRelationshipsMenuBlade/Settings)에서 이러한 설정을 구성할 수 있습니다.

Azure AD에는 외부 사용자를 구성하기위한 다음 설정이 포함되어 있습니다.

- [게스트 사용자 액세스 제한](https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-restrict-guest-permissions)

- **게스트 초대자 역할의 관리자 및 사용자 초대 가능**: **예**는 게스트 초대자 역할의 관리자 및 사용자가 게스트를 테넌트로 초대할 수 있음을 의미합니다. **아니요**는 관리자와 사용자가 테넌트에 게스트를 초대할 수 없음을 의미합니다.
- **회원 초대 가능**: 디렉토리의 관리자가 아닌 회원이 손님을 초대할 수 있게 하려면 이 정책을 **예**(권장)로 설정하십시오. 관리자만 게스트를 추가할 수 있게 하려는 경우 이 정책을 **아니오**로 설정할 수 있습니다. **아니오**로 설정할 경우 관리자가 아닌 Teams 소유자의 게스트 환경이 제한됨에 유의하십시오. 이 소유자들은 AAD에 이미 추가된 Teams에만 게스트를 추가할 수 있습니다.
- **게스트 초대 가능**: **예**는 디렉터리의 게스트를 초대하여 SharePoint 사이트 또는 Azure 리소스와 같은 Azure AD로 보안된 리소스에 대해 공동 작업을 수행할 수 있음을 의미합니다. **아니요**는 게스트가 다른 게스트를 초대하여 조직과 공동 작업을 할 수는 없습니다.
    > [!IMPORTANT]
    > 현재 Teams는 게스트 초대자 역할을 지원하지 않으므로 **참석자를 초대 할 수 있음**으로 **설정**하더라도 손님은 Teams에서 다른 참석자를 초대할 수 없습니다.
 
게스트를 초대할 수 있는 사용자를 제어 하는 방법에 대 한 자세한 내용은 [B2B 외부 공동 작업 사용 및 게스트를 초대할 수 있는 사용자 관리](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)를 참조 하세요

> [!NOTE]
> 또한 테넌트에 게스트로 초대되는 도메인을 관리할 수 있습니다. [특정 조직의 B2B 사용자에 대 한 초대 허용 또는 차단을](https://docs.microsoft.com/azure/active-directory/external-identities/allow-deny-list)참조 하세요.

Teams에 게스트를 추가할 때 계정이 디렉터리에 자동으로 추가되므로 사용자 게스트 계정을 Azure AD B2B에 수동으로 추가할 필요가 없습니다.

### <a name="licensing-for-guest-access"></a>게스트 액세스에 대한 라이선스

게스트 액세스 라이선스는 Azure AD External Id 가격을 사용 하며 월간 활성 게스트를 기반으로 합니다. 자세한 내용은 [AZURE AD External id에 대 한 청구 모델을](https://docs.microsoft.com/azure/active-directory/external-identities/external-identities-pricing) 참조 하세요.

> [!NOTE]
> Exchange Online Plan 2와 같이 독립실행형 Office 365 구독 계획만 가진 조직의 사용자는 Teams에서 동일한 조직에 속한 것으로 간주하기 때문에 조직에 게스트로 초대될 수 없습니다. 사용자가 Teams를 사용하려면 Microsoft 365 Business Standard, Office 365 Enterprise 또는 Office 365 Education 구독에 할당되어야 합니다. 

## <a name="external-access-federation-vs-guest-access"></a>외부 액세스 (페더레이션) 및 게스트 액세스

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="related-topics"></a>관련 항목

- [Microsoft 365 게스트 공유 설정 참조](https://docs.microsoft.com/Office365/Enterprise/microsoft-365-guest-settings)

[Microsoft 365를 사용 하 여 보안 공동 작업 설정](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)
