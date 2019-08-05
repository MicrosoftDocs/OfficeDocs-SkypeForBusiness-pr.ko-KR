---
title: 팀 업데이트
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/13/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: annaray
search.appverid: MET150
description: 팀 데스크톱 클라이언트가 업데이트 되는 방법에 대해 알아보세요.
appliesto:
- Microsoft Teams
ms.openlocfilehash: ba5280e03e316dfcde3bda9b62520fa513f3157a
ms.sourcegitcommit: 5faa89ea686448d5b339178f1330edc63e21a52f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2019
ms.locfileid: "36184763"
---
# <a name="teams-update-process"></a>팀 업데이트 프로세스

팀 웹 앱이 매주 업데이트 됩니다.

팀 데스크톱 클라이언트 업데이트는 기술 채택 프로그램을 통해 엄격 하 게 내부 테스트 및 유효성 검사 후 2 주 마다 릴리스됩니다 (탭). 이는 일반적으로 화요일에 발생 합니다. 중요 업데이트가 필요한 경우 팀은이 일정을 무시 하 고 업데이트가 제공 되는 즉시이를 해제 합니다.

데스크톱 클라이언트가 자동으로 업데이트 됩니다. 팀은 백그라운드에서 몇 시간 마다 업데이트를 확인 하 고 다운로드 한 다음 업데이트를 자동으로 설치 하기 전에 컴퓨터가 유휴 상태가 될 때까지 기다립니다.

또한 사용자는 앱 오른쪽 상단의 **프로필** 드롭다운 메뉴에서 **업데이트 확인** 을 클릭 하 여 수동으로 업데이트를 다운로드할 수 있습니다. 업데이트를 사용할 수 있는 경우 컴퓨터가 유휴 상태일 때 다운로드 되 고 자동으로 설치 됩니다.

사용자에 게 업데이트를 다운로드 하려면 로그인 해야 합니다. 

7 월 9 일부터 2019, 팀 클라이언트 업데이트는 업데이트 중에 훨씬 낮은 네트워크 대역폭을 사용 합니다. 이 기능은 기본적으로 설정 되어 있으며 관리자 또는 사용자의 작업이 필요 하지 않습니다.


## <a name="what-about-updates-to-office-365-proplus"></a>Office 365 ProPlus 업데이트에 대 한 자세한 정보

팀은 [office 365 proplus를 사용 하 여 Microsoft 팀 배포](https://docs.microsoft.com/DeployOffice/teams-install)에 설명 된 대로 Office 365 ProPlus의 새 설치와 함께 기본적으로 설치 됩니다. 

팀은 위에 설명 된 대로 자체 업데이트 프로세스를 수행 하 고 Word 및 Excel과 같은 다른 Office 앱에 대 한 업데이트 프로세스를 수행 하지 않습니다. 자세한 내용은 [Office 365 ProPlus의 업데이트 채널에 대 한 개요](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus) 를 읽어 보세요.

## <a name="what-about-updates-to-teams-on-vdi"></a>VDI에서 팀을 업데이트 하는 방법은 무엇 인가요?

VDI (가상 데스크톱 인프라)의 팀 클라이언트는 비 VDI 팀 클라이언트의 방식으로 자동 업데이트 되지 않습니다. [VDI에 팀을 설치](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi)하는 지침에 설명 된 대로 새 MSI를 설치 하 여 VM 이미지를 업데이트 해야 합니다. 최신 버전으로 업데이트 하려면 현재 버전을 제거 해야 합니다.

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>관리자가 팀 자동 업데이트 대신 업데이트를 배포할 수 있나요?

팀은 모든 배달 메커니즘을 통해 관리자에 게 업데이트를 배포 하는 기능을 제공 하지 않습니다.
