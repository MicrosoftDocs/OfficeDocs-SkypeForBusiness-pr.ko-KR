---
title: Microsoft 팀 대화방 복구 도구 사용
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: sohailta
ms.date: 4/17/2018
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection: M365-voice
localization_priority: Normal
description: 이 문서에서는 Microsoft 팀 대화방에 대 한 복구 도구를 사용 하는 방법에 대해 설명 하 고 최신 시스템을 지원 되는 상태로 전환 하는 데 사용 합니다.
ms.openlocfilehash: aded92fac90f20246444419bff19415922175856
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "36775208"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>Microsoft 팀 대화방 복구 도구 사용
 
이 문서에서는 Microsoft 팀 대화방에 대 한 복구 도구를 사용 하는 방법에 대해 설명 하 고 최신 시스템을 지원 되는 상태로 전환 하는 데 사용 합니다. Microsoft 팀 대화방 콘솔에 "시스템 구성 날짜가 만료 됨" 오류가 표시 되는 경우이 도구를 사용 합니다.
  

<a name="Prerequisites"> </a>  
## <a name="prerequisites"></a>필요 조건

최신 [Microsoft 팀 대화방 설치 패키지](https://go.microsoft.com/fwlink/?linkid=851168) 를 다운로드 하 고 Microsoft 팀 회의실 장치에서 액세스할 수 있는 USB 메모리 스틱 또는 네트워크 공유에 압축을 풉니다.

[KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu)를 설치 해야 할 수도 있습니다.

<a name="Windows-ver"> </a>
## <a name="verify-windows-version"></a>Windows 버전 확인 

1. **Windows 설정> 설정** 으로 이동한 다음 Microsoft 팀 대화방 장치에서 관리자 로그인> 관리자 계정에 로그인 합니다. 이 옵션은 로그인 화면으로 가져옵니다.
2. 관리자 계정에 로그인 하 고, 기본 관리자 계정 `admin` 으로 암호를 입력 `sfb`합니다.
3. 시작 메뉴를 클릭 하 고 검색 `winver.exe` 상자에 입력 한 다음 * 결과에 대해 **실행 명령을* 클릭 합니다.
4. 정보 창의 두 번째 행에 있는 ' 버전 ' 다음의 번호를 기록해 둡니다.

>[!NOTE]
>표시 되는 버전이 1607 이거나 이전인 경우 복구 단계를 <a href="#Perform">수행</a> 하기 전에 <a href="#Windows-up">복구 하기 전에 Windows 업데이트</a> 단계 proceding를 따릅니다. 표시 된 버전이 1607 보다 크면 <a href="#Perform">복구 수행</a>단계만 따르세요.

<a name="Windows-up"> </a>
## <a name="update-windows-before-recovery-if-needed"></a>복구 하기 전에 Windows 업데이트 (필요한 경우)

1. 계속 해 서 관리자 사용자로 로그인 한 상태에서 관리자 권한 Powershell 프롬프트를 실행 합니다.
2. 명령을 `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`실행 합니다.
3. Windows 업데이트를 실행 하 고 Windows 1709 업데이트를 설치 합니다.
4. 1709에 대 한 업데이트가 완료 되 면 관리자 계정으로 다시 로그인 하 고 [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu)를 설치 합니다. 이 업데이트는 링크 또는 Windows Update를 사용 하 여 수행할 수 있습니다.
5. 선택적 단계로 Windows Update에서 사용할 수 있는 추가 업데이트를 설치 합니다.

<a name="Perform"> </a>
## <a name="perform-a-recovery"></a>복구 수행

1. Microsoft 팀 대화방 장치에서 관리자 계정에 로그인 하 고 관리자 권한 명령 프롬프트를 실행 합니다.
2. Microsoft 팀 대화방 설치 패키지에서 추출한 파일에 포함 되어 있는 `RecoveryTool.ps1` 파일에 액세스할 수 있는지 확인 합니다. 이 키트는 필수 구성 요소를 준비할 때 사용 되는 네트워크 공유 또는 USB 드라이브에서 찾을 수 있습니다.
3. Debug.exe 명령을 `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`실행 합니다.
4. 스크립트 선택 옵션 `1:"Repair System"`에 따라 메시지가 표시 되는 경우
5. 완료 되 면 Microsoft 팀 대화방 장치를 다시 부팅 합니다. 자동으로 다시 부팅 되 고 두 번 완전히 복구 됩니다.



<a name="See"> </a>  
## <a name="see-also"></a>참고 항목
 
[Microsoft 팀 대화방 도움말](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft 팀 대화방 관리](skype-room-systems-v2.md)
