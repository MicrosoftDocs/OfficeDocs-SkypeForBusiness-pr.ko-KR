---
title: Microsoft Teams에서 게스트 액세스 권한 부여
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- SPO_Content
ms.reviewer: sbhatta
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
description: 네 가지 수준의 권한 부여를 통해 Microsoft Teams 게스트 액세스 기능을 관리합니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: b1743b8d2fea354716138800ffe2c1b50d9e71b6
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41834808"
---
<a name="authorize-guest-access-in-microsoft-teams"></a>Microsoft Teams에서 게스트 액세스 권한 부여
===========================================

조직의 요구 사항을 충족시키기 위해, 네 가지 수준의 권한 부여를 통해 Microsoft Teams 게스트 액세스 기능을 관리할 수 있습니다. 모든 권한 수준은 Office 365 테넌트에 적용됩니다. 각 권한 수준은 아래와 같이 게스트 경험을 제어합니다.

- **Azure Active Directory**: Microsoft Teams의 게스트 액세스는 Azure AD B2B (Business-to-Business) 플랫폼에 의존합니다. 이 권한 수준은 디렉터리, 테넌트 및 응용 프로그램 수준에서의 게스트 경험을 제어합니다.
- **Microsoft Teams**: Microsoft Teams의 게스트 경험만 제어합니다.
- **Office 365 그룹**: Office 365 그룹 및 Microsoft Teams에서 게스트 환경을 제어합니다.
- **SharePoint Online 및 비즈니스용 OneDrive**: SharePoint Online, 비즈니스용 OneDrive, Office 365 그룹 및 Microsoft Teams에서 게스트 환경을 제어 합니다.

이러한 서로 다른 권한 수준은 조직에 게스트 액세스를 설정하는 방법에 유연성을 제공합니다. 예를 들어 Microsoft Teams에서 게스트 사용자를 허용하지 않고 조직 전체에서 게스트 사용자를 허용하려면 Microsoft Teams에서 게스트 액세스를 해제하기만 하면 됩니다. 또 다른 예: Azure AD, Teams, 그룹 수준에서 게스트 액세스를 사용하도록 설정할 수 있지만, 선택한 팀에서 데이터 분류와 같은 하나 이상의 조건과 일치하는 게스트 사용자를 추가하는 기능을 사용하지 않도록 설정합니다. SharePoint Online 및 비즈니스용 OneDrive에는 Office 365 그룹에 의존하지 않는 자체 게스트 액세스 설정이 있습니다.

> [!NOTE]
> 게스트는 [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) 및 [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) 서비스 제한에 영향을 받습니다. 

다음 다이어그램은 게스트 액세스 권한 종속성이 Azure Active Directory, Microsoft Teams 및 Office 365간에 부여되고 통합되는 방법을 보여줍니다.

![게스트 액세스에 대한 권한 종속성 다이어그램.](media/teams_dependencies_image1.png)

다음 다이어그램은 일반적인 게스트 액세스 초대 및 상환 흐름을 통해 사용자 경험이 권한 모델을 사용하는 방법을 개략적으로 보여줍니다.

![초대 및 상환 흐름 다이어그램](media/authorize-guest-image1.png)

여기에서 앱, 봇 및 커넥터는 사용자 계정에 고유한 권한 및 / 또는 동의가 필요할 수 있습니다. 이들은 별도로 부여해야 할 수도 있습니다. 마찬가지로 SharePoint는 특정 사용자, 사용자 그룹 또는 사이트 수준에 대해 추가 외부 공유 경계를 부과할 수 있습니다.

앞의 두 다이어그램은 [Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/media/teams_dependencies.vsdx?raw=true)에서도 사용할 수 있습니다.

## <a name="control-guest-access-in-azure-active-directory"></a>Azure Active Directory에서 게스트 액세스 제어

Azure AD를 사용하여 외부 협력자를 게스트로 초대할지와 초대 방식을 결정할 수 있습니다. Azure B2B 게스트 액세스에 대한 자세한 내용은 [Azure Active Directory B2B의 게스트 사용자 액세스란](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b)을 참조하세요. Azure AD 역할에 대한 자세한 내용은 [Azure Active Directory 테넌트에서 파트너 조직의 사용자에게 권한 부여](https://docs.microsoft.com/azure/active-directory/b2b/add-guest-to-role)를 참조하세요.

초대 설정은 테넌트 수준에서 적용되고 디렉터리, 테넌트 및 응용 프로그램 수준에서 게스트 환경을 제어합니다. Azure Portal에서 이러한 설정을 구성하려면 **Azure Active Directory** > **사용자** > **사용자 설정**으로 이동하고, **외부 사용자**에서 **외부 공동 작업 설정 관리**를 선택합니다.

Azure AD에는 외부 사용자를 구성하기위한 다음 설정이 포함되어 있습니다.

- **게스트 사용자 권한이 제한됨**: **예**는 게스트, 그룹 또는 기타 디렉토리 리소스 열거와 같은 특정 디렉토리 작업에 대한 권한이 게스트에게 없음을 의미합니다. 또한 게스트를 디렉토리의 관리 역할에 할당할 수 없습니다. **아니요**는 게스트가 일반 사용자의 디렉토리에 있는 디렉토리 데이터에 동일한 액세스 권한을 갖음을 의미합니다.
- **게스트 초대자 역할의 관리자 및 사용자 초대 가능**: **예**는 게스트 초대자 역할의 관리자 및 사용자가 게스트를 테넌트로 초대할 수 있음을 의미합니다. **아니요**는 관리자와 사용자가 테넌트에 게스트를 초대할 수 없음을 의미합니다.
- **회원 초대 가능**: 디렉토리의 관리자가 아닌 회원이 손님을 초대할 수 있게 하려면 이 정책을 **예**(권장)로 설정하십시오. 관리자만 게스트를 추가할 수 있게 하려는 경우 이 정책을 **아니오**로 설정할 수 있습니다. **아니오**로 설정할 경우 관리자가 아닌 Teams 소유자의 게스트 환경이 제한됨에 유의하십시오. 이 소유자들은 AAD에 이미 추가된 Teams에만 게스트를 추가할 수 있습니다.
- **게스트 초대 가능**: **예**는 디렉터리의 게스트를 초대하여 SharePoint 사이트 또는 Azure 리소스와 같은 Azure AD로 보안된 리소스에 대해 공동 작업을 수행할 수 있음을 의미합니다. **아니요**는 게스트가 다른 게스트를 초대하여 조직과 공동 작업을 할 수는 없습니다.
    > [!IMPORTANT]
    > 현재 Teams는 게스트 초대자 역할을 지원하지 않으므로 **참석자를 초대 할 수 있음**으로 **설정**하더라도 손님은 Teams에서 다른 참석자를 초대할 수 없습니다.
 
게스트를 초대할 수 있는 사용자를 제어하는 방법에 대한 자세한 내용은 [Azure Active Directory B2B 공동 작업에 대한 초대 위임](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)을 참조합니다.

> [!NOTE]
> 또한 테넌트에 게스트로 초대되는 도메인을 관리할 수 있습니다. [Office 365 그룹에 대한 게스트 액세스 허용/차단](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-group-access-to-office-365-groups)을 참조하세요.

Teams에 게스트를 추가할 때 계정이 디렉터리에 자동으로 추가되므로 사용자 게스트 계정을 Azure AD B2B에 수동으로 추가할 필요가 없습니다.

### <a name="licensing-for-guest-access"></a>게스트 액세스에 대한 라이선스
게스트 액세스 라이선스는 Azure AD 라이선스의 일부입니다. 모든 Office 365 Business Premium 및 Office 365 Enterprise 구독에는 게스트 액세스가 포함됩니다. 라이선스에 대한 자세한 내용은 [Azure Active Directory B2B 공동 작업 라이선스 지침](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)을 참조하세요.


> [!NOTE]
> Exchange Online Plan 2와 같이 독립실행형 Office 365 구독 계획만 가진 조직의 사용자는 Teams에서 동일한 조직에 속한 것으로 간주하기 때문에 조직에 게스트로 초대될 수 없습니다. 사용자가 Teams를 사용하려면 Office 365 Business Premium, Office 365 Enterprise 또는 Office 365 Education 구독에 할당되어야 합니다. 

## <a name="control-guest-access-in-teams"></a>Teams에서 게스트 액세스 제어

Teams에서 게스트 액세스 기능은 기본적으로 꺼져있습니다. 게스트 액세스를 켜려면 [Microsoft Teams에서 게스트 액세스 설정 또는 해제](set-up-guests.md)를 참조하세요. 


## <a name="control-guest-access-in-office-365-groups"></a>Office 365 그룹에서 게스트 액세스 제어

Office 365 그룹에서 조직의 모든 Office 365 그룹 및 Microsoft Teams 팀에 대한 게스트 사용자 및 게스트 액세스 추가를 제어할 수 있습니다.

1. [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home)에서 Office 365 전역 관리자 계정으로 로그인 합니다.

2. 왼쪽에서**설정**을 선택한 다음 **서비스 &amp; 추가 기능**을 선택합니다.

3. **Office 365 그룹**을 선택합니다.

     ![설정에서 Office 365 그룹의 스크린샷](media/authorize-guest-image2.png)
  
4. Office 365 그룹 페이지에서 조직 외부의 팀 및 그룹 소유자가 Office 365 그룹에 액세스 할 수 있도록 허용할지에 따라 전환을 **설정** 또는 **해제**로 설정합니다. **그룹 소유자가 조직 외부의 사람들을 그룹에 추가하도록 허용** 옆의 토글을 **켬**으로 설정하거나 탭합니다. 이 토글을 **켬**으로 설정하면 그룹 및 팀 소유자가 조직 외부의 사용자를 Office 365 그룹 및 Microsoft Teams에 추가할 수 있도록 할지 여부를 제어하는 다른 옵션이 표시됩니다. 그룹 및 팀 소유자에게 게스트 사용자를 추가할 수 있도록 허용하려면 이 토글을 **켬**으로 설정합니다. 
 
   ![옵션이 설정된 Office 365 그룹 패널의 스크린 샷](media/authorize-guest-image3.png)

이러한 설정은 테넌트 수준에서 적용되며 Office 365 그룹 및 팀에서 게스트 환경을 제어합니다.

게스트 액세스 작동 방식, 게스트 액세스 관리 방법, 자주 묻는 질문에 대한 답변 등 그룹의 게스트 액세스에 대한 자세한 내용은 [Office 365 그룹의 게스트 액세스](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)를 참조합니다.

## <a name="control-guest-access-to-sharepoint-online-and-onedrive-for-business"></a>SharePoint Online 및 비즈니스용 OneDrive에 대한 게스트 액세스 제어

Teams는 SharePoint Online 및 비즈니스용 OneDrive를 사용하여 채널 및 채팅 대화를 위한 파일과 문서를 저장합니다.  

전체 Teams 게스트 액세스 환경을 위해서는 Office 365 관리자가 다음 설정을 구성해야 합니다.

- SharePoint Online에서 **기존 게스트**, **신규 및 기존 게스트** 또는 모두를 선택합니다.

    자세한 내용은 [외부 공유 설정 또는 해제](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)를 참조하세요.

- Office 365 그룹에서 **그룹 소유자가 조직 외부의 사람을 그룹에 추가하도록 허용** 설정

    자세한 내용은 위의 [Office 365 그룹에서 게스트 액세스 제어](#control-guest-access-in-office-365-groups)를 참조하세요.
  
이러한 설정은 테넌트 수준에서 적용되며 SharePoint Online, 비즈니스용 OneDrive, Office 365 그룹 및 Teams에서 게스트 환경을 제어합니다.

Teams에 연결된 팀 사이트의 SharePoint Online 외부 사용자 설정을 관리할 수 있습니다. 자세한 내용은 [SharePoint 팀 사이트 설정 관리](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42)를 참조하세요.

## <a name="external-access-federation-vs-guest-access"></a>외부 액세스 (페더레이션) 및 게스트 액세스

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="related-topics"></a>관련 항목

- [Microsoft 365 게스트 공유 설정 참조](https://docs.microsoft.com/Office365/Enterprise/microsoft-365-guest-settings)
