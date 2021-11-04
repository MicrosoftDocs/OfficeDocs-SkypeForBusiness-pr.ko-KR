---
title: VDI 비즈니스용 Skype 계획
author: cichur
ms.author: v-mahoffman
ms.reviewer: krishra
manager: serdars
ms.date: 1/9/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ea68414b-bb7e-483a-b731-b6b5a44372b1
description: 이 항목에서는 원격 가상 데스크톱에 연결하는 동안 비즈니스용 Skype 계획 고려 사항을 논의합니다.
ms.openlocfilehash: 441f31dc2de7d07c01070bd4ad3c88070564609e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60745894"
---
# <a name="plan-for-skype-for-business-in-vdi-environments"></a>VDI 비즈니스용 Skype 계획
 
이 항목에서는 원격 가상 데스크톱에 연결하는 동안 비즈니스용 Skype 계획 고려 사항을 논의합니다. 
  
보안 및 규정 준수 문제가 특히 중요한 일부 조직에서는 VDI(가상 데스크톱 인프라) 환경이 사용됩니다. 사용자는 원격 데스크톱 서비스 또는 유사한 원격 연결을 사용하여 모든 데스크톱 응용 프로그램 및 파일을 사용하여 가상 데스크톱에서 작업을 합니다. 가상 비즈니스용 Skype 있는 클라이언트에서 오디오 및 비디오 처리를 과도하게 로드해야 하는 경우처럼 연결에서 전체 오디오 및 비디오와 함께 사용할 수 있습니다. 최종 사용자의 로컬 컴퓨터로 처리를 오프로드하고 가상 데스크톱의 부하를 줄이는 추가 VDI 플러그 인 소프트웨어를 사용할 수 있습니다.
  
Microsoft, Citrix 또는 VMWare에서 제공하는 VDI 플러그 인 구성 요소에 사용할 수 있는 세 가지 솔루션이 있습니다. 새 배포의 경우 Citrix HDX RealTime Optimization Pack 솔루션 또는 VMWare Horizon 가상화 팩을 사용하는 것이 좋습니다. 원래 Lync VDI 플러그 인은 나머지 수명 주기에 대해 계속 지원됩니다.
  
- **Lync VDI** 플러그 인은 Lync 2013을 위해 개발되고 가상 데스크톱에서 실행되는 Lync 2013 또는 비즈니스용 Skype 2015 클라이언트와 호환됩니다. 로컬 컴퓨터에 설치하고 가상 데스크톱의 클라이언트에서 로컬 오디오 및 비디오 장치를 사용할 수 있는 독립 실행형 응용 프로그램입니다. 플러그 인을 사용하려면 비즈니스용 Skype 클라이언트를 설치할 필요가 없습니다. 이 클라이언트는 Windows 7, Windows 8 또는 Windows Server 2008 운영 체제를 실행해야 합니다. (이러한 운영 체제를 사용하고 Microsoft에서 지원하는 씬 클라이언트 디바이스에는 Dell Wyse Z90D7, Dell Wyse R90L7, Dell Wyse X90m7, HP t610 및 HP t5740e가 포함됩니다.) 이 플러그 인은 계속 지원되지만 향후 업데이트는 계획되지 않습니다. Citrix 기반 가상 환경의 경우 Citrix 실시간 최적화 팩을 권장합니다.
    
- **Citrix 실시간** 최적화 팩은 Lync VDI 플러그 인을 빌드하고 가상 데스크톱의 Lync 2013 또는 비즈니스용 Skype 2016 클라이언트에서 작동합니다. 원래 VDI 플러그 인을 개선하기 위해 Citrix와 Microsoft에서 공동 개발한 것입니다. Windows 비영구 운영 체제(Windows 10, Mac 및 Linux 포함)가 있는 클라이언트에 Windows 수 있습니다. 이 구성 요소는 RealTime Connector(가상 데스크톱에 설치)와 RealTime 미디어 엔진(최종 사용자의 로컬 컴퓨터에 설치)의 두 구성 요소로 구성됩니다. 이 두 구성 요소를 사용하면 사용자의 로컬 컴퓨터에서 A/V 처리가 로컬 컴퓨터로 이동된 비즈니스용 Skype 실행 중인 비즈니스용 Skype 클라이언트를 사용할 수 있습니다. Citrix 기반 가상 데스크톱 환경의 경우 Citrix 실시간 최적화 팩을 권장하며 추가 지원이 계획됩니다.
    
- VMWare와 함께 개발된 비즈니스용 Skype용 **VMWare Horizon** 가상화 팩을 사용하면 뛰어난 사용자 환경을 제공하는 동시에 가상 데스크톱에서 비즈니스용 Skype 제공할 수 있습니다. 이 솔루션은 클라이언트의 미디어 엔진을 사용하여 최적화된 솔루션을 만들고 클라이언트 끝점은 오디오 및 비디오 통화에 대한 미디어 오프로드 기능을 제공합니다. 일대일 공동 작업을 위한 끝점 간에 직접 오디오 및 비디오를 전달하거나, 다중 회의 통화 또는 모임을 위해 중앙 MCU(Multipoint Control Unit)로 오프로드할 수 있는 이 솔루션입니다.
    
> [!NOTE]
> 기본 비즈니스용 Skype Citrix HDX RealTime 최적화 팩 또는 VMWare Horizon 가상화 팩에서는 지원되지 않습니다. 
  
## <a name="citrix-hdx-realtime-optimization-pack"></a>Citrix HDX 실시간 최적화 팩
<a name="Citrix_RT"> </a>

Citrix의 VDI 환경 플러그 인(XenApp 및 XenDesktop의 기능)은 Lync 2013 및 비즈니스용 Skype 2015 및 2016(모든 클릭으로 설치 관리자를 실행하거나 2017년 1월 PU 이후 릴리스된 MSI 설치 관리자) 클라이언트와 호환됩니다. 전체적인 작동은 Microsoft Lync VDI 플러그 인을 기반으로 하지만 Windows 10, Macintosh 및 Linux를 비롯한 다양한 클라이언트 운영 체제에서 작동합니다.
  
기능 및 지원되는 기술의 전체 목록은 Citrix 웹 사이트에서 [XenApp 및 XenDesktop](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf)사용자에게 Microsoft 비즈니스용 Skype 제공에서 찾을 수 있습니다.
  
자세한 내용은 다음 링크를 검토하세요.
  
- Citrix [HDX RealTime Optimization Pack 2.1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)
    
- [기술 개요](https://docs.citrix.com/en-us/hdx-optimization/2-1/about.mdl)
    
- [CTX200279 비즈니스용 Skype 기능 지원](https://support.citrix.com/article/CTX200279)
    
## <a name="vmware-horizon-virtualization-pack"></a>VMWare Horizon 가상화 팩
<a name="Citrix_RT"> </a>

VMWare의 VDI 환경 솔루션은 가상 데스크톱에 설치된 비즈니스용 Skype 2015 및 2016 전체 클라이언트와 호환됩니다. 전체적인 작동은 Microsoft Lync VDI 플러그 인을 기반으로 하지만 Windows 10, Macintosh 및 Linux를 비롯한 다양한 클라이언트 운영 체제에서 작동합니다. 
  
기능 및 지원되는 기술에 대한 전체 설명은 다음 링크에서 VMWare 웹 사이트에서 확인할 수 있습니다.
  
- [VMware Horizon 7.4 &amp; Horizon Client 4.7의 새로운](https://blogs.vmware.com/euc/2018/01/vmware-horizon-7-4-horizon-client-4-7-whats-new.mdl)
    
- [Horizon Virtualization Pack for 비즈니스용 Skype](https://www.vmware.com/products/horizon/skype-for-business.mdl)
    
- [Microsoft 비즈니스용 Skype VMWare Horizon 사용](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/products/horizon/vmware-skype-for-business-solution-brief.pdf)
    
## <a name="microsofts-lync-vdi-plug-in"></a>Microsoft의 Lync VDI 플러그 인
<a name="Citrix_RT"> </a>

Microsoft Lync VDI 플러그 인 솔루션을 사용할 경우 사용자는 Windows 컴퓨터 또는 씬 클라이언트에 있으며 가상 데스크톱의 클라이언트에서 오디오/비디오 스트림을 처리하기 위해 Microsoft의 Lync VDI 플러그 인을 설치해야 합니다. 사용자는 다음을 할 수 있습니다.
  
1. 커넥트/비디오 장치(예: 헤드셋 또는 카메라)를 로컬 컴퓨터에 연결합니다.
    
2. 커넥트 Lync 2013 또는 비즈니스용 Skype 원격 가상 데스크톱에 연결합니다.
    
3. 가상 데스크톱에서 비즈니스용 Skype 자격 증명을 입력합니다.
    
4. 사용자 자격 증명을 다시 입력하여 로컬 컴퓨터 또는 씬 클라이언트에서 Lync VDI Windows 연결합니다.
    
연결이 설정되면 사용자는 오디오 및 비디오 통화를 걸고 받을 수 있습니다. 로컬 컴퓨터가 오디오/비디오 처리를 처리하기 때문에 네트워크의 트래픽과 가상 데스크톱의 부하가 최소화됩니다.
  
Microsoft의 Lync VDI 플러그 인은 특정 Windows 운영 체제에서만 지원하며 Lync 2013 또는 비즈니스용 Skype 2015 클라이언트만 지원합니다. [지원되는](vdi-environments.md#Supported_virt) 기술 및 제한에 대한 자세한 내용은 지원되는 가상화 기술 및 알려진 제한 사항을 참조합니다.
  
자세한 내용은 다음 링크를 검토하세요.
  
- [지원되는 가상화 기술 및 알려진 제한 사항](vdi-environments.md#Supported_virt)
    
- [Lync VDI 플러그 인 필요](vdi-environments.md#VDI_prereq)
    
- [Lync VDI 플러그 인을 비즈니스용 Skype 서버](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)
    
- Citrix 기술 센터 문서 [CTX138408](https://support.citrix.com/article/CTX138408)
    
Microsoft VDI 플러그 인은 [Microsoft Lync VDI 2013 플러그 인(32비트)](https://www.microsoft.com/download/details.aspx?id=35457) 또는 [Microsoft Lync VDI 2013 플러그 인(64비트)에서](https://www.microsoft.com/download/details.aspx?id=35454)사용할 수 있습니다. 이 플러그 인은 이름과는 비즈니스용 Skype 클라이언트에서 지원됩니다.
  
### <a name="supported-virtualization-technologies-and-known-limitations"></a>지원되는 가상화 기술 및 알려진 제한 사항
<a name="Supported_virt"> </a>

Lync VDI 플러그 인을 사용하면 지원되는 가상화 기술에 대한 오디오 및 비디오 통화가 허용됩니다. 표준 전화 규정을 준수하는 E911 지원도 포함됩니다. 다음 섹션에서는 Lync VDI 플러그 인에서 지원하는 가상화 기술 및 알려진 기능 제한에 대해 설명합니다.
  
#### <a name="support-for-virtualization-technologies"></a>가상화 기술 지원

Lync VDI 플러그 인은 개인 가상 데스크톱 시나리오에서 전체 데스크톱 원격 세션을 지원하지만 원격 데스크톱 세션 시나리오에서는 지원되지 않습니다. 이러한 시나리오는 다음과 같이 설명할 수 있습니다.
  
- **지원: 개인 설정된 가상 데스크톱 또는 VDI(가상 데스크톱 인프라)** 이 시나리오에서 각 사용자는 사용자 지정 가능한 가상 데스크톱에 로그온하고 세션 전체에서 유지되는 파일을 데스크톱에 저장할 수 있습니다. Microsoft 원격 데스크톱 서비스 및 VMware Horizon View는 2015에서 사용하기 위해 테스트된 비즈니스용 Skype 구현입니다. 유효성 검사를 진행하는 다른 구현에는 Citrix XenDesktop이 포함됩니다. Microsoft에서 테스트한 공급업체별 VDI 환경 및 클라이언트 하드웨어에 대한 자세한 내용은 Microsoft Lync에 대해 자격을 갖춘 [인프라를 참조하세요.](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md)
    
- **지원되지 않는 경우: 원격 데스크톱 세션.** 이 시나리오에서 각 사용자는 사용자 정의할 수 없는 일반 가상 데스크톱 세션에 로그온합니다. 예를 들어 Microsoft 원격 데스크톱(RDSH) 및 Citrix Receiver와 결합된 Citrix XenApp이 있습니다.
    
Lync VDI 플러그 인은 전체 응용 프로그램을 로컬로 설치하지 않고도 응용 프로그램을 사용할 수 있는 응용 프로그램 가상화와 같은 다른 가상화 기술을 지원하지 않습니다. 구현 예로는 Citrix XenApp 및 Microsoft App-V(Application Virtualization)가 있습니다. 응용 프로그램 스트리밍, 응용 프로그램 원격 및 혼합 가상화 모드(예: 전체 데스크톱 원격의 응용 프로그램 원격)는 지원되지 않습니다.
  
Lync VDI 플러그 인은 DVC(동적 가상 채널)라는 플랫폼 독립적 API를 사용하도록 디자인되었습니다. 명시적으로 지원되지 않는 시나리오는 VDI 솔루션 공급자의 지원 문을 참조하세요.
  
#### <a name="lync-vdi-plug-in-prerequisites"></a>Lync VDI 플러그 인 필요
<a name="VDI_prereq"> </a>

VDI 환경에서는 가상 컴퓨터와 사용자의 로컬 컴퓨터가 이 섹션에 설명된 요구 사항을 충족해야 합니다.
  
> [!NOTE]
>  가상화 솔루션 공급자는 해당 환경을 설치 및 배포하는 방법에 대한 세부 정보를 제공합니다. Hyper-V 및 원격 데스크톱 서비스를 기반으로 가상화된 환경을 배포하는 데 대한 일반적인 정보는 Microsoft 라이브러리의 Hyper-V [,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753637(v=ws.10))Windows [Server 2008 R2의](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd736539(v=ws.10)) 원격 데스크톱 서비스를 참조하십시오. 
  
가상 컴퓨터는 최신 서비스 팩을 Windows 8, Windows 7 또는 Windows Server 2008 R2로 구성해야 합니다.
  
사용자의 로컬 컴퓨터는 다음 요구 사항을 충족해야 합니다.
  
- 사용자가 Lync Server 2013 또는 비즈니스용 Skype 서버 있어야 합니다.
    
- 로컬 컴퓨터에서 Embedded Standard 7 SP1 Windows SP1, Windows 7 SP1 또는 Windows 8.
    
- 원격 데스크톱 서비스를 사용하는 경우 로컬 컴퓨터의 운영 체제와 일치하게 32비트 또는 64비트 Lync VDI 플러그 인을 선택하십시오. 로컬 컴퓨터와 가상 컴퓨터 모두 32비트 또는 64비트 운영 체제를 사용할 필요는 없습니다. 다른 가상화 솔루션 또는 플랫폼을 사용하는 경우 공급자의 요구 사항을 참조하세요.
    
- 로컬 컴퓨터에서 최신 버전의 원격 데스크톱 [클라이언트를 실행하고 있어야 합니다.](/windows-server/remote/remote-desktop-services/clients/remote-desktop-clients) Microsoft에서 제공하는 원격 데스크톱 서비스 클라이언트의 최신 업데이트를 설치하거나 가상화 솔루션 공급자가 제공하는 최신 원격 데스크톱 클라이언트 소프트웨어를 설치합니다. 
    
- 로컬 컴퓨터에서 오디오가 재생되고 원격 녹음을 사용할 수 없도록 원격 데스크톱 클라이언트 설정을 구성해야 합니다. 원격 데스크톱 연결에 대해 이러한 설정을 Windows 다음 섹션인 "원격 데스크톱 연결 설정을 구성하려면"을 참조하세요. 
    
Microsoft VDI 플러그 인은 [Microsoft Lync VDI 2013 플러그 인(32비트)](https://www.microsoft.com/download/details.aspx?id=35457) 또는 [Microsoft Lync VDI 2013 플러그 인(64비트)에서](https://www.microsoft.com/download/details.aspx?id=35454)사용할 수 있습니다.
  
#### <a name="known-feature-limitations"></a>알려진 기능 제한 사항
<a name="VDI_prereq"> </a>

다음은 VDI 환경에서 비즈니스용 Skype 2015 클라이언트를 사용할 때 알려진 제한 사항입니다.
  
통화 위임 및 응답 그룹 에이전트의Onymization 기능에 대한 지원은 제한됩니다.
  
다음 기능은 지원하지 않습니다.
  
- 통합 오디오 장치 및 비디오 장치 조정 페이지.
    
- 다중 보기 비디오.
    
- 대화 기록.
    
- 모임에 익명으로 참가(즉, 조직과 페더 비즈니스용 Skype 조직에서 호스팅하는 모임에 참가)
    
- Lync 전화 장치와 함께 Lync VDI 플러그 인 사용
    
- 네트워크가 정전된 경우 통화 연속성
    
- 사용자 지정된 벨소리 및 보류 음악 기능.
    
Lync VDI 플러그 인은 Microsoft 365 환경에서 Office 365 않습니다.
  
> [!NOTE]
> Citrix 실시간 최적화 팩은 이러한 Microsoft 365 Office 365. Citrix 기반 가상 환경의 경우 지원되는 기능 및 버전 목록은 Citrix의 [기술](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl) 개요 설명서를 참조하세요.
  
## <a name="see-also"></a>참고 항목
<a name="Citrix_RT"> </a>

[Lync VDI 플러그 인을 비즈니스용 Skype 서버](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)