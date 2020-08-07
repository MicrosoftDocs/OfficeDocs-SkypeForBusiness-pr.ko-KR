---
title: Microsoft 팀 관리자 역할을 사용 하 여 팀 관리
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
description: 관리 역할을 사용 하 여 팀을 관리 하는 데 다른 수준의 액세스가 필요한 관리자를 지정 하는 방법을 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4f9059815e61ff0343f909ef76d03abf904c8bd4
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583537"
---
# <a name="use-microsoft-teams-administrator-roles-to-manage-teams"></a>Microsoft 팀 관리자 역할을 사용 하 여 팀 관리

Azure AD (Active Directory)를 사용 하 여 Microsoft 팀을 관리 하기 위해 다른 수준의 액세스 권한을 필요로 하는 관리자를 지정할 수 있습니다. 관리자는 전체 팀 작업 부하를 관리할 수 있으며, 통화 품질 문제를 해결 하기 위한 권한을 위임 하거나 조직의 전화 통신 요구 사항을 관리할 수 있습니다.

## <a name="teams-roles-and-capabilities"></a>팀 역할 및 기능

팀 서비스 관리자, 팀 통신 관리자, 팀 의사 소통 지원 전문가, 팀 의사 소통 지원 엔지니어가 4 명의 팀 관리자 역할을 사용할 수 있습니다. 다음 표를 검토 하 여 각 역할이 수행할 수 있는 작업과 Microsoft 팀 관리 센터 및 PowerShell에서 관리자가 사용할 수 있는 도구에 대해 알아봅니다.

팔 로우 하려면 관리자 여야 합니다. 이 문서에서는 사용 권한을 얻기 위한 지침이 나와 있습니다.

<!-- add Global admin role? -->

| 역할                                    | 수행할 수 있는 작업                                                           | 다음 도구에 액세스할 수 있습니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-----------------------------------------|------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Teams 서비스 관리자             | 팀 서비스 관리 및 Microsoft 365 그룹 관리 및 만들기            | Microsoft 팀 관리 센터의 모든 내용과 관련 된 PowerShell 컨트롤에는 다음이 포함 됩니다.<ul><li> 모임 정책, 구성, 회의 브리지 등 모임을 관리 합니다. <sup>1, 3</sup></li><li>통화 정책, 전화 번호 목록 및 과제를 포함 하 여 음성 관리 <sup>1</sup></li><li>메시징 정책을 포함 하 여 메시지를 관리 합니다. <sup>1, 3</sup></li><li>페더레이션, 팀 업그레이드, 팀 클라이언트 설정을 비롯 한 모든 조직 차원의 설정을 관리 합니다. <sup>1, 3</sup></li><li>조직에서 팀을 관리 하 고 멤버 자격 (PowerShell을 통해 지원 되는 그룹 관리, 팀 관리 센터의 팀 관리)를 포함 하 여 관련 설정을 관리할 때 <sup>2, 3</sup></li><li>팀 인증 장치를 관리 하 고 구성 정책을 설정 및 할당 합니다. <sup>2</sup></li><li>고급 문제 해결 도구 집합을 사용 하 여 사용자 프로필 페이지를 보고 사용자 통화 품질 문제를 해결 합니다. <sup>3</sup> </li><li>Microsoft 팀 관리 센터의 모든 보고서에 액세스</li><li> 통화 품질 대시보드 (CQD)에 표시 된 데이터를 사용 하 여 테 넌 트의 통화 품질 및 안정성에 액세스 하 고 문제를 해결 하 고 통화 품질이 나쁜 사용자에 게 제공 됩니다. 필요에 따라 통화 품질 보고서를 새로 만들고, 업데이트 하 고, 제거 합니다. CQD 데이터 빌드를 업로드 하 고 업데이트 합니다.</li><li> [Microsoft 팀 관리 센터의 테 넌 트 앱 카탈로그에 앱 게시](manage-apps.md)</li></ul> |
| Teams 커뮤니케이션 관리자      | 팀 서비스 내에서 통화 및 모임 기능을 관리 합니다.               | 모임 정책, 구성, 회의 브리지 등 모임을 관리 합니다. <sup>1, 3</sup><br><br> 통화 정책, 전화 번호 목록 및 과제를 포함 하 여 음성 관리 <sup>1</sup><br><br> 고급 문제 해결 도구 집합을 사용 하 여 사용자 프로필 페이지를 보고 사용자 통화 품질 문제를 해결 합니다. <sup>3</sup><br><br>Microsoft 팀 관리 센터에서 팀 PSTN 차단 사용자 보고서, PSTN 시간 단위 보고서 및 PSTN 사용 보고서에 액세스 합니다. <br><br> 통화 품질 대시보드 (CQD)에 표시 된 데이터를 사용 하 여 테 넌 트의 통화 품질 및 안정성에 액세스 하 고 문제를 해결 하려면 통화 품질이 떨어지는 사용자에 게 문의 하세요. 필요에 따라 통화 품질 보고서를 새로 만들고, 업데이트 하 고, 제거 합니다. CQD 데이터 빌드를 업로드 하 고 업데이트 합니다.|
| Teams 커뮤니케이션 지원 엔지니어   | **고급** 도구를 사용 하 여 팀 내의 통신 문제를 해결 합니다. | 고급 문제 해결 도구 집합을 사용 하 여 사용자 프로필 페이지를 보고 사용자 통화 품질 문제를 해결 합니다. <sup>3</sup> <br><br> 통화 품질 대시보드 (CQD)에 표시 된 데이터를 사용 하 여 테 넌 트의 통화 품질 및 안정성에 액세스 하 고 문제를 해결 하려면 통화 품질이 떨어지는 사용자에 게 문의 하세요. |
| 팀 의사 소통 지원 전문가 | **기본** 도구를 사용 하 여 팀 내의 통신 문제를 해결 합니다.    | 통화 분석에서 전화 문제 해결을 위한 사용자 프로필 페이지 액세스 검색하는 특정 사용자에 대한 사용자 정보만 볼 수 있습니다.<sup>3</sup> <br><br> CQD (통화 품질 대시보드)에서 제공 하는 데이터를 사용 하 여 테 넌 트의 통화 품질 및 안정성에 액세스 하 고 해당 문제를 해결 합니다. |

<sup>1</sup> [PowerShell-비즈니스용 Skype 모듈](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)<br>
PowerShell <sup>2 개</sup> [-Microsoft 팀 모듈](https://www.powershellgallery.com/packages/MicrosoftTeams/)<br>
<sup>3 개의</sup> [Microsoft 팀 관리 센터](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)
<!-- <sup>4</sup> Azure Active Directory admin center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
<sup>5</sup> Microsoft 365 Admin Center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
-->
Microsoft 팀을 관리 하는 데 사용할 수 있는 관리 도구에 대 한 자세한 내용은 [Microsoft 팀 관리](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)를 참조 하세요.

팀에 적용 되는 제한, 사양 및 기타 요구 사항에 대 한 자세한 내용은 [Microsoft 팀에 대 한 제한 및 사양을](limits-specifications-teams.md)참조 하세요.

## <a name="assign-users-to-each-role"></a>각 역할에 사용자 할당

Azure AD에서 이러한 역할에 사용자를 할당할 수 있습니다. Azure AD의 사용자에 게 관리자 역할을 할당 하는 방법에 대 한 자세한 내용은 [Azure Active Directory에서 관리자 역할에 사용자 할당](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)을 참조 하세요.

## <a name="cmdlets-available-for-each-role"></a>각 역할에 대해 제공 되는 cmdlet

이러한 관리자 역할에 대 한 대부분의 PowerShell 도구는 비즈니스용 Skype PowerShell 모듈에 살고 있으며, 이러한 관리자 역할이 비즈니스용 Skype Online에도 사용 되는 공유 설정을 제어 하는 데 액세스할 수 있다는 것을 기억해 야 합니다. 비즈니스용 Skype 관리자 역할은 또한 비즈니스용 Skype PowerShell 모듈의 모든 cmdlet에 액세스할 수 있습니다.

비즈니스용 Skype PowerShell 모듈에서 주어진 역할에 대해 현재 사용할 수 있는 cmdlet의 전체 목록을 보려면 다음 단계를 수행 합니다.

1. 해당 역할을 사용자에 게 할당 하 고 사용자에 게 다른 역할이 없는지 확인 합니다.
2. 비즈니스용 Skype PowerShell 모듈에 연결:<br>
   a. $session = new-csonlinesession<br>
   b. 가져오기-pssession $session<br>
   c. **Get 모듈** 을 사용 하 여 가져온 세션의 이름 (임의로 생성 되는 이름)을 식별 합니다.<br>
3. > 위의 **Get-Command-Module**  < *name* 을 사용 하 여 사용 가능한 모든 cmdlet을 식별 합니다.

### <a name="related-topics"></a>관련 항목

- [Microsoft 팀 PowerShell 개요](teams-powershell-overview.md)
- [Microsoft 팀 PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)
- [Microsoft 팀에서 팀 소유자 및 구성원 지정](https://docs.microsoft.com/microsoftteams/assign-roles-permissions)

