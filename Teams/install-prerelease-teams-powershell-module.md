---
title: 시험판 버전의 팀 PowerShell 모듈 설치
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: brandber
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: PowerShell 테스트 갤러리에서 팀 PowerShell 모듈의 시험판 버전을 설치 하려면 다음 단계를 따릅니다.
ms.openlocfilehash: 1d85fac2ee6a1c8565f8482f7208a2f5ae33db60
ms.sourcegitcommit: 1a6b4efad1e6a958cdbaae4b0e2e231145c9658f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "44321771"
---
# <a name="install-the-pre-release-version-of-the-teams-powershell-module"></a>시험판 버전의 팀 PowerShell 모듈 설치

이 문서에서는 [Powershell 테스트 갤러리](https://www.poshtestgallery.com/packages/MicrosoftTeams/)에서 팀 powershell 모듈의 최신 시험판 버전을 설치 하는 방법을 설명 합니다. 팀 구성 기능을 관리 하는 cmdlet은 일반적으로 사용 가능한 모듈 버전에서 지원 되지 않고 시험판 버전 에서만 사용할 수 있는 시나리오에서 팀 PowerShell 모듈의 시험판 버전이 필요 합니다.

이 단계를 사용 하 여 PowerShell 테스트 갤러리에서 팀 PowerShell 모듈의 최신 시험판 버전을 설치 합니다.

> [!NOTE]
> PowerShell 테스트 갤러리에서 팀 PowerShell 모듈을 [공용 Powershell 갤러리](https://www.powershellgallery.com/packages/MicrosoftTeams/)의 모듈 버전과 나란히 설치 하지 마세요. 이 단계에 따라 먼저 공용 PowerShell 갤러리에서 팀 PowerShell 모듈을 제거 하 고 PowerShell 테스트 갤러리에서 최신 버전의 모듈을 설치 합니다.

1. 모든 기존 PowerShell 세션을 닫습니다.
2. Windows PowerShell 모듈의 새 인스턴스를 시작 합니다.
3. 공용 PowerShell 갤러리에서 팀 PowerShell 모듈을 제거 하려면 다음을 실행 합니다.

    ```PowerShell
    Uninstall-Module -Name MicrosoftTeams
    ```

4. 모든 기존 PowerShell 세션을 닫습니다.
5. Windows PowerShell 모듈을 다시 시작 하 고 다음을 실행 하 여 PowerShell 테스트 갤러리를 신뢰할 수 있는 원본으로 등록 합니다.

    ```PowerShell
    Register-PSRepository -Name PSGalleryInt -SourceLocation https://www.poshtestgallery.com/ -InstallationPolicy Trusted
    ```

6. PowerShell 테스트 갤러리에서 최신 팀 PowerShell 모듈을 설치 하려면 다음을 실행 합니다.

    ```PowerShell
    Install-Module -Name MicrosoftTeams -Repository PSGalleryInt -Force
    ```

7. 다음을 실행 하 여 PowerShell 테스트 갤러리에서 최신 버전의 팀 PowerShell 모듈이 성공적으로 설치 되었는지 확인 합니다.

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

#### <a name="update-to-the-latest-version-of-the-teams-powershell-module-from-the-powershell-test-gallery"></a>PowerShell 테스트 갤러리에서 최신 버전의 팀 PowerShell 모듈로 업데이트

PowerShell 테스트 갤러리에서 팀 PowerShell 모듈을 이미 설치한 경우 다음 단계를 사용 하 여 최신 버전으로 업데이트 합니다.

1. 모든 기존 PowerShell 세션을 닫습니다.
2. Windows PowerShell 모듈의 새 인스턴스를 시작 합니다.
3. 다음을 실행 하 여 PowerShell 테스트 갤러리에서 현재 설치 된 버전의 팀 PowerShell 모듈을 업데이트 합니다.

    ```PowerShell
    Update-Module -Name MicrosoftTeams -Force
    ```

4. 다음을 실행 하 여 PowerShell 테스트 갤러리에서 최신 버전의 팀 PowerShell 모듈이 성공적으로 설치 되었는지 확인 합니다.

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

## <a name="related-topics"></a>관련 항목

- [Teams PowerShell 개요](teams-powershell-overview.md)
