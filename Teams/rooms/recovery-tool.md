---
title: Microsoft Teams 룸 복구 도구 사용
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 이 문서에서는 오래된 시스템을 지원되는 상태로 만드는 데 사용할 Microsoft Teams 룸 복구 도구를 사용하는 방법을 설명합니다.
ms.openlocfilehash: 70b2d199c4fe13138e2f46fd0b49e95efbd18e9c
ms.sourcegitcommit: 0bf44683f5263d7bf635689b4c1d813bd9842650
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706167"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>Microsoft Teams 룸 복구 도구 사용

이 문서에서는 오래된 시스템을 지원되는 상태로 만드는 데 사용할 Microsoft Teams 룸 복구 도구를 사용하는 방법을 설명합니다. 이 도구는 Microsoft Teams 룸 콘솔에 "시스템 구성 만료" 오류가 표시되거나 푸시 단추 초기화 [팩터리 복원](./rooms-operations.md#microsoft-teams-rooms-reset-factory-restore)을 수행하기 전에 적용해야 합니다.

## <a name="prerequisites"></a>필수 구성 요소

최신 [Microsoft Teams 룸 설치 패키지를 다운로드](https://go.microsoft.com/fwlink/?linkid=851168)하여 Microsoft Teams 룸 액세스할 수 있는 USB 메모리 스틱 또는 네트워크 공유로 추출합니다.

> [!NOTE]
> MSI에서 파일을 추출하는 작업은 여러 방법을 통해 수행할 수 있습니다. 모든 파일을 추출하고 해당 디렉터리 구조를 유지하는 모든 메커니즘을 사용할 수 있습니다. 이러한 방법 중 하나는 Microsoft Teams 룸 설치 패키지의 전체 경로를 나타내고 `PathToTarget` 압축을 풀려는 폴더의 전체 경로를 나타내는 명령을 `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` `PathToMsi` 사용하는 것입니다.

## <a name="running-the-tool"></a>도구 실행

1) Microsoft Teams 룸 디바이스에서 관리자 계정에 로그인하고 관리자 권한 명령 프롬프트를 시작합니다.
2) Microsoft Teams 룸 설치 패키지에서 추출한 파일에 포함된 파일에 액세스할 `RecoveryTool.ps1` 수 있는지 Microsoft Teams 룸 디바이스에서 확인합니다. 이 키트는 필수 구성 요소를 준비할 때 사용되는 네트워크 공유 또는 USB 드라이브에서 찾을 수 있습니다.
3) 를 실행합니다 `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.
4) 공장 복원을 수행하려면 다음을 수행합니다.
   1. 스크립트에서 메시지가 표시되면 옵션 선택 2: **다시 설정**
   2. BitLocker가 켜진 경우 스크립트 출력의 끝에 제공된 지침에 따라 사용하지 않도록 설정합니다.
   3. 팩터리 복원을 수행합니다.
      1. **설정** 앱을 열고 **& 보안 업데이트를** 선택합니다.
      2. **복구** 탭으로 이동합니다.
      3. **이 PC 다시 설정** 아래에서 **시작** 선택
      4. **모든 항목 제거** 를 선택한 다음 **, 다음** 으로 **다시 설정**
        > [!WARNING]
        > **내 파일 유지 - 앱 및 설정을 제거하지만** Windows 재설정 프로세스 중에 개인 파일 옵션을 선택한 경우 Microsoft Teams 룸 디바이스를 사용할 수 없게 될 수 있습니다. 이 옵션을 선택하지 마세요.
      5. 시스템이 여러 번 다시 부팅됩니다. 다시 설정이 완료되면 시스템이 Windows OOBE("기본 제공 환경") 화면에 표시됩니다.



## <a name="see-also"></a>참고 항목

[Microsoft Teams 룸 도움말](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams 룸 관리](rooms-manage.md)
