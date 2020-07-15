---
title: Microsoft 팀에서 파일 공유
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: haagaraw
audience: admin
search.appverid: MET150
description: Microsoft 팀의 파일 공유 환경에 대해 알아보세요.
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 98935f7d8629e22b733b12f3f046ccb7af36b396
ms.sourcegitcommit: 70b80892a152f86a6d596f0f5b58cf391bc29098
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138384"
---
# <a name="sharing-files-in-microsoft-teams"></a>Microsoft 팀에서 파일 공유

Microsoft 팀에서 사용자는 조직의 내부 및 외부에 있는 다른 팀 사용자와 콘텐츠를 공유할 수 있습니다. 팀에서 공유 하는 작업은 SharePoint 및 OneDrive에서 구성 된 설정을 기반으로 하므로 SharePoint와 OneDrive에 대해 설정 하는 모든 작업은 팀의 공유를 제어 합니다.

## <a name="overview"></a>개요

사용자는 OneDrive, 액세스 권한이 있는 팀 및 사이트, 컴퓨터에서 파일을 공유할 수 있습니다. 파일을 공유 하기 위해 사용자는 다음을 수행할 수 있습니다.

- 채널에서 **첨부** (클립 아이콘)를 클릭 하 고 **최근**, **팀 및 채널**, **OneDrive**또는 **내 컴퓨터에서 업로드**를 선택 하 고 공유 하려는 파일을 선택 합니다. <br> 
    ![채널에서 파일을 공유 하는 방법을 보여 주는 스크린샷](media/share-files-channel.png)
- 채팅에서 **첨부** (클립 아이콘)를 클릭 하 고 **내 컴퓨터에서** **OneDrive** 또는 업로드를 선택한 다음 공유 하려는 파일을 선택 합니다. <br>
    ![채팅에서 파일을 공유 하는 것을 보여 주는 스크린샷](media/share-files-chat.png)
- 작성 상자에 공유 링크를 복사 하 여 붙여 넣습니다.<br>
    ![작성 상자에 파일 미리 보기를 표시 하는 스크린샷](media/share-files-link.png)

### <a name="what-you-need-to-know-about-the-file-sharing-experience"></a>파일 공유 환경에 대해 알아야 할 사항

### <a name="permissions-of-shared-files-and-sharing-links"></a>공유 파일 및 공유 링크의 사용 권한

사용자가 OneDrive 또는 팀과 채널에서 파일을 공유할 때 [조직 수준에서 설정 된 기본 사용 권한과](https://docs.microsoft.com/sharepoint/change-default-sharing-link)함께 모든 받는 사람에 게 액세스 권한이 부여 됩니다.

사용자가 공유 링크를 복사 하 여 붙여 넣으면 해당 공유 링크에 설정 된 사용 권한이 유지 되 고 SharePoint URL이 파일 이름으로 짧아집니다. 즉, 팀은 파일 이름만 사용 하 여 파일에 연결 합니다.

사용자가 팀 내에서 파일을 공유 하는 경우 Microsoft 365에서와 마찬가지로 파일에 액세스할 수 있는 사용자를 설정할 수 있습니다. 이러한 사용자는 조직의 모든 사용자, 기존 액세스 권한이 있는 사용자 또는 특정 사용자 (1:1 채팅, 그룹 채팅 또는 채널에 사람을 포함할 수 있음)에 대 한 액세스 권한을 부여할 수 있습니다.  파일을 공유 하는 경우에는 메시지에서 파일 미리 보기를 사용할 수 있으며, **온라인 열기**, **다운로드**, **복사 링크**등의 모든 파일 작업을 할 수 있습니다. 기본적으로 파일은 팀에서 열립니다. 경우에 따라 공유 링크는 사용자가 메시지를 보낼 때 파일 미리 보기로 전환 되지 않았을 수 있습니다. 시스템에서 파일 미리 보기를 생성 하지만이 시나리오에서는 공유 링크가 파일 이름 으로만 단축 되지 않습니다.

사용자가 채팅 또는 채널에서 파일을 공유 하는 경우 일부 또는 모든 받는 사람이 파일을 볼 수 있는 권한이 없는지에 대 한 알림이 표시 됩니다. 메시지에 표시 되는 파일 미리 보기 옆에 있는 화살표를 클릭 하 여 공유 하기 전에 해당 파일에 대 한 사용 권한을 변경할 수 있습니다.

![받는 사람에 게 사용 권한이 없는 경우 알림 스크린샷](media/share-files-permissions.png)

### <a name="copy-a-sharing-link-in-teams"></a>팀에서 공유 링크 복사

사용자는 Microsoft 365에서와 마찬가지로 SharePoint 공유 링크를 복사 하 고 공유 권한을 변경할 수 있습니다. 사용자는 조직의 모든 사용자, 기존 액세스 권한이 있는 사용자 또는 특정 사용자에 게 액세스 권한을 부여할 수 있습니다. 링크의 기본 권한은 SharePoint 사이트 수준 사용 권한이이를 재정의 하지 않는 한 조직 수준의 기본 사용 권한 집합과 동일 합니다.

## <a name="configure-sharing-in-onedrive-and-sharepoint"></a>OneDrive 및 SharePoint에서 공유 구성

공유 구성 방법, 공유 설정 및 해제 방법을 비롯 하 여 OneDrive 및 SharePoint에서 파일을 공유 하는 방법에 대 한 자세한 내용은 다음을 참조 하세요.

- [외부 공유 개요](https://docs.microsoft.com/sharepoint/external-sharing-overview) -사용자가 공유 하는 항목 및 상대에 따라 공유할 때 발생 하는 상황을 설명 합니다.

- [공유 설정 관리](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) -전역 및 sharepoint 관리자가 Sharepoint 및 OneDrive에 대 한 조직 수준의 공유 설정을 변경 하는 방법에 대해 설명 합니다.

- [사이트에 대해 외부 공유 설정 또는 해제](https://docs.microsoft.com/sharepoint/change-external-sharing-site) -전역 및 SharePoint 관리자가 사이트에 대해 외부 공유를 설정 하거나 해제 하는 방법에 대해 설명 합니다.

- [사이트의 기본 링크 종류 변경](https://docs.microsoft.com/sharepoint/change-default-sharing-link) -기본 링크 종류를 더 엄격 하 게 설정 하는 방법에 대해 설명 합니다.

## <a name="more-information"></a>추가 정보

- [SharePoint Online 및 비즈니스용 OneDrive가 Microsoft 팀과 상호 작용 하는 방법](sharepoint-onedrive-interact.md)

- [SharePoint 및 팀: 함께 개선](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)

- [OneDrive 파일 및 폴더 공유](https://support.office.com/article/Share-OneDrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07#OS_Type=OneDrive_-_Business)

- [SharePoint 파일 또는 폴더 공유](https://support.office.com/article/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c)
