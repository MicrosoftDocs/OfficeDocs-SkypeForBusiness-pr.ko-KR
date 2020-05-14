---
title: VDI 환경에서 비즈니스용 Skype 계획
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
description: 이 항목에서는 원격 가상 데스크톱에 연결 하는 동안 비즈니스용 Skype를 사용할 때의 계획 고려 사항에 대해 설명 합니다.
ms.openlocfilehash: 6886eab8a13db852e0aa86b63d08aa33f82fdaed
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219528"
---
# <a name="plan-for-skype-for-business-in-vdi-environments"></a>VDI 환경에서 비즈니스용 Skype 계획
 
이 항목에서는 원격 가상 데스크톱에 연결 하는 동안 비즈니스용 Skype를 사용할 때의 계획 고려 사항에 대해 설명 합니다. 
  
보안 및 준수 문제가 특히 중요 한 일부 조직에서는 VDI (가상 데스크톱 인프라) 환경이 사용 됩니다. 사용자는 원격 데스크톱 서비스 또는 이와 비슷한 원격 연결을 사용 하 여 모든 데스크톱 응용 프로그램 및 파일을 포함 하는 가상 데스크톱에서 작업을 수행 합니다. 비즈니스용 Skype를 사용 하 여 전체 오디오 및 비디오를 가상 데스크톱에 있는 클라이언트의 오디오 및 비디오 처리를 과도 하 게 로드 해야 하는 것과 같이 연결 합니다. 최종 사용자의 로컬 컴퓨터로 처리 되는 추가 VDI 플러그 인 소프트웨어를 사용 하 여 가상 데스크톱의 부하를 줄일 수 있습니다.
  
Microsoft, Citrix 또는 VMWare에서 제공 하는 VDI 플러그 인 구성 요소에 대해 세 가지 솔루션을 사용할 수 있습니다. 새 배포의 경우 Citrix HDX 실시간 최적화 팩 솔루션 또는 VMWare 수평 가상화 팩을 사용 하는 것이 좋습니다. 원래 Lync VDI 플러그 인은 해당 수명 주기의 나머지 부분에 대해서도 계속 지원 됩니다.
  
- **LYNC VDI 플러그** 인은 lync 2013 용으로 개발 되었으며, 가상 데스크톱에서 실행 되는 lync 2013 또는 비즈니스용 Skype 2015 클라이언트와 호환 됩니다. 로컬 컴퓨터에 설치 되는 독립 실행형 응용 프로그램으로, 가상 데스크톱의 클라이언트와 로컬 오디오 및 비디오 장치를 사용할 수 있습니다. 플러그 인을 사용 하려면 비즈니스용 Skype 클라이언트를 로컬 컴퓨터 또는 씬 클라이언트 (Windows 7, Windows 8 또는 Windows Server 2008 운영 체제를 실행 해야 함)에 설치할 필요가 없습니다. (이러한 운영 체제를 사용 하 고 Microsoft에서 지 원하는 씬 클라이언트 장치에는 Dell Wyse Z90D7, Dell Wyse R90L7, Dell Wyse X90m7, HP t610 및 HP t5740e)이 포함 되어 있습니다. 이 플러그 인은 여전히 지원 되지만 향후 업데이트는 계획 되지 않습니다. Citrix 기반 가상 환경의 경우 Citrix 실시간 최적화 팩을 사용 하는 것이 좋습니다.
    
- **Citrix 실시간 최적화 팩** 은 lync VDI 플러그 인을 기반으로 하며, 가상 데스크톱에서 lync 2013 또는 비즈니스용 Skype 2016 클라이언트와 함께 작동 합니다. 이는 원래 VDI 플러그 인을 개선 하기 위해 Citrix와 Microsoft에서 공동으로 개발한 것입니다. Windows 및 비 Windows 운영 체제 (Windows 10, Mac 및 Linux 포함)를 사용 하 여 클라이언트에 설치할 수 있습니다. 이 구성 요소는 실시간 커넥터 (가상 데스크톱에 설치 됨)와 실시간 미디어 엔진 (최종 사용자의 로컬 컴퓨터에 설치 됨)의 두 가지 요소로 구성 됩니다. 이러한 두 구성 요소를 통해 사용자의 로컬 컴퓨터는 로컬 컴퓨터로 이동 된 A/V 처리를 통해 가상 데스크톱에서 실행 되는 비즈니스용 Skype 클라이언트를 사용할 수 있습니다. Citrix 기반 가상 데스크톱 환경의 경우 Citrix 실시간 최적화 팩을 사용 하는 것이 좋지만 추가 지원이 계획 됩니다.
    
- VMWare와 공동 작업을 통해 개발 된 비즈니스용 Skype의 **VMWare 수평 가상화 팩** 을 사용 하 여 가상 데스크톱에 비즈니스용 skype를 제공 하 고 뛰어난 사용자 환경을 제공할 수 있습니다. 이 솔루션은 클라이언트 끝점이 오디오 및 비디오 통화에 대 한 미디어 오프 로드 기능을 제공 하는 미디어 엔진을 사용 하 여 최적화 된 솔루션을 만드는 방식으로 작동 합니다. 이 솔루션은 일대일 공동 작업을 위한 끝점 간에 직접 오디오 및 비디오를 배달 하거나 단체 전화 회의 또는 회의를 위한 중앙 Multipoint 제어 장치 (MCU)로 오프 로드할 수 있습니다.
    
> [!NOTE]
> 비즈니스용 Skype 기본 클라이언트는 Citrix HDX 실시간 최적화 팩 이나 VMWare 수평 가상화 팩에서 지원 되지 않습니다. 
  
## <a name="citrix-hdx-realtime-optimization-pack"></a>Citrix HDX 실시간 최적화 팩
<a name="Citrix_RT"> </a>

Citrix의 VDI 환경 플러그 인 (XenApp 및 XenDesktop의 특징)은 Lync 2013 및 비즈니스용 Skype 2015 및 2016 (전체 클라이언트는 설치 관리자를 실행 하는 모든 권한 또는 모든 클라이언트가 가상 데스크톱에 설치 된 경우에는 모든 경우에 사용 하는 클라이언트 또는 1 월 2017 일 이후에 릴리스된 MSI installer)와 호환 됩니다. 이 작업은 Microsoft Lync VDI 플러그 인을 기반으로 하지만 Windows 10, Macintosh 및 Linux를 포함 하 여 광범위 한 클라이언트 운영 체제에서 작동 합니다.
  
[Microsoft 비즈니스용 Skype를 XenApp 및 XenDesktop 사용자에 게 제공 하](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf)여 Citrix 웹 사이트에서 기능 및 지원 되는 기술의 전체 목록을 확인할 수 있습니다.
  
자세한 내용은 다음 링크를 참조 하십시오.
  
- Citrix [HDX 실시간 최적화 팩 2.1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)
    
- [기술 개요](https://docs.citrix.com/en-us/hdx-optimization/2-1/about.mdl)
    
- [CTX200279 비즈니스용 Skype 기능 지원](https://support.citrix.com/article/CTX200279)
    
## <a name="vmware-horizon-virtualization-pack"></a>VMWare 수평 가상화 팩
<a name="Citrix_RT"> </a>

VMWare의 VDI 환경 솔루션은 가상 데스크톱에 설치 된 비즈니스용 Skype 2015 및 2016 전체 클라이언트와 호환 됩니다. 이 작업은 Microsoft Lync VDI 플러그 인을 기반으로 하지만 Windows 10, Macintosh 및 Linux를 포함 하 여 광범위 한 클라이언트 운영 체제에서 작동 합니다. 
  
기능 및 지원 되는 기술에 대 한 자세한 내용은 VMWare 웹 사이트에서 다음 링크를 참조 하십시오.
  
- [VMware 수평 7.4 수평 4.7의 새로운 기능 &amp;](https://blogs.vmware.com/euc/2018/01/vmware-horizon-7-4-horizon-client-4-7-whats-new.mdl)
    
- [비즈니스용 Skype에 대 한 수평 가상화 팩](https://www.vmware.com/products/horizon/skype-for-business.mdl)
    
- [VMWare 수평을 사용 하는 Microsoft 비즈니스용 Skype](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/products/horizon/vmware-skype-for-business-solution-brief.pdf)
    
## <a name="microsofts-lync-vdi-plug-in"></a>Microsoft의 Lync VDI 플러그 인
<a name="Citrix_RT"> </a>

Microsoft Lync VDI 플러그 인 솔루션을 사용 하는 경우 사용자는 Windows 컴퓨터나 씬 클라이언트에 있고, 가상 데스크톱에서 클라이언트의 오디오/비디오 스트림을 처리 하기 위해 Microsoft의 Lync VDI 플러그 인이 설치 되어 있어야 합니다. 사용자는 다음을 수행 합니다.
  
1. 헤드셋 이나 카메라와 같은 오디오/비디오 장치를 로컬 컴퓨터에 연결 합니다.
    
2. Lync 2013 또는 비즈니스용 Skype 2015 클라이언트를 사용 하 여 원격 가상 데스크톱에 연결 합니다.
    
3. 가상 데스크톱에서 비즈니스용 Skype에 대 한 자격 증명을 입력 합니다.
    
4. 사용자 자격 증명을 다시 입력 하 여 로컬 Windows 컴퓨터 또는 씬 클라이언트에서 Lync VDI 플러그 인에 대 한 연결을 설정 합니다.
    
연결이 설정 된 후에는 사용자가 오디오 및 비디오 통화를 설정 하 고 받을 준비가 된 것입니다. 로컬 컴퓨터가 오디오/비디오 처리를 처리 하므로 네트워크의 트래픽이 가상 데스크톱의 부하와 최소화 됩니다.
  
Microsoft의 Lync VDI 플러그 인은 특정 Windows 운영 체제 에서만 지원 되며 Lync 2013 또는 비즈니스용 Skype 2015 클라이언트만 지원 합니다. 지원 되는 기술 및 제한 사항에 대 한 자세한 내용은 [지원 되는 가상화 기술 및 알려진 제한](vdi-environments.md#Supported_virt) 사항을 참조 하세요.
  
자세한 내용은 다음 링크를 참조 하십시오.
  
- [지원 되는 가상화 기술 및 알려진 제한 사항](vdi-environments.md#Supported_virt)
    
- [Lync VDI 플러그 인 필수 구성 요소](vdi-environments.md#VDI_prereq)
    
- [비즈니스용 Skype 서버를 사용 하 여 Lync VDI 플러그 인 배포](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)
    
- Citrix 지식 센터 문서 [CTX138408](https://support.citrix.com/article/CTX138408)
    
Microsoft VDI 플러그 인은 [Microsoft LYNC vdi 2013 플러그 인 (32 비트)](https://www.microsoft.com/download/details.aspx?id=35457) 또는 [microsoft lync vdi 2013 플러그 인 (64 bit)](https://www.microsoft.com/download/details.aspx?id=35454)에서 사용할 수 있습니다. 이 플러그 인은 이름을 사용 하지만 비즈니스용 Skype 2015 클라이언트에서 지원 됩니다.
  
### <a name="supported-virtualization-technologies-and-known-limitations"></a>지원 되는 가상화 기술 및 알려진 제한 사항
<a name="Supported_virt"> </a>

Lync VDI 플러그 인을 사용 하면 지원 되는 가상화 기술에 대 한 오디오 및 비디오 통화를 할 수 있습니다. 표준 전화 규정 준수에는 E911에 대 한 지원도 포함 되어 있습니다. 다음 섹션에서는 Lync VDI 플러그 인 및 알려진 기능 제한에 의해 지원 되는 가상화 기술에 대해 설명 합니다.
  
#### <a name="support-for-virtualization-technologies"></a>가상화 기술 지원

Lync VDI 플러그 인은 개인용 가상 데스크톱 시나리오에서 전체 데스크톱 원격 세션을 지원 하지만 원격 데스크톱 세션 시나리오에서는 사용 하지 않습니다. 이러한 시나리오는 다음과 같이 설명할 수 있습니다.
  
- **지원: 개인 설정 된 가상 데스크톱 또는 VDI (가상 데스크톱 인프라)** 이 시나리오에서는 각 사용자가 맞춤형 가상 데스크톱에 로그온 하 고 세션 간에 지속 되는 파일을 데스크톱에 저장할 수 있습니다. Microsoft 원격 데스크톱 서비스 및 VMware 수평 보기는 비즈니스용 Skype 2015에서 사용 하도록 테스트 된 예제 구현입니다. 유효성 검사 중인 기타 구현에는 Citrix XenDesktop 포함 됩니다. Microsoft에서 테스트 한 공급 업체별 VDI 환경 및 클라이언트 하드웨어에 대 한 자세한 내용은 [Microsoft Lync의 인프라 자격](https://go.microsoft.com/fwlink/?LinkID=313435)을 참조 하십시오.
    
- **지원 되지 않음: 원격 데스크톱 세션** 이 시나리오에서 각 사용자는 사용자 지정할 수 없는 일반 가상 데스크톱 세션에 로그온 합니다. 예를 들면 Microsoft RDSH (원격 데스크톱 세션) 및 citrix 수신기와 함께 사용 되는 Citrix XenApp 포함 됩니다.
    
Lync VDI 플러그 인은 전체 응용 프로그램을 로컬로 설치 하지 않고도 응용 프로그램을 사용할 수 있도록 하는 응용 프로그램 가상화와 같은 다른 가상화 기술을 지원 하지 않습니다. 예제 구현에는 Citrix XenApp 및 Microsoft Application Virtualization (App-v)이 포함 됩니다. 응용 프로그램 스트리밍, 응용 프로그램 원격 및 혼합 가상화 모드 (예: 전체 데스크톱 원격에서의 응용 프로그램 원격)는 지원 되지 않습니다.
  
Lync VDI 플러그 인은 DVCs (동적 가상 채널) 라는 플랫폼 독립적 Api를 사용 하도록 설계 되었습니다. 명시적으로 지원 되지 않는 시나리오는 VDI solution provider의 지원 문을 참조 하십시오.
  
#### <a name="lync-vdi-plug-in-prerequisites"></a>Lync VDI 플러그 인 필수 구성 요소
<a name="VDI_prereq"> </a>

VDI 환경에서는 가상 컴퓨터와 사용자의 로컬 컴퓨터가이 섹션에 설명 된 요구 사항을 충족 해야 합니다.
  
> [!NOTE]
>  가상화 솔루션 공급자는 환경을 설치 및 배포 하는 방법에 대 한 세부 정보를 제공할 수 있습니다. Hyper-v 및 원격 데스크톱 서비스를 기반으로 가상화 된 환경을 배포 하는 방법에 대 한 일반적인 정보는 Microsoft 라이브러리: [hyper-v](https://go.microsoft.com/fwlink/p/?linkid=247514), [Windows Server 2008의 원격 데스크톱 서비스](https://go.microsoft.com/fwlink/p/?linkid=247513) 에서 다음 문서를 참조 하세요. 
  
Windows 8, Windows 7 또는 Windows Server 2008 R2에서 최신 서비스 팩을 사용 하 여 가상 컴퓨터를 구성 해야 합니다.
  
사용자의 로컬 컴퓨터는 다음 요구 사항을 충족 해야 합니다.
  
- 사용자가 비즈니스용 Skype 서버 또는 Lync Server 2013에 있어야 합니다.
    
- 로컬 컴퓨터에는 SP1, Windows 7 SP1 또는 Windows 8을 사용 하는 Windows Embedded Standard 7이 실행 되 고 있어야 합니다.
    
- 원격 데스크톱 서비스를 사용 하는 경우 로컬 컴퓨터의 운영 체제와 일치 하는 32 비트 또는 64 비트 Lync VDI 플러그 인을 선택 합니다. 로컬 컴퓨터와 가상 컴퓨터 둘 다에 32 비트 또는 64 비트 운영 체제가 필요 하지는 않습니다. 다른 가상화 솔루션 또는 플랫폼을 사용 중인 경우에는 공급자의 요구 사항을 참조 하세요.
    
- 로컬 컴퓨터에서 [최신 버전의 원격 데스크톱 클라이언트](https://go.microsoft.com/fwlink/p/?LinkId=268032)를 실행 하 고 있어야 합니다. Microsoft에서 제공하는 원격 데스크톱 서비스 클라이언트의 최신 업데이트를 설치하거나 가상화 솔루션 공급자가 제공하는 최신 원격 데스크톱 클라이언트 소프트웨어를 설치합니다. 
    
- 로컬 컴퓨터에서 오디오가 재생되고 원격 녹음을 사용할 수 없도록 원격 데스크톱 클라이언트 설정을 구성해야 합니다. Windows에서 원격 데스크톱 연결에 대 한 이러한 설정을 구성 하려면 다음 섹션인 "원격 데스크톱 연결 설정을 구성 하려면"을 참조 하십시오. 
    
Microsoft VDI 플러그 인은 [Microsoft LYNC vdi 2013 플러그 인 (32 비트)](https://www.microsoft.com/download/details.aspx?id=35457) 또는 [microsoft lync vdi 2013 플러그 인 (64 bit)](https://www.microsoft.com/download/details.aspx?id=35454)에서 사용할 수 있습니다.
  
#### <a name="known-feature-limitations"></a>알려진 기능 제한 사항
<a name="VDI_prereq"> </a>

VDI 환경에서 비즈니스용 Skype 2015 클라이언트를 사용할 때의 알려진 제한은 다음과 같습니다.
  
통화 위임 및 응답 그룹 에이전트 익명화 기능에 대 한 지원은 제한적입니다.
  
다음 기능은 지원 되지 않습니다.
  
- 통합 오디오 장치 및 비디오 장치 조정 페이지
    
- 다중 보기 비디오
    
- 대화 기록
    
- 사용자의 조직과 페더레이션 하지 않는 조직에서 호스팅하는 비즈니스용 Skype 모임에 참가 하 여 모임에 익명으로 참가 합니다.
    
- Lync Phone Edition 장치와 함께 Lync VDI 플러그 인 사용
    
- 네트워크 중단이 발생 하는 경우의 통화 연속성
    
- 사용자 지정 된 벨 소리 및 보류 된 음악 기능
    
Lync VDI 플러그 인은 Microsoft 365 또는 Office 365 환경에서 지원 되지 않습니다.
  
> [!NOTE]
> Citrix 실시간 최적화 팩은 Microsoft 365 및 Office 365를 지원 합니다. Citrix 기반 가상 환경의 경우 지원 되는 기능 및 버전 목록에 대 한 Citrix [기술 개요](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl) 설명서를 검토 하십시오.
  
## <a name="see-also"></a>참고 항목
<a name="Citrix_RT"> </a>

[비즈니스용 Skype 서버를 사용 하 여 Lync VDI 플러그 인 배포](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)

