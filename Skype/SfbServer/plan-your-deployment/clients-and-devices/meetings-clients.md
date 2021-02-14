---
title: 모임 클라이언트 계획(Web App 및 모임 앱)
ms.author: v-cichur
author: cichur
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
description: '요약: IT 전문가는 비즈니스용 Skype 서버를 계획하는 동안 비즈니스용 Skype Web App 및 Skype 모임 앱에 대한 지원 요구 사항을 검토해야 합니다. 이 문서는 이러한 앱의 사용자를 위한 것이 아니며,'
ms.openlocfilehash: 4956a11c0ed163cbe50c49233e9aa05a0fbbd872
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826018"
---
# <a name="plan-for-meetings-clients-web-app-and-meetings-app"></a>모임 클라이언트 계획(Web App 및 모임 앱)
 
**요약:** IT 전문가는 비즈니스용 Skype 서버를 계획하는 동안 비즈니스용 Skype Web App 및 Skype 모임 앱에 대한 지원 요구 사항을 검토해야 합니다. 이 문서는 이러한 앱의 사용자를 위한 것이 아니며,
  
비즈니스용 Skype 서버를 구현한 후 조직의 사용자에게는 배포 프로세스의 일부로 비즈니스용 Skype 클라이언트가 설치될 수 있습니다. 
  
나중에 이러한 사용자는 모임을 만들고 조직 외부의 사용자를 초대할 수 있으며, 해당 모임 초대에 비즈니스용 Skype 클라이언트 버전이 없는 것일 수 있습니다. 이러한 사용자가 모임 초대 URL을 클릭하면 클라이언트 부족이 감지되고 비즈니스용 Skype 클라이언트가 없는 초대자는 모임에 참가할 수 있도록 경량의 모임 전용 클라이언트를 다운로드하여 설치하도록 요청됩니다.
  
> [!NOTE]
> 비즈니스용 Skype Web App 및 Skype 모임 앱은 비즈니스용 Skype 없이 모임에 로그인하려고 할 때만 사용할 수 있습니다. 이러한 앱에 대한 사용자 도움말이 [https://aka.ms/smahelp](https://aka.ms/smahelp) 있습니다. 
  
> [!NOTE]
> 비즈니스용 Skype Web App 또는 Skype 모임 앱을 사전 설치할 수 [](https://products.office.com/skype-for-business/download-app?tab=tabs-1) 없지만 [](https://products.office.com/skype-for-business/download-app?tab=tabs-2) 스마트폰 및 태블릿 사용자는 모임에 참석하는 데 사용할 수 있는 저렴한 모바일 클라이언트를 설치할 수 있습니다.
  
기본적으로 모임을 호스팅하는 서버는 사용자가 비즈니스용 Skype Web App을 다운로드하고 설치하여 모임에 참가하도록 지시합니다. 비즈니스용 Skype Web App은 프런트 엔드 서버에 저장되고 모임 참석자에게 전송됩니다. 
  
비즈니스용 Skype 서버의 경우 비즈니스용 Skype 모임 앱(Windows) 및 Mac용 비즈니스용 Skype(Mac)는 CU5로 시작되는 비즈니스용 Skype Web App의 대체로 사용할 수 있지만, 대체 앱을 제공하려면 비즈니스용 Skype Web [App을](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable)대체하기 위해 Skype 모임 앱 사용(선택 사항)에 설명된 추가 구성이 필요합니다. Skype 모임 앱 및 Mac용 비즈니스용 Skype를 사용하도록 설정하면 사용자는 비즈니스용 Skype 서버가 아닌 Microsoft 365 또는 Office 365 CDN(콘텐츠 배달 네트워크)에서 최신 버전의 앱을 다운로드합니다. 비즈니스용 Skype 서버 2019의 경우 Skype 모임 앱과 Mac용 비즈니스용 Skype를 사용하는 것이 유일한 옵션입니다.
  
Skype 모임 앱은 앱을 다운로드 및 설치하고 모임에 참가할 수 있는 간소화된 브라우저 환경을 제공합니다. 단 한 번의 클릭으로 모임에 참가할 수 Internet Explorer. Skype 모임 앱은 안정성 및 모임 환경을 위해 비즈니스용 Skype Web App에 대한 많은 개선 기능도 제공합니다. 
  
> [!NOTE]
> 비즈니스용 Skype 서버 2015 CU5 이상에서 비즈니스용 Skype Online을 사용하여 진행된 모임은 더 이상 클라이언트 없는 사용자를 비즈니스용 Skype Web App으로 보내지 않고 대신 Skype 모임 앱(Windows) 또는 Mac용 비즈니스용 Skype(Mac)로 전송됩니다. 비즈니스용 Skype 서버 2015 CU5 이상에서 비즈니스용 Skype Web [App(선택](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable)사항)을 대체하도록 Skype 모임 앱을 사용하도록 설정하면 클라이언트 없는 사용자에게 비즈니스용 Skype Web App 대신 Skype 모임 앱 또는 Mac용 Skype for Mac이 전송됩니다. 
  
## <a name="software-requirements"></a>소프트웨어 요구 사항
<a name="OS-Browser"> </a>

비즈니스용 Skype Web App을 사용하려면 사용자에게 지원되는 다음 운영 체제 및 브라우저 조합 중 하나가 있어야 합니다. 
  
**비즈니스용 Skype 웹앱에 대한 운영 체제 및 최소 브라우저 지원**

| 운영 체제 | Edge | 32비트 및 64비트 Internet Explorer 11 이상 | 32비트 및 64비트 Internet Explorer 10 이상 | 32비트 및 64비트 Internet Explorer 9 이상 | 32비트 및 64비트 버전의 Safari 6.2.8 - 11.X | 32비트 및 64비트 버전의 Chrome 18.X 이상 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Windows 10  <br/> |예  <br/> |예  <br/> |해당 없음  <br/> |해당 없음  <br/> |해당 없음  <br/> |예 &#x2778; <br/> |
|Windows 8.1 &#x2776; <br/> |해당 없음  <br/> |예  <br/> |해당 없음  <br/> |해당 없음  <br/> |해당 없음 <br/> |예 &#x2778; <br/> |
|Windows 8(Intel 기반) &#x2776; <br/> |해당 없음  <br/> |해당 없음  <br/> |예  <br/> |해당 없음 <br/> |해당 없음  <br/> |예 &#x2778; <br/> |
|Windows 7 SP1 &#x2777; <br/> |해당 없음  <br/> |예  <br/> |아니요  <br/> |아니요  <br/> |해당 없음 <br/>|예 &#x2778; <br/> |
|Windows Server 2008 R2 SP1 &#x2777; <br/> |해당 없음  <br/> |예  <br/> |예  <br/> |예  <br/> |해당 없음 <br/>|예 &#x2778; <br/> |
|macOS 10.8 이상(Intel 기반) &#x2777; <br/> |해당 없음  <br/> |해당 없음  <br/> |해당 없음  <br/> |해당 없음  <br/> |예  <br/> |예 <br/> |
   
&#x2776; Skype 웹앱 브라우저 플러그 인을 사용하려면 컴퓨터 기반 음성, 비디오, 공유 및 지속적인 화면 공유 및 기타 기능을 사용하려면 특정 공유 플러그 인이 필요합니다. 모임 참석자에는 모임에 참가하거나 이러한 기능 중 하나를 시작할 때 공유 플러그 인을 설치할 수 있는 옵션이 제공됩니다. Windows 8 및 Windows 8.1에서 데스크톱용 Internet Explorer 10 또는 Internet Explorer 11을 실행하는 경우 공유 플러그 인을 설치할 수 있습니다. 이러한 기능은 데스크톱이 아닌 버전의 Internet Explorer 및 11에서는 사용할 수 없습니다. Firefox 및 Safari 버전 12.0 이상은 더 이상 지원되지 않습니다.
  
&#x2777; 지원되는 Windows 7, Windows Server 2008 R2 및 Macintosh 운영 체제에서는 컴퓨터 기반 음성, 비디오, 응용 프로그램 보기, 응용 프로그램 공유, 데스크톱 보기 및 데스크톱 공유를 비롯한 모든 기능을 사용할 수 있습니다. 이러한 기능을 사용하려면 메시지가 표시될 때 플러그 인을 설치해야 합니다. Mac OS X 버전 10.7은 더 이상 지원되지 않습니다.  또한 웹 앱은 OS X 10.15 이상에 설치되지 않습니다.  앞으로 익명 가입 시나리오를 지원하는 Mac용 비즈니스용 Skype의 최신 버전을 사용하는 것이 좋습니다.
  
&#x2778; Chrome에서 Web App에 액세스하면 포함된 프레임에 Web App을 로드하는 작은 Internet Explorer 실행됩니다. 이 프로그램을 사용하려면 웹앱이 제대로 로드될 수 Internet Explorer 버전 중 하나를 설치해야 합니다.
  
> [!NOTE]
> Microsoft 365 및 Office 365 사용자는 비즈니스용 Skype에서 Internet Explorer 10 이상을 사용할 수 있습니다. 
  
### <a name="skype-meetings-app"></a>Skype 모임 앱

Skype 모임 앱은 32비트 및 64비트 Internet Explorer 11 이상이 설치된 Windows 10, Windows 8.1, Windows 8, Windows 7을 사용하는 컴퓨터에서 앱으로 실행됩니다. 
  
다른 종속성에 대한 자세한 내용은 Skype 모임 앱에 대해 지원되는 [플랫폼을 참조하세요.](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
  
### <a name="skype-for-business-for-mac"></a>Mac용 비즈니스용 Skype

Mac용 비즈니스용 Skype는 macOS 버전 10.8 이상을 사용하는 컴퓨터에서 실행됩니다. 

## <a name="hardware-requirements"></a>하드웨어 요구 사항
<a name="OS-Browser"> </a>

컴퓨터 하드웨어 요구 사항은 운영 체제 및 브라우저에 따라 결정됩니다. 음성 및 전화 통신 기능을 사용하려면 마이크와 스피커, 마이크가 있는 헤드셋 또는 컴퓨터와 호환되는 동등한 장치가 필요합니다. 비디오 기능을 사용하려면 컴퓨터와 호환되는 비디오 장치가 필요합니다. 비디오 하드웨어 지원 및 예상 비디오 품질에 대한 자세한 내용은 비즈니스용 [Skype 클라이언트 비디오 해상도를 참조하세요.](video-resolutions.md)
  
## <a name="network-requirements"></a>네트워크 요구 사항
<a name="Network"> </a>

비즈니스용 Skype Web App 또는 Skype 모임 앱 사용자가 연결 문제를 경험하는 경우 Office 365 URL 및 IP 주소 범위에 설명된 Office [365를](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)지원하도록 조직의 네트워크 인프라가 구성되지 않은 것일 수 있습니다. 이 경우 비즈니스용 Skype Online 또는 비즈니스용 Skype 서버의 사용자가 모임을 만들지 여부가 결정됩니다. 
  
사용자가 설명한 바와 같이 구성되지 않은 네트워크에 있는 경우 많은 앱 기능이 작동하지 않을 수 있으며 모임에 연결하지 못하게 될 수 있습니다.
  
## <a name="supported-meetings-features"></a>지원되는 모임 기능
<a name="BKMK_Conferencing"> </a>

이 표에서는 비즈니스용 Skype 클라이언트, 비즈니스용 Skype Web App, Skype 모임 앱 및 Lync Web App의 사용자가 사용할 수 있는 모임 기능을 비교합니다. Lync Web App은 기능 비교 목적으로 나열됩니다. 사용자는 모임이 Lync 2013 서버에서 호스팅된 경우 Lync Web App만 다운로드하고 사용하게 됩니다.

| 기능 | 비즈니스용 Skype 2016 또는 2019 클라이언트 | Mac의 비즈니스용 Skype 클라이언트 | Skype 모임 앱 | 비즈니스용 Skype Web App | Lync Web App |
|:-----|:-----|:-----|:-----|:-----|:-----|
|컴퓨터 오디오 추가  <br/> |&#x2714;|&#x2714;|&#x2714;(플러그 인 필요)  <br/> |&#x2714;(플러그 인 필요)  <br/> |&#x2714;(플러그 인 필요)  <br/> |
|비디오 추가  <br/> |&#x2714;|&#x2714;|&#x2714;(플러그 인 필요)  <br/> |&#x2714;(플러그 인 필요)  <br/> |&#x2714;(플러그 인 필요)  <br/> |
|인증된 참가자를 위해 전화로 오디오 전환  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|게스트 참가자를 위해 전화로 오디오 전환  <br/> |&#x2714;|&#x2714;|&#x2714;|||
|멀티파일 비디오 보기(갤러리 보기)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|비디오 기반 화면 공유  <br/> |&#x2714;|&#x2714; <br/> |&#x2714;(보기 전용)  <br/> |||
|모임 내 발표자 컨트롤 사용  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|자세한 모임 명단 액세스  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|단체 메신저 대화에 참가  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|IM 메시지를 중요도 높음으로 설정  <br/> |&#x2714;|||||
|데스크톱 공유(사용하도록 설정된 경우)  <br/> |&#x2714;|&#x2714;|&#x2714;(플러그 인 필요)  <br/> |&#x2714;(플러그 인 필요)  <br/> |&#x2714;(플러그 인 필요)  <br/> |
|프로그램 공유(사용하도록 설정된 경우)  <br/> |&#x2714;||&#x2714;(Windows에만 해당, 플러그 인 필요)  <br/> |&#x2714;(Windows에만 해당, 플러그 인 필요)  <br/> |&#x2714;(Windows에만 해당, 플러그 인 필요)  <br/> |
|다른 사용자의 공유 데스크톱 또는 프로그램 제어  <br/> |&#x2714;||&#x2714;(&#x2776; Windows에만 해당, 플러그 인 필요)  <br/> |&#x2714;(&#x2776; Windows에만 해당, 플러그 인 필요)  <br/> |&#x2714;(&#x2776; Windows에만 해당, 플러그 인 필요)  <br/> |
|다른 사용자가 공유 데스크톱 또는 프로그램을 제어할 수 있도록 합니다.  <br/> |&#x2714;|||||
|익명 참가자 추가(사용하도록 설정된 경우)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|이름으로 참가자 초대  <br/> |&#x2714;|&#x2714;||||
|전화 번호로 참가자 초대  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|전자 메일로 참가자 초대  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|전화 접속 오디오 모임 사용  <br/> |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|모임 시작 모임 시작  <br/> |&#x2714;|&#x2714;||||
|모임 기록  <br/> |&#x2714;|||||
|첨부 파일 추가 및 다운로드  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Microsoft PowerPoint 파일 추가 및 프레젠테이션 진행  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Microsoft PowerPoint 파일 탐색  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|OneNote 모임 메모 추가 및 편집  <br/> |&#x2714;||편집만(추가 안 )  <br/> |편집만(추가 안 )  <br/> |편집만(추가 안 )  <br/> |
|화이트보드 사용  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|설문 진행  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|다른 사용자와 공유할 파일 업로드  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|모임 또는 회의 예약  <br/> |Outlook 또는 비즈니스용 Skype 웹 스케줄러  <br/> |Outlook 또는 비즈니스용 Skype 웹 스케줄러  <br/> |비즈니스용 Skype 웹 스케줄러  <br/> |비즈니스용 Skype 웹 스케줄러  <br/> |비즈니스용 Skype 웹 스케줄러  <br/> |
|Q &amp; A Manager  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|참석자 비디오를 사용하지 않도록 설정  <br/> |&#x2714;|||||
|모임 IM을 사용하지 않도록 설정  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|대상 음소거  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|모든 사람을 참석자로 만들기  <br/> |&#x2714;|||||
|Skype 모임 브로드캐스트 생성  <br/> |&#x2714;|||||
   
 &#x2776; 참가자가 Mac용 Skype, Mac용 Lync 2011 또는 Mac 2011용 Communicator 공유하는 데스크톱을 제어할 수 없습니다. 이는 Max OSX의 비즈니스용 Skype Web App에도 작동하지 않습니다.
  
 &#x2777; Online의 경우 이 기능을 사용하려면 Microsoft PSTN 회의, Exchange 통합 메시징 또는 제3자 오디오 회의 공급자가 필요합니다.
  
 &#x2778; Lync for Mac 2011 클라이언트는 비즈니스용 Skype Web App에서 회의에서 공유한 Microsoft Office 2013 PowerPoint 프레젠테이션을 볼 수 없습니다.
  
## <a name="known-issues-and-troubleshooting"></a>알려진 문제 및 문제 해결
<a name="BKMK_Conferencing"> </a>

최종 사용자의 경우 이러한 [앱에 대한 온라인](https://aka.ms/smahelp) 도움말을 쉽게 사용할 수 있습니다. IT 전문가는 다음과 같은 문제를 알고 있어야 합니다.
  
- 사용자가 네트워크 요구 사항을 충족하도록 구성되어 [](meetings-clients.md#Network)있지 않은 네트워크에 있는 경우 많은 앱 기능이 작동하지 않을 수 있으며 모임에 연결하지 못하게 될 수 있습니다.
    
- 일부 사용자는 앱을 설치할 수 있는 권한이 비활성화된 회사에서 관리하는 컴퓨터를 사용할 수 있습니다. 이러한 사용자의 경우 두 앱 모두 [](https://products.office.com/skype-for-business/download-app?tab=tabs-1) 옵션이 아니며, 스마트폰 및 태블릿 사용자는 모임에 참석하는 데 사용할 수 있는 저렴한 모바일 클라이언트를 설치할 수 있습니다. [](https://products.office.com/skype-for-business/download-app?tab=tabs-2)
    
    기타 설치 문제도 도움말 항목에서 [다를 수 있습니다.](https://support.office.com/article/Trouble-installing-the-Skype-for-Business-Web-App-plug-in-958fc5f1-2d6f-42e3-815d-a9516c591274?ui=en-US&amp;rs=en-US&amp;ad=US) 
    
- 모임 앱을 처음 실행할 때 방화벽 경고가 표시될 수 있습니다. 환경을 최적화하기 위해 포트를 열지 묻는 메시지가 표시될 수 있으며, 이 경우 사용할 수 없는 컴퓨터의 관리자 권한이 필요할 수 있습니다. 앱이 계속 작동해야 합니다. 사용자는 요청된 포트 열기를 안전하게 거부할 수 있습니다. 
    
- IE가 [ActiveX 브라우저가](https://support.office.com/article/Turn-off-ActiveX-filtering-for-Skype-for-Business-Web-App-b6de8ff6-ac7e-4e2f-b18c-2f13db643c41?ui=en-US&amp;rs=en-US&amp;ad=US) 아니어도 Internet Explorer 필터링하지 않고 이 기능을 사용하도록 설정해야 합니다. 비즈니스용 Skype Web App에서는 오디오ActiveX 비디오 및 화면 공유를 위해 웹 앱 또는 다른 프로그램에 추가 기능을 추가하는 작은 모듈인 앱 컨트롤이 필요합니다.
    
- 비즈니스용 Skype Web App의 일부 기능이 제대로 작동하려면 [](https://support.office.com/article/Allow-cookies-for-Skype-Meetings-App-Skype-for-Business-Web-App-2108276b-b5c3-484b-bf2b-dac6eeba4c93) 브라우저에서 컴퓨터 또는 장치에 쿠키를 저장하도록 허용해야 합니다.
    
- 일부 비즈니스용 Skype Web App 기능이 예상대로 작동하려면 브라우저에서 [JavaScript](https://support.office.com/article/Turn-on-JavaScript-for-Skype-Meetings-App-Skype-for-Business-Web-App-3d997bf9-637c-4fe6-8ee3-9e62bfda52cd) 지원을 켜야 할 수 있습니다.
    
### <a name="aes-support"></a>AES 지원 

비즈니스용 Skype 서버 2015 CU5부터는 ASP.NET 4.6에 대해 AES가 지원되지 않습니다. 이로 인해 Skype 모임 앱이 시작되지 않을 수 있습니다. [ASP .NET 4.5로](../security/user-and-client-authentication.md#cryptographic-requirements-due-to-asp-net-45) 인한 암호화 요구 사항에는 자세한 정보가 있습니다.
  
## <a name="see-also"></a>참고 항목
<a name="BKMK_Conferencing"> </a>

[비즈니스용 Skype 서버에서 웹 다운로드 가능 클라이언트 배포](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Skype 모임 앱에 대해 지원되는 플랫폼](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
