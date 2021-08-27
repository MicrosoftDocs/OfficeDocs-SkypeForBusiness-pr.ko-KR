---
title: 복구 Microsoft Teams 룸 사용
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
ms.localizationpriority: medium
description: 이 문서에서는 최신 시스템을 지원되는 상태로 Microsoft Teams 룸 복구 도구를 사용하는 방법을 설명합니다.
ms.openlocfilehash: 8b5f61ef3ebfc1ef08a1db6667159ff97c2cdd78
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58597582"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>복구 Microsoft Teams 룸 사용

이 문서에서는 최신 시스템을 지원되는 상태로 Microsoft Teams 룸 복구 도구를 사용하는 방법을 설명합니다. 이 도구는 Microsoft Teams 룸 "시스템 구성" 오류가 표시되거나 푸시 단추 재설정 팩터리 복원을 수행하기 전에 를 표시하는 경우 [적용해야 합니다.](./rooms-operations.md#microsoft-teams-rooms-reset-factory-restore)

## <a name="prerequisites"></a>필수 구성 요소

최신 설치 [Microsoft Teams 룸](https://go.microsoft.com/fwlink/?linkid=851168) 패키지를 다운로드하고 USB 메모리 스틱 또는 네트워크 공유에 Microsoft Teams 룸 추출합니다.

> [!NOTE]
> MSI에서 파일을 추출하는 것은 여러 가지 수단으로 수행할 수 있습니다. 모든 파일을 추출하고 디렉터리 구조를 보존하는 모든 메커니즘은 허용됩니다. 이러한 한 가지 방법은 룸 설치 패키지에 대한 전체 경로를 Microsoft Teams 파일을 추출할 폴더의 전체 경로를 나타내는 명령을 사용하는 `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` `PathToMsi` `PathToTarget` 것입니다.

## <a name="running-the-tool"></a>도구 실행

1) 디바이스의 관리자 계정에 Microsoft Teams 룸 상승된 명령 프롬프트를 실행합니다.
2) 설치 패키지에서 Microsoft Teams 룸 파일에 포함된 에 액세스할 수 있는지 Microsoft Teams 룸 `RecoveryTool.ps1 file` 확인합니다. 키트는 전제 구성을 준비할 때 사용되는 네트워크 공유 또는 USB 드라이브에서 찾을 수 있습니다.
3) `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`을 실행합니다.
4) 팩터리 복원을 수행하기 위해:
   1. 스크립트가 묻는 메시지가 표시되면 옵션 2: **재설정을 선택합니다.**
   2. BitLocker가 설정되어 있는 경우 스크립트 출력의 끝에 제공된 지침을 따라 비활성화합니다.
   3. 팩터리 복원을 수행합니다.
      1. 설정 **앱을** 열고 보안 업데이트 **& 선택합니다.**
      2. 복구 **탭으로** 이동합니다.
      3. 이 **PC 재설정 아래에서** **시작을 선택합니다.**
      4. 모든 **제거**, 다음 및 **재설정을** **선택합니다.**
        > [!WARNING]
        > 내 Microsoft Teams 룸 유지 **-** 앱 및 설정을 제거하지만 개인 파일 옵션이 다시 설정 프로세스 중에 선택되어 있는 경우 Windows 수 있습니다. 이 옵션을 선택하지 않습니다.
      5. 시스템이 여러 번 다시 부팅됩니다. 재설정이 완료되면 시스템은 "OOBE(Windows 경험 부족) 화면이 됩니다.



## <a name="see-also"></a>참고 항목

[Microsoft Teams 룸 도움말](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams 룸 관리](rooms-manage.md)