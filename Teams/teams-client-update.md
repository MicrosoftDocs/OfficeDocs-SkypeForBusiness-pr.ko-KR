---
title: 팀 업데이트
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: annaray
search.appverid: MET150
f1.keywords:
- NOCSH
description: 팀 데스크톱 클라이언트가 업데이트 되는 방법에 대해 알아보세요.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8058fa1e79b7d415d03c08500213206579029042
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41832618"
---
# <a name="teams-update-process"></a>팀 업데이트 프로세스

팀 웹 앱이 매주 업데이트 됩니다.

팀 데스크톱 클라이언트 업데이트는 기술 채택 프로그램을 통해 엄격 하 게 내부 테스트 및 유효성 검사 후 2 주 마다 릴리스됩니다 (탭). 이는 일반적으로 화요일에 발생 합니다. 중요 업데이트가 필요한 경우 팀은이 일정을 무시 하 고 업데이트가 제공 되는 즉시이를 해제 합니다.

데스크톱 클라이언트가 자동으로 업데이트 됩니다. 팀은 백그라운드에서 몇 시간 마다 업데이트를 확인 하 고 다운로드 한 다음 업데이트를 자동으로 설치 하기 전에 컴퓨터가 유휴 상태가 될 때까지 기다립니다.

또한 사용자는 앱 오른쪽 상단의 **프로필** 드롭다운 메뉴에서 **업데이트 확인** 을 클릭 하 여 수동으로 업데이트를 다운로드할 수 있습니다. 업데이트를 사용할 수 있는 경우 컴퓨터가 유휴 상태일 때 다운로드 되 고 자동으로 설치 됩니다.

사용자에 게 업데이트를 다운로드 하려면 로그인 해야 합니다. 

2019 년 7 월 31 일에 팀 클라이언트 업데이트는 업데이트 중 매우 낮은 네트워크 대역폭을 사용 합니다. 이 기능은 기본적으로 설정 되어 있으며 관리자 또는 사용자의 작업이 필요 하지 않습니다.

## <a name="what-about-updates-to-office-365-proplus"></a>Office 365 ProPlus 업데이트에 대 한 자세한 정보

팀은 [office 365 proplus를 사용 하 여 Microsoft 팀 배포](https://docs.microsoft.com/DeployOffice/teams-install)에 설명 된 대로 Office 365 ProPlus의 새 설치와 함께 기본적으로 설치 됩니다. 

팀은 위에 설명 된 대로 자체 업데이트 프로세스를 수행 하 고 Word 및 Excel과 같은 다른 Office 앱에 대 한 업데이트 프로세스를 수행 하지 않습니다. 자세한 내용은 [Office 365 ProPlus의 업데이트 채널에 대 한 개요](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus) 를 읽어 보세요.

## <a name="what-about-updates-to-teams-on-vdi"></a>VDI에서 팀을 업데이트 하는 방법은 무엇 인가요?

VDI (가상 데스크톱 인프라)의 팀 클라이언트는 비 VDI 팀 클라이언트의 방식으로 자동 업데이트 되지 않습니다. [VDI에 팀을 설치](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi)하는 지침에 설명 된 대로 새 MSI를 설치 하 여 VM 이미지를 업데이트 해야 합니다. 최신 버전으로 업데이트 하려면 현재 버전을 제거 해야 합니다.

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>관리자가 팀 자동 업데이트 대신 업데이트를 배포할 수 있나요?

팀은 모든 배달 메커니즘을 통해 관리자에 게 업데이트를 배포 하는 기능을 제공 하지 않습니다.

## <a name="servicing-agreement"></a>서비스 계약

최신 온라인 서비스인 팀 클라이언트는 2 주 마다 자동으로 업데이트 됩니다. 팀은 최신 수명 주기 정책에 따라 관리 되므로 사용자가 데스크톱 클라이언트의 최신 버전을 그대로 유지 해야 합니다. 이렇게 하면 사용자에 게 최신 기능, 성능 향상, 보안 및 서비스 안정성이 제공 됩니다.

데스크톱 클라이언트가 만료 되는 경우를 식별 하는 기능을 지원 하기 위해 사용자의 현재 버전이 1 개월 이상 이전이 고 사용할 수 있는 새 버전이 있으면 앱에서 경고가 표시 됩니다. 이 앱 내 메시지는 사용자가 최신 버전의 팀으로 업데이트 하거나 필요한 경우 IT 관리자에 게 연락 하 여이 작업을 수행할 수 있도록 합니다. 3 개월 이상 지난 팀 데스크톱 클라이언트의 사용자에 게는 지금 업데이트 하는 옵션을 제공 하는 차단 페이지 (IT 관리자에 게 연락 하거나 웹의 팀으로 계속)가 표시 됩니다.

팀의 첫 번째 설치 및/또는 최초 실행 시 3 개월 이상의 데스크톱 클라이언트 버전이 앞에서 언급 한 서비스 정보를 시작 하기 전에 28 일 유예 기간을 보유 합니다. 이 기간 동안에는 자동 업데이트 프로세스가 팀 클라이언트를 업데이트 합니다. 업데이트 하지 않은 경우 사용자는 앱에서 최신 버전을 수동으로 업데이트 하거나 필요한 경우 IT 관리자에 게 연락 하 여이에 대 한 알림이 표시 됩니다. 여기에는 Office 365 ProPlus 번들의 일부로 팀 데스크톱 클라이언트를 사용 하는 사용자가 포함 됩니다.

현재 정부 클라우드의 팀 데스크톱 클라이언트는 추가 공지에 도달할 때까지이 서비스 계약에 대 한 예외를 발생 합니다.

새 버전 릴리스에 대 한 자세한 내용은 [메시지 센터](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) 를 확인 하거나 클라이언트의**새로운 기능** 에 대 한 **도움말을 참조** > 하세요.
