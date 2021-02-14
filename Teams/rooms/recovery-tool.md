---
title: Microsoft Teams 회의실 복구 도구 사용
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: 이 문서에서는 최신 시스템을 지원되는 상태로 가져오는 데 사용하는 Microsoft Teams 회의실에 대한 복구 도구를 사용하는 방법을 논의합니다.
ms.openlocfilehash: 47e9bed4377a111a1c1284684bbc40517dbb42d8
ms.sourcegitcommit: 4099da7b1db7663e63ef5bece16e3090c33ea207
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2020
ms.locfileid: "45021726"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>Microsoft Teams 회의실 복구 도구 사용

이 문서에서는 최신 시스템을 지원되는 상태로 가져오는 데 사용하는 Microsoft Teams 회의실에 대한 복구 도구를 사용하는 방법을 논의합니다. 이 도구는 Microsoft Teams 회의실 콘솔에 "시스템 구성이 최신이 아닙니다." 오류가 표시되거나 푸시 단추 초기화 팩터리 복원을 수행하기 전에 [적용해야 합니다.](https://docs.microsoft.com/microsoftteams/rooms/rooms-operations#microsoft-teams-rooms-reset-factory-restore)

## <a name="prerequisites"></a>필수 구성 요소

최신 [Microsoft Teams Rooms](https://go.microsoft.com/fwlink/?linkid=851168) 설치 패키지를 다운로드하여 Microsoft Teams 회의실 장치에 액세스할 수 있는 USB 메모리 스틱 또는 네트워크 공유에 추출합니다.

> [!NOTE]
> MSI에서 파일을 추출하는 것은 여러 가지 수단으로 수행할 수 있습니다. 모든 파일을 추출하고 해당 디렉터리 구조를 보존하는 모든 메커니즘은 허용됩니다. 이러한 한 가지 방법은 Microsoft Teams Room 설치 패키지의 전체 경로를 나타내고 추출할 파일을 원하는 폴더의 전체 경로를 나타내는 명령을 사용하는 `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` `PathToMsi` `PathToTarget` 것입니다.

## <a name="running-the-tool"></a>도구 실행

1) Microsoft Teams Rooms 장치에서 관리자 계정에 로그인하고 관리자 권한 명령 프롬프트를 실행합니다.
2) Microsoft Teams Rooms 설치 패키지에서 추출한 파일에 포함된 파일에 액세스할 수 있는지 Microsoft Teams 회의실 장치에서 `RecoveryTool.ps1 file` 확인합니다. 키트는 전제 구성을 준비할 때 사용되는 네트워크 공유 또는 USB 드라이브에서 찾을 수 있습니다.
3) `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`실행합니다.
4) 팩터리 복원을 수행하기 위해:
   1. 스크립트에서 메시지가 표시되면 옵션 2: **재설정을 선택합니다.**
   2. BitLocker가 설정되어 있는 경우 스크립트 출력의 끝에 제공된 지침에 따라 비활성화합니다.
   3. 팩터리 복원을 수행 합니다.
      1. 설정 **앱을 열고** 보안 업데이트 **& 선택합니다.**
      2. 복구 **탭으로** 이동합니다.
      3. 이 **PC 재설정 아래에서** **시작을 선택합니다.**
      4. 모두 **제거,** **다음** 및 다시 설정 **선택**
        > [!WARNING]
        > 내 파일 유지 **-** 앱 및 설정을 제거하지만 Windows 재설정 프로세스 중에 개인 파일 옵션이 선택된 경우 Microsoft Teams 회의실 장치를 사용할 수 없습니다. 이 옵션을 선택하지 않습니다.
      5. 시스템이 여러 번 다시부팅됩니다. 다시 설정이 완료되면 시스템이 Windows "기본 환경"(OOBE) 화면에 표시됩니다.



## <a name="see-also"></a>참고 항목

[Microsoft Teams 회의실 도움말](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams 룸 관리](rooms-manage.md)
