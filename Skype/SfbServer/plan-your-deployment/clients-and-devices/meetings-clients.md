---
title: 모임 클라이언트 계획 (웹 앱 및 모임 앱)
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 31e95e16-f79f-46c6-b123-973fa56a824e
description: '요약: IT 전문가는 비즈니스용 Skype 서버에 대 한 계획을 진행 하는 동안 비즈니스용 Skype 웹 앱 및 Skype 모임 앱에 대 한 지원 요구 사항을 검토 해야 합니다. 이 문서는 이러한 앱의 사용자를 위한 것이 아닙니다.'
ms.openlocfilehash: 0e1ce225f99a112f11d55d76eb8039a10d9aac6b
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43777793"
---
# <a name="plan-for-meetings-clients-web-app-and-meetings-app"></a>모임 클라이언트 계획 (웹 앱 및 모임 앱)
 
**요약:** IT 전문가는 비즈니스용 Skype 서버에 대 한 계획을 진행 하는 동안 비즈니스용 Skype 웹 앱 및 Skype 모임 앱에 대 한 지원 요구 사항을 검토 해야 합니다. 이 문서는 이러한 앱의 사용자를 위한 것이 아닙니다.
  
비즈니스용 Skype 서버를 구현한 후에는 조직의 사용자가 배포 프로세스의 일부로 비즈니스용 Skype 클라이언트를 설치할 수 있습니다. 
  
나중에 해당 사용자는 모임을 만들고 조직 외부에서 사용자를 초대할 수 있으며, 이러한 모임 초대 대 상자에는 비즈니스용 Skype 클라이언트 버전이 없을 수도 있습니다. 사용자가 모임 초대에 대 한 URL을 클릭 하는 경우에는 클라이언트 부재를 감지 하 고 비즈니스용 Skype 클라이언트가 없는 초대 대 상자에서 모임에 참가할 수 있도록 경량 모임 전용 클라이언트를 다운로드 하 여 설치 하 라는 메시지가 표시 됩니다.
  
> [!NOTE]
> 비즈니스용 skype 웹 앱 및 Skype 모임 앱은 비즈니스용 Skype 없이 모임에 로그인 하려고 할 때만 사용할 수 있습니다. 이러한 앱에 대 한 사용자 도움말 [https://aka.ms/smahelp](https://aka.ms/smahelp)은에 있습니다. 
  
> [!NOTE]
> 비즈니스용 Skype 웹 앱 이나 Skype 모임 앱을 미리 설치할 수는 없지만 [스마트 전화](https://products.office.com/skype-for-business/download-app?tab=tabs-1) 및 [태블릿](https://products.office.com/skype-for-business/download-app?tab=tabs-2) 사용자가 회의에 참석할 때 사용할 수 있는 저렴 한 모바일 클라이언트를 설치할 수도 있습니다.
  
기본적으로 모임을 호스트 하는 서버는 회의에 참가 하기 위해 비즈니스용 Skype Web App을 다운로드 하 고 설치 하도록 사용자에 게 지시 합니다. 비즈니스용 Skype 웹 앱이 프런트 엔드 서버에 저장 되 고 모임 참석자에 게 전송 됩니다. 
  
비즈니스용 Skype 서버에서 비즈니스용 skype 모임 앱 (Windows) 및 비즈니스용 Skype (Mac)는 CU5로 시작 하는 비즈니스용 Skype 웹 앱에 대 한 교체로 사용할 수 있지만 교체 앱을 제공 [하려면 Skype 모임 앱에서 비즈니스용 Skype 웹 앱 교체](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable)에 설명 된 추가 구성이 필요 합니다 (선택 사항).  비즈니스용 skype 모임 앱 및 Mac 용 비즈니스용 Skype를 사용 하는 경우 사용자는 비즈니스용 Skype 서버가 아닌 Office 365 CDN (콘텐츠 배달 네트워크)에서 최신 버전의 앱을 다운로드 합니다. 비즈니스용 Skype 서버 2019의 경우 Skype 모임 앱과 Mac 용 비즈니스용 Skype를 사용 하는 것이 유일한 옵션입니다.
  
Skype 모임 앱은 앱을 다운로드 및 설치 하 고 모임에 참가할 수 있는 간소화 된 브라우저 환경을 제공 하며, Internet Explorer 사용자를 위해 한 번 클릭 참가 등을 포함 합니다. 또한 안정성과 모임 환경을 위해 비즈니스용 Skype Web App에 비해 많은 향상 된 skype 모임 앱이 제공 됩니다. 
  
> [!NOTE]
> 비즈니스용 Skype 서버 2015 CU5 이상에서 비즈니스용 skype Online을 사용 하 여 개최 된 모임은 더 이상 clientless 사용자를 비즈니스용 skype Web App으로 전송 되지 않으며, 대신 비즈니스용 skype 모임 앱 (Windows) 또는 mac for Business for mac을 보내지 않습니다. 비즈니스용 skype 서버 2015 CU5 이상에서 [Skype 모임 앱이 비즈니스용 Skype Web app을 교체 하도록 설정 하는 경우 (선택 사항)](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable)clientless는 비즈니스용 Skype web App 대신 비즈니스용 Skype 모임 앱 또는 비즈니스용 skype를 전송 합니다. 
  
## <a name="software-requirements"></a>소프트웨어 요구 사항
<a name="OS-Browser"> </a>

비즈니스용 Skype 웹 앱을 사용 하려면 사용자는 다음의 지원 되는 운영 체제 및 브라우저 조합 중 하나를 충족 해야 합니다. 
  
**비즈니스용 Skype 웹 앱에 대 한 운영 체제 및 최소 브라우저 지원**

| 운영 체제 | 면 | 32-및 64 비트 Internet Explorer 11 이상 | 32-및 64 비트 Internet Explorer 10 이상 | 32-및 64 비트 Internet Explorer 9 이상 | 32 및 64 비트 버전의 Safari 6.2.8-11. X | 32 및 64 비트 버전의 Chrome 18.x 이상 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Windows 10  <br/> |예  <br/> |예  <br/> |해당 없음  <br/> |해당 없음  <br/> |해당 없음  <br/> |예 &#x2778; <br/> |
|Windows 8.1 &#x2776; <br/> |해당 없음  <br/> |예  <br/> |해당 없음  <br/> |해당 없음  <br/> |해당 없음 <br/> |예 &#x2778; <br/> |
|Windows 8 (Intel 기반) &#x2776; <br/> |해당 없음  <br/> |해당 없음  <br/> |예  <br/> |해당 없음 <br/> |해당 없음  <br/> |예 &#x2778; <br/> |
|Windows 7-SP1 &#x2777; <br/> |해당 없음  <br/> |예  <br/> |아니요  <br/> |아니요  <br/> |해당 없음 <br/>|예 &#x2778; <br/> |
|Windows Server 2008 R2 SP1 &#x2777; <br/> |해당 없음  <br/> |예  <br/> |예  <br/> |예  <br/> |해당 없음 <br/>|예 &#x2778; <br/> |
|macOS 10.8 이상 (Intel 기반) &#x2777; <br/> |해당 없음  <br/> |해당 없음  <br/> |해당 없음  <br/> |해당 없음  <br/> |예  <br/> |예 <br/> |
   
&#x2776; 비즈니스용 Skype Web App 브라우저 플러그 인을 사용 하려면 컴퓨터 기반 음성, 비디오, 공유 및 진행 중인 화면 공유 및 기타 기능 보기를 위해 특정 공유 플러그 인이 필요 합니다. 모임 참석자가 모임에 참가할 때 또는 이러한 기능 중 하나를 시작할 때 공유 플러그 인을 설치 하는 옵션이 제공 됩니다. Windows 8 및 Windows 8.1에서 공유 플러그 인은 데스크톱용 internet Explorer 10 또는 Internet Explorer 11을 실행 하는 경우에만 설치할 수 있습니다. 이러한 기능은 비 데스크톱 버전의 Internet Explorer 10 및 11에서는 사용할 수 없습니다. Firefox 및 Safari 버전 12.0 이상이 더 이상 지원 되지 않습니다.
  
&#x2777; 지원 되는 Windows 7, Windows Server 2008 R2 및 Macintosh 운영 체제의 경우 컴퓨터 기반 음성, 비디오, 응용 프로그램 보기, 응용 프로그램 공유, 데스크톱 보기 및 데스크톱 공유를 포함 하 여 모든 기능을 사용할 수 있습니다. 이러한 기능을 사용 하려면 메시지가 표시 되 면 플러그 인을 설치 해야 합니다. Mac OS X 버전 10.7은 더 이상 지원 되지 않습니다.  또한 웹 앱은 OS X 10.15 이상에 설치 되지 않습니다.  익명 가입 시나리오를 지 원하는 Mac 용 비즈니스용 Skype 최신 버전을 사용 하는 것이 좋습니다.
  
Windows의 Chrome에서 웹 앱에 액세스 하는 &#x2778;에는 웹 앱이 포함 된 Internet Explorer 프레임에 로드 되는 작은 프로그램이 실행 됩니다. 이 프로그램을 사용 하려면 웹 앱이 제대로 로드 되도록 지원 되는 버전의 Internet Explorer 중 하나가 설치 되어 있어야 합니다.
  
> [!NOTE]
> Microsoft 365 및 Office 365 사용자는 비즈니스용 Skype를 사용 하 여 Internet Explorer 10 이상을 사용할 수 있습니다. 
  
### <a name="skype-meetings-app"></a>Skype 모임 앱

Skype 모임 앱은 Windows 10, Windows 8.1, Windows 8, Windows 7, 32-및 64 비트 Internet Explorer 11 이상이 설치 된 컴퓨터에서 앱으로 실행 됩니다. 
  
다른 모든 종속성의 경우 [Skype 모임 앱에 대해 지원 되는 플랫폼](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001) 을 참조 하세요.
  
### <a name="skype-for-business-for-mac"></a>Mac용 비즈니스용 Skype

Mac 용 비즈니스용 Skype는 macOS 버전 10.8 이상을 사용 하는 컴퓨터에서 실행 됩니다. 

## <a name="hardware-requirements"></a>하드웨어 요구 사항
<a name="OS-Browser"> </a>

컴퓨터 하드웨어 요구 사항은 운영 체제 및 브라우저에 따라 결정 됩니다. 음성 및 전화 통신 기능을 사용 하려면 마이크 및 스피커, 마이크와 함께 헤드셋 또는 컴퓨터와 호환 되는 장치가 필요 합니다. 비디오 기능을 사용 하려면 컴퓨터와 호환 되는 비디오 장치가 필요 합니다. 비디오 하드웨어 지원 및 예상 비디오 품질에 대 한 자세한 내용은 [비즈니스용 Skype 클라이언트 비디오 해상도](video-resolutions.md)를 참조 하세요.
  
## <a name="network-requirements"></a>네트워크 요구 사항
<a name="Network"> </a>

비즈니스용 Skype 웹 앱 또는 Skype 모임 앱 사용자가 모임 연결 문제를 경험 하는 경우, 조직의 네트워크 인프라가 [office 365 url 및 IP 주소 범위](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)에 설명 된 대로 office 365을 지원 하도록 구성 되지 않을 수 있습니다. 비즈니스용 Skype Online 또는 비즈니스용 Skype 서버의 사용자가 모임을 만들었는지 여부입니다. 
  
사용자가 설명 된 대로 네트워크에 구성 되어 있지 않은 경우 많은 앱 기능이 작동 하거나 제대로 연결 되지 않을 수 있습니다.
  
## <a name="supported-meetings-features"></a>지원 되는 모임 기능
<a name="BKMK_Conferencing"> </a>

이 표에서는 비즈니스용 Skype 클라이언트, 비즈니스용 Skype 웹 앱, Skype 모임 앱 및 Lync Web App의 사용자가 사용할 수 있는 모임 기능을 비교 합니다. Lync Web App은 기능 비교를 위해 나열 됩니다. 사용자는 lync 2013 서버에서 모임이 호스트 된 경우에만 Lync 웹 앱을 다운로드 하 고 사용 합니다.

| 기능/기능 | 비즈니스용 Skype 2016 또는 2019 클라이언트 | Mac 클라이언트의 비즈니스용 Skype | Skype 모임 앱 | 비즈니스용 Skype Web App | Lync Web App |
|:-----|:-----|:-----|:-----|:-----|:-----|
|컴퓨터 오디오 추가  <br/> |&#x2714;|&#x2714;|&#x2714; (플러그 인 필요)  <br/> |&#x2714; (플러그 인 필요)  <br/> |&#x2714; (플러그 인 필요)  <br/> |
|비디오 추가  <br/> |&#x2714;|&#x2714;|&#x2714; (플러그 인 필요)  <br/> |&#x2714; (플러그 인 필요)  <br/> |&#x2714; (플러그 인 필요)  <br/> |
|인증 된 참가자가 전화로 오디오를 전환 합니다.  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|게스트 참가자가 전화로 오디오를 전환 합니다.  <br/> |&#x2714;|&#x2714;|&#x2714;|||
|단체 비디오 보기 (갤러리 보기)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|비디오 기반 화면 공유  <br/> |&#x2714;|&#x2714; <br/> |&#x2714; (보기 전용)  <br/> |||
|모임 내 발표자 컨트롤 사용  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|자세한 모임 명단 액세스  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|단체 메신저 대화에 참가  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|중요도 높음으로 IM 메시지 설정  <br/> |&#x2714;|||||
|데스크톱 공유(사용하도록 설정된 경우)  <br/> |&#x2714;|&#x2714;|&#x2714; (플러그 인 필요)  <br/> |&#x2714; (플러그 인 필요)  <br/> |&#x2714; (플러그 인 필요)  <br/> |
|프로그램 공유(사용하도록 설정된 경우)  <br/> |&#x2714;||&#x2714; (Windows 전용, 플러그 인 필요)  <br/> |&#x2714; (Windows 전용, 플러그 인 필요)  <br/> |&#x2714; (Windows 전용, 플러그 인 필요)  <br/> |
|다른 사용자의 공유 데스크톱 또는 프로그램에 대 한 제어권 가져오기  <br/> |&#x2714;||&#x2714; (Windows 에서만 &#x2776;, 플러그 인 필요)  <br/> |&#x2714; (Windows 에서만 &#x2776;, 플러그 인 필요)  <br/> |&#x2714; (Windows 에서만 &#x2776;, 플러그 인 필요)  <br/> |
|다른 사용자가 공유 데스크톱 또는 프로그램의 제어권을 사용 하도록 허용  <br/> |&#x2714;|||||
|익명 참가자 추가(사용하도록 설정된 경우)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|이름별로 참가자 초대  <br/> |&#x2714;|&#x2714;||||
|전화 번호로 참가자 초대  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|전자 메일로 참가자 초대  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|전화 접속 오디오 회의 사용  <br/> |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|모임 시작 모임을 시작할 수 있습니다.  <br/> |&#x2714;|&#x2714;||||
|모임 녹음  <br/> |&#x2714;|||||
|첨부 파일 추가 및 다운로드  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Microsoft PowerPoint 파일 추가 및 프레젠테이션 진행  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Microsoft PowerPoint 파일 탐색  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|OneNote 모임 메모 추가 및 편집  <br/> |&#x2714;||편집 전용 (추가 하지 않음)  <br/> |편집 전용 (추가 하지 않음)  <br/> |편집 전용 (추가 하지 않음)  <br/> |
|화이트보드 사용  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|설문 진행  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|다른 사용자와 공유할 파일 업로드  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|모임 또는 회의 예약  <br/> |Outlook 또는 비즈니스용 Skype 웹 스케줄러  <br/> |Outlook 또는 비즈니스용 Skype 웹 스케줄러  <br/> |비즈니스용 Skype 웹 스케줄러  <br/> |비즈니스용 Skype 웹 스케줄러  <br/> |비즈니스용 Skype 웹 스케줄러  <br/> |
|Q&amp;A 관리자  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|참석자 비디오 사용 안 함  <br/> |&#x2714;|||||
|모임 메신저 사용 안 함  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|대상 그룹 음소거  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|모든 사용자에 게 참석자 지정  <br/> |&#x2714;|||||
|Skype 모임 브로드캐스트 생성  <br/> |&#x2714;|||||
   
 &#x2776; 참석자는 비즈니스용 Skype for mac, Lync for Mac 2011 또는 Mac 용 Communicator 2011 사용자가 공유 하는 데스크톱을 제어할 수 없습니다. 또한이는 Max OSX에서 비즈니스용 Skype Web App에 대해서도 작동 하지 않습니다.
  
 비즈니스용 Skype Online에 대 한 &#x2777;이 기능을 사용 하려면 Microsoft PSTN 회의, Exchange 통합 메시징 또는 타사 오디오 회의 공급자가 필요 합니다.
  
 &#x2778; Lync for Mac 2011 클라이언트는 비즈니스용 Skype Web App에서 전화 회의에서 공유한 경우 Microsoft Office 2013 PowerPoint 프레젠테이션을 볼 수 없습니다.
  
## <a name="known-issues-and-troubleshooting"></a>알려진 문제 및 문제 해결
<a name="BKMK_Conferencing"> </a>

최종 사용자의 경우 이러한 앱에 대 한 [온라인 도움말](https://aka.ms/smahelp) 을 즉시 사용할 수 있습니다. IT 전문가는 다음과 같은 문제를 파악 해야 합니다.
  
- 사용자가 [네트워크 요구 사항을](meetings-clients.md#Network)충족 하도록 구성 되지 않은 네트워크에 있는 경우 많은 앱 기능이 제공 되거나 작동 하지 않을 수 있으며,이로 인해 모임에 전혀 연결할 수 없을 수도 있습니다.
    
- 일부 사용자에 게는 앱을 설치할 수 있는 사용 권한이 없는 회사 관리 컴퓨터가 있을 수 있습니다. 이러한 사용자에 대해 두 앱이 모두 옵션은 아니지만 [스마트 전화](https://products.office.com/skype-for-business/download-app?tab=tabs-1) 및 [태블릿](https://products.office.com/skype-for-business/download-app?tab=tabs-2) 사용자가 회의에 참석할 때 사용할 수 있는 저렴 한 모바일 클라이언트를 설치할 수 있습니다.
    
    기타 설치 문제는 [도움말 항목](https://support.office.com/article/Trouble-installing-the-Skype-for-Business-Web-App-plug-in-958fc5f1-2d6f-42e3-815d-a9516c591274?ui=en-US&amp;rs=en-US&amp;ad=US)에서도 설명 합니다. 
    
- 사용자가 모임 앱을 처음 실행할 때 방화벽 경고가 표시 될 수 있습니다. 환경을 최적화 하기 위해 포트를 여는 메시지가 표시 될 수 있으며,이 경우 해당 컴퓨터에 대 한 관리자 권한이 필요할 수도 있습니다. 앱이 계속 작동 하 고 사용자가 요청 된 포트를 여는 것을 안전 하 게 거부할 수 있습니다. 
    
- IE가 기본 브라우저가 아닌 경우에도 Internet Explorer에서 [필터링 하지 않고 ActiveX가 사용 하도록 설정](https://support.office.com/article/Turn-off-ActiveX-filtering-for-Skype-for-Business-Web-App-b6de8ff6-ac7e-4e2f-b18c-2f13db643c41?ui=en-US&amp;rs=en-US&amp;ad=US) 되어 있어야 합니다. 비즈니스용 Skype 웹 앱에서 웹 앱 이나 기타 프로그램에 추가 기능을 추가 하는 소규모 모듈인 음성, 비디오 및 화면 공유에 필요한 ActiveX 컨트롤입니다.
    
- 비즈니스용 Skype Web App의 일부 기능이 제대로 작동 하려면 브라우저에서 컴퓨터 또는 장치에 [쿠키를 저장](https://support.office.com/article/Allow-cookies-for-Skype-Meetings-App-Skype-for-Business-Web-App-2108276b-b5c3-484b-bf2b-dac6eeba4c93) 하도록 허용 해야 합니다.
    
- 일부 비즈니스용 Skype Web App 기능이 예상 대로 작동 하려면 브라우저에서 [JavaScript 지원을 설정](https://support.office.com/article/Turn-on-JavaScript-for-Skype-Meetings-App-Skype-for-Business-Web-App-3d997bf9-637c-4fe6-8ee3-9e62bfda52cd) 해야 할 수 있습니다.
    
### <a name="aes-support"></a>AES 지원 

비즈니스용 Skype 서버 2015 CU5에서 AES는 ASP.NET 4.6에서 지원 되지 않으며이로 인해 Skype 모임 앱이 시작 되지 못할 수 있습니다. [ASP .net 4.5로 인 한 암호화 요구 사항](../security/user-and-client-authentication.md#cryptographic-requirements-due-to-asp-net-45) 에 대 한 자세한 내용이 있습니다.
  
## <a name="see-also"></a>참고 항목
<a name="BKMK_Conferencing"> </a>

[비즈니스용 Skype 서버에서 웹 다운로드 가능 클라이언트 배포](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Skype 모임 앱에 대해 지원 되는 플랫폼](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
