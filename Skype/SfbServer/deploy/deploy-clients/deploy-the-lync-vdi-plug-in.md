---
title: Lync VDI 플러그 인을 비즈니스용 Skype 서버
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: krishra
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: 이 항목에서는 원격 가상 데스크톱에 연결하는 동안 비즈니스용 Skype 배포 절차에 대해 설명합니다.
ms.openlocfilehash: 9d745321a398828d6ec31a55528008b467ddea47
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58608615"
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server"></a>Lync VDI 플러그 인을 비즈니스용 Skype 서버
 
이 항목에서는 원격 가상 데스크톱에 연결하는 동안 비즈니스용 Skype 배포 절차에 대해 설명합니다. 계획 고려 사항은 [Plan for 비즈니스용 Skype in VDI environments 에 있습니다.](../../plan-your-deployment/clients-and-devices/vdi-environments.md)
  
보안 및 규정 준수 문제가 특히 중요한 일부 조직에서는 VDI(가상 데스크톱 인프라) 환경이 사용됩니다. 사용자가 로컬 Windows 가상 데스크톱의 클라이언트를 사용하고 있습니다. 추가 비즈니스용 Skype VDI 플러그 인 소프트웨어가 필요한 경우와 같은 연결에서 데이터를 사용할 수 있습니다.
  
VDI 플러그 인 구성 요소에는 Microsoft에서 제공하는 솔루션과 Citrix에서 제공하는 두 가지 솔루션이 있습니다. Microsoft는 새 배포에서 새 HDX RealTime 최적화 팩 솔루션을 사용하는 것이 권장되지만 나머지 수명 주기 동안 원래 Lync VDI 플러그 인을 계속 지원할 것입니다. 
  
이 항목에서는 Windows 7 및 Windows 8 또는 Windows Server 2008에서만 지원되는 Microsoft Lync VDI 플러그 인 배포에 대해 자세히 설명하며 Lync 2013 또는 비즈니스용 Skype 클라이언트만 지원합니다. 이 플러그 인을 업데이트할 계획은 없지만, 필요한 경우 이 플러그 인용 [Citrix HDX](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) 비즈니스용 Skype 팩이 업데이트됩니다.
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a>Lync VDI 플러그 인을 위한 환경 준비
<a name="Prepare_vdi"> </a>

1. 이 비즈니스용 Skype 서버 모든 Lync VDI 플러그 인 사용자에 대해 EnableMediaRedirection이 TRUE로 설정되어 있도록 합니다. 자세한 내용은 [New-CsClientPolicy cmdlet 및 Set-CsClientPolicy](/powershell/module/skype/new-csclientpolicy?view=skype-ps) cmdlet에 대한 도움말 항목을 참조하십시오. [](/powershell/module/skype/set-csclientpolicy?view=skype-ps)
    
2. 데이터 센터 서버에서 모든 가상 비즈니스용 Skype 클라이언트를 설치합니다.
    
3. 로컬 컴퓨터에서 Lync VDI 플러그 인을 설치합니다.
    
    이제 사용자는 헤드셋 또는 웹캠과 같은 장치를 로컬 컴퓨터에 연결해야 합니다.
    
## <a name="configure-remote-desktop-connection-settings"></a>원격 데스크톱 연결 설정 구성
<a name="Prepare_vdi"> </a>

Lync VDI 플러그 인에 대해 원격 데스크톱 연결을 준비하려면 로컬 컴퓨터에서 다음 단계를 수행합니다.
  
1. 로컬 컴퓨터에서 실행 중인 Windows 8 건너뛰어도 됩니다. 로컬 컴퓨터에서 Windows 7 SP1을 실행하는 경우 최신 Windows 8 버전의 원격 데스크톱 서비스 [클라이언트를 설치합니다.](/windows-server/remote/remote-desktop-services/clients/remote-desktop-clients)
    
2. **시작** 을 클릭하고 **원격 데스크톱 연결** 을 클릭하여 원격 데스크톱 서비스 클라이언트를 시작합니다.
    
3. **옵션** 을 클릭합니다.
    
4. **로컬 자원** 탭을 클릭합니다. **원격 오디오** 에서 **설정** 을 클릭하고 다음을 수행합니다.
    
   - **원격 오디오 재생** 에서 **이 컴퓨터에서 재생** 을 선택합니다.
    
   - **원격 오디오 녹음** 에서 **녹음 안 함** 을 선택합니다.
    
   - **확인** 을 클릭합니다.
    
5. **작업 환경** 탭을 클릭합니다. **성능** 아래에서 **지속적인 비트맵 캐싱** 확인란의 선택을 취소합니다.
    
6. 일반 **탭을** 클릭합니다. 컴퓨터에서 가상 데스크톱의 이름을 입력하고 를 클릭하여 **커넥트.** 
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a>가상 데스크톱에서 비즈니스용 Skype 로그인 및 사용
<a name="SfB_signin"> </a>

Lync VDI 플러그 인을 사용하도록 설정한 후 사용자는 가상 데스크톱에서 비즈니스용 Skype 다음 단계를 수행합니다.
  
1. 사용자는 자신의 자격 증명을 가상 데스크톱에서 비즈니스용 Skype 클라이언트에 입력합니다.
    
2. Lync 비즈니스용 Skype 플러그 인을 검색한 비즈니스용 Skype 자격 증명을 다시 입력하라는 메시지가 사용자에게 표시될 수 있습니다. 이 대화 상자에서는 사용자가 이후 로그인할 때 자격 증명을 입력할 필요가 없도록 **암호 저장** 확인란을 선택하는 것이 좋습니다.
    
3. 비즈니스용 Skype Lync VDI 플러그 인과의 페어링을 시작해야 합니다. 이 경우 클라이언트는 상태 표시줄에 두 개의 비즈니스용 Skype 표시됩니다. 왼쪽 아래 아이콘은 사용할 수 있는 오디오 장치가 없음을 나타내고 오른쪽 아래에서 깜박이는 아이콘은 VDI 페어링이 진행 중임: a를 나타냅니다. VDI 페어링이 성공하면 아이콘이 변경하여 통화에 사용할 오디오 장치와 VDI 페어링 성공을 나타냅니다. b. 이제 사용자는 로컬 컴퓨터에 연결된 비즈니스용 Skype 호환 장치에서 자신의 현재 현재 정보를 보고 평소처럼 통화를 걸고 응답할 수 있습니다.
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a>Lync VDI 플러그 인 문제 해결
<a name="tshoot_VDI"> </a>

Lync VDI 플러그 인을 설치한 후 문제가 발생하는 경우 다음 섹션을 참조하세요.
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a>Lync VDI 플러그 인 설치 관련 문제

Lync VDI 플러그 인 설치에 문제가 있는 경우 다음을 검사합니다.
  
- TEMP 및 TMP 시스템 변수에 지정한 폴더에 충분한 공간이 있는지 확인합니다.
    
- 쓰기 금지가 해제되어 있는지 확인합니다. 지침은 장치 제조업체 설명서를 참조하세요.
    
### <a name="troubleshooting-issues-with-pairing"></a>페어링 관련 문제 해결

Lync VDI 플러그 인 페어링이 실패하면 오른쪽 아래에서 페어링 아이콘이 다음과 같이 빨간색 "X"로 표시됩니다. 
  
다음은 오류의 가능한 이유와 문제를 해결하기 위해 수행할 수 있는 조치입니다. 
  
- **사용자가 로그인 중에 잘못된 자격 증명을 입력함**
    
    사용자는 로그아웃했다가 비즈니스용 Skype 자격 증명으로 다시 로그인해야 합니다. 그러면 페어링 대화 상자가 다시 나타나고 페어링 성공 여부가 표시됩니다.
    
- **다른 원격 데스크톱 클라이언트 인스턴스가 실행되고 있음**
    
    사용자가 로컬에서 원격 데스크톱 연결을 사용하는 Windows 다음을 해야 합니다.
    
1. **Alt+Ctrl+Delete** 를 누르고 **작업 관리자 시작** 을 클릭하여 작업 관리자를 시작합니다.
    
2. **프로세스** 탭을 클릭하고 목록에서 이름이 **mstsc.exe** 인 모든 프로세스를 찾습니다.
    
3. 각 **mstsc.exe** 프로세스를 강조 표시하고 **프로세스 끝내기** 를 클릭합니다. 
    
4. 새 원격 데스크톱 세션을 시작하고 다시 연결해 봅니다. 
    
- **필요한 파일이 올바르게 설치되지 않음**
    
    로컬 컴퓨터에 플러그 인을 설치한 후 이러한 파일이 C:\Program Files\Microsoft Office\Office15(또는 적절한 드라이브 문자)에 있는지 확인합니다.
    
  - LyncVdiPlugin.dll
    
  - UcVdi.dll
    
- **로컬 비즈니스용 Skype 실행 중인 클라이언트입니다.**
    
    Lync VDI 플러그 인을 사용하려면 비즈니스용 Skype 클라이언트가 로컬 컴퓨터에서 실행되고 있지 않으면 페어링이 실패합니다. 사용자가 로컬 컴퓨터에 비즈니스용 Skype 설치하지 않는 것이 가장 좋습니다.
    
## <a name="see-also"></a>참고 항목
<a name="tshoot_VDI"> </a>

[VDI 비즈니스용 Skype 계획](../../plan-your-deployment/clients-and-devices/vdi-environments.md)