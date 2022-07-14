---
title: Microsoft Teams용 클라우드 비디오 Interop
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: naforer
f1.keywords:
- NOCSH
description: 클라우드 비디오 Interop을 중간 솔루션으로 사용하여 타사 회의실 디바이스가 Microsoft Teams 모임에 참가할 수 있도록 합니다.
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 91ec337ad94341e20b07cd376be5156a526d8cd0
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789363"
---
# <a name="cloud-video-interop-for-microsoft-teams"></a>Microsoft Teams용 클라우드 비디오 Interop

CVI(Cloud Video Interop)는 타사 회의실(원격 통신) 및 개인 비디오 장치(VTC)가 Microsoft Teams 모임에 참가할 수 있도록 하는 Microsoft 정규화된 타사 솔루션입니다.
 
Microsoft Teams를 사용하면 오디오, 비디오 및 콘텐츠 공유가 포함된 모임에서 풍부한 온라인 콘텐츠 공동 작업을 수행할 수 있습니다. 이 기능은 데스크톱 및 웹 클라이언트뿐만 아니라 Microsoft Teams와 기본적으로 통합되는 많은 파트너 디바이스를 통해 즐길 수 있습니다. 그러나 많은 고객이 이미 비디오 원격 회의 및 개인 비디오 통신 디바이스에 투자하여 업그레이드 비용이 많이 들 수 있습니다. Cloud Video Interop은 업그레이드할 준비가 될 때까지 기존 솔루션을 계속 사용할 수 있는 쉬운 솔루션을 제공합니다.

Cloud Video Interop을 통해 Microsoft Teams는 모든 참가자(회의실 또는 Teams 클라이언트 내부)를 위한 네이티브 모임 환경을 제공합니다.

### <a name="is-cloud-video-interop-for-me"></a>Cloud Video Interop이 적합한가요?

Cloud Video Interop은 Teams 엔드포인트를 사용하여 전체 네이티브 Microsoft Teams 솔루션으로 전환하는 동안 중간 서비스를 제공합니다. 제공된 서비스는 마이그레이션 경로의 일부여야 합니다.

Cloud Video Interop은 다음 조건을 충족하는 고객을 위한 것입니다.

- Microsoft Teams와 직접 통합할 자격이 없는 회의실 디바이스 및 개인 비디오 디바이스 배포(50개 이상 장치)를 대규모로 배포
- Cloud Video Interop 파트너 중 하나에서 지원됩니다.
- 네이티브 Microsoft Teams 솔루션으로 마이그레이션하는 동안 현재 회의실 장치 및 개인 비디오 디바이스에 대한 투자 가치를 유지하려고 합니다.

Cloud Video Interop은 훌륭한 중간 솔루션을 제공하지만, 고객은 장기적으로 Teams 룸 시스템과 같은 네이티브 Teams 모임 솔루션을 살펴보는 것이 좋습니다. 

### <a name="office-365-us-government-and-third-party-services"></a>미국 정부 및 타사 서비스 Office 365

Office 365 타사 응용 프로그램을 SharePoint Online 사이트, 비즈니스용 Skype, Teams, 엔터프라이즈용 Microsoft 365 앱 포함된 Office 응용 프로그램(예: Word, Excel, PowerPoint, Outlook) 및 Outlook Web App 통합하는 기능을 제공합니다. 또한 Office 365 타사 서비스 공급자와의 통합을 지원합니다. 이러한 타사 애플리케이션 및 서비스에는 Office 365 인프라 외부에 있으므로 Office 365 규정 준수 및 데이터 보호 약정에 포함되지 않는 타사 시스템에서 조직의 고객 데이터를 저장, 전송 및 처리하는 작업이 포함될 수 있습니다. **조직에 대한 이러한 서비스의 적절한 사용을 평가할 때 타사에서 제공하는 개인 정보 보호 및 규정 준수 문을 검토하는 것이 좋습니다.**



### <a name="partners-certified-for-microsoft-teams"></a>Microsoft Teams용 파트너 인증

다음 파트너에는 Microsoft Teams용 비디오 interop 솔루션이 있습니다. 회사에서 기업 내에서 이러한 파트너의 조합으로 작업하도록 선택할 수 있습니다. 

|파트너|파트너 솔루션|
|----|---|
|![Poly RealConnect를 나타내는 로고입니다.](media/polycom.png) | <a href="https://aka.ms/PolycomRealConnect" target="_blank">Poly RealConnect 서비스</a> |
|![Pexip Infinity를 나타내는 로고입니다.](media/pexip.png)| <a href="https://aka.ms/PexipInfinity" target="_blank">Microsoft Teams용 Pexip Infinity</a> | 
|![BlueJeans 게이트웨이를 나타내는 로고입니다.](media/bluejeans.png)| <a href="https://aka.ms/BluejeansGateway" target="_blank">Microsoft Teams용 BlueJeans 게이트웨이</a> |
|![Cisco CVI를 나타내는 로고입니다.](media/cisco.png)|<a href="https://aka.ms/CiscoCVI" target="_blank">Microsoft Teams용 Cisco Webex 비디오 통합</a>|

### <a name="cloud-video-interop-overview"></a>Cloud Video Interop 개요

Cloud Video Interop는 파트너가 기존 비디오 회의와 온-프레미스의 개인 비디오 디바이스 솔루션과 Microsoft Teams 간의 상호 운용성을 제공하기 위해 제공하는 타사 서비스입니다.

파트너가 제공하는 솔루션은 완전 클라우드 기반 또는 부분적으로/완전히 온-프레미스에 배포할 수 있는 구성 요소로 구성됩니다. 
     
다음 다이어그램에서는 파트너 솔루션의 개략적인 아키텍처를 보여 줍니다.

![Teams Cloud Video Interop 파트너 솔루션을 설명하는 다이어그램](media/teams-cloud-video-interop-partner-solution.png)


## <a name="deploy-cloud-video-interop"></a>Cloud Video Interop 배포

Cloud Video Interop 솔루션을 배포할 때 파트너 솔루션을 배포하고 있음을 이해하는 것이 중요합니다. Cloud Video Interop를 배포하기 위해 수행해야 하는 일반적인 단계는 다음 다이어그램에 나열되어 있습니다.

![조직에서 CVI 배포를 설명하는 다이어그램](media/deploying-cvi.png)

### <a name="plan"></a>계획

계획 단계에서는 네이티브 Teams 디바이스로 대체하지 않을 디바이스를 식별하고 이러한 디바이스를 지원할 수 있는 Cloud Video Interop 파트너를 찾아야 합니다.  

Cloud Video Interop 지원 디바이스가 참가할 모임을 예약할 각 사용자에 대한 라이선스가 필요하다는 것도 이해하는 것이 중요합니다. 정확한 라이선스 요구 사항은 Cloud Video Interop 파트너로부터 얻을 수 있습니다. 배포를 시작하기 전에 명확한지 확인합니다.

### <a name="configure"></a>구성

CVI 배포를 위해 선택한 파트너는 조직 내에서 성공적으로 배포하는 데 필요한 모든 단계로 구성된 전체 배포 문서를 제공합니다. 여기에는 방화벽 포트 및 IP 범위, 디바이스에 대한 구성 변경 및 변경해야 하는 기타 설정이 포함됩니다.

### <a name="provision"></a>제공  

프로비전 단계에서는 파트너 구성 가이드에 따라 적절한 사용자에게 라이선스를 할당합니다. 또한 Teams 환경에 대한 파트너 액세스를 제공하기 위해 Azure 동의 프로세스를 거쳐야 합니다. Azure 동의 프로세스에 대한 자세한 내용은 [Microsoft ID 플랫폼 엔드포인트의 사용 권한 및](/azure/active-directory/develop/v2-permissions-and-consent) 동의를 참조하세요.

### <a name="schedule"></a>일정

사용자가 Cloud Video Interop에 대해 사용하도록 설정되면 Outlook용 Teams 모임 추가 기능 또는 Teams 클라이언트를 사용하여 예약된 모든 모임에는 Cloud Video Interop 호환 디바이스가 이러한 모임에 참가할 수 있도록 Teams 모임에 적절한 추가 정보가 자동으로 추가됩니다.

### <a name="join"></a>가입

파트너 솔루션에 따라 Cloud Video Interop 사용 모임에 참가하는 방법에는 여러 가지가 있습니다. Cloud Video Interop 파트너가 정확한 모임 참가 시나리오를 제공합니다. 아래에 몇 가지 예제가 나열되어 있습니다.

- IVR(대화형 음성 응답) 
  - tenantkey@domain 사용하여 파트너의 IVR에 전화를 걸 수 있습니다.
  - 파트너 IVR에 있는 경우 VTC conferenceId를 입력하라는 메시지가 표시됩니다. 그러면 Teams 모임에 연결됩니다.
- 직통 
  - 테넌트 키의 전체 문자열을 사용하여 직접 다이얼 기능을 사용하여 파트너의 IVR과 상호 작용하지 않고 Teams 모임에 직접 전화를 걸 수 있습니다. VTC ConferenceId@domain.
- 원터시 다이얼 
  - Teams 룸이 통합되어 있는 경우 파트너가 제공하는 원터치 다이얼 기능을 사용할 수 있습니다(다이얼 문자열을 입력할 필요 없이).

## <a name="manage-cloud-video-interop"></a>Cloud Video Interop 관리

Cloud Video Interop이 배포된 후 파트너가 제공하는 솔루션을 사용하여 디바이스를 관리할 수 있습니다. 각 파트너는 라이선스 및 디바이스 관리를 모두 포함하는 관리 인터페이스를 제공합니다. 

보고는 파트너 관리 인터페이스에서 직접 사용할 수도 있습니다. 보고 기능에 대한 자세한 내용은 원하는 파트너에게 문의하세요. 

### <a name="troubleshooting-cloud-video-interop"></a>Cloud Video Interop 문제 해결

Cloud Video Interop는 파트너가 제공하는 서비스입니다. 문제가 발생하는 경우 첫 번째 단계는 Teams 클라이언트가 설치된 디바이스를 연결하고 문제를 일으키는 Cloud Video Interop 디바이스와 동일한 세그먼트에 연결하는 것입니다. 

Teams가 이 세그먼트에서 올바르게 작동하고 파트너가 제공한 모든 네트워킹 및 구성 지침을 따른 경우 추가 문제 해결을 위해 파트너에게 문의해야 합니다. 

## <a name="powershell-for-cloud-video-interop"></a>클라우드 비디오 Interop용 PowerShell

다음 PowerShell cmdlet은 Cloud Video Interop 배포를 부분적으로 자동화하는 데 사용할 수 있습니다.

- **Get-CsTeamsVideoInteropServicepolicy**: Microsoft는 Cloud Video Interop에 사용할 파트너를 지정할 수 있도록 지원되는 각 파트너에 대해 미리 구성된 정책을 제공합니다.<br>이 cmdlet을 사용하면 조직에서 사용할 수 있는 미리 구성된 정책을 식별할 수 있습니다. Grant-CsTeamsVideoInteropServicePolicy cmdlet을 활용하여 하나 이상의 사용자에게 이 정책을 할당할 수 있습니다.
- **Grant-CsTeamsVideoInteropServicePolicy**: 이 cmdlet을 사용하면 조직에서 사용할 미리 구성된 정책을 할당하거나 특정 사용자에게 정책을 할당할 수 있습니다.
- **New-CsVideoInteropServiceProvider**: 이 cmdlet을 사용하여 조직에서 사용하려는 지원되는 CVI 파트너에 대한 정보를 지정합니다.
- **Set-CsVideoInteropServiceProvider**: 이 cmdlet을 사용하여 조직에서 사용하는 지원되는 CVI 파트너에 대한 정보를 업데이트합니다.
- **Get-CsVideoInteropServiceProvider**: 이 cmdlet을 사용하여 조직 내에서 사용하도록 구성된 모든 공급자를 가져옵니다.
- **Remove-CsVideoInteropServiceProvider**: 이 cmdlet을 사용하여 조직에서 더 이상 사용하지 않는 공급자에 대한 모든 공급자 정보를 제거합니다.