---
title: Office 365 그룹 및 Microsoft 팀
ms.reviewer: phlouie
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 04/16/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
description: Microsoft 팀에서 Office 365 그룹 및 그룹 구성원을 사용 하는 방법에 대해 알아봅니다.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a0daed292ccccb85c5231242161c75e8cb60949c
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43136498"
---
<a name="office-365-groups-and-microsoft-teams"></a>Office 365 그룹 및 Microsoft 팀
=====================================

> [!Tip]
> Azure AD (azure Active Directory), Office 365 그룹, Exchange, SharePoint 및 비즈니스용 OneDrive와 상호 작용 하는 방법에 대해 알아보려면 다음 세션을 시청 하세요. [Microsoft 팀의 기초](https://aka.ms/teams-foundations)

Office 365 그룹은 Office 365의 응용 프로그램 간 구성원 서비스입니다. 기본 수준에서 Office 365 그룹은 SharePoint 팀 사이트, Yammer 그룹, 공유 Exchange 사서함 리소스, Planner, Power BI, OneNote 등의 관련 작업 부하에 대 한 느슨한 결합, 구성원 목록이 있는 Azure Active Directory의 개체입니다. Active Directory의 다른 그룹 기반 보안 개체와 마찬가지로 그룹에 사용자를 추가 하거나 제거할 수 있습니다.

Office 365 관리자는 Exchange 공유 사서함, SharePoint 문서 라이브러리, Yammer 그룹 등의 기능을 통해 Office 365 그룹을 정의 하 고, 구성원을 추가 하 고, 혜택을 활용할 수 있습니다. Office 365 그룹에 대 한 자세한 내용은 [office 365 그룹에 대 한](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)자세한 정보를 참조 하세요.

[IT 설계자 용 Microsoft 365에서 포스터 그룹](teams-architecture-solutions-posters.md#groups-in-microsoft-365)을 놓치지 마세요.

<a name="how-office-365-groups-work"></a>Office 365 그룹의 작동 방식
--------------------------

팀을 만들 때 백 엔드에서 Office 365 그룹 및 연결 된 SharePoint 문서 라이브러리 및 OneNote 전자 필기장을 다른 Office 365 클라우드 응용 프로그램에 묶는 것과 함께 만듭니다. 팀을 만드는 사람이 기존 Office 365 공용 또는 개인 그룹의 소유자 인 경우 그룹에 팀에 추가 된 적이 없는 5000 경우 해당 사용자는 팀에 기능을 추가할 수 있습니다. 이렇게 하면 채팅 메시지, 문서, OneNote 및 기타 개체가 있는 기본 **일반** 채널이 하나 만들어집니다. 채널에 대 한 문서 라이브러리를 보면 팀에서 채널을 나타내는 **일반** 폴더가 표시 됩니다. 더 중요 한 것은 문서 라이브러리 내에서 고유한 폴더 구조를 만드는 경우 팀에 채널로 **전파 되지 않는다는 것** 입니다. 지금은 팀에서 SharePoint로 이동 합니다.

> [!NOTE]
> Microsoft 팀에서 팀을 만들기 위해 생성 된 새 Office 365 그룹은 고객 의견을 기반으로 Outlook에 더 이상 기본적으로 표시 되지 않습니다. Outlook에서 이러한 그룹을 표시 하는 기존 동작을 계속 하려는 고객의 경우 Outlook 환경을 위해 그룹을 사용할 수 있는 Exchange Online PowerShell cmdlet이 제공 됩니다. Outlook을 통해 만들어지고 나중에 팀에서 사용 하도록 설정 된 그룹은 Outlook과 팀에 계속 표시 됩니다. 이 업데이트는 앞으로 진행 되는 달에 Outlook과 팀 간에 점차적으로 롤아웃 됩니다.

> [!NOTE]
> Office 365 그룹을 삭제 하면 영구 Outlook/OWA 대화 및 팀 모임 초대에 대 한 사서함 별칭이 제거 되 고 SharePoint 사이트를 삭제 하도록 표시 합니다. 팀을 제거 하는 시간과 Outlook에 미치는 영향 사이에 약 20 분이 걸립니다. 팀 클라이언트에서 팀을 삭제 하면 해당 팀의 구성원 인 모든 사용자가 보기에서 즉시 제거 됩니다. 팀 기능을 사용 하도록 설정한 Office 365 그룹의 구성원을 제거 하는 경우 팀 클라이언트에서 해당 사용자가 제거 된 영향을 받는 사람을 보기에서 제거 하기 전에 약 2 시간이 지연 될 수 있습니다.
>
>삭제 한 Office 365 그룹을 복원 하는 방법에 대 한 자세한 내용은 [다음](https://support.office.com/article/Restore-a-deleted-Office-365-Group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54) 을 참조 하세요.

<a name="group-membership"></a>그룹 구성원
----------------

그룹 구성원을 드라이브에 저장 하는 위치에 따라 사용자의 그룹 기능 및 기능이 달라 집니다. 예를 들어 팀 구성원을 제거 하면 Office 365 그룹 에서도 제거 됩니다. 그룹에서 제거 하면 팀 클라이언트에서 팀과 채널이 즉시 제거 됩니다. Microsoft 365 관리 센터를 사용 하 여 그룹에서 사용자를 제거 하는 경우에는 더 이상 SharePoint Online 문서 라이브러리, Yammer 그룹 또는 공유 OneNote와 같은 다른 공동 작업에 액세스할 수 없습니다. 그러나 약 2 시간 동안 팀의 채팅 기능에 계속 액세스할 수 있습니다.

팀 구성원을 관리 하는 가장 좋은 방법은 팀 클라이언트에서 구성원을 추가 및 제거 하 여 다른 종속 클라우드 응용 프로그램에 대 한 올바른 연속 된 액세스 제어가 적용 되도록 하는 것입니다. 또한 사용자가 사용 하는 리소스에 대 한 액세스 권한을 갖고 있는 (다음 동기화 주기에서 서비스의 특정 구성 요소에 대 한 액세스를 추가 하거나 해지할 때까지) 연결 되지 않은 환경이 유지 됩니다. 팀 클라이언트 (예를 들어 Microsoft 365 관리 센터, Azure AD 또는 Exchange Online PowerShell을 사용 하 여)의 구성원을 추가 하거나 제거 하는 경우 변경 내용이 팀에 반영 되는 데 최대 2 시간까지 걸릴 수 있습니다.
