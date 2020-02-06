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
description: '요약: IT 전문가는 비즈니스용 Skype for business Web App 및 Skype 모임 앱에 대 한 지원 요구 사항을 검토 해야 합니다. 이 문서는 이러한 앱의 사용자를 위한 것이 아닙니다.'
ms.openlocfilehash: 126d8ffc71a2ff1a0bcbf26c744301736d2b47b2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803558"
---
# <a name="plan-for-meetings-clients-web-app-and-meetings-app"></a>모임 클라이언트 계획 (웹 앱 및 모임 앱)
 
**요약:** IT 전문가는 비즈니스용 Skype for business Web App 및 Skype 모임 앱에 대 한 지원 요구 사항을 검토 하는 것이 좋습니다. 이 문서는 이러한 앱의 사용자를 위한 것이 아닙니다.
  
비즈니스용 Skype 서버를 구현한 후에는 조직의 사용자가 배포 프로세스의 일부로 비즈니스용 Skype 클라이언트를 설치 하 게 됩니다. 
  
나중에 이러한 사용자는 모임을 만들어 조직 외부의 사용자를 초대할 수 있으며, 이러한 모임 초대 대 상자는 비즈니스용 Skype 클라이언트 버전을 보유 하 고 있지 않을 수 있습니다. 해당 사용자가 모임 초대에 대 한 URL을 클릭 하면 클라이언트의 부족이 감지 되 고 비즈니스용 Skype 클라이언트가 없는 초대 대 상자가 표시 되어 사용자가 모임에 참가할 수 있도록 간단한 모임 전용 클라이언트만 다운로드 및 설치 하 라는 메시지가 표시 됩니다.
  
> [!NOTE]
> 비즈니스용 skype Web App 및 Skype 모임 앱은 비즈니스용 Skype 없이 모임에 로그인 하려고 할 때만 사용할 수 있습니다. 이러한 앱에 대 한 사용자 도움말 [https://aka.ms/smahelp](https://aka.ms/smahelp)은에 있습니다. 
  
> [!NOTE]
> 비즈니스용 Skype Web App 또는 Skype 모임 앱을 사전 설치할 수는 없지만, [스마트 휴대폰](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-1) 및 [태블릿](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-2) 사용자가 모임에 참석 하는 데 사용할 수 있는 저렴 한 모바일 클라이언트를 설치할 수 있습니다.
  
기본적으로 모임을 호스트 하는 서버는 사용자에 게 비즈니스용 Skype Web App을 다운로드 하 고 설치 하도록 지시 합니다. 비즈니스용 Skype Web App은 프런트 엔드 서버에 저장 되며 모임 참석자에 게 전송 됩니다. 
  
비즈니스용 Skype 서버용 skype 모임 앱 (Windows)과 mac 용 비즈니스용 Skype (Mac)는 CU5으로 시작 되는 비즈니스용 Skype Web App에 대 한 대체 기능으로 사용할 수 있지만, 대체 앱을 제공 [하려면 Skype 모임 앱에서 비즈니스용 Skype Web App을 대체 하는 데](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable)설명 된 추가 구성이 필요 합니다 (선택 사항).  Skype 모임 앱과 Mac 용 비즈니스용 Skype를 사용 하는 경우 사용자는 비즈니스용 Skype 서버가 아닌 Office 365 콘텐츠 배달 네트워크 (CDN)에서 최신 버전의 앱을 다운로드 합니다. 비즈니스용 Skype 서버 2019의 경우 Skype 모임 앱을 사용 하 고 Mac 용 비즈니스용 Skype만 선택할 수 있습니다.
  
Skype Meeting App에서는 Internet Explorer 사용자를 위한 클릭 참가를 포함 하 여 앱을 다운로드 및 설치 하 고 모임에 참가할 수 있는 간단한 브라우저 환경을 제공 합니다. 또한 안정성과 모임 환경을 위해 비즈니스용 Skype Web App에 비해 다양 한 기능을 skype 모임 앱에 제공 합니다. 
  
> [!NOTE]
> 비즈니스용 skype Server 2015 CU5 이상에서는 비즈니스용 skype Online을 사용 하는 모임이 더 이상 clientless 사용자를 비즈니스용 Skype Web App으로 전송할 수 없으며, 대신 비즈니스용 skype 모임 앱 (Windows) 또는 비즈니스용 Skype for mac (Mac의 경우)를 전송 하 게 됩니다. 비즈니스용 skype Server 2015 CU5 이상에서 [skype Online 앱을 사용 하도록 설정 하 여 비즈니스용 Skype Web app을 교체한 경우 (선택 사항)](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable)clientless 사용자가 비즈니스용 Skype web App 대신 비즈니스용 Skype 모임 앱 또는 비즈니스용 skype를 전송 하 게 됩니다. 
  
## <a name="software-requirements"></a>소프트웨어 요구 사항
<a name="OS-Browser"> </a>

비즈니스용 Skype Web App을 사용 하려면 사용자는 다음과 같은 지원 되는 운영 체제 및 브라우저 조합 중 하나가 있어야 합니다. 
  
**비즈니스용 Skype Web App의 운영 체제 및 최소 브라우저 지원**

| 운영 체제 | 쪽 | 32 및 64 비트 Internet Explorer 11 이상 | 32 및 64 비트 Internet Explorer 10 이상 | 32 및 64 비트 Internet Explorer 9 이상 | 32 및 64 비트 버전의 Safari 6.2.8-11. X | 32 및 64 비트 버전의 Chrome 18. X 이상 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Windows 10  <br/> |예  <br/> |예  <br/> |해당 없음  <br/> |해당 없음  <br/> |해당 없음  <br/> |예 &#x2778; <br/> |
|Windows 8.1 &#x2776; <br/> |해당 없음  <br/> |예  <br/> |해당 없음  <br/> |해당 없음  <br/> |해당 없음 <br/> |예 &#x2778; <br/> |
|Windows 8 (Intel 기반) &#x2776; <br/> |해당 없음  <br/> |해당 없음  <br/> |예  <br/> |해당 없음 <br/> |해당 없음  <br/> |예 &#x2778; <br/> |
|Windows 7 SP1 &#x2777; <br/> |해당 없음  <br/> |예  <br/> |아니요  <br/> |아니요  <br/> |해당 없음 <br/>|예 &#x2778; <br/> |
|Windows Server 2008 R2 SP1 &#x2777; <br/> |해당 없음  <br/> |예  <br/> |예  <br/> |예  <br/> |해당 없음 <br/>|예 &#x2778; <br/> |
|macOS 10.8 이상 (Intel 기반) &#x2777; <br/> |해당 없음  <br/> |해당 없음  <br/> |해당 없음  <br/> |해당 없음  <br/> |예  <br/> |예 <br/> |
   
비즈니스용 Skype Web App 브라우저 플러그 인을 &#x2776;, 진행 중인 화면 공유 및 기타 기능을 컴퓨터 기반 음성, 비디오, 공유 및 보기를 사용 하기 위해 특정 공유 플러그인이 필요 합니다. 모임 참석자가 모임에 참가 하거나 이러한 기능 중 하나를 시작할 때 공유 플러그 인을 설치할 수 있는 옵션이 제공 됩니다. Windows 8 및 Windows 8.1에서 공유 플러그 인은 데스크톱용 Internet Explorer 10 또는 Internet Explorer 11을 실행 중인 경우에만 설치할 수 있습니다. 비 데스크톱 버전의 Internet Explorer 10 및 11에서는 이러한 기능을 사용할 수 없습니다. Firefox와 Safari 버전 12.0 이상은 더 이상 지원 되지 않습니다.
  
지원 되는 Windows 7, Windows Server 2008 R2 및 Macintosh 운영 체제의 &#x2777; 컴퓨터 기반 음성, 비디오, 응용 프로그램 보기, 응용 프로그램 공유, 데스크톱 보기, 데스크톱 공유 등 모든 기능을 사용할 수 있습니다. 이러한 기능을 사용 하려면 메시지가 나타날 때 플러그 인을 설치 해야 합니다. Mac OS X 버전 10.7은 더 이상 지원 되지 않습니다.
  
Windows의 Chrome에서 웹 앱에 액세스 하는 &#x2778;는 웹 앱을 포함 된 Internet Explorer 프레임으로 로드 하는 작은 프로그램을 실행 합니다. 이 프로그램을 설치 하려면 웹 앱이 제대로 로드 되도록 지원 되는 Internet Explorer 버전 중 하나가 필요 합니다.
  
> [!NOTE]
> Office 365 사용자는 비즈니스용 Skype에서 Internet Explorer 10 이상을 사용할 수 있습니다. 
  
### <a name="skype-meetings-app"></a>Skype 모임 앱

Skype Meeting 앱은 Windows 10, Windows 8.1, Windows 8, Windows 7, 32 및 64 비트 Internet Explorer 11 이상을 설치 하는 컴퓨터에서 앱으로 실행 됩니다. 
  
다른 종속성에 대 한 자세한 내용은 [Skype 모임에 지원 되는 플랫폼 앱](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001) 을 참조 하세요.
  
### <a name="skype-for-business-for-mac"></a>Mac 용 비즈니스용 Skype

Mac 용 비즈니스용 Skype는 macOS 버전 10.8 이상을 사용 하는 컴퓨터에서 실행 됩니다. 

## <a name="hardware-requirements"></a>하드웨어 요구 사항
<a name="OS-Browser"> </a>

컴퓨터 하드웨어 요구 사항은 운영 체제 및 브라우저에 따라 결정 됩니다. 음성 및 전화 통신 기능을 사용 하려면 마이크와 스피커, 마이크와 함께 헤드셋 또는 컴퓨터와 호환 되는 장치가 필요 합니다. 비디오 기능을 사용 하려면 컴퓨터와 호환 되는 비디오 장치가 필요 합니다. 비디오 하드웨어 지원 및 예상 되는 비디오 품질에 대 한 자세한 내용은 [비즈니스용 Skype 클라이언트 비디오 해상도](video-resolutions.md)를 참조 하세요.
  
## <a name="network-requirements"></a>네트워크 요구 사항
<a name="Network"> </a>

비즈니스용 Skype Web App 또는 Skype 모임 앱에서 모임 연결 문제가 발생 하는 경우 조직의 네트워크 인프라가 [office 365 url 및 IP 주소 범위](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)에 설명 된 대로 office 365를 지원 하도록 구성 되지 않았을 수 있습니다. 비즈니스용 Skype Online 또는 비즈니스용 Skype 서버용 사용자가 모임을 만들었는지 여부입니다. 
  
사용자가 설명 대로 구성 되지 않은 네트워크에 있는 경우 많은 앱 기능이 작동 하지 않을 수 있으며, 모임에 전혀 연결 되지 않을 수 있습니다.
  
## <a name="supported-meetings-features"></a>지원 되는 모임 기능
<a name="BKMK_Conferencing"> </a>

이 표는 비즈니스용 Skype 클라이언트, 비즈니스용 Skype Web App, Skype 모임 앱, Lync Web App 사용자가 사용할 수 있는 모임 기능을 비교 합니다. Lync Web App이 기능 비교를 위해 나열 됨: 모임이 Lync 2013 서버에서 호스팅되는 경우 사용자는 Lync Web App을 다운로드 하 고 사용 합니다.

| 기능/기능 | 비즈니스용 Skype 2016 또는 2019 클라이언트 | Mac 클라이언트의 비즈니스용 Skype | Skype 모임 앱 | 비즈니스용 Skype Web App | Lync Web App |
|:-----|:-----|:-----|:-----|:-----|:-----|
|컴퓨터 오디오 추가  <br/> |&#x2714;|&#x2714;|&#x2714; (플러그 인 필요)  <br/> |&#x2714; (플러그 인 필요)  <br/> |&#x2714; (플러그 인 필요)  <br/> |
|비디오 추가  <br/> |&#x2714;|&#x2714;|&#x2714; (플러그 인 필요)  <br/> |&#x2714; (플러그 인 필요)  <br/> |&#x2714; (플러그 인 필요)  <br/> |
|인증 된 참가자를 위해 오디오를 전화기로 전환  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|게스트 참가자를 위해 오디오를 전화기로 전환  <br/> |&#x2714;|&#x2714;|&#x2714;|||
|단체 영상 보기 (갤러리 보기)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|비디오 기반 화면 공유  <br/> |&#x2714;|&#x2714; <br/> |&#x2714; (보기 전용)  <br/> |||
|모임 내 발표자 컨트롤 사용  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|자세한 모임 명단에 액세스  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|단체 메신저 대화에 참여  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|메신저 대화 메시지를 중요도 높음으로 설정  <br/> |&#x2714;|||||
|데스크톱 공유 (설정 된 경우)  <br/> |&#x2714;|&#x2714;|&#x2714; (플러그 인 필요)  <br/> |&#x2714; (플러그 인 필요)  <br/> |&#x2714; (플러그 인 필요)  <br/> |
|프로그램 공유 (설정 된 경우)  <br/> |&#x2714;||&#x2714; (Windows 에서만, 플러그인 필요)  <br/> |&#x2714; (Windows 에서만, 플러그인 필요)  <br/> |&#x2714; (Windows 에서만, 플러그인 필요)  <br/> |
|다른 사용자의 공유 데스크톱 또는 프로그램에 대 한 제어권을 갖습니다.  <br/> |&#x2714;||&#x2714; (Windows 에서만 &#x2776;, 플러그 인 필요)  <br/> |&#x2714; (Windows 에서만 &#x2776;, 플러그 인 필요)  <br/> |&#x2714; (Windows 에서만 &#x2776;, 플러그 인 필요)  <br/> |
|다른 사용자가 공유 데스크톱 또는 프로그램에 대 한 제어권을 가질 수 있도록 허용  <br/> |&#x2714;|||||
|익명 참가자 추가 (사용 하도록 설정 된 경우)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|이름으로 참가자 초대  <br/> |&#x2714;|&#x2714;||||
|전화 번호를 기준으로 참가자 초대  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|전자 메일로 참가자 초대  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|전화 접속 오디오 모임 사용  <br/> |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|지금 시작 모임 만들기  <br/> |&#x2714;|&#x2714;||||
|모임 녹음/녹화  <br/> |&#x2714;|||||
|첨부 파일 추가 및 다운로드  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Microsoft PowerPoint 파일 추가 및 발표  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Microsoft PowerPoint 파일 탐색  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|OneNote 모임 메모 추가 및 편집  <br/> |&#x2714;||편집만 (추가 아님)  <br/> |편집만 (추가 아님)  <br/> |편집만 (추가 아님)  <br/> |
|화이트 보드 사용  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|설문 수행  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|파일을 업로드 하 여 다른 사용자와 공유  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|모임 또는 전화 회의 예약  <br/> |Outlook 또는 비즈니스용 Skype Web Scheduler  <br/> |Outlook 또는 비즈니스용 Skype Web Scheduler  <br/> |비즈니스용 Skype Web Scheduler  <br/> |비즈니스용 Skype Web Scheduler  <br/> |비즈니스용 Skype Web Scheduler  <br/> |
|Q&amp;A 관리자  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|참석자 영상 사용 안 함  <br/> |&#x2714;|||||
|모임 메신저 사용 안 함  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|청중 음소거  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|모든 사용자를 참석자로 만들기  <br/> |&#x2714;|||||
|Skype 모임 브로드캐스트 만들기  <br/> |&#x2714;|||||
   
 &#x2776; 참가자는 비즈니스용 Skype에서 공유 하는 데스크톱, mac 용 Lync 2011 또는 Mac 용 Communicator 2011 사용자를 제어할 수 없습니다. 이는 또한 Max OSX의 비즈니스용 Skype Web App에서 작동 하지 않습니다.
  
 비즈니스용 Skype Online의 &#x2777;이 기능을 사용 하려면 Microsoft PSTN 회의, Exchange 통합 메시징 또는 타사 오디오 회의 공급자가 필요 합니다.
  
 Mac 용 Lync 2011 클라이언트는 비즈니스용 Skype Web App에서 컨퍼런스를 통해 공유 하는 경우 Microsoft Office 2013 PowerPoint 프레젠테이션을 볼 수 없습니다. &#x2778;
  
## <a name="known-issues-and-troubleshooting"></a>알려진 문제점 및 문제 해결
<a name="BKMK_Conferencing"> </a>

최종 사용자의 경우 이러한 앱에 대 한 [온라인 도움말](https://aka.ms/smahelp) 을 바로 사용할 수 있습니다. IT 전문가는 다음과 같은 문제에 유의 해야 합니다.
  
- 네트워크 [요구 사항](meetings-clients.md#Network)에 맞게 구성 되지 않은 네트워크를 사용 하는 경우 많은 앱 기능이 작동 하지 않을 수 있으며, 모임에 전혀 연결 하지 못할 수 있습니다.
    
- 일부 사용자는 앱을 설치할 수 있는 사용 권한이 없는 회사 관리 컴퓨터를 보유 하 고 있을 수 있습니다. 이러한 사용자의 경우 두 앱이 모두 옵션이 아니지만 [스마트 휴대폰](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-1) 및 [태블릿](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-2) 사용자가 모임에 참석할 때 사용할 수 있는 저렴 한 모바일 클라이언트를 설치할 수 있습니다.
    
    기타 설치 문제는 [도움말 항목](https://support.office.com/en-us/article/Trouble-installing-the-Skype-for-Business-Web-App-plug-in-958fc5f1-2d6f-42e3-815d-a9516c591274?ui=en-US&amp;rs=en-US&amp;ad=US)에서도 다룹니다. 
    
- 모임 앱을 처음 실행할 때 사용자에 게 방화벽 경고가 표시 될 수 있습니다. 환경을 최적화 하기 위해 포트를 열어야 하는 메시지가 나타날 수 있으며,이 경우 해당 사용자에 게 없을 수 있는 컴퓨터에 대 한 관리자 권한이 필요할 수 있습니다. 앱이 계속 작동 하 고 사용자가 요청 된 포트를 여는 것을 안전 하 게 거부할 수 있습니다. 
    
- IE가 기본 브라우저가 아닌 경우에도 Internet Explorer에서 [필터링 하지 않고 ActiveX를 사용할](https://support.office.com/en-us/article/Turn-off-ActiveX-filtering-for-Skype-for-Business-Web-App-b6de8ff6-ac7e-4e2f-b18c-2f13db643c41?ui=en-US&amp;rs=en-US&amp;ad=US) 수 있어야 합니다. 비즈니스용 Skype Web App에서 오디오, 비디오, 화면 공유에는 ActiveX 컨트롤 (웹 앱 또는 기타 프로그램에 추가 기능을 추가 하는 작은 모듈)이 필요 합니다.
    
- 비즈니스용 Skype Web App의 일부 기능이 제대로 작동 하려면 브라우저에서 컴퓨터 또는 장치에 [쿠키를 저장할](https://support.office.com/en-us/article/Allow-cookies-for-Skype-Meetings-App-Skype-for-Business-Web-App-2108276b-b5c3-484b-bf2b-dac6eeba4c93) 수 있도록 허용 해야 합니다.
    
- 일부 비즈니스용 Skype Web App 기능이 예상 대로 작동 하려면 브라우저에서 [JavaScript 지원을 설정](https://support.office.com/en-us/article/Turn-on-JavaScript-for-Skype-Meetings-App-Skype-for-Business-Web-App-3d997bf9-637c-4fe6-8ee3-9e62bfda52cd) 해야 할 수 있습니다.
    
### <a name="aes-support"></a>AES 지원 

비즈니스용 Skype Server 2015 CU5의 경우 ASP.NET 4.6에는 AES가 지원 되지 않으며,이로 인해 Skype 모임 앱이 시작 되지 않을 수 있습니다. [ASP .net 4.5 때문에 암호화 요구 사항](../security/user-and-client-authentication.md#cryptographic-requirements-due-to-asp-net-45) 에 대 한 자세한 내용이 있습니다.
  
## <a name="see-also"></a>참고 항목
<a name="BKMK_Conferencing"> </a>

[비즈니스용 Skype 서버에서 웹 다운로드 가능 클라이언트 배포](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Skype 모임 앱에 대해 지원 되는 플랫폼](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
