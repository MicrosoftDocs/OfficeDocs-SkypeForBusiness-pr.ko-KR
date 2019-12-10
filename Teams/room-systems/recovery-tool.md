---
title: Microsoft 팀 대화방 복구 도구 사용
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
localization_priority: Normal
description: 이 문서에서는 Microsoft 팀 대화방에 대 한 복구 도구를 사용 하는 방법에 대해 설명 하 고 최신 시스템을 지원 되는 상태로 전환 하는 데 사용 합니다.
ms.openlocfilehash: 79cdd7b2e3530570033083bdac7089e862f169ce
ms.sourcegitcommit: dc70fd277d9542d831741e14dba9ae22367210ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2019
ms.locfileid: "39909464"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>Microsoft 팀 대화방 복구 도구 사용

이 문서에서는 Microsoft 팀 대화방에 대 한 복구 도구를 사용 하는 방법에 대해 설명 하 고 최신 시스템을 지원 되는 상태로 전환 하는 데 사용 합니다. Microsoft 팀 대화방 콘솔에 "시스템 구성 날짜가 만료 됨" 오류가 표시 되거나 푸시 단추 다시 설정 [공장 복원을](https://docs.microsoft.com/microsoftteams/room-systems/room-systems-v2-operations#microsoft-teams-rooms-reset-factory-restore)수행 하기 전에이 도구를 적용 해야 합니다.

## <a name="prerequisites"></a>필요 조건

최신 [Microsoft 팀 대화방 설치 패키지](https://go.microsoft.com/fwlink/?linkid=851168) 를 다운로드 하 고 Microsoft 팀 회의실 장치에서 액세스할 수 있는 USB 메모리 스틱 또는 네트워크 공유에 압축을 풉니다.

> [!NOTE]
> MSI에서 파일의 압축을 푸는 것은 여러 방법에서 수행할 수 있습니다. 모든 파일을 추출 하 고 해당 디렉터리 구조를 유지 하는 메커니즘은 허용 됩니다. 그 이유 중 하나는 Microsoft 팀 대화방 `msiexec /qn PathToMsi /qb TARGETDIR=PathToTarget` 설치 `PathToMsi` 패키지에 대 한 전체 경로를 나타내는 명령을 사용 하는 것 `PathToTarget` 이 고, 압축을 푼 파일을 원하는 폴더의 전체 경로를 나타내는 것입니다.

## <a name="running-the-tool"></a>도구 실행

1) Microsoft 팀 대화방 장치에서 관리자 계정에 로그인 하 고 관리자 권한 명령 프롬프트를 실행 합니다.
2) Microsoft 팀 대화방 설치 패키지에서 추출 된 파일에 포함 된에 `RecoveryTool.ps1 file`액세스할 수 있는 microsoft 팀원 장치에서 확인 합니다. 이 키트는 필수 구성 요소를 준비할 때 사용 되는 네트워크 공유 또는 USB 드라이브에서 찾을 수 있습니다.
3) 실행 `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`합니다.
4) 공장 복원을 수행 하는 경우:
   - 스크립트에 메시지가 표시 되 면 옵션 2: **Reset**을 선택 합니다.
   - BitLocker가 켜져 있는 경우 스크립트 출력 끝부분에 나와 있는 지침에 따라 사용 하지 않도록 설정 합니다.
   - 공장 복원을 수행 합니다.
      - **설정** 앱을 열고 **& 보안 업데이트** 를 선택 합니다.
      - **복구** 탭으로 이동 합니다.
      - **이 PC 초기화**아래에서 **시작 하기** 선택
      - **모두 제거**를 선택한 다음 **다음** 을 선택 하 고 **다시 설정** 합니다.
      - 시스템이 여러 번 재부팅 됩니다. 재설정이 완료 되 면 시스템은 Windows OOBE 화면에 있게 됩니다.
5) "오래 된" 시스템을 복구 하는 경우:
    - 스크립트에 메시지가 표시 되 면 옵션 1: **복구**를 선택 합니다.
    - 완료 되 면 Microsoft 팀 대화방 장치를 다시 부팅 합니다. 자동으로 다시 부팅 되 고 두 번 완전히 복구 됩니다.

> [!NOTE]
> Microsoft 팀 대화방을 사용할 수 없게 되는 알려진 문제가 있습니다. **내 파일 유지-앱과 설정을 제거 하지만,** Windows 재설정 프로세스 중에 개인 파일 옵션 유지 옵션이 선택 되어 있습니다. 이 옵션을 사용 *하지* 마세요.

## <a name="see-also"></a>참고 항목

[Microsoft 팀 대화방 도움말](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft 팀 대화방 관리](skype-room-systems-v2.md)
