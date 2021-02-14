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
description: 관리 역할을 사용하여 Teams를 관리하기 위해 다양한 수준의 액세스 권한이 필요한 관리자를 지정하는 방법을 배워야 합니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 637d6e63b0eabdc9517e8d5cd5986ae7661ad118
ms.sourcegitcommit: 032a22c8b61456dcbd798ec390f0ae1ca7d8eda0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/05/2020
ms.locfileid: "48357616"
---
# <a name="use-microsoft-teams-administrator-roles-to-manage-teams"></a>Microsoft Teams 관리자 역할을 사용하여 Teams 관리

Azure AD(Azure Active Directory)를 사용하여 Microsoft Teams를 관리하기 위해 다양한 수준의 액세스 권한이 필요한 관리자를 지정할 수 있습니다. 관리자는 전체 Teams 워크로드를 관리하거나 통화 품질 문제를 해결하거나 조직의 전화 통신 요구 사항을 관리하기 위한 위임된 권한을 부여할 수 있습니다.

## <a name="teams-roles-and-capabilities"></a>Teams 역할 및 기능

Teams 서비스 관리자, Teams 통신 관리자, Teams 통신 지원 전문가, Teams 통신 지원 엔지니어 및 Teams 장치 관리자와 같은 여러 Teams 관리자 역할을 사용할 수 있습니다. 다음 표를 검토하여 각 역할이 할 수 있는 작업 및 관리자가 Microsoft Teams 관리 센터 및 PowerShell에서 사용할 수 있는 도구를 이해합니다.

따라가기 위해 관리자 권한이 있어야 합니다. 사용 권한을 부여하기 위한 지침은 이 문서에 있습니다.

<!-- add Global admin role? -->

| 역할                                    | 이러한 작업을 수행할 수 있습니다.                                                           | 다음 도구에 액세스할 수 있습니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-----------------------------------------|------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Teams 서비스 관리자             | Teams 서비스를 관리하고 Microsoft 365 그룹을 관리하고 만들 수 있습니다.        | 다음을 포함하여 Microsoft Teams 관리 센터 및 관련 PowerShell 컨트롤의 모든 사항:<ul><li> 모임 정책, 구성 및 회의 브리지를 포함하여 모임을 관리합니다. <sup>1,3</sup></li><li>통화 정책, 전화 번호 인벤토리 및 할당을 포함하여 음성을 관리합니다. <sup>1</sup></li><li>메시징 정책을 포함하여 메시징을 관리합니다. <sup>1,3</sup></li><li>페더맹, 팀 업그레이드 및 팀 클라이언트 설정을 포함하여 모든 전체 설정을 관리합니다. <sup>1,3</sup></li><li>구성원 자격(PowerShell을 통해 지원되는 그룹 관리, Teams 관리 센터의 팀 관리)을 포함하여 조직의 팀 및 관련 설정을 관리합니다. <sup>2,3</sup></li><li>Teams 인증 디바이스를 관리하고 구성 정책을 설정하고 할당합니다. <sup>2</sup></li><li>고급 문제 해결 도구 도구를 사용하여 사용자 프로필 페이지를 보고 사용자 통화 품질 문제를 해결합니다. <sup>3</sup> </li><li>Microsoft Teams 관리 센터에서 모든 보고서에 액세스</li><li> CQD(통화 품질 대시보드)에 노출된 데이터를 사용하여 테넌트의 통화 품질 및 안정성에 액세스, 모니터링 및 문제를 해결하여 낮은 통화 품질의 영향을 미치는 사용자에게 제공합니다. 새 통화 품질 보고서를 만들고, 필요한 경우 통화 품질 보고서를 업데이트하고 제거합니다. CQD 건물 데이터를 업로드하고 업데이트합니다.</li><li> [Microsoft Teams 관리 센터에서 테넌트 앱 카탈로그에 앱 게시](manage-apps.md)</li></ul> |
| Teams 커뮤니케이션 관리자      | Teams 서비스 내에서 통화 및 모임 기능을 관리합니다.               | 모임 정책, 구성 및 회의 브리지를 포함하여 모임을 관리합니다. <sup>1,3</sup><br><br> 통화 정책, 전화 번호 인벤토리 및 할당을 포함하여 음성을 관리합니다. <sup>1</sup><br><br> 고급 문제 해결 도구 도구를 사용하여 사용자 프로필 페이지를 보고 사용자 통화 품질 문제를 해결합니다. <sup>3</sup> <br><br> CQD(통화 품질 대시보드)에 노출된 데이터를 사용하여 테넌트의 통화 품질 및 안정성에 액세스, 모니터링 및 문제를 해결하여 통화 품질이 좋지 않은 사용자에게 제공합니다. 새 통화 품질 보고서를 만들고, 필요한 경우 통화 품질 보고서를 업데이트하고 제거합니다. CQD 건물 데이터를 업로드하고 업데이트합니다.|
| Teams 커뮤니케이션 지원 엔지니어   | 고급 도구를 사용하여 Teams 내의 통신 문제를 **해결합니다.** | 고급 문제 해결 도구 도구를 사용하여 사용자 프로필 페이지를 보고 사용자 통화 품질 문제를 해결합니다. <sup>3</sup> <br><br> CQD(통화 품질 대시보드)에 노출된 데이터를 사용하여 테넌트의 통화 품질 및 안정성에 액세스, 모니터링 및 문제를 해결하여 통화 품질이 좋지 않은 사용자에게 제공합니다. |
| Teams Communications 지원 전문가 | 기본 도구를 사용하여 Teams 내의 통신 문제를 **해결합니다.**    | 통화 분석에서 호출 문제 해결을 위한 사용자 프로필 페이지에 액세스합니다. 검색하는 특정 사용자에 대한 사용자 정보만 볼 수 있습니다.<sup>3</sup> <br><br> CQD(통화 품질 대시보드)에 노출된 데이터를 사용하여 테넌트의 통화 품질 및 안정성에 액세스, 모니터링 및 문제 해결 |
| Teams 장치 관리자              | Teams 서비스에서 사용하도록 구성된 디바이스를 관리합니다.                    | 디바이스 구성 및 업데이트를 관리하고, 연결된 주변 장치의 디바이스 상태 및 상태를 검토하고, 구성 프로필을 설정 및 적용하고, 디바이스를 다시 시작합니다.<p>Teams 장치 관리자 역할은 통화 품질 데이터 또는 통화 분석에 대한 액세스를 제공하지 않습니다. 통화 품질 데이터 또는 통화 분석을 보거나 Teams 통신 관리자 역할을 할당해야 합니다. |

<sup>1</sup> [PowerShell - 비즈니스용 Skype 모듈](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)<br>
<sup>2</sup> [PowerShell - Microsoft Teams 모듈](https://www.powershellgallery.com/packages/MicrosoftTeams/)<br>
<sup>3</sup> [Microsoft Teams 관리 센터](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)
<!-- <sup>4</sup> Azure Active Directory admin center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
<sup>5</sup> Microsoft 365 Admin Center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
-->
Microsoft Teams를 관리하는 데 사용할 수 있는 관리 도구에 대한 자세한 내용은 [Microsoft Teams 관리를 참조하세요.](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)

Teams에 적용되는 제한, 사양 및 기타 요구 사항에 대한 자세한 내용은 Microsoft Teams의 제한 및 [사양을 참조하세요.](limits-specifications-teams.md)

## <a name="assign-users-to-each-role"></a>각 역할에 사용자 할당

Azure AD에서 이러한 역할에 사용자를 할당할 수 있습니다. Azure AD에서 사용자에게 관리 역할을 할당하는 방법에 대한 자세한 내용은 Azure Active Directory에서 관리자 역할에 사용자 [할당을 참조하세요.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)

## <a name="cmdlets-available-for-each-role"></a>각 역할에 사용할 수 있는 Cmdlet

이러한 관리자 역할에 대한 PowerShell 도구는 대부분 비즈니스용 Skype PowerShell 모듈에 있으며, 이러한 관리자 역할이 비즈니스용 Skype Online에도 사용되는 공유 설정을 제어하는 액세스 권한이 있는 일부 cmdlet에 유의해야 합니다. 비즈니스용 Skype 관리자 역할도 비즈니스용 Skype PowerShell 모듈의 모든 cmdlet에 액세스할 수 있습니다.

비즈니스용 Skype PowerShell 모듈에서 현재 제공된 역할에 사용할 수 있는 cmdlet의 전체 목록을 보기 위해 다음 단계를 수행합니다.

1. 사용자에게 해당 역할을 할당합니다(사용자에게 다른 역할이 없는지 확인).
2. 비즈니스용 Skype PowerShell 모듈에 연결합니다.<br>
   a. $session = new-csonlinesession<br>
   b. Import-pssession $session<br>
   c. **Get-Module을** 사용하여 가져온 세션의 이름을 식별합니다(임의로 생성된 이름임).<br>
3. 위의 **Get-Command -Module** 이름을 사용하여>  <  cmdlet을 식별합니다.

### <a name="related-topics"></a>관련 항목

- [Microsoft Teams PowerShell 개요](teams-powershell-overview.md)
- [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)
- [Microsoft Teams에서 팀 소유자와 팀 구성원 할당](https://docs.microsoft.com/microsoftteams/assign-roles-permissions)

