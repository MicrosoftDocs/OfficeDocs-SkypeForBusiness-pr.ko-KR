---
title: Microsoft Teams 룸 디바이스 수동 업데이트
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: sohailta
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
description: Microsoft Teams 룸 디바이스를 특정 버전으로 수동으로 업데이트하는 방법을 알아봅니다.
ms.openlocfilehash: c3128f5b909901da0eb5578f1586aaad785b49a6
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267643"
---
# <a name="manually-update-a-microsoft-teams-rooms-device"></a>Microsoft Teams 룸 디바이스 수동 업데이트

Microsoft Teams 룸 앱은 Microsoft Store를 통해 배포됩니다. 앱에 대한 업데이트 야간 유지 관리 중에 자동으로 Microsoft Store에서 설치됩니다. 업데이트를 가져오는 데 권장되는 방법입니다. 그러나 Teams 룸 디바이스가 Microsoft Store에서 업데이트를 받을 수 없는 경우도 있습니다. 예를 들어 보안 정책은 디바이스가 인터넷에 연결하는 것을 허용하지 않거나 Microsoft Store에서 앱을 다운로드하는 것을 허용하지 않을 수 있습니다. 또는 Microsoft Store를 사용할 수 없는 동안 설치를 수행하기 전에 디바이스를 업데이트할 수 있습니다.

Microsoft Store에서 업데이트를 받을 수 없는 경우 오프라인 앱 업데이트 PowerShell 스크립트를 사용하여 Teams 룸 디바이스를 최신 버전의 Teams 룸 앱으로 수동으로 업데이트할 수 있습니다. 이 문서의 단계에 따라 Teams 룸 디바이스를 수동으로 업데이트합니다.

> [!NOTE]
> 이 프로세스는 Teams 룸 앱이 이미 설치된 Teams 룸 디바이스만 업데이트할 수 있습니다. 새 설치를 수행하는 데 사용할 수 없습니다. 또한 앱을 이전 버전으로 다운그레이드하는 데 사용할 수 없습니다. Teams 룸 앱의 새 설치를 수행하려면 디바이스 제조업체에 관련 미디어에 문의하세요.

## <a name="step-1-download-the-offline-app-update-script"></a>1단계: 오프라인 앱 업데이트 스크립트 다운로드

먼저 오프라인 앱 업데이트 스크립트의 최신 버전을 다운로드합니다. 스크립트를 다운로드하려면 을 클릭합니다 <https://go.microsoft.com/fwlink/?linkid=2151817>. 스크립트는 디바이스의 기본 다운로드 폴더에 다운로드됩니다.

다운로드한 파일은 Windows에서 차단된 것으로 표시될 수 있습니다. 상호 작용 없이 스크립트를 실행해야 하는 경우 스크립트 차단을 해제해야 합니다. 스크립트 차단을 해제하려면 다음을 수행합니다.

1. 파일 탐색기 파일을 마우스 오른쪽 단추로 클릭합니다.
2. **속성** 클릭
3. **차단 해제** 선택
4. **확인을 클릭합니다.**

PowerShell을 사용하여 스크립트 차단을 해제하려면 차단 [해제 파일을 참조하세요](/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1).

오프라인 앱 업데이트 스크립트를 다운로드한 후 파일을 Teams 룸 디바이스로 전송합니다. USB 드라이브를 사용하거나 디바이스의 관리 모드에 있는 동안 네트워크 파일 공유에서 파일에 액세스하여 디바이스로 파일을 전송할 수 있습니다. 디바이스에서 파일을 저장할 위치를 확인해야 합니다.

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a>2단계: 스크립트를 실행하여 Teams 룸 앱 업데이트

Skype 사용자(앱이 실행되는 사용자)가 여전히 로그인되어 있는 동안 상승된 명령 프롬프트에서 오프라인 앱 업데이트 스크립트를 실행해야 합니다. Skype 사용자가 계속 로그인하는 동안 관리자 계정에 로그인하여 관리자 권한 명령 프롬프트를 사용하는 방법에 대한 자세한 내용은 [Microsoft Teams 룸 앱이 충돌할 때 관리 모드로 전환하고 다시](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes) 전환하는 방법을 참조하세요.

관리자 권한 명령 프롬프트에서 스크립트를 실행하려면 다음을 수행합니다.

1. 관리 모드로 전환
2. 시작 아이콘을 클릭하고 **명령 프롬프트를** 입력한 다음 **관리자 권한으로 실행을** 선택합니다.
3. 스크립트의 전체 경로와 스크립트 파일의 이름을 포함하는 다음 명령을 `<path to script>` 실행합니다.

    ```console
    PowerShell -ExecutionPolicy Unrestricted "<path to script>"
    ```

예를 들어 스크립트 파일이 있고 `C:\Users\Admin\Downloads`스크립트 파일 이름이 `MTR-Update-4.5.6.7.ps1`있으면 다음 명령을 실행합니다.

```console
PowerShell -ExecutionPolicy Unrestricted "C:\Users\Admin\Downloads\MTR-Update-4.5.6.7.ps1"
```

스크립트를 실행하도록 허용합니다. 완료되면 스크립트가 Teams 룸 디바이스를 다시 부팅합니다.

원격 PowerShell을 사용하여 스크립트를 실행할 수도 있습니다. Teams 룸 디바이스에서 원격 PowerShell을 사용하는 방법에 대한 자세한 내용은 [PowerShell을 사용한 원격 관리를](rooms-operations.md#remote-management-using-powershell) 참조하세요.

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a>3단계: 앱이 성공적으로 업데이트되었는지 확인

스크립트가 성공적으로 실행되면 디바이스가 Teams 룸 앱으로 다시 부팅됩니다.

스크립트에 문제가 발생하면 명령줄의 문제를 나타내고 해당 출력을 파일에 기록합니다. 스크립트에서 제공하는 모든 지침을 따릅니다. Microsoft 지원 문의해야 하는 경우 지원 요청과 함께 로그 파일을 포함해야 합니다. 스크립트는 로그 파일의 경로를 제공합니다.
