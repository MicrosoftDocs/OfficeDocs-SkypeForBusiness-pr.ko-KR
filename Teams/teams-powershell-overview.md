---
title: Microsoft Teams PowerShell 개요
ms.reviewer: ''
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: PowerShell 컨트롤을 사용하여 Microsoft Teams 관리하는 방법을 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 07a97ee8242da28796664892d092b503e10c59cf
ms.sourcegitcommit: 1d990582e2deb5f55ba9adada3e17377f792a141
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2022
ms.locfileid: "64922819"
---
# <a name="microsoft-teams-powershell-overview"></a>Microsoft Teams PowerShell 개요

Microsoft Teams PowerShell 모듈은 PowerShell 명령줄에서 직접 Teams 관리하기 위한 cmdlet 집합입니다. PowerShell은 Teams 워크로드를 관리하는 데 활용할 수 있는 자동화를 위한 강력한 기능을 제공합니다.  

다음 방법 중 하나를 사용하여 Microsoft Teams PowerShell 모듈을 사용할 수 있습니다. 

- PowerShell 갤러리(권장 옵션)를 통해 [Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams) PowerShell 모듈을 설치합니다. 
- 수동 다운로드를 통해 Microsoft Teams PowerShell 모듈을 [설치합니다](https://www.powershellgallery.com/packages/MicrosoftTeams). 

> [!NOTE]
> Microsoft Teams 4.x.x 이전의 PowerShell 모듈 버전은 사용 중지됩니다. 최신 버전으로 업데이트하세요. [자세한 내용은 Teams PowerShell 모듈 - 지원되는 버전](teams-powershell-supported-versions.md)입니다.

## <a name="features"></a>기능 

Microsoft Teams PowerShell 모듈에는 다음과 같은 기능이 포함되어 있습니다. 

- 단일 모듈을 사용하여 사용자, 팀, 정책 및 구성을 포함하여 Teams 관리의 모든 측면을 관리합니다.  
- 액세스 토큰 및 자격 증명과 같은 인증 메커니즘을 지원합니다. 

##  <a name="data-collection"></a>데이터 수집 

Microsoft Teams PowerShell 모듈 기본 설정은 원격 분석 데이터를 수집합니다. Microsoft는 수집된 데이터를 집계하여 사용 패턴 및 성공률이 낮은 cmdlet과 같은 일반적인 문제를 식별하여 Teams PowerShell 환경을 개선하기 위해 작업의 우선 순위를 지정합니다. Microsoft Teams PowerShell 모듈은 개인 또는 개인 데이터를 수집하지 않습니다. 자세한 내용은 [Microsoft 개인정보처리방침](https://privacy.microsoft.com/privacystatement)을 참조하세요.

## <a name="related-topics"></a>관련 항목

[Teams PowerShell 설치](teams-powershell-install.md)

[Teams PowerShell을 사용하여 Teams 관리](teams-powershell-managing-teams.md)

[PowerShell 릴리스 정보 Teams](teams-powershell-release-notes.md)

[Microsoft Teams cmdlet 참조](/powershell/teams/?view=teams-ps)

[비즈니스용 Skype cmdlet 참조](/powershell/skype/intro?view=skype-ps)

[Microsoft Teams 관리자 역할을 사용하여 Teams 관리](using-admin-roles.md)
