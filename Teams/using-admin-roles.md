---
title: Microsoft Teams 관리자 역할을 사용하여 Teams 관리
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 09/19/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.errorpage.needadminpermsforadmincenter.assignadminrolesarticle
- ms.teamsadmincenter.errorpage.needadminperms.assignadminrolesarticle
- ms.teamsadmincenter.signin.error.nopermissions
- ms.teamsadmincenter.directrouting.cqd
- seo-marvel-apr2020
ms.reviewer: islubin
description: 관리 역할을 사용하여 관리자를 관리하기 위해 다양한 수준의 액세스가 필요한 관리자를 Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: c227abe677d75d06fd6577ccbfc8057c82f00002
ms.sourcegitcommit: 39378888464ade3cb45879a449143f40f202f3e9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2022
ms.locfileid: "64456961"
---
# <a name="use-microsoft-teams-administrator-roles-to-manage-teams"></a>Microsoft Teams 관리자 역할을 사용하여 Teams 관리

Azure AD(Azure Active Directory)를 사용하여 관리자를 관리하기 위해 다양한 수준의 액세스가 필요한 관리자를 Microsoft Teams. 관리자는 전체 Teams 관리할 수 있습니다. 또는 통화 품질 문제 해결 또는 조직의 전화 통신 요구 사항을 관리하기 위한 위임된 권한을 부여할 수 있습니다.

## <a name="teams-roles-and-capabilities"></a>Teams 및 기능

사용 가능한 Teams 관리자, Teams 통신 관리자 Teams, Teams 통신 지원 전문가, Teams 통신 지원 엔지니어 및 Teams 관리자 역할이 있습니다. 다음 표를 검토하여 각 역할이 할 수 있는 작업 및 관리자가 관리 센터 및 PowerShell에서 사용할 수 있는 Microsoft Teams 이해합니다.

> [!NOTE]
> 비즈니스용 Skype Online 관리자는 PowerShell을 통해 Teams 비즈니스용 Skype  **모든 온라인** 앱 정책을 관리할 수 있습니다.

따라 가기 위해 관리자 되어야 합니다. 사용 권한을 부여하는 지침은 이 문서에 있습니다.

<!-- add Global admin role? -->

| 역할                                    | 이러한 작업을 수행할 수 있습니다.                                                           | 다음 도구에 액세스할 수 있습니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-----------------------------------------|------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Teams 관리자             | 서비스 Teams 관리하고 그룹 관리 및 Microsoft 365 합니다.        | 다음을 포함하여 Microsoft Teams 관리 센터 및 연결된 PowerShell 컨트롤의 모든 것:<ul><li> 모임 정책, 구성 및 회의 브리지를 포함하여 모임을 관리합니다. <sup>1,2</sup></li><li>통화 정책 및 전화 번호 인벤토리 및 할당을 포함하여 음성을 관리합니다. <sup>1,3</sup></li><li>메시징 정책을 포함하여 메시징을 관리합니다. <sup>1,2</sup></li><li>페더리, 팀 업그레이드 및 팀 클라이언트 설정을 포함하여 모든 구성 전체 설정을 관리합니다. <sup>1,2</sup></li><li>멤버 자격(PowerShell을 통해 지원되는 그룹 관리, 관리 센터의 팀 관리)을 포함하여 조직 Teams 관리합니다.<sup> 1,2</sup></li><li>인증 Teams 디바이스를 관리하고 구성 정책을 설정하고 할당합니다.<sup> 1</sup></li><li>고급 문제 해결 도구세트에서 사용자 프로필 페이지를 보고 사용자 통화 품질 문제를 해결합니다. <sup>2</sup> </li><li>관리 센터의 Microsoft Teams 액세스</li><li> CQD(통화 품질 대시보드)에 노출된 데이터를 사용하여 테넌트의 통화 품질 및 안정성에 액세스, 모니터링 및 문제 해결 필요한 경우 새 통화 품질 보고서를 만들고, 통화 품질 보고서를 업데이트하고 제거합니다. 업로드 CQD 빌딩 데이터를 업데이트하고 업데이트합니다.</li><li> [관리 센터에서 테넌트 앱 카탈로그에 Microsoft Teams 게시](manage-apps.md)</li></ul> |
| Teams 커뮤니케이션 관리자      | 서비스 내에서 통화 및 모임 Teams 관리합니다.               | 모임 정책, 구성 및 회의 브리지를 포함하여 모임을 관리합니다. <sup>1,2</sup><br><br> 통화 정책 및 전화 번호 인벤토리 및 할당을 포함하여 음성을 관리합니다. <sup>1,3</sup><br><br> 고급 문제 해결 도구세트에서 사용자 프로필 페이지를 보고 사용자 통화 품질 문제를 해결합니다. <sup>2</sup> <br><br> CQD(통화 품질 대시보드)에 노출된 데이터를 사용하여 테넌트의 통화 품질 및 안정성에 액세스, 모니터링 및 문제 해결 필요한 경우 새 통화 품질 보고서를 만들고, 통화 품질 보고서를 업데이트하고 제거합니다. 업로드 CQD 빌딩 데이터를 업데이트하고 업데이트합니다.|
| Teams 커뮤니케이션 지원 엔지니어   | 고급 도구를 사용하여 Teams 통신 문제를 **해결** 합니다. | 고급 문제 해결 도구세트에서 사용자 프로필 페이지를 보고 사용자 통화 품질 문제를 해결합니다. <sup>2</sup> <br><br> CQD(통화 품질 대시보드)에 노출된 데이터를 사용하여 테넌트의 통화 품질 및 안정성에 액세스, 모니터링 및 문제 해결 |
| Teams 통신 지원 전문가 | 기본 도구를 사용하여 Teams 통신 문제를 **해결** 합니다.    | Call Analytics에서 호출 문제 해결을 위해 사용자 프로필 페이지에 액세스합니다. 검색되는 특정 사용자의 사용자 정보만 볼 수 있습니다. <sup>2</sup> <br><br> CQD(통화 품질 대시보드)에 노출된 데이터를 사용하여 테넌트의 통화 품질 및 안정성에 액세스, 모니터링 및 문제 해결 |
| Teams 장치 관리자              | 서비스에서 사용하도록 구성된 Teams 관리합니다.                    | 디바이스 구성 및 업데이트를 관리하고, 연결된 주변 장치의 디바이스 상태 및 상태를 검토하고, 구성 프로필을 설정하고 적용하고, 디바이스를 다시 시작합니다.<p>디바이스 Teams 역할은 품질 데이터 또는 호출 분석에 대한 액세스 권한을 제공하지 않습니다. 통화 품질 데이터 또는 통화 분석을 보기 위해 통신 관리자 역할에 Teams 할당해야 합니다. |

<sup>1</sup> [PowerShell -](https://www.powershellgallery.com/packages/MicrosoftTeams/) Microsoft Teams 모듈(공개 릴리스 1.1.6 이상은 온라인 커넥터와 비즈니스용 Skype 통합됩니다.)<br>
<sup>2</sup> [Microsoft Teams 관리자](./manage-teams-skypeforbusiness-admin-center.md)
 Teams 관리자 계정에 유효한 Teams 있어야 합니다.<sup></sup>
<!-- <sup>3</sup> Azure Active Directory admin center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
<sup>4</sup> Microsoft 365 Admin Center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
-->
관리에 사용할 수 있는 관리 도구에 대한 자세한 내용은 Microsoft Teams 관리 [Microsoft Teams.](./manage-teams-skypeforbusiness-admin-center.md)

제한, 사양 및 기타 요구 사항에 대한 자세한 내용은 Teams 제한 및 사양을 [Microsoft Teams](limits-specifications-teams.md).

## <a name="assign-users-to-each-role"></a>각 역할에 사용자 할당

Azure AD에서 이러한 역할에 사용자를 할당할 수 있습니다. Azure AD의 사용자에게 관리 역할을 할당하는 방법에 대한 자세한 내용은 관리자 역할에 [사용자 할당을 Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).

## <a name="cmdlets-available-for-each-role"></a>각 역할에 사용할 수 있는 Cmdlet

이러한 관리자 역할에 대한 PowerShell 도구의 대부분은 PowerShell Teams PowerShell 모듈에 있으며, 이러한 관리자 역할의 일부 cmdlet은 온라인에 사용되는 공유 설정을 제어하는 비즈니스용 Skype 있습니다. 

cmdlet의 전체 목록을 표시하는 경우:

```powershell
Get-Command -Module MicrosoftTeams
 ```

### <a name="related-articles"></a>관련 기사

- [Microsoft Teams PowerShell 개요](teams-powershell-overview.md)
- [Microsoft Teams PowerShell](/powershell/module/teams/)
- [Microsoft Teams에서 팀 소유자 및 구성원 할당](./assign-roles-permissions.md)
