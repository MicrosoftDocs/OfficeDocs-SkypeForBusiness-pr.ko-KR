---
title: Microsoft Teams 관리자 역할을 사용하여 Teams 관리
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: 관리 역할을 사용하여 Teams를 관리하기 위해 다양한 수준의 액세스가 필요한 관리자를 지정하는 방법을 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 17a8f6e9475355a5ee0f8960294bf3589d228ed1
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615454"
---
# <a name="use-microsoft-teams-administrator-roles-to-manage-teams"></a>Microsoft Teams 관리자 역할을 사용하여 Teams 관리

Azure AD(Azure Active Directory)를 사용하여 Microsoft Teams를 관리하기 위해 다양한 수준의 액세스가 필요한 관리자를 지정할 수 있습니다. 관리자는 전체 Teams 워크로드를 관리하거나 통화 품질 문제를 해결하거나 조직의 전화 통신 요구 사항을 관리하기 위한 위임된 권한을 가질 수 있습니다.

## <a name="teams-roles-and-capabilities"></a>Teams 역할 및 기능

Teams 관리자, Teams 커뮤니케이션 관리자, Teams 커뮤니케이션 지원 전문가, Teams 커뮤니케이션 지원 엔지니어 및 Teams 디바이스 관리자 등 여러 Teams 관리자 역할이 있습니다. 다음 표를 검토하여 각 역할이 수행할 수 있는 작업과 관리자가 Microsoft Teams 관리 센터 및 PowerShell에서 사용할 수 있는 도구를 이해합니다.

> [!NOTE]
> 비즈니스용 Skype Online 관리자는 PowerShell을 통해 **Teams** 및 **비즈니스용 Skype Online** 앱 정책을 관리할 수 있습니다.

따라가려면 관리자여야 합니다. 사용 권한을 가져오기 위한 지침은 이 문서에 있습니다.

<!-- add Global admin role? -->

| 역할                                    | 이러한 작업을 수행할 수 있습니다.                                                           | 다음 도구에 액세스할 수 있습니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-----------------------------------------|------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Teams 관리자             | Teams 서비스를 관리하고 Microsoft 365 그룹 관리하고 만듭니다.        | 다음을 포함하여 Microsoft Teams 관리 센터 및 관련 PowerShell 컨트롤의 모든 항목:<ul><li> 모임 정책, 구성 및 회의 브리지를 포함하여 모임을 관리합니다. <sup>1,2</sup></li><li>통화 정책, 전화 번호 인벤토리 및 할당을 포함하여 음성을 관리합니다. <sup>1,3</sup></li><li>메시징 정책을 포함하여 메시징을 관리합니다. <sup>1,2</sup></li><li>페더레이션, 팀 업그레이드 및 팀 클라이언트 설정을 비롯한 모든 조직 전체 설정을 관리합니다. <sup>1,2</sup></li><li>구성원 자격(PowerShell을 통해 지원되는 그룹 관리, Teams 관리 센터의 팀 관리)을 포함하여 조직의 팀 및 관련 설정을 관리합니다. <sup>1,2</sup></li><li>Teams 인증 디바이스를 관리하고 구성 정책을 설정하고 할당합니다. <sup>1</sup></li><li>고급 문제 해결 도구 집합을 사용하여 사용자 프로필 페이지를 보고 사용자 통화 품질 문제를 해결합니다. <sup>2</sup> </li><li>Microsoft Teams 관리 센터의 모든 보고서에 액세스</li><li> 통화 품질 저하의 영향을 받는 사용자에게 CQD(통화 품질 대시보드)에 노출된 데이터를 사용하여 테넌트의 통화 품질 및 안정성에 액세스, 모니터링 및 문제를 해결합니다. 필요에 따라 새 통화 품질 보고서를 만들고, 통화 품질 보고서를 업데이트하고 제거합니다. CQD 빌드 데이터를 업로드하고 업데이트합니다.</li><li> [Microsoft Teams 관리 센터의 테넌트 앱 카탈로그에 앱 게시](manage-apps.md)</li></ul> |
| Teams 커뮤니케이션 관리자      | Teams 서비스 내에서 통화 및 모임 기능을 관리합니다.               | 모임 정책, 구성 및 회의 브리지를 포함하여 모임을 관리합니다. <sup>1,2</sup><br><br> 통화 정책, 전화 번호 인벤토리 및 할당을 포함하여 음성을 관리합니다. <sup>1,3</sup><br><br> 고급 문제 해결 도구 집합을 사용하여 사용자 프로필 페이지를 보고 사용자 통화 품질 문제를 해결합니다. <sup>2</sup> <br><br> 통화 품질 저하의 영향을 받는 사용자에게 CQD(통화 품질 대시보드)에 노출된 데이터를 사용하여 테넌트의 통화 품질 및 안정성에 액세스, 모니터링 및 문제를 해결합니다. 필요에 따라 새 통화 품질 보고서를 만들고, 통화 품질 보고서를 업데이트하고 제거합니다. CQD 빌드 데이터를 업로드하고 업데이트합니다.|
| Teams 커뮤니케이션 지원 엔지니어   | **고급** 도구를 사용하여 Teams 내의 통신 문제를 해결합니다. | 고급 문제 해결 도구 집합을 사용하여 사용자 프로필 페이지를 보고 사용자 통화 품질 문제를 해결합니다. <sup>2</sup> <br><br> 통화 품질 저하의 영향을 받는 사용자에게 CQD(통화 품질 대시보드)에 노출된 데이터를 사용하여 테넌트의 통화 품질 및 안정성에 액세스, 모니터링 및 문제를 해결합니다. |
| Teams 커뮤니케이션 지원 전문가 | **기본** 도구를 사용하여 Teams 내의 통신 문제를 해결합니다.    | 통화 분석에서 호출 문제를 해결하기 위한 사용자 프로필 페이지에 액세스합니다. 검색할 특정 사용자에 대한 사용자 정보만 볼 수 있습니다. <sup>2</sup> <br><br> CQD(통화 품질 대시보드)에 노출된 데이터를 사용하여 테넌트의 통화 품질 및 안정성에 액세스, 모니터링 및 문제를 해결합니다. |
| Teams 디바이스 관리자              | Teams 서비스에 사용하도록 구성된 디바이스를 관리합니다.                    | 디바이스 구성 및 업데이트를 관리하고, 디바이스 상태 및 연결된 주변 장치의 상태를 검토하고, 구성 프로필을 설정 및 적용하고, 디바이스를 다시 시작합니다.<p>Teams 디바이스 관리자 역할은 통화 품질 데이터 또는 통화 분석에 대한 액세스를 제공하지 않습니다. 통화 품질 데이터를 보거나 분석을 호출하려면 Teams Communications 관리자 역할이 할당되어야 합니다. |

<sup>1</sup> [PowerShell - Microsoft Teams 모듈](https://www.powershellgallery.com/packages/MicrosoftTeams/)(공개 릴리스 1.1.6 이상은 비즈니스용 Skype Online Connector와 통합됩니다.)<br>
<sup>2</sup> [Microsoft Teams 관리 센터](./manage-teams-skypeforbusiness-admin-center.md)
<sup>3</sup> Teams 관리자 계정에 유효한 Teams 라이선스가 있어야 합니다.
<!-- <sup>3</sup> Azure Active Directory admin center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
<sup>4</sup> Microsoft 365 Admin Center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
-->
Microsoft Teams를 관리하는 데 사용할 수 있는 관리 도구에 대한 자세한 내용은 [Microsoft Teams 관리를 참조하세요](./manage-teams-skypeforbusiness-admin-center.md).

Teams에 적용되는 제한, 사양 및 기타 요구 사항에 대한 자세한 내용은 [Microsoft Teams의 제한 및 사양을 참조하세요](limits-specifications-teams.md).

## <a name="assign-users-to-each-role"></a>각 역할에 사용자 할당

Azure AD 이러한 역할에 사용자를 할당할 수 있습니다. Azure AD 사용자에게 관리 역할을 할당하는 방법을 알아보려면 [Azure Active Directory에서 관리자 역할에 사용자 할당을 참조하세요](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).

## <a name="cmdlets-available-for-each-role"></a>각 역할에 사용할 수 있는 Cmdlet

이러한 관리자 역할에 대한 대부분의 PowerShell 도구는 Teams PowerShell 모듈에 있으며, 이러한 관리자 역할이 비즈니스용 Skype Online에도 사용되는 공유 설정을 제어할 수 있는 액세스 권한이 있는 cmdlet 중 일부에 유의해야 합니다. 

cmdlet의 전체 목록을 보려면 다음을 수행합니다.

```powershell
Get-Command -Module MicrosoftTeams
 ```

### <a name="related-articles"></a>관련 기사

- [Microsoft Teams PowerShell 개요](teams-powershell-overview.md)
- [Microsoft Teams PowerShell](/powershell/module/teams/)
- [Microsoft Teams에서 팀 소유자 및 구성원 할당](./assign-roles-permissions.md)
