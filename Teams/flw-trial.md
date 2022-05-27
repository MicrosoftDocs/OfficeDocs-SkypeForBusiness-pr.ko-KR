---
title: Teams 최전방 평가판 관리
author: daisyfell
ms.author: daisyfeller
ms.reviewer: samanro
manager: pamgreen
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 조직의 일선 작업자 평가판에 대한 90일 Teams 설정하는 방법을 알아봅니다.
ms.localizationpriority: medium
ms.collection:
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 098cb4cd84616a9b26ea7df5c1451219fd5b5f0e
ms.sourcegitcommit: 8ce73ea99be607f5cdccb22a5366bc96e8fb09c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2022
ms.locfileid: "65758303"
---
# <a name="manage-the-frontline-trial-in-teams"></a>Teams 최전방 평가판 관리

> [!NOTE]
> 이 평가판 환경은 곧 제공될 예정입니다. Microsoft 365 관리 [센터의 메시지 센터에서](https://go.microsoft.com/fwlink/p/?linkid=2070717) 메시지를 찾아 조직에서 사용할 수 있는 시기를 확인할 수 있습니다.

Microsoft Teams 일선 평가판 환경을 통해 조직의 사용자는 다른 구성원이 Azure Active Directory(Azure AD) 있는 한 Teams 전체 최전방 팀에 대한 Teams 환경을 시작할 수 있습니다. [AllowSelfServicePurchase PowerShell 모듈](/microsoft-365/commerce/subscriptions/allowselfservicepurchase-powershell)을 사용하여 조직의 사용자에 대해 이 기능을 사용하지 않도록 설정할 수 있습니다.

## <a name="what-services-are-included"></a>포함된 서비스

평가판에는 다음과 같은 예외가 있는 [Microsoft 365 F3 라이선스](https://www.microsoft.com/microsoft-365/enterprise/f3)의 모든 항목이 포함됩니다.

- 최전방 평가판에는 키오스크를 Exchange 대신 Exchange 재단이 포함됩니다. 이 변경으로 인해 사용자에게 다른 Teams 기능이 누락될 수 있습니다.

## <a name="eligibility"></a>자격

> [!NOTE]
> Microsoft 365 관리 [센터의 메시지 센터에서](https://go.microsoft.com/fwlink/p/?linkid=2070717) 알림을 검색하여 조직이 평가판 파일럿의 일부인지 확인할 수 있습니다. 사용자가 평가판을 시작하거나 참여하려면 조직에서 평가판 파일럿의 일부가 되어야 합니다. 이 서비스는 GCC, GCC High, DoD 또는 EDU 고객에게는 제공되지 않습니다.

최전방 평가판은 평가판당 최대 300명의 사용자를 수용할 수 있습니다.

사용자는 다음과 같은 경우 팀의 최전방 평가판을 시작할 수 있습니다.

- Teams 대한 액세스 권한을 제공하는 활성 라이선스가 있어야 합니다.
- 이전에 일선 작업자 재판을 시작하지 않았습니다.

> [!IMPORTANT]
> 평가판을 시작한 사용자가 평가판이 끝나기 전에 조직을 떠나는 경우 관리자는 평가판을 모니터링하고, 팀에 문의하여 이러한 기능의 혜택을 받는 사용자를 확인하고, 유료 라이선스로 업그레이드해야 하는 사용자를 결정해야 합니다.

사용자는 관리되는 Azure Active Directory 도메인 전자 메일 주소가 있는 경우 일선 작업자 평가판에 참여할 수 있습니다.

사용자가 이전에 평가판을 시작한 경우 참여할 수 있지만 다른 평가판을 시작할 수는 없습니다.

> [!NOTE]
> Teams 대한 기존 액세스 권한이 없는 사용자는 팀 생성 시 평가판 팀에만 추가할 수 있습니다. 팀을 만든 후에도 기존 Teams 사용자를 평가판에 추가할 수 있습니다.

## <a name="set-up-the-trial"></a>평가판 설정

적격 사용자는 데스크톱 또는 [웹앱](https://teams.microsoft.com/_#/apps/com.microsoft.teamspace.tab.planner/sections/mytasks)에서 Teams 작업 앱에 로그인하여 최전방 평가판을 시작할 수 있습니다. 현재 모바일을 통한 최전방 평가판 시작은 지원되지 않습니다. 평가판이 시작되면 전체 팀에 최전방 평가판 라이선스가 자동으로 할당됩니다. Teams 대한 액세스 권한을 부여하는 기존 유료 라이선스가 있는 사용자에게는 평가판 라이선스가 할당되지만 평가판 전체에서 기존 라이선스의 기능을 유지하고 평가판이 종료된 후 기존 유료 라이선스를 유지합니다. 평가판을 시작한 사용자는 평가판 과정 내내 이메일 알림을 받게 됩니다.

## <a name="manage-the-frontline-trials-experience"></a>최전방 평가판 환경 관리

관리자는 **AllowSelfServicePurchase** PowerShell 모듈을 사용하여 최종 사용자가 조직 내에서 최전방 평가판을 시작하지 못하도록 방지할 수 있습니다. 이는 평가판 라이선스에만 해당됩니다. [AllowSelfServicePurchase PowerShell 모듈을 사용하는 방법을 알아봅니](/microsoft-365/commerce/subscriptions/allowselfservicepurchase-powershell)다.

### <a name="manage-teams-for-users-who-have-the-frontline-trial-license"></a>Frontline 평가판 라이선스가 있는 사용자의 Teams 관리

일반 유료 라이선스가 있는 사용자를 관리하는 것처럼 Frontline 평가판 라이선스가 있는 사용자를 관리할 수 있습니다. 자세한 내용은 [조직에서 Teams 설정 관리](/microsoftteams/manage-teams-overview)를 참조하세요.

### <a name="remove-a-trial-license"></a>평가판 라이선스 제거

PowerShell 또는 Microsoft 365 관리 센터 통해 Frontline 평가판 라이선스를 제거할 수 있습니다.

[PowerShell을 사용하여 제거하는 방법을 알아봅니](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)다.

[관리 센터에서 제거하는 방법을 알아봅니다](/microsoft-365/admin/add-users/delete-a-user).

## <a name="upgrade-users-from-frontline-trial"></a>최전방 평가판에서 사용자 업그레이드

사용자는 평가판이 종료되면 사용자에게 연락하여 라이선스를 요청할 수 있습니다. 사용자를 업그레이드하려면 관리자 권한이 필요합니다.

### <a name="when-to-upgrade"></a>업그레이드 시기

90일 평가판이 끝날 무렵, 유료 라이선스를 계속 사용해야 하는 사용자를 사용자에게 확인해야 합니다. 사용자의 환경이 중단되는 것을 방지하려면 Frontline 평가판 구독이 만료되기 전에 이 작업을 수행해야 합니다.

> [!IMPORTANT]
> Frontline 평가판 라이선스가 종료되고 사용자에게 Teams 포함된 라이선스가 즉시 할당되지 않은 경우 Teams 대한 액세스 권한이 손실됩니다. 30일이 지나면 해당 데이터(파일, 메시지 등)가 삭제됩니다. 사용자가 여전히 Azure Active Directory에 있습니다. 30일 이내에 Teams 기능을 사용하도록 사용자에게 새 라이선스가 할당된 경우 Teams 모든 콘텐츠가 계속 존재합니다.

### <a name="choose-an-upgrade-path"></a>업그레이드 경로 선택

> [!TIP]
> 최전방 평가판은 [Microsoft 365 F3 라이선스](https://www.microsoft.com/microsoft-365/enterprise/f3)를 기반으로 합니다.

조직에서 현재 보유하고 있는 구독에 따라 Frontline 평가판에서 유료 라이선스로 업그레이드하는 세 가지 방법이 있습니다.

- **기존 Microsoft 365 구독 업그레이드** 조직에 Teams를 제외한 다른 Office 제품에 대한 구독이 있는 경우 이 옵션을 사용합니다. 자세한 내용은 [다른 플랜으로 업그레이드를 참조하세요](/microsoft-365/commerce/subscriptions/upgrade-to-different-plan). 기존 구독에 대한 활성 사용자를 보려면 Microsoft 365 관리 센터에서 **사용자 >** [활성 사용자](https://go.microsoft.com/fwlink/p/?linkid=834822)로 이동합니다.

- **기존 Microsoft 365 구독에 사용자 추가** 조직에 최전방 팀을 커버하기에 충분한 유료 Teams 라이선스가 없는 경우 이 옵션을 사용합니다. 자세한 내용은 [라이선스 구입 또는 제거](/microsoft-365/commerce/licenses/buy-licenses)를 참조하세요. 사용 가능한 라이선스가 이미 충분한 기존 구독에 사용자를 추가하려면 [사용자를 다른 구독에 이동](/microsoft-365/commerce/subscriptions/move-users-different-subscription)을 참조하세요. 기존 구독에 대한 활성 사용자를 보려면 Microsoft 365 관리 센터에서 **사용자 >** [활성 사용자](https://go.microsoft.com/fwlink/p/?linkid=834822)로 이동합니다.

- **새 Microsoft 365 구독을 구입합니다.** 조직에 Office 제품에 대한 기존 구독이 없거나 조직에서 기존 구독과 다른 구독을 구입하여 일선 사용자를 커버하려는 경우 이 옵션을 사용합니다. 자세한 내용은 [일선 작업자에 대한 Microsoft 365 참조하세요](https://www.microsoft.com/microsoft-365/enterprise/frontline).

업그레이드할 Microsoft 365 구독을 잘 모르는 경우 [일선 작업자에 대한 Microsoft 365 참조하세요](https://www.microsoft.com/microsoft-365/enterprise/frontline). 구독을 선택하는 데 추가 도움이 필요하거나 조직에 300개 이상의 라이선스가 필요한 경우 [Microsoft 파트너](https://www.microsoft.com/solution-providers/home) 또는 Microsoft 계정 담당자에게 문의하세요.

### <a name="assign-paid-licenses"></a>유료 라이선스 할당

새로 획득한 라이선스를 할당하려면 [사용자에게 라이선스 할당](/microsoft-365/admin/manage/assign-licenses-to-users)을 참조하세요.  

새 라이선스를 할당한 후 Teams Exploratory 라이선스의 할당을 취소합니다. 자세한 내용은 [사용자에게서 라이선스 할당 취소](/microsoft-365/admin/manage/remove-licenses-from-users)를 참조하세요.

## <a name="faq"></a>FAQ

**평가판이 얼마나 오래 지속되는지** <br>
최전방 평가판은 90일 동안 지속됩니다.

**관리자는 90일 최전방 평가판 환경이 끝나면 어떻게 해야 하나요?** <br>
90일 평가판이 끝나면 유료 라이선스를 계속 사용해야 하는 사용자를 사용자에게 확인해야 합니다. 그런 다음 [사용자를 업그레이드해야 합니다](#upgrade-users-from-frontline-trial).

**평가판을 시작한 사용자가 조직을 떠나면 어떻게 될까요?** <br>
관리자는 90일 기간의 나머지 기간 동안 평가판을 모니터링하고 평가판이 종료될 때 필요한 사용자를 위해 유료 라이선스로 업그레이드해야 합니다.

**데이터 보존 정책이란?** <br>
[Microsoft 365 구독 정보](/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?)에서 데이터 보존에 대해 알아볼 수 있습니다.

**사용자가 최전방 평가판을 시작할 때 오류가 발생하면 어떻게 해야 할까요?** <br>
조직, 평가판을 시작하는 사용자 및 평가판에 추가되는 사용자가 [자격 기준을](#eligibility) 충족하는지 확인합니다.