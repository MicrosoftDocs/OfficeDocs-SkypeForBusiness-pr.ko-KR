---
title: Microsoft 365 그룹 및 Microsoft 팀
ms.reviewer: Kyle Blevins
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 04/16/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
description: 이 문서에서는 microsoft 365 그룹 및 그룹 구성원이 Microsoft 팀과 어떻게 작동 하는가에 대해 알아봅니다.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a44adb84cb6669bb96bd617fb52ea9b5fdceb7af
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581129"
---
<a name="microsoft-365-groups-and-microsoft-teams"></a>Microsoft 365 그룹 및 Microsoft 팀
=====================================

> [!Tip]
> Azure AD (azure Active Directory), Microsoft 365 그룹, Exchange, SharePoint 및 비즈니스용 OneDrive와 상호 작용 하는 방법에 대해 알아보려면 다음 세션을 시청 하세요. [Microsoft 팀의 기초](https://aka.ms/teams-foundations)

Microsoft 365 그룹은 Office 365의 응용 프로그램 간 구성원 서비스입니다. 기본 수준에서 Microsoft 365 그룹은 SharePoint 팀 사이트, Yammer 그룹, 공유 Exchange 사서함 리소스, Planner, Power BI, OneNote 등의 관련 작업 부하에 대 한 느슨한 결합, 구성원 목록이 있는 Azure Active Directory의 개체입니다. Active Directory의 다른 그룹 기반 보안 개체와 마찬가지로 그룹에 사용자를 추가 하거나 제거할 수 있습니다.

Office 365 관리자는 Exchange 공유 사서함, SharePoint 문서 라이브러리, Yammer 그룹 등의 기능을 통해 Microsoft 365 그룹을 정의 하 고, 구성원을 추가 하 고, 혜택을 활용할 수 있습니다. Microsoft 365 그룹에 대 한 자세한 내용은 [microsoft 365 그룹에 대 한](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)자세한 정보를 참조 하세요.

[IT 설계자 용 Microsoft 365에서 포스터 그룹](teams-architecture-solutions-posters.md#groups-in-microsoft-365)을 놓치지 마세요.

<a name="how-microsoft-365-groups-work"></a>Microsoft 365 그룹이 작동 하는 방식
--------------------------

팀을 만들 때 백 엔드에서 Microsoft 365 그룹 및 연결 된 SharePoint 문서 라이브러리 및 OneNote 전자 필기장을 다른 Office 365 클라우드 응용 프로그램에 묶는 것과 함께 만듭니다. 팀을 만드는 사람이 기존 Office 365 공용 또는 개인 그룹의 소유자 인 경우 그룹에 팀에 추가 된 적이 없는 5000 경우 해당 사용자는 팀에 기능을 추가할 수 있습니다. 이렇게 하면 채팅 메시지, 문서, OneNote 및 기타 개체가 있는 기본 **일반** 채널이 하나 만들어집니다. 채널에 대 한 문서 라이브러리를 보면 팀에서 채널을 나타내는 **일반** 폴더가 표시 됩니다. 더 중요 한 것은 문서 라이브러리 내에서 고유한 폴더 구조를 만드는 경우 팀에 채널로 **전파 되지 않는다는 것** 입니다. 지금은 팀에서 SharePoint로 이동 합니다.

> [!NOTE]
> Microsoft 팀 클라이언트에서 팀을 만들기 위해 생성 된 새로운 Microsoft 365 그룹은 고객 의견을 기반으로 Outlook에서 기본적으로 더 이상 표시 되지 않습니다. Outlook에서 그룹의 표시를 설정 하거나 해제 하려면 [UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-unifiedgroup) Cmdlet을 **HiddenFromExchangeClientsEnabled** 매개 변수와 함께 사용 합니다. Outlook을 통해 만들어지고 나중에 팀에서 사용 하도록 설정 된 그룹은 Outlook과 팀에 계속 표시 됩니다. 

> [!NOTE]
> Microsoft 365 그룹을 삭제 하면 영구 Outlook/OWA 대화 및 팀 모임 초대에 대 한 사서함 별칭이 제거 되 고 SharePoint 사이트를 삭제 하도록 표시 합니다. 팀을 제거 하는 시간과 Outlook에 미치는 영향 사이에 약 20 분이 걸립니다. 팀 클라이언트에서 팀을 삭제 하면 해당 팀의 구성원 인 모든 사용자가 보기에서 즉시 제거 됩니다. 팀 기능을 사용할 수 있는 Microsoft 365 그룹의 구성원을 제거 하는 경우 팀 클라이언트에서 해당 사용자가 제거 된 영향을 받는 사람을 보기에서 제거 하기 전에 약 2 시간이 지연 될 수 있습니다.
>
>삭제 한 Microsoft 365 그룹 복원에 대 한 자세한 내용은 [여기](https://support.office.com/article/Restore-a-deleted-Office-365-Group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54) 를 참조 하세요.

<a name="group-membership"></a>그룹 구성원
----------------

그룹 구성원을 드라이브에 저장 하는 위치에 따라 사용자의 그룹 기능 및 기능이 달라 집니다. 예를 들어 팀 구성원을 제거 하면 Microsoft 365 그룹 에서도 제거 됩니다. 그룹에서 제거 하면 팀 클라이언트에서 팀과 채널이 즉시 제거 됩니다. Microsoft 365 관리 센터를 사용 하 여 그룹에서 사용자를 제거 하는 경우에는 더 이상 SharePoint Online 문서 라이브러리, Yammer 그룹 또는 공유 OneNote와 같은 다른 공동 작업에 액세스할 수 없습니다. 그러나 약 2 시간 동안 팀의 채팅 기능에 계속 액세스할 수 있습니다.

팀 구성원을 관리 하는 가장 좋은 방법은 팀 클라이언트에서 구성원을 추가 및 제거 하 여 다른 종속 클라우드 응용 프로그램에 대 한 올바른 연속 된 액세스 제어가 적용 되도록 하는 것입니다. 또한 사용자가 사용 하는 리소스에 대 한 액세스 권한을 갖고 있는 (다음 동기화 주기에서 서비스의 특정 구성 요소에 대 한 액세스를 추가 하거나 해지할 때까지) 연결 되지 않은 환경이 유지 됩니다. 팀 클라이언트 (예를 들어 Microsoft 365 관리 센터, Azure AD 또는 Exchange Online PowerShell을 사용 하 여)를 추가 하거나 제거 하는 경우 팀에 변경 내용이 반영 되도록 최대 24 시간 (경우에 따라)까지 걸릴 수 있습니다.

<a name="ability-to-add-group-as-attendee-while-scheduling-meetings"></a>모임을 예약 하는 동안 참석자에 게 그룹을 추가할 수 있는 기능
----------------------------------------------------------

2020 년 5 월부터 시작 하 여 예정 된 모임에 그룹을 초대 하면 다음과 같은 주의 사항이 있습니다.
1. 기존 Microsoft 365 그룹에서 만든 기존의 모든 Microsoft 365 그룹 및 팀은 검색 가능 하며 모임에 추가 될 수 있습니다. 그러나 구성원은 그룹에 대 한 구독을 기준으로 모임 초대를 받습니다.
2. 5 월 2018까지 처음부터 만든 팀은 검색 가능 하지만, 구성원은 자신의 기본 그룹 구독에 대 한 "회신만"을 선택 하 여 모임 초대를 받지 않습니다. 이는 Outlook에서 그룹 설정을 수정 하 여 변경할 수 있습니다.
3. 2018 년 5 월에 처음부터 만든 팀은 검색 가능 하지 않으며 속성 "HiddenFromAddressListsEnabled"을 사용 하 여 숨겨집니다. 관리자가 수정할 수 있는 관리자 제어 설정입니다.
