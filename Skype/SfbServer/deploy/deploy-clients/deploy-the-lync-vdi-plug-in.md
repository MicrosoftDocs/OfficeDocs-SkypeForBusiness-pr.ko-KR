---
title: 비즈니스용 Skype 서버를 사용 하 여 Lync VDI 플러그 인 배포
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: krishra
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: 이 항목에서는 원격 가상 데스크톱에 연결 하는 동안 비즈니스용 Skype를 사용 하기 위한 배포 절차에 대해 설명 합니다.
ms.openlocfilehash: f864136ab55f37a9bfaf54d6c31d74d31844da59
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768951"
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server"></a>비즈니스용 Skype 서버를 사용 하 여 Lync VDI 플러그 인 배포
 
이 항목에서는 원격 가상 데스크톱에 연결 하는 동안 비즈니스용 Skype를 사용 하기 위한 배포 절차에 대해 설명 합니다. 계획 고려 사항은 [VDI 환경의 비즈니스용 Skype 계획](../../plan-your-deployment/clients-and-devices/vdi-environments.md)에 있습니다.
  
VDI (가상 데스크톱 인프라) 환경은 보안 및 준수 문제가 특히 중요 한 일부 조직에 사용 됩니다. 해당 사용자는 로컬 Windows 컴퓨터에 있고 가상 데스크톱에서 클라이언트를 사용 합니다. 추가 VDI 플러그 인 소프트웨어가 필요한 것과 같은 연결에 비즈니스용 Skype를 사용 합니다.
  
VDI 플러그 인 구성 요소에는 Microsoft에서 제공 하는 두 가지 솔루션과 Citrix에서 제공 하는 둘 중 하나가 있습니다. Microsoft는 새 배포에서 새 HDX 실시간 최적화 팩 솔루션을 사용 하는 것이 좋지만 나머지 수명 주기 동안 원본 Lync VDI 플러그 인을 계속 지원 합니다. 
  
이 항목에서는 Windows 7 및 Windows 8 또는 Windows Server 2008 에서만 지원 되며 Lync 2013 또는 비즈니스용 Skype 클라이언트만을 지 원하는 Microsoft Lync VDI 플러그 인을 배포 하는 방법에 대해 자세히 설명 합니다. 이 플러그 인을 업데이트할 계획이 없지만 비즈니스용 Skype에 대 한 [CITRIX HDX 실시간 최적화 팩](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) 이 필요에 따라 업데이트 됩니다.
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a>Lync VDI 플러그 인을 위한 환경 준비
<a name="Prepare_vdi"> </a>

1. 비즈니스용 Skype 서버에서 모든 Lync VDI 플러그 인 사용자에 대해 EnableMediaRedirection이 TRUE로 설정 되어 있는지 확인 합니다. 자세한 내용은 [새 csclientpolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) Cmdlet 및 [Set csclientpolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) Cmdlet에 대 한 도움말 항목을 참조 하세요.
    
2. 데이터 센터 서버에서 모든 가상 데스크톱에 비즈니스용 Skype 클라이언트를 설치 합니다.
    
3. 로컬 컴퓨터에서 Lync VDI 플러그 인을 설치 합니다.
    
    이제 사용자는 헤드셋 또는 웹캠 같은 장치를 로컬 컴퓨터에 연결 해야 합니다.
    
## <a name="configure-remote-desktop-connection-settings"></a>원격 데스크톱 연결 설정 구성
<a name="Prepare_vdi"> </a>

Lync VDI 플러그 인에 대 한 원격 데스크톱 연결을 준비 하려면 로컬 컴퓨터에서 다음 단계를 수행 합니다.
  
1. 로컬 컴퓨터에서 Windows 8을 실행 하는 경우에는이 단계를 건너뛰십시오. 로컬 컴퓨터에서 SP1을 사용 하 여 Windows 7을 실행 하는 경우 최신 Windows 8 버전의 [원격 데스크톱 서비스 클라이언트](https://go.microsoft.com/fwlink/p/?LinkId=268032)를 설치 합니다.
    
2. **시작**을 클릭 한 다음 **원격 데스크톱 연결**을 클릭 하 여 원격 데스크톱 서비스 클라이언트를 시작 합니다.
    
3. **옵션**을 클릭 합니다.
    
4. **로컬 리소스** 탭을 클릭 합니다. **원격 오디오**에서 **설정을**클릭 하 고 다음을 수행 합니다.
    
   - **원격 오디오 재생**에서 **이 컴퓨터에서 재생**을 선택 합니다.
    
   - **원격 오디오 기록**에서 **녹화 안 함**을 선택 합니다.
    
   - **확인**을 클릭합니다.
    
5. **환경** 탭을 클릭 합니다. **성능**에서 **영구적 비트맵 캐싱** 확인란의 선택을 취소 합니다.
    
6. **일반** 탭을 클릭 합니다. **컴퓨터**에서 가상 데스크톱의 이름을 입력 한 다음 **연결**을 클릭 합니다. 
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a>가상 데스크톱에서 비즈니스용 Skype에 로그인 및 사용
<a name="SfB_signin"> </a>

Lync VDI 플러그 인을 사용 하도록 설정한 후 사용자는 가상 데스크톱에서 비즈니스용 Skype에 로그인 할 때 다음 단계를 따릅니다.
  
1. 사용자는 가상 데스크톱에서 실행 되는 비즈니스용 Skype 클라이언트에 자신의 자격 증명을 입력 합니다.
    
2. 비즈니스용 Skype에서 Lync VDI 플러그 인을 감지 하면 비즈니스용 Skype에서 사용자에 게 자격 증명을 다시 입력 하 라는 메시지를 표시 합니다. 이 대화 상자에서 사용자가 다음에 로그인 할 때 자격 증명을 입력할 필요가 없도록 **암호 저장** 확인란을 선택 하는 것이 좋습니다.
    
3. 비즈니스용 Skype는 Lync VDI 플러그 인과 페어링 하기 시작 합니다. 이 문제가 발생 하는 동안에는 클라이언트가 비즈니스용 Skype 상태 표시줄에 두 개의 아이콘을 표시 합니다. 왼쪽 아래에 있는 아이콘은 사용할 수 있는 오디오 장치가 없음을 나타내고 오른쪽 아래에 깜박이는 아이콘은 VDI 페어링이 진행 중임을 나타냅니다. VDI 페어링에 성공한 후에는이 아이콘이 변경 되어 통화에 사용 되는 오디오 장치 및 성공한 VDI 페어링에는 b가 표시 됩니다. 이제 사용자는 로컬 컴퓨터에 연결 된 비즈니스용 Skype 호환 장치에서 현재 상태를 볼 수 있으며 평소와 같이 전화를 걸고 응답 합니다.
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a>Lync VDI 플러그 인 문제 해결
<a name="tshoot_VDI"> </a>

Lync VDI 플러그 인을 설치한 후 문제가 발생 하는 경우 다음 섹션을 참조 하세요.
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a>Lync VDI 플러그 인 설치 문제

Lync VDI 플러그 인을 설치 하는 데 문제가 있는 경우 다음을 확인 합니다.
  
- TEMP 및 TMP 시스템 변수에 지정한 폴더에 충분 한 공간이 있는지 확인 합니다.
    
- 쓰기 방지가 꺼져 있는지 확인 합니다. 자세한 내용은 장치 제조업체의 설명서를 참조 하세요.
    
### <a name="troubleshooting-issues-with-pairing"></a>페어링 문제 해결

Lync VDI 플러그 인 페어링에 실패 하면 오른쪽 아래에 있는 페어링 아이콘은 표시 된 대로 빨간색 "X"로 표시 됩니다. 
  
오류 및 문제를 해결 하기 위해 수행할 수 있는 작업에 대 한 가능한 원인은 다음과 같습니다. 
  
- **로그인 하는 동안 사용자가 잘못 된 자격 증명을 입력 했습니다.**
    
    사용자는 비즈니스용 Skype에서 로그 아웃 하 고 올바른 자격 증명으로 다시 로그인 해야 합니다. 페어링 대화 상자가 다시 표시 되 고 페어링이 성공할 수 있는지를 보여 줍니다.
    
- **원격 데스크톱 클라이언트의 다른 인스턴스가 실행 중입니다.**
    
    Windows에서 원격 데스크톱 연결을 사용 하는 경우 사용자는 다음을 수행 해야 합니다.
    
1. 작업 관리자 시작: **Alt + Ctrl + Delete**를 누른 다음 **작업 관리자 시작**을 클릭 합니다.
    
2. **프로세스** 탭을 클릭 하 고 목록에서 **mstsc** 라는 모든 프로세스를 찾습니다.
    
3. 각 **mstsc** 프로세스를 강조 표시 한 다음 **프로세스 끝내기**를 클릭 합니다. 
    
4. 새 원격 데스크톱 세션을 시작 하 고 다시 연결 해 보세요. 
    
- **필요한 파일이 올바르게 설치 되지 않았습니다.**
    
    로컬 컴퓨터에 플러그 인을 설치한 후 이러한 파일이 C:\Program Files\Microsoft Office\Office15 (또는 적절 한 드라이브 문자) 아래에 있는지 확인 합니다.
    
  - LyncVdiPlugin
    
  - (Vdi) dll
    
- **비즈니스용 Skype 클라이언트가 로컬 컴퓨터에서 실행 되 고 있습니다.**
    
    Lync VDI 플러그 인을 사용 하려면 비즈니스용 Skype 클라이언트가 로컬 컴퓨터에서 실행 되 고 있지 않아야 하 고, 그렇지 않으면 페어링이 실패 합니다. 가장 좋은 방법은 사용자가 로컬 컴퓨터에 비즈니스용 Skype 클라이언트를 설치 하지 않아야 한다는 것입니다.
    
## <a name="see-also"></a>참고 항목
<a name="tshoot_VDI"> </a>

[VDI 환경에서 비즈니스용 Skype에 대 한 계획](../../plan-your-deployment/clients-and-devices/vdi-environments.md)
