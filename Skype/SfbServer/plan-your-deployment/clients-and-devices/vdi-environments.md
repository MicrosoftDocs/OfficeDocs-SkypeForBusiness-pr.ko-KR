---
title: VDI 환경에서 비즈니스용 Skype에 대 한 계획
author: lanachin
ms.author: v-lanac
ms.reviewer: krishra
manager: serdars
ms.date: 1/9/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ea68414b-bb7e-483a-b731-b6b5a44372b1
description: 이 항목에서는 원격 가상 데스크톱에 연결 하는 동안 비즈니스용 Skype를 사용 하기 위한 계획 고려 사항에 대해 설명 합니다.
ms.openlocfilehash: d2d65167eb574d17e31c19759364841147af6c05
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803508"
---
# <a name="plan-for-skype-for-business-in-vdi-environments"></a>VDI 환경에서 비즈니스용 Skype에 대 한 계획
 
이 항목에서는 원격 가상 데스크톱에 연결 하는 동안 비즈니스용 Skype를 사용 하기 위한 계획 고려 사항에 대해 설명 합니다. 
  
VDI (가상 데스크톱 인프라) 환경은 보안 및 준수 문제가 특히 중요 한 일부 조직에 사용 됩니다. 사용자는 원격 데스크톱 서비스 또는 유사한 원격 연결을 사용 하 여 데스크톱 응용 프로그램 및 파일을 모두 가상 데스크톱에서 사용할 수 있습니다. 예를 들어 전체 오디오 및 비디오를 사용 하 여 가상 데스크톱에 있는 클라이언트의 오디오 및 비디오 처리 로드가 필요 합니다. 추가 VDI 플러그 인 소프트웨어를 사용 하 여 최종 사용자의 로컬 컴퓨터로 처리 하는 작업을 오프 로드 하 고 가상 데스크톱의 부하를 줄일 수 있습니다.
  
Microsoft, Citrix 또는 VMWare에서 제공 하는 VDI 플러그 인 구성 요소에 대해 세 가지 해결 방법을 사용할 수 있습니다. 새 배포의 경우 Citrix HDX 실시간 최적화 팩 솔루션 또는 VMWare 수평 가상화 팩을 사용 하는 것이 좋습니다. 원래 Lync VDI 플러그 인은 나머지 수명 주기 동안 계속 지원 됩니다.
  
- Lync **VDI 플러그** 인은 lync 2013 용으로 개발 되었으며, 가상 데스크톱에서 실행 되는 lync 2013 또는 비즈니스용 Skype 2015 클라이언트와 호환 됩니다. 로컬 컴퓨터에 설치 되는 독립 실행형 응용 프로그램이 며 가상 데스크톱의 클라이언트에 로컬 오디오 및 비디오 장치를 사용할 수 있습니다. 플러그 인에서는 비즈니스용 Skype 클라이언트를 Windows 7, Windows 8 또는 Windows Server 2008 운영 체제를 실행 해야 하는 로컬 컴퓨터 또는 씬 클라이언트에 설치할 필요가 없습니다. (이러한 운영 체제를 사용 하 고 Microsoft에서 지원 되는 씬 클라이언트 장치에는 Dell Wyse Z90D7, Dell Wyse R90L7, Dell Wyse X90m7, HP t610 및 HP t5740e이 포함 됩니다.) 이 플러그인은 여전히 지원 되지만 향후 업데이트는 예정 되어 있지 않습니다. Citrix 기반 가상 환경의 경우 Citrix 실시간 최적화 팩을 사용 하는 것이 좋습니다.
    
- **Citrix 실시간 최적화 팩** 은 lync VDI 플러그 인을 기반으로 하며, 가상 데스크톱의 lync 2013 또는 비즈니스용 Skype 2016 클라이언트에서 작동 합니다. Microsoft는 Citrix에 의해 공동 개발 되었으며, 원래의 VDI 플러그 인을 개선 했습니다. Windows 및 windows 이외의 운영 체제 (Windows 10, Mac 및 Linux 포함)를 사용 하 여 클라이언트에 설치할 수 있습니다. 이 구성 요소는 실시간 커넥터 (가상 데스크톱에 설치 되어 있음)와 실시간 미디어 엔진 (최종 사용자의 로컬 컴퓨터에 설치 되어 있음)로 구성 됩니다. 이 두 가지 구성 요소를 통해 사용자의 로컬 컴퓨터는 로컬 컴퓨터로 이동 된 A/V 처리를 사용 하 여 가상 데스크톱에서 실행 되는 비즈니스용 Skype 클라이언트를 사용할 수 있습니다. Citrix 기반 가상 데스크톱 환경의 경우 Citrix 실시간 최적화 팩을 사용 하는 것이 좋지만 추가 지원이 계획 되어 있습니다.
    
- VMWare와 공동 작업을 통해 개발 된 비즈니스용 Skype의 **Vmware 수평 가상화 팩** 을 사용 하면 우수한 사용자 환경을 제공 하면서 가상 데스크톱에서 비즈니스용 skype를 제공할 수 있습니다. 솔루션은 클라이언트 끝점에서 오디오 및 비디오 통화에 대 한 미디어 오프 로드 기능을 제공 하 여 최적화 된 솔루션을 만들기 위해 클라이언트에서 미디어 엔진을 활용 하 여 작동 합니다. 일대일 공동 작업을 위해 끝점 간에 직접 오디오 및 비디오를 제공 하거나, 단체 전화 회의 또는 모임에 대 한 중앙 Multipoint 컨트롤 단위 (MCU)로 오프 로드 하는 솔루션입니다.
    
> [!NOTE]
> 비즈니스용 Skype 기본 클라이언트는 Citrix HDX 실시간 최적화 팩 또는 VMWare 수평 가상화 팩에서 지원 되지 않습니다. 
  
## <a name="citrix-hdx-realtime-optimization-pack"></a>Citrix HDX 실시간 최적화 팩
<a name="Citrix_RT"> </a>

Citrix의 VDI 환경 플러그 인 (XenApp 및 XenDesktop의 기능)은 Lync 2013 및 비즈니스용 Skype 2015 및 2016 (전체 클라이언트에서 설치 프로그램을 실행 하는 모든 작업을 사용 하는 모든 경우) 또는 가상 컴퓨터에 설치 된 클라이언트에는 1 월 2017 PU에 릴리스된 MSI 설치 관리자)와 호환 됩니다. 데스크톱이. 전체 기능은 Microsoft Lync VDI 플러그 인을 기반으로 하지만 Windows 10, Macintosh, Linux 등의 광범위 한 클라이언트 운영 체제에서 작동 합니다.
  
모든 기능 및 지원 되는 기술의 목록은 [Microsoft 비즈니스용 Skype를 XenApp 및 XenDesktop 사용자에 게 제공 하](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf)는 Citrix 웹사이트에 나와 있습니다.
  
자세한 내용은 다음 링크를 검토 하세요.
  
- Citrix [HDX 실시간 최적화 팩 2.1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)
    
- [기술 개요](https://docs.citrix.com/en-us/hdx-optimization/2-1/about.mdl)
    
- [CTX200279 Skype for Business 기능 지원](https://support.citrix.com/article/CTX200279)
    
## <a name="vmware-horizon-virtualization-pack"></a>VMWare 수평 가상화 팩
<a name="Citrix_RT"> </a>

VMWare의 VDI 환경 솔루션은 가상 데스크톱에 설치 된 비즈니스용 Skype 2015 및 2016 전체 클라이언트와 호환 됩니다. 전체 기능은 Microsoft Lync VDI 플러그 인을 기반으로 하지만 Windows 10, Macintosh, Linux 등의 광범위 한 클라이언트 운영 체제에서 작동 합니다. 
  
기능 및 지원 되는 기술에 대 한 자세한 내용은 VMWare 웹 사이트에서 다음 링크를 참조 하세요.
  
- [VMware 수평 7.4 &amp; 수평 클라이언트 4.7의 새로운 기능](https://blogs.vmware.com/euc/2018/01/vmware-horizon-7-4-horizon-client-4-7-whats-new.mdl)
    
- [비즈니스용 Skype의 수평 가상화 팩](https://www.vmware.com/products/horizon/skype-for-business.mdl)
    
- [VMWare 구간이 있는 비즈니스용 Microsoft Skype](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/products/horizon/vmware-skype-for-business-solution-brief.pdf)
    
## <a name="microsofts-lync-vdi-plug-in"></a>Microsoft의 Lync VDI 플러그 인
<a name="Citrix_RT"> </a>

Microsoft Lync VDI 플러그 인 솔루션을 사용 하는 경우 사용자는 Windows 컴퓨터 또는 씬 클라이언트에 있어야 하며 가상 데스크톱의 클라이언트에서 오디오/비디오 스트림을 처리 하기 위해 Microsoft의 Lync VDI 플러그 인이 설치 되어 있어야 합니다. 사용자는 다음을 수행 합니다.
  
1. 오디오/비디오 장치 (예: 헤드셋 또는 카메라)를 로컬 컴퓨터에 연결 합니다.
    
2. Lync 2013 또는 비즈니스용 Skype 2015 클라이언트를 사용 하 여 원격 가상 데스크톱에 연결 합니다.
    
3. 가상 데스크톱에 비즈니스용 Skype에 대 한 자격 증명을 입력 합니다.
    
4. 사용자 자격 증명을 다시 입력 하 여 로컬 Windows 컴퓨터 또는 씬 클라이언트의 Lync VDI 플러그 인에 연결을 설정 합니다.
    
연결이 설정 되 면 사용자는 음성 및 영상 통화를 설정 하 고 수신할 준비가 된 것입니다. 로컬 컴퓨터에서 오디오/비디오 처리를 처리 하므로 네트워크의 트래픽 및 가상 데스크톱의 부하가 최소화 됩니다.
  
Microsoft의 Lync VDI 플러그 인은 특정 Windows 운영 체제 에서만 지원 되며 Lync 2013 또는 비즈니스용 Skype 2015 클라이언트만 지원 합니다. 지원 되는 기술 및 제한 사항에 대 한 자세한 내용은 [지원 되는 가상화 기술 및 알려진 제한 사항을](vdi-environments.md#Supported_virt) 참조 하세요.
  
자세한 내용은 다음 링크를 검토 하세요.
  
- [지원되는 가상화 기술 및 알려진 제한 사항](vdi-environments.md#Supported_virt)
    
- [Lync VDI 플러그 인 필수 구성 요소](vdi-environments.md#VDI_prereq)
    
- [비즈니스용 Skype 서버를 사용 하 여 Lync VDI 플러그 인 배포](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)
    
- Citrix 지식 센터 문서 [CTX138408](https://support.citrix.com/article/CTX138408)
    
Microsoft VDI 플러그 인은 [Microsoft LYNC vdi 2013 플러그 인 (32 비트)](https://www.microsoft.com/en-us/download/details.aspx?id=35457) 또는 [microsoft lync vdi 2013 플러그 인 (64 bit)](https://www.microsoft.com/en-us/download/details.aspx?id=35454)에서 사용할 수 있습니다. 이 플러그인은 이름에 관계 없이 비즈니스용 Skype 2015 클라이언트에서 지원 됩니다.
  
### <a name="supported-virtualization-technologies-and-known-limitations"></a>지원되는 가상화 기술 및 알려진 제한 사항
<a name="Supported_virt"> </a>

Lync VDI 플러그 인을 사용 하면 지원 되는 가상화 기술에 대 한 오디오 및 비디오 통화를 할 수 있습니다. 표준 전화 규정을 준수 하는 경우 E911에 대 한 지원도 포함 됩니다. 다음 섹션에서는 Lync VDI 플러그 인 및 알려진 기능 제한에서 지원 되는 가상화 기술에 대해 설명 합니다.
  
#### <a name="support-for-virtualization-technologies"></a>가상화 기술 지원

Lync VDI 플러그 인은 개인용 가상 데스크톱 시나리오에서 전체 데스크톱 원격 세션을 지원 하지만, 원격 데스크톱 세션 시나리오에는 해당 하지 않습니다. 이러한 시나리오는 아래와 같이 설명할 수 있습니다.
  
- **지원됨: 개인용 가상 데스크톱 또는 VDI(가상 데스크톱 인프라). ** 이 시나리오에서 각 사용자는 사용자 지정 가능한 가상 데스크톱에 로그온하고 세션 간 동일하게 유지되는 데스크톱에 파일을 저장할 수 있습니다. Microsoft 원격 데스크톱 서비스 및 VMware 수평 뷰는 비즈니스용 Skype 2015에서 사용 하도록 테스트 된 예제 구현입니다. 유효성 검사를 수행 하는 다른 구현에는 Citrix XenDesktop 포함 됩니다. Microsoft에서 테스트 한 공급 업체별 VDI 환경과 클라이언트 하드웨어에 대 한 자세한 내용은 [Microsoft Lync의 인프라 적격](https://go.microsoft.com/fwlink/?LinkID=313435)을 참조 하세요.
    
- **지원되지 않음: 원격 데스크톱 세션. ** 이 시나리오에서는 각 사용자가 사용자 지정할 수 없는 일반 가상 데스크톱 세션에 로그온 합니다. 예제에는 Microsoft RDSH (원격 데스크톱 세션) 및 Citrix 수신기와 함께 XenApp 포함 됩니다.
    
Lync VDI 플러그 인은 응용 프로그램 가상화와 같은 다른 가상화 기술을 지원 하지 않으며, 응용 프로그램을 사용 하 여 전체 응용 프로그램을 로컬로 설치할 필요 없이 사용할 수 있습니다. 예제 구현에는 Citrix XenApp 및 Microsoft Application Virtualization (App-v)이 포함 됩니다. 응용 프로그램 스트리밍, 응용 프로그램 원격, 혼합 가상화 모드 (예: 전체 데스크톱 remoting의 응용 프로그램 원격)는 지원 되지 않습니다.
  
Lync VDI 플러그 인은 DVCs (동적 가상 채널) 라는 플랫폼 독립적인 Api를 사용 하도록 디자인 되었습니다. 명시적으로 지원 되지 않는 시나리오는 VDI 솔루션 공급자의 지원 문을 참조 하세요.
  
#### <a name="lync-vdi-plug-in-prerequisites"></a>Lync VDI 플러그 인 필수 구성 요소
<a name="VDI_prereq"> </a>

VDI 환경에서 가상 컴퓨터와 사용자의 로컬 컴퓨터는이 섹션에 설명 된 요구 사항을 충족 해야 합니다.
  
> [!NOTE]
>  가상화 솔루션 공급자는 환경을 설치 하 고 배포 하는 방법에 대 한 세부 정보를 제공할 수 있습니다. Hyper-v 및 원격 데스크톱 서비스를 기반으로 가상화 된 환경을 배포 하는 방법에 대 한 일반적인 내용은 Microsoft 라이브러리에서 [hyper-v](https://go.microsoft.com/fwlink/p/?linkid=247514), [Windows Server 2008 R2의 원격 데스크톱 서비스](https://go.microsoft.com/fwlink/p/?linkid=247513) 문서를 참조 하세요. 
  
최신 서비스 팩을 사용 하 여 Windows 8, Windows 7 또는 Windows Server 2008 R2를 사용 하 여 가상 컴퓨터를 구성 해야 합니다.
  
사용자의 로컬 컴퓨터는 다음 요구 사항을 충족 해야 합니다.
  
- 사용자는 비즈니스용 Skype 서버 또는 Lync Server 2013에 있어야 합니다.
    
- 로컬 컴퓨터는 SP1, Windows 7 SP1 또는 Windows 8을 사용 하 여 Windows Embedded 표준 7을 실행 해야 합니다.
    
- 원격 데스크톱 서비스를 사용 하 고 있는 경우 로컬 컴퓨터의 운영 체제와 일치 하도록 32 비트 또는 64 비트 Lync VDI 플러그 인을 선택 합니다. 로컬 컴퓨터와 가상 머신에서 32 비트 또는 64 비트 운영 체제를 사용 하는 것이 필요 하지 않습니다. 다른 가상화 솔루션 또는 플랫폼을 사용 하 고 있는 경우 공급자의 요구 사항을 참조 하세요.
    
- 로컬 컴퓨터는 [최신 버전의 원격 데스크톱 클라이언트](https://go.microsoft.com/fwlink/p/?LinkId=268032)를 실행 중 이어야 합니다. Microsoft 또는 가상화 솔루션 공급자의 최신 원격 데스크톱 클라이언트 소프트웨어에서 원격 데스크톱 서비스 클라이언트의 최신 업데이트를 설치 합니다. 
    
- 로컬 컴퓨터에서 오디오를 재생 하 고 원격 기록을 사용할 수 없도록 원격 데스크톱 클라이언트 설정을 구성 해야 합니다. Windows에서 원격 데스크톱 연결에 대해 이러한 설정을 구성 하려면 다음 섹션인 "원격 데스크톱 연결 설정 구성"을 참조 하세요. 
    
Microsoft VDI 플러그 인은 [Microsoft LYNC vdi 2013 플러그 인 (32 비트)](https://www.microsoft.com/en-us/download/details.aspx?id=35457) 또는 [microsoft lync vdi 2013 플러그 인 (64 bit)](https://www.microsoft.com/en-us/download/details.aspx?id=35454)에서 사용할 수 있습니다.
  
#### <a name="known-feature-limitations"></a>알려진 기능 제한
<a name="VDI_prereq"> </a>

다음은 VDI 환경에서 비즈니스용 Skype 2015 클라이언트를 사용할 때 발생 하는 알려진 제한 사항입니다.
  
통화 위임 및 응답 그룹 에이전트 익명화 기능에 대해 제한적인 지원이 제공 됩니다.
  
다음 기능은 지원되지 않습니다.
  
- 통합 오디오 장치 및 비디오 장치 조정 페이지
    
- 다중 보기 비디오
    
- 대화 기록
    
- 익명으로 모임 참가 (즉, 조직과 페더레이션 되지 않는 조직에서 호스트 하는 비즈니스용 Skype 모임 참가).
    
- Lync VDI 플러그 인을 Lync Phone Edition 장치와 함께 사용 합니다.
    
- 네트워크 중단 시 통화 지속
    
- 사용자 지정된 벨 소리 및 대기 음악 기능
    
Lync VDI 플러그 인은 Office 365 환경에서 지원 되지 않습니다.
  
> [!NOTE]
> Citrix 실시간 최적화 팩은 Office 365를 지원 합니다. Citrix 기반 가상 환경의 경우 지원 되는 기능 및 버전 목록에 대 한 Citrix [기술 개요](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl) 문서를 참조 하세요.
  
## <a name="see-also"></a>참고 항목
<a name="Citrix_RT"> </a>

[비즈니스용 Skype 서버를 사용 하 여 Lync VDI 플러그 인 배포](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)

