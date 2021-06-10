---
title: Microsoft Teams용 클라우드 비디오 Interop
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: naforer
f1.keywords:
- NOCSH
description: 클라우드 비디오 Interop을 중간 솔루션으로 사용하여 타사 회의실 디바이스가 모임에 참가할 Microsoft Teams 수 있습니다.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3a8d657e2cbc12695453e26ef0e4bf9ad55070bf
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122362"
---
# <a name="cloud-video-interop-for-microsoft-teams"></a>Microsoft Teams용 클라우드 비디오 Interop

CVI(Cloud Video Interop)는 타사 회의실(telepresence) 및 VTC(개인 비디오 디바이스)가 모임에 참가할 수 있는 Microsoft 공인 타사 Microsoft Teams 솔루션입니다.
 
이 Microsoft Teams 사용하면 오디오, 비디오 및 콘텐츠 공유를 포함 하는 모임에서 풍부한 온라인 콘텐츠 공동 작업을 얻을 수 있습니다. 데스크톱 및 웹 클라이언트뿐만 아니라 기본으로 통합되는 많은 파트너 디바이스를 통해 이 기능을 Microsoft Teams. 그러나 많은 고객이 이미 비디오 원격회의 및 개인 비디오 통신 디바이스에 투자하여 업그레이드하는 데 비용이 많이 들 수 있습니다. Cloud Video Interop은 쉽게 솔루션을 제공하므로 업그레이드할 준비가 될 때까지 기존 솔루션을 계속 사용할 수 있습니다.

Cloud Video Interop을 통해 Microsoft Teams 모든 참가자에게 네이티브 모임 환경을 제공합니다. 회의실 또는 클라이언트 Teams 제공합니다.

### <a name="is-cloud-video-interop-for-me"></a>Cloud Video Interop이 제게는 있나요?

Cloud Video Interop은 전체 네이티브 솔루션으로 전환하는 동안 중간 서비스를 Microsoft Teams 엔드포인트를 사용하여 Teams 제공합니다. 제공된 서비스는 마이그레이션 경로의 일부로 제공해야 합니다.

Cloud Video Interop은 다음 조건을 충족하는 고객을 위한 것입니다.

- 회의실 디바이스 및 개인 비디오 디바이스 배포(50개 이상의 디바이스)를 대규모로 배포하여 직접 통합할 수 Microsoft Teams
- Cloud Video Interop 파트너 중 하나에서 지원됩니다.
- 네이티브 솔루션으로 마이그레이션하는 동안 현재 회의실 디바이스 및 개인 비디오 디바이스에 대한 투자 Microsoft Teams

Cloud Video Interop은 훌륭한 중간 솔루션을 제공하면서 고객이 장기적으로 Teams 룸 시스템과 같은 Teams 모임 솔루션을 살펴보는 것이 권장됩니다. 

### <a name="office-365-us-government-and-third-party-services"></a>Office 365 미국 정부 및 타사 서비스

Office 365 타사 애플리케이션을 SharePoint, 비즈니스용 Skype, Teams, Office 엔터프라이즈용 Microsoft 365 앱(예: Word, Excel, PowerPoint 및 Outlook) 및 Outlook Web App. 또한 타사 Office 365 공급자와의 통합을 지원합니다. 이러한 타사 애플리케이션 및 서비스에는 조직의 고객 데이터를 타사 시스템에 저장, 전송 및 처리해야 할 수 Office 365 인프라 외부에 있으므로 규정 준수 및 데이터 Office 365 적용되지 않습니다. **조직에 이러한 서비스의 적절한 사용을 평가할 때 타사에서 제공하는 개인 정보 및 규정 준수 정책을 검토하는 것이 좋습니다.**



### <a name="partners-certified-for-microsoft-teams"></a>파트너 인증을 Microsoft Teams

다음 파트너에는 비디오 인터프 솔루션이 Microsoft Teams. 회사에서는 엔터프라이즈 내에서 이러한 파트너의 조합으로 작업할 수 있습니다. 

|파트너|파트너 솔루션|
|----|---|
|![Poly RealConnect를 나타내는 로고](media/polycom.png) | <a href="https://aka.ms/PolycomRealConnect" target="_blank">Poly RealConnect 서비스</a> |
|![Pexip Infinity를 나타내는 로고](media/pexip.png)| <a href="https://aka.ms/PexipInfinity" target="_blank">Pexip Infinity for Microsoft Teams</a> | 
|![BlueJeans Gateway를 나타내는 로고](media/bluejeans.png)| <a href="https://aka.ms/BluejeansGateway" target="_blank">BlueJeans Gateway for Microsoft Teams</a> |
|![Cisco CVI를 나타내는 로고](media/cisco.png)|<a href="https://aka.ms/CiscoCVI" target="_blank">Cisco Webex Video Integration for Microsoft Teams</a>|

### <a name="cloud-video-interop-overview"></a>클라우드 비디오 Interop 개요

Cloud Video Interop은 프레미스에서 기존 비디오 회의 및 개인 비디오 디바이스 솔루션 간의 상호운용성을 제공하기 위해 파트너가 제공하는 타사 Microsoft Teams.

파트너가 제공하는 솔루션은 완전 클라우드 기반 또는 부분적으로 온-프레미스를 배포할 수 있는 구성 요소로 구성됩니다. 
     
다음 다이어그램은 파트너 솔루션의 고급 아키텍처를 보여줍니다.

![클라우드 비디오 Teams 파트너 솔루션을 설명하는 다이어그램](media/teams-cloud-video-interop-partner-solution.png)


## <a name="deploy-cloud-video-interop"></a>클라우드 비디오 Interop 배포

Cloud Video Interop 솔루션을 배포할 때 파트너 솔루션을 배포하고 있는 것을 이해하는 것이 중요합니다. Cloud Video Interop을 배포하는 데 필요한 일반적인 단계는 다음 다이어그램에 나열되어 있습니다.

![조직에서 CVI 배포를 설명하는 다이어그램](media/deploying-cvi.png)

### <a name="plan"></a>계획

계획 단계에서는 네이티브 디바이스로 대체하지 않을 디바이스를 식별하고, Teams 지원할 수 있는 Cloud Video Interop 파트너를 찾아야 합니다.  

또한 Cloud Video Interop 지원 디바이스가 조인할 모임을 예약하는 각 사용자에 대한 라이선스가 필요하다는 것을 이해하는 것이 중요합니다. Cloud Video Interop 파트너에서 정확한 라이선스 요구 사항을 얻을 수 있습니다. 배포를 시작하기 전에 이 방법을 명확히 지정해야 합니다.

### <a name="configure"></a>구성

CVI 배포를 위해 선택한 파트너는 조직 내에서 성공적으로 배포하는 데 필요한 모든 단계로 구성된 전체 배포 문서를 제공합니다. 여기에는 방화벽 포트 및 IP 범위, 디바이스에 대한 구성 변경 내용 및 변경해야 하는 기타 설정이 포함됩니다.

### <a name="provision"></a>프로비전  

프로비전 단계에서 파트너 구성 가이드에 따라 적절한 사용자에게 라이선스를 할당합니다. 또한 파트너가 사용자 환경에 대한 액세스 권한을 제공하려면 Azure 동의 프로세스를 Teams 합니다. Azure 동의 프로세스에 대한 자세한 내용은 Microsoft ID 플랫폼 엔드포인트의 사용 [권한](/azure/active-directory/develop/v2-permissions-and-consent) 및 동의를 참조하세요.

### <a name="schedule"></a>일정

사용자가 Cloud Video Interop을 사용하도록 설정한 후 클라우드 Teams 모임 추가 기능을 사용하여 예약된 모든 Outlook Teams 클라이언트는 클라우드 비디오 상호프 호환 디바이스가 이러한 모임에 참가할 수 있도록 Teams 추가 정보가 자동으로 추가됩니다.

### <a name="join"></a>조인

파트너 솔루션에 따라 Cloud Video Interop 지원 모임에 참가하는 방법에는 여러 가지가 있습니다. Cloud Video Interop 파트너가 정확한 모임 조인 시나리오를 제공합니다. 아래에 몇 가지 예제가 나열되어 있습니다.

- IVR(대화형 음성 응답) 
  - 파트너의 IVR에 전화 접속할 수 tenantkey@domain.
  - 파트너 IVR에 있는 경우 VTC conferenceId를 입력하라는 메시지가 표시되어 모임에 Teams 합니다.
- 직접 다이얼 
  - 테넌트키의 전체 문자열을 사용하여 직접 Teams 전화 걸기 기능을 사용하여 파트너의 IVR과 상호 작용하지 않고도 모임에 직접 전화를 걸 수 있습니다. VTC ConferenceId@domain.
- 원터치 다이얼 
  - 통합된 Teams 있는 경우 파트너가 제공하는 원터치 다이얼 기능을 사용할 수 있습니다(다이얼 문자열을 입력할 필요 없이).

## <a name="manage-cloud-video-interop"></a>클라우드 비디오 Interop 관리

Cloud Video Interop을 배포한 후 파트너가 제공하는 솔루션을 사용하여 디바이스를 관리할 수 있습니다. 각 파트너는 라이선스 및 디바이스 관리를 모두 포함할 관리 인터페이스를 제공합니다. 

보고는 파트너 관리 인터페이스에서 직접 사용할 수 있습니다. 보고 기능에 대한 자세한 내용은 선택한 파트너에게 문의하세요. 

### <a name="troubleshooting-cloud-video-interop"></a>클라우드 비디오 Interop 문제 해결

Cloud Video Interop은 파트너가 제공하는 서비스입니다. 문제가 발생하는 경우 첫 번째 단계는 클라이언트가 설치되어 있는 디바이스를 Teams 문제가 발생하는 Cloud Video Interop 디바이스와 동일한 세그먼트에 연결하는 것입니다. 

이 Teams 올바르게 작동하고 파트너가 제공한 모든 네트워킹 및 구성 지침을 따르는 경우 추가 문제 해결을 위해 파트너에게 문의해야 합니다. 

## <a name="powershell-for-cloud-video-interop"></a>Cloud Video Interop용 PowerShell

다음 PowerShell cmdlet은 Cloud Video Interop 배포를 자동화(부분적으로)할 수 있습니다.

- **Get-CsTeamsVideoInteropServicepolicy:** Microsoft는 클라우드 비디오 Interop에 사용할 파트너를 지정할 수 있도록 지원되는 각 파트너에 대해 미리 생성된 정책을 제공합니다.<br>이 cmdlet을 사용하면 조직에서 사용할 수 있는 미리 생성된 정책을 식별할 수 있습니다. cmdlet을 사용하여 하나 이상의 사용자에게 이 정책을 할당할 Grant-CsTeamsVideoInteropServicePolicy 있습니다.
- **Grant-CsTeamsVideoInteropServicePolicy**: 이 cmdlet을 사용하면 조직에서 사용할 미리 생성된 정책을 할당하거나 특정 사용자에게 정책을 할당할 수 있습니다.
- **New-CsVideoInteropServiceProvider**: 이 cmdlet을 사용하여 조직에서 사용할 지원되는 CVI 파트너에 대한 정보를 지정합니다.
- **Set-CsVideoInteropServiceProvider:** 이 cmdlet을 사용하여 조직에서 사용하는 지원되는 CVI 파트너에 대한 정보를 업데이트합니다.
- **Get-CsVideoInteropServiceProvider**: 이 cmdlet을 사용하여 조직 내에서 사용하도록 구성된 모든 공급자를 얻습니다.
- **Remove-CsVideoInteropServiceProvider**: 이 cmdlet을 사용하여 조직에서 더 이상 사용하지 않습니다.