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
- m365initiative-externalcollab
ms.reviewer: rafarhi
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
description: 네 가지 수준의 권한 부여를 통해 Microsoft Teams 게스트 액세스 기능을 관리합니다.
ms.openlocfilehash: 40bc8c68ac3f1ad3117fa47aa0aad5f14ff3be69
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030994"
---
# <a name="authorize-guest-access-in-microsoft-teams"></a>Microsoft Teams에서 게스트 액세스 권한 부여

조직의 요구 사항을 충족하기 위해 네 가지 수준의 권한 부여를 통해 Teams 게스트 액세스 기능 및 기능을 관리할 수 있습니다. 모든 권한 부여 수준은 Microsoft 365 조직에 적용됩니다. 각 권한 수준은 아래와 같이 게스트 경험을 제어합니다.

- **Azure Active Directory:** Teams의 게스트 액세스는 Azure AD B2B(Business-to-Business) 플랫폼에 의존합니다. 이 권한 수준은 디렉터리, 테넌트 및 응용 프로그램 수준에서의 게스트 경험을 제어합니다.
- **Teams:** Teams에서만 게스트 환경을 제어합니다.
- **Microsoft 365 그룹:** Microsoft 365 그룹 및 Teams의 게스트 환경을 제어합니다.
- **SharePoint 및 OneDrive:** SharePoint, OneDrive, Microsoft 365 그룹 및 Teams에서 게스트 환경을 제어합니다.

이러한 서로 다른 권한 수준은 조직에 게스트 액세스를 설정하는 방법에 유연성을 제공합니다. 예를 들어 Teams에서 게스트 사용자를 허용하지 않지만 조직에서 게스트 사용자를 허용하려는 경우 Teams에서 게스트 액세스를 해제하면 됩니다. 또 다른 예: Azure AD, Teams 및 그룹 수준에서 게스트 액세스를 사용하도록 설정한 다음 데이터 분류와 같은 하나 이상의 조건과 일치하는 선택한 팀에 게스트 사용자를 추가하지 않도록 설정할 수 [있습니다.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites) SharePoint 및 OneDrive에는 Microsoft 365 그룹을 사용하지 않는 자체 게스트 액세스 설정이 있습니다.

종단별 게스트 액세스 구성 지침은 팀의 게스트와 공동 [작업을 참조하세요.](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)

> [!NOTE]
> 게스트는 [Microsoft 365 및 Office 365 서비스 설명](https://go.microsoft.com/fwlink/p/?linkid=282347) 및 [Azure AD B2B 공동 작업의 제한 사항](https://docs.microsoft.com/azure/active-directory/external-identities/current-limitations)에서 설명하는 서비스 제한의 적용을 받습니다. 

다음 다이어그램에서는 Azure Active Directory, Teams 및 Microsoft 365 간에 게스트 액세스 권한 부여 종속성의 부여 및 통합 방법을 보여줍니다.

> [!div class="mx-imgBorder"]
> ![게스트 액세스에 대한 권한 종속성 다이어그램.](media/teams_dependencies_image1.png)

다음 다이어그램은 일반적인 게스트 액세스 초대 및 상환 흐름을 통해 사용자 경험이 권한 모델을 사용하는 방법을 개략적으로 보여줍니다.

> [!div class="mx-imgBorder"]
> ![초대 및 상환 흐름 다이어그램](media/authorize-guest-image1.png)

앱, 봇 및 커넥터에는 사용자 계정에 특정된 자체 사용 권한 및/또는 동의 집합이 필요할 수 있습니다. 이들은 별도로 부여해야 할 수도 있습니다. 마찬가지로 SharePoint는 특정 사용자, 사용자 그룹 또는 사이트 수준에 대해 추가 외부 공유 경계를 부과할 수 있습니다.

앞의 두 다이어그램은 [Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/media/teams_dependencies.vsdx?raw=true)에서도 사용할 수 있습니다.

## <a name="control-guest-access-in-azure-active-directory"></a>Azure Active Directory에서 게스트 액세스 제어

Azure AD를 사용하여 외부 협력자를 게스트로 초대할지와 초대 방식을 결정할 수 있습니다. Azure B2B 게스트 액세스에 대한 자세한 내용은 [Azure Active Directory B2B의 게스트 사용자 액세스란](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b)을 참조하세요. Azure AD 역할에 대한 자세한 내용은 [Azure Active Directory 테넌트에서 파트너 조직의 사용자에게 권한 부여](https://docs.microsoft.com/azure/active-directory/b2b/add-guest-to-role)를 참조하세요.

초대 설정은 조직 수준에서 적용하고 디렉터리 및 애플리케이션 수준에서 게스트 환경을 제어합니다. 외부 공동 작업 설정에서 이러한 [설정을 구성할 수 있습니다.](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/CompanyRelationshipsMenuBlade/Settings)

Azure AD에는 외부 사용자를 구성하기위한 다음 설정이 포함되어 있습니다.

- [게스트 사용자 액세스 제한](https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-restrict-guest-permissions)

- **게스트 초대자 역할의 관리자 및 사용자 초대 가능**: **예** 는 게스트 초대자 역할의 관리자 및 사용자가 게스트를 테넌트로 초대할 수 있음을 의미합니다. **아니요** 는 관리자와 사용자가 테넌트에 게스트를 초대할 수 없음을 의미합니다.
- **회원 초대 가능**: 디렉토리의 관리자가 아닌 회원이 손님을 초대할 수 있게 하려면 이 정책을 **예**(권장)로 설정하십시오. 관리자만 게스트를 추가할 수 있게 하려는 경우 이 정책을 **아니오** 로 설정할 수 있습니다. **아니오** 로 설정할 경우 관리자가 아닌 Teams 소유자의 게스트 환경이 제한됨에 유의하십시오. 이 소유자들은 AAD에 이미 추가된 Teams에만 게스트를 추가할 수 있습니다.
- **게스트 초대 가능**: **예** 는 디렉터리의 게스트를 초대하여 SharePoint 사이트 또는 Azure 리소스와 같은 Azure AD로 보안된 리소스에 대해 공동 작업을 수행할 수 있음을 의미합니다. **아니요** 는 게스트가 다른 게스트를 초대하여 조직과 공동 작업을 할 수는 없습니다. 예로 **설정되어 있는 경우에도** 게스트는 Teams에서 다른 게스트를 초대할 수 없습니다.
 
게스트를 초대할 수 있는 사용자 제어에 대한 자세한 내용은 B2B 외부 공동 작업 사용 및 게스트 초대할 수 있는 [사용자 관리를 참조하세요.](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)

> [!NOTE]
> 또한 테넌트에 게스트로 초대되는 도메인을 관리할 수 있습니다. 특정 조직의 B2B 사용자에 대한 초대 허용 또는 [차단을 참조합니다.](https://docs.microsoft.com/azure/active-directory/external-identities/allow-deny-list)

Teams에 게스트를 추가할 때 계정이 디렉터리에 자동으로 추가되므로 사용자 게스트 계정을 Azure AD B2B에 수동으로 추가할 필요가 없습니다.

### <a name="licensing-for-guest-access"></a>게스트 액세스에 대한 라이선스

게스트 액세스 라이선스는 Azure AD 외부 ID 가격을 사용하며 월별 활성 게스트를 기반으로 합니다. 자세한 [내용은 Azure AD 외부 ID에](https://docs.microsoft.com/azure/active-directory/external-identities/external-identities-pricing) 대한 청구 모델을 참조하세요.

> [!NOTE]
> Exchange Online Plan 2와 같이 독립실행형 Office 365 구독 계획만 가진 조직의 사용자는 Teams에서 동일한 조직에 속한 것으로 간주하기 때문에 조직에 게스트로 초대될 수 없습니다. 사용자가 Teams를 사용하려면 Microsoft 365 Business Standard, Office 365 Enterprise 또는 Office 365 Education 구독에 할당되어야 합니다. 

## <a name="external-access-federation-vs-guest-access"></a>외부 액세스 (페더레이션) 및 게스트 액세스

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="related-topics"></a>관련 항목

- [Microsoft 365 게스트 공유 설정 참조](https://docs.microsoft.com/Office365/Enterprise/microsoft-365-guest-settings)

[Microsoft 365를 사용하여 안전한 공동 작업 설정](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)
