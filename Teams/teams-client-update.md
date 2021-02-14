---
title: Teams 업데이트
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: annaray
search.appverid: MET150
f1.keywords:
- NOCSH
description: 이 문서에서는 Microsoft Teams 데스크톱 클라이언트를 업데이트하는 프로세스에 대해 배웠습니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f8681f3f4cc7c25e9499e25e3978848084086a2a
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031884"
---
# <a name="teams-update-process"></a>Teams 업데이트 프로세스

Teams 웹앱은 매주 업데이트됩니다.

Teams 데스크톱 클라이언트 업데이트는 TAP(기술 채택 프로그램)를 통해 엄격한 내부 테스트 및 유효성 검사 후 2주마다 릴리스됩니다. 이 시간은 일반적으로 화요일에 진행됩니다. 중요한 업데이트가 필요한 경우 Teams는 이 일정을 무시하고 사용 가능한 즉시 업데이트를 릴리스합니다.

데스크톱 클라이언트는 자동으로 업데이트됩니다. Teams는 몇 시간마다 배후에서 업데이트를 확인하고, 다운로드한 다음, 자동으로 업데이트를 설치하기 전에 컴퓨터가 유휴될 때까지 기다릴 수 있습니다.

또한 사용자는 앱의 오른쪽  위에 있는 프로필  드롭다운 메뉴에서 업데이트 확인을 클릭하여 업데이트를 수동으로 다운로드할 수도 있습니다. 업데이트를 사용할 수 있는 경우 컴퓨터가 유휴일 때 다운로드되어 자동으로 설치됩니다.

업데이트를 다운로드하려면 사용자가 로그인해야 합니다. 

2019년 7월 31일을 시작으로 Teams 클라이언트 업데이트는 업데이트 중에 훨씬 낮은 네트워크 대역폭을 사용합니다. 이 설정은 기본적으로 설정되어 있으며 관리자 또는 사용자의 조치가 필요 없습니다.

## <a name="what-about-updates-to-microsoft-365-apps-for-enterprise"></a>엔터프라이즈용 Microsoft 365 앱 업데이트는 어떻게 하나요?

Teams는 엔터프라이즈용 Microsoft 365 앱을 사용하여 Microsoft Teams 배포에 설명된 엔터프라이즈용 Microsoft [365 앱의](https://docs.microsoft.com/DeployOffice/teams-install)새로운 설치를 통해 기본적으로 설치됩니다. 

Teams는 위에서 설명한 대로 자체 업데이트 프로세스를 따르며 Word 및 Excel과 같은 다른 Office 앱에 대한 업데이트 프로세스는 따르지 않습니다. 자세한 내용은 [엔터프라이즈용 Microsoft 365 앱의](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus) 업데이트 채널 개요를 참조하세요.

## <a name="what-about-updates-to-teams-on-vdi"></a>VDI의 Teams 업데이트는 어떻게 하나요?

VDI(Virtual Desktop Infrastructure)의 Teams 클라이언트는 비 VDI Teams 클라이언트와 같은 방식으로 자동으로 업데이트되지 않습니다. VDI에 Teams를 설치하는 지침에 설명된 새 MSI를 설치하여 [VM 이미지를 업데이트해야 합니다.](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi) 최신 버전으로 업데이트하려면 현재 버전을 제거해야 합니다.

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>관리자가 Teams 자동 업데이트 대신 업데이트를 배포할 수 있나요?

Teams는 배달 메커니즘을 통해 업데이트를 배포하는 기능을 관리자에게 제공하지 않습니다.

## <a name="servicing-agreement"></a>서비스 계약

최신 온라인 서비스인 Teams 클라이언트는 2주마다 자동으로 업데이트됩니다. Teams는 최신 수명 주기 정책이 적용되어 있기 때문에 사용자가 데스크톱 클라이언트의 최신 버전을 유지해야 합니다. 이렇게 하면 사용자가 최신 기능, 성능 향상, 보안 및 서비스 안정성을 사용할 수 있습니다.

데스크톱 클라이언트가 오래된 시간 식별을 시작하기 위해 사용자의 현재 버전이 1개월에서 3개월 사이인 경우와 사용 가능한 새 버전이 있는 경우 앱 내 경고가 표시됩니다. 이 앱 내 메시지는 사용자가 최신 버전의 Teams로 업데이트하거나 필요한 경우 IT 관리자에게 문의하여 업데이트하도록 권장합니다. 3개월이 넘은 Teams 데스크톱 클라이언트의 사용자는 지금 업데이트하거나, IT 관리자에게 문의하거나, 웹의 Teams로 계속할 수 있는 옵션을 제공하는 차단 페이지를 볼 수 있습니다.

Teams를 처음 설치 및/또는 처음 실행할 때 3개월 이상 경과된 데스크톱 클라이언트 버전에는 위에서 언급한 서비스 정보가 발생하기 전에 28일의 유예 기간이 있습니다. 이 기간 동안 자동 업데이트 프로세스는 Teams 클라이언트를 업데이트합니다. 업데이트되지 않은 경우 최신 버전의 Teams로 수동으로 업데이트하거나 필요한 경우 IT 관리자에게 문의하여 업데이트할 수 있도록 하는 앱 내 경고가 표시됩니다. 여기에는 Microsoft 365 Apps for Enterprise 번들의 일부로 Teams 데스크톱 클라이언트를 사용하는 사용자가 포함됩니다.

정부 클라우드의 Teams 데스크톱 클라이언트는 현재 추가 공지까지 이 서비스 계약에 대한 예외가 있습니다.

새 버전 릴리스에 대한 자세한 내용은 [메시지](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) 센터를 확인하거나 클라이언트의 새로운 도움말로   >   이동하세요.
