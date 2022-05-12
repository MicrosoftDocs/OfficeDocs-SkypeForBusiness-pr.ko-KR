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
description: 이 문서에서는 Microsoft Teams 데스크톱 클라이언트를 업데이트하는 과정에 대해 알아봅니다.
ms.localizationpriority: high
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a7d296e296b2f5a20b5d7d10da6e598a989f0d71
ms.sourcegitcommit: cd4464fe9bf0f38ed4c3ca058a51bcd29578eef9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2022
ms.locfileid: "65316504"
---
# <a name="teams-update-process"></a>Teams 업데이트 프로세스

Teams 웹앱 업데이트는 일반적으로 매월 넷째 월요일에 릴리스됩니다.

Teams 데스크톱 클라이언트 업데이트는 TAP(기술 채택 프로그램)를 통한 엄격한 내부 테스트 및 유효성 검사를 거쳐 매월 릴리스됩니다. 데스크톱 클라이언트 업데이트는 일반적으로 매월 넷째 월요일에 시작되며 나머지 주 동안 고객에게 점진적으로 배포됩니다. 중요한 업데이트가 필요한 경우 Teams는 이 일정을 건너뛰고 업데이트가 제공되는 즉시 릴리스합니다.

데스크톱 클라이언트는 자동으로 업데이트됩니다. Teams에서는 몇 시간마다 백그라운드에서 업데이트를 확인하고 다운로드한 다음 자동으로 업데이트를 설치하기 전에 컴퓨터가 유휴 상태가 될 때까지 기다립니다.

사용자는 앱 오른쪽 상단의 **프로필** 아이콘 옆에 있는 **...** 드롭다운 메뉴에서 **업데이트 확인** 을 선택하여 업데이트를 수동으로 다운로드할 수도 있습니다. 업데이트가 있는 경우 컴퓨터가 유휴 상태일 때 업데이트가 다운로드되어 자동으로 설치됩니다.

업데이트를 다운로드하려면 사용자가 로그인해야 합니다.

## <a name="what-about-updates-to-microsoft-365-apps-for-enterprise"></a>엔터프라이즈용 Microsoft 365 앱에 대한 업데이트는 어떤가요?

Teams는 [엔터프라이즈용 Microsoft 365 앱으로 Microsoft Teams 배포](/DeployOffice/teams-install)에 설명된 대로 엔터프라이즈용 Microsoft 365 앱을 새로 설치할 때 기본적으로 설치됩니다.

Teams는 위에 설명된 대로 자체 업데이트 프로세스를 따릅니다. Teams는 Word 및 Excel과 같은 다른 Office 앱에 대한 업데이트 프로세스를 따르지 않습니다. 자세한 내용은 [Microsoft 365 앱의 업데이트 채널 개요](/DeployOffice/overview-update-channels)를 참조하세요.

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>관리자가 Teams 자동 업데이트 대신 업데이트를 배포할 수 있나요?

Teams는 관리자에게 전달 메커니즘을 통해 업데이트를 배포할 수 있는 기능을 제공하지 않습니다.

## <a name="servicing-agreement"></a>서비스 계약

최신 온라인 서비스인 Teams 클라이언트는 2주마다 자동 업데이트됩니다. Teams는 최신 수명 주기 정책의 적용을 받기 때문에 사용자는 데스크톱 클라이언트의 최신 버전을 유지해야 합니다. 자동 업데이트를 통해 사용자는 최신 기능, 성능 향상, 보안 및 서비스 안정성을 확보할 수 있습니다.

데스크톱 클라이언트가 만료된 경우를 식별하기 위해 사용자의 현재 버전이 1개월에서 3개월 사이이고 사용 가능한 새 버전이 있는 경우 인앱 알림이 표시됩니다. 이 인앱 메시지는 사용자가 최신 버전의 Teams로 업데이트하거나 필요한 경우 IT 관리자에게 연락하여 업데이트하도록 권장합니다. 3개월 이상된 Teams 데스크톱 클라이언트의 사용자에게는 지금 업데이트하거나, IT 관리자에게 연락하거나, 웹에서 Teams를 계속할 수 있는 옵션을 제공하는 차단 페이지가 표시됩니다.

정부 클라우드의 Teams 데스크톱 클라이언트에는 현재 추가 공지가 있을 때까지 이 서비스 계약에 대한 예외가 있습니다.

새 버전 릴리스에 대한 정보는 [메시지 센터](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter)를 확인하거나 클라이언트의 **도움말** > **새로운 기능** 을 참조하세요.

## <a name="what-about-updates-to-teams-on-vdi"></a>VDI의 Teams 업데이트는 어떤가요?

VDI(가상 데스크톱 인프라)의 Teams 클라이언트는 VDI가 아닌 Teams 클라이언트처럼 자동으로 업데이트되지 않습니다. [VDI에 Teams 설치](teams-for-vdi.md) 지침에 설명된 대로 새 MSI를 설치하여 VM 이미지를 업데이트해야 합니다. 최신 버전으로 업데이트하려면 현재 버전을 제거해야 합니다.
