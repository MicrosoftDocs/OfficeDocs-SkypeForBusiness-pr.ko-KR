---
title: Microsoft Teams 룸 요구사항
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6b2b2684-8e9e-49ea-8c46-1c690964f982
ms.collection:
- M365-collaboration
description: 적절한 디바이스, 마이크, Microsoft Teams 룸, 카메라 및 디스플레이를 선택하는 등 지원에 대한 요구 사항에 대해 자세히 알아보습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 17f791298d86bfc6988899a2e090d0d11651e91558bc14c23d515c75ad91cce0
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54348823"
---
# <a name="microsoft-teams-rooms-requirements"></a>Microsoft Teams 룸 요구사항

Microsoft Teams 룸 크기로 확장할 수 있습니다. Teams 룸 크기 및 사용에 따라 다양한 인증된 오디오 및 비디오 주변 장치를 사용할 수 있습니다. 공간에 적합한 마이크, 스피커, 카메라 및 디스플레이와 결합된 올바른 코어 디바이스 및 콘솔을 선택하여 작은 Microsoft Teams 룸 공간에서 큰 회의 공간 및 회의실을 통해 모든 크기의 공간에 Microsoft Teams 룸 배포할 수 있습니다.  룸을 구성 하는데 사용할 수 있는 모든 사용 가능한 인증 오디오 및 비디오 주변 장치는 [장치 보기](https://products.office.com/microsoft-teams/across-devices)에서 볼 수 있습니다.

이 문서는 Microsoft Teams 룸을 지원하는데 필요한 장치 배포 및 구성 요구 사항을 간략하게 설명합니다.

배포를 위해서는 [Microsoft Teams 룸 배포에](rooms-deploy.md) 설명되어 있는 대로 계정을 생성해야 하며 [Microsoft Teams 룸 콘솔 구성에](console.md) 설명되어 있는 대로 룸 콘솔을 설정하세요.

참조:

- [비즈니스용 Skype 추가 기능 라이선스](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)
- [계획에 따른 라이선스 옵션: Microsoft Teams 룸](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2)

> [!NOTE]
> Microsoft Teams 룸 로그인은 Microsoft Teams, 비즈니스용 Skype 서버 2019, 비즈니스용 Skype 서버 2015 혹은 비즈니스 온라인용 Skype에서 사용되며 다른 서비스에서 호스트하는 모임에 참가할 수 있습니다. 
>
> Lync Server 2013 같은 이전 플랫폼은 Microsoft Teams 룸에서 지원하지 않습니다. Microsoft Teams 룸 21Vianet 또는 DoD Microsoft 365 Office 365 환경에서 지원되지 않습니다.
>
> 온프레미스 Exchange 서버를 사용하는 경우 Microsoft Teams 룸에서 Exchange Server 2013 SP1이나 이후 버전을 사용해야 합니다.

## <a name="hardware-requirements"></a>하드웨어 요구 사항
하드웨어 배포에는 인증 오디오 및 비디오 주변기기와 통합된 Microsoft Teams 룸 시스템 선택지와 이 장치를 모두 통합하는 케이블 솔루션을 포함합니다.  여기에서 사용 가능한 옵션에 대해 설명합니다.

**지원 되는 Microsoft Teams 룸 시스템**

모든 현재 Microsoft Teams 룸 장치 및 번들은 [룸 시스템 제품 보기](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=20&page=1&filterIds=)에서 확인 할 수 있습니다.

  |콘솔|프로세서|RAM|디스크|
  |:-----|:-----|:-----|:-----|
  |[Intel NUC를 통해 Crestron Flex UC-M130-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M130-T)|Core i5|8GB |128GB |
  |[Intel NUC를 통해 Crestron Flex UC- B130-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B130-T)|Core i5|8GB |128GB |
  |[Intel NUC를 통해 Crestron Flex UC-B140-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B140-T)|Core i5|8GB |128GB |
  [Intel NUC를 통해 Crestron Flex UC-C140-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C140-T)|Core i7|8GB |128GB|
  |[Intel NUC를 통해 Crestron Flex UC-M150-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M150-T)  +  [CCS-UCA-MIC](https://www.crestron.com/Products/Audio/Microphones/Wired-Microphones/CCS-UCA-MIC-KIT)|Core i7|8GB |128GB |
  |[Intel NUC를 통해 Crestron Flex UC-MX150-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MX150-T)|Core i5|8GB |128GB |
   [Intel NUC를 통해 Crestron Flex UC-B160-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B160-T)|Core i7|8GB |128GB|
  |[Intel NUC를 통해 Crestron Flex UC-C160-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C160-T)|Core i7|8GB|128GB|
  |[UC-PR(UC-PR) 및 ASUS PC가 있는 Crestron Flex UC-MMX30-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MMX30-T)|Core i5|8GB |128GB |
  |[UC-PR(UC-PR) 및 ASUS PC가 있는 Crestron Flex UC-BX30-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-BX30-T)|Core i5|8GB |128GB |
  |[UC-PR(UC-PR) 및 ASUS PC가 있는 Crestron Flex UC-CX100-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-CX100-T)|Core i5|8GB |128GB |
  |[ASUS PC를 통해 Crestron Flex UC-B30-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B30-T)|Core i5|8GB |128GB |
   |[ASUS PC를 통해 Crestron Flex UC-C100-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C100-T)|Core i5|8GB |128GB |
   |[ASUS PC를 통해 Crestron Flex UC-M50-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M50-T)|Core i5|8GB |128GB |
   |[ASUS PC를 통해 Crestron Flex UC-M70-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M70-T)|Core i5|8GB |128GB |
   |[ASUS PC를 통해 Crestron Flex UC-MX50-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MX50-T)|Core i5|8GB |128GB |
   |[ASUS PC를 통해 Crestron Flex UC-MX70-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MX70-T)|Core i5|8GB |128GB |
  |[Crestron Mercury Mini UC-MM30-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MM30-T)|Core i5|8GB |128GB |
  |[Logitech TAP을 사용하여 Dell OptiPlex 7080](https://www.dell.com/work/shop/cty/pdp/spd/optiplex-7080-xe-teams) | Core i7 |16GB |128GB|
  |[회의실 G2 용 HP Elite Slice](https://www8.hp.com/us/en/elite-family/elite-slice-for-meetings.html) |Core i5 |8GB |128GB |
  |[ Microsoft Teams 룸과 HP Elite Slice G2 오디오 준비](https://store.hp.com/us/en/pdp/hp-elite-slice-for-meeting-rooms-g2-skype-room-systems-audio-ready?jumpid=cp_r12131_us/en/psg/elite_slice_for_meetings/product/shop-now-eliteslicemeeting-g2-audio) |Core i5 |8GB |128GB |
  |[Logitech TAP을 사용하여 HP 슬라이스 파트너 준비]( https://www.logitech.com/video-collaboration/partners/hp.html)|Core i5|8GB|128GB| 
  |[Lenovo ThinkSmart Hub 500](https://www3.lenovo.com/us/en/hub500) |Core i5 |8GB |128GB |
  |[Lenovo ThinkSmart Hub](https://news.lenovo.com/pressroom/press-releases/new-thinksmart-hub-collaboration-solution-from-lenovo-helps-organizations-embrace-hybrid-working-model/) |Core i5 |8GB |128GB|
  |[Intel NUC를 사용하여 Logitech Tap](https://www.logitech.com/product/microsoft-rooms)|Core i5|8GB |128GB |
  |Logitech Tap 및 Intel Tiger Canyon NUC PC |Core i5|8GB|128GB|
  |[Logitech Tap 및 Lenovo ThinkSmart Tiny](https://www.logitech.com/video-collaboration/partners/lenovo.html)|Core i5|8GB |128GB|
  |[Lenovo ThinkSmart Tiny이 있는 Poly G10-T](https://www.poly.com/us/en/products/video-conferencing/g/g10) |Core i5| 8GB | 128GB|
  |[Intel NUC를 통해 Yealink MVC300](https://www.yealink.com/products_154.html)|Core i5|8GB |128GB |
  |[Intel NUC를 통해 Yealink MVC500](https://www.yealink.com/products_126.html)|Core i5|8GB |128GB |
  |[Intel NUC를 통해 Yealink MVC800](https://www.yealink.com/products_125.html)|Core i5|8GB|128GB|
  |[Intel NUC를 통해 Yealink MVC900](https://www.yealink.com/product/microsoft-teams-room-system-mvc900)|Core i5|8GB|128GB|
  |[Yealink MVC 300 II](https://www.yealink.com/product/microsoft-teams-room-system-mvc300II) |Core i5|8GB | 128GB|
  |[Yealink MVC400](https://www.yealink.com/product/microsoft-teams-room-system-mvc400)        |Core i5|8GB | 128GB|
  |[Yealink MVC 500 II](https://www.yealink.com/product/microsoft-teams-room-system-mvc500II) |Core i5|8GB | 128GB|
  |[Yealink MVC 800 II](https://www.yealink.com/product/microsoft-teams-room-system-mvc800II) |Core i5|8GB | 128GB|
  |[Yealink MVC 900 II](https://www.yealink.com/product/microsoft-teams-room-system-mvc900II) |Core i5|8GB | 128GB|
  |[Yealink MVC840](https://www.yealink.com/product/microsoft-teams-room-system-mvc840) |Core i5|8GB | 128GB|
  |[Yealink MVC940](https://www.yealink.com/product/microsoft-teams-room-system-mvc940) |Core i5|8GB | 128GB|
  |Yealink MVC660|Core i5|8GB | 128GB|
  |Yealink MVC640|Core i5|8GB | 128GB|
  |Yealink MVC320|Core i5|8GB | 128GB|
  
  
> [!NOTE]
> - Core M3 프로세서는 지원되지 않습니다. 
> - Windows 10 Enterprise 용 부트 가능한 Windows 설치 미디어 구성을 위해 32GB 이상의 USB 드라이브가 필요합니다.

**도킹 스타일 시스템용 Surface Pro 태블릿 지원**

  |태블릿|프로세서|RAM|디스크|
  |:-----|:-----|:-----|:-----|
  |Surface Pro 6| Core i5 |16 GB 혹은 8 GB |128GB 이상 |
  |Surface Pro </br>(5G) |Core i5 |8 GB 혹은 4 GB |128GB 이상 |
  |Surface Pro 4 |Core i5 |8 GB 혹은 4 GB |128GB 이상 |

- Surface Pro 디바이스에는 다음 도킹 스테이션 옵션 중 하나가 필요합니다.

  - [Logitech SmartDock](https://www.logitech.com/product/smartdock)
  - [Crestron SR](https://www.crestron.com/products/line/sr-for-skype-for-business-room-system )
  - [Polycom MSR Series](https://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.html)

### <a name="certified-firmware-versions-for-usb-audio-and-video-peripherals"></a>USB 오디오 및 비디오 주변 기기와 인증된 펌웨어 버전

이러한 장치는 [룸 시스템 액세서리 제품 소개](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73&page=1&filterIds=) 및 [https://office.com/teamsdevices](https://office.com/teamsdevices)에서 확인할 수 있습니다.

|Microsoft Teams 룸 주변기기|인증된 펌웨어 버전 | 카메라는 콘텐츠 카메라 사용을 지원 합니다.|
|:--- |:--- | :--- |
|[Aver VC520 Pro 카메라 + 스피커폰](https://www.averusa.com/products/conference-camera/vc520pro) |1004.35|
|[Aver VB342+ 카메라 사운드바](https://www.averusa.com/products/conference-camera/vb342plus) | 사운드바: 0.0.0000.97|
|[Aver CAM 540](https://www.averusa.com/products/conference-camera/cam540) |0.0.6002.83 |
|[Aver CAM 520 Pro](https://www.averusa.com/products/conference-camera/cam520pro) |0.0.1000.73 |
|[Aver CAM 520 Pro 2](https://www.averusa.com/products/conference-camera/cam520pro2) |0.0.7200.3 |
|[Aver CAM 130](https://www.averusa.com/products/conference-camera/cam130) |0.0.7400.03 |
|[Bose Video Bar VB1](https://pro.bose.com/en_us/products/conferencing/videobars/bose-videobar-vb1.html?mc=25_PS_VB_BO_00_BI_&&msclkid=fc99b79880f714727a63e86ea0e5642a&utm_source=bing&utm_medium=cpc&utm_campaign=US%20-%20Brand_Videobar%20VB1_Exact&utm_term=bose%20videobar%20vb1&utm_content=Bose%20Videobar%20VB1&gclid=fc99b79880f714727a63e86ea0e5642a&gclsrc=3p.ds) |19.2|
|[Biamp Devio SCR-20CX Web-Based 마이크가 있는 회의 허브](https://www.biamp.com/products/product-families/devio/huddle-room-solutions) |2.2.0.9|
|[Tabletop 마이크를 사용하여 Biamp Devio SCR-20TX Web-Based 회의 허브](https://www.biamp.com/products/product-families/devio/huddle-room-solutions) |2.2.0.9 |
|[Crestron Huddly IQ](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Accessories/CCS-CAM-USB-F-400)   | 1.02.09.33901  | 
|[Huddly Canvas](https://www.huddly.com/blog/say-hello-to-huddly-canvas-our-latest-ai-technology-for-content-capture-and-enhancement/) | 1.3.25 |  &#x2714; |
|[Huddly IQ](https://www.huddly.com/conference-cameras/iq/) |1.3.22|
|[Huddly IQ Lite](https://www.huddly.com/conference-cameras/iq/) |1.3.29|
|[Huddly IQ 카메라](https://www.huddly.com/conference-cameras/iq/) |1.3.27|
|[Jabra Panacast3 카메라](https://www.jabra.com/business/video-conferencing/jabra-panacast)|1.3.9.12|
|[Jabra Panacast 50 Video Bar](https://www.jabra.com/business/video-conferencing/jabra-panacast-50)|1.9.3|
|[Lenovo ThinkSmart Cam Camera](https://www.lenovo.com/us/en/accessories-and-monitors/webcams-and-video/webcams/SMARTOF-BO-ThinkSmart-Cam/p/4Y71C41660)|1.0.111.4|
|[Lenovo ThinkSmart Bar](https://www.lenovo.com/us/en/virtual-reality-and-smart-devices/smart-collaboration/thinksmart/ThinkSmart-Bar/p/11SP1TSSDBR)|0.9.3|
|Lenovo ThinkSmart Bar Expand XL|5.9.5|
|[Logitech Brio](https://www.logitech.com/product/brio)   |V2.2.50| &#x2714; |
|[Logitech 930e](https://www.logitech.com/product/c930e-webcam)   | 8.0.914   | &#x2714; |
|[Logitech Rally](https://www.logitech.com/product/rally-ultra-hd-conferencecam)   |1.2.4 |
|[Logitech Rally Bar](https://www.logitech.com/products/video-conferencing/room-solutions/rallybar.960-001308.html)   |10.3.82|
|[Logitech MeetUp](https://www.logitech.com/product/meetup-conferencecam)   |오디오 — 1.0.172 <br/> 비디오 — 1.0.156  |
|[Logitech ConferenceCam 연결](https://www.logitech.com/product/conferencecam-connect)   |1.1.248.0 <br/> 1.1.684   |
|[Logitech Group](https://www.logitech.com/product/conferencecam-group)   |8.5.778   |
|[Logitech PTZ Pro](https://www.logitech.com/product/conferencecam-ptz-pro)   | 1.1.219   |
|[Logitech PTZ Pro 2](https://www.logitech.com/product/conferencecam-ptz-pro2)   |
|[Nureva HDL300](https://www.nureva.com/audio-conferencing/hdl300) |2.3.6|
|[Poly Eagle Eye Cube 카메라](https://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.html)  |1.2.0 |
|[Polycom EagleEye IV](https://www.poly.com/us/en/products/video-conferencing/eagleeye/eagleeye-iv)   |1.0.0   |
|[Polycom CX5100](https://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.mdl)   | 1.2.0.70232   |
|[Polycom Eagle Eye Director II](https://www.polycom.com/hd-video-conferencing/peripherals/eagleeye-director-ii.html)|2.1.0.10|
|[Polycom Studio Soundbar](https://www.polycom.com/hd-video-conferencing/room-video-systems/polycom-studio.html)|1.1.2.000570|
|[Poly Sync 40](https://www.poly.com/us/en/products/phones/sync/sync-40)|0.0.94.1461|
|[Poly Sync 60](https://www.poly.com/us/en/products/phones/sync/sync-60)|0.0.150.1671|
|[Polycom Trio 8500 / 8800](https://www.polycom.com/voice-conferencing-solutions/conference-phones/trio.html)   |5.7.2.3205|
|[Poly Trio C60](https://www.poly.com/us/en/products/phones/trio/trio-c60)  |5.9.5.3066|
|[Poly Studio P15 비디오 표시줄](https://www.poly.com/us/en/products/video-conferencing/studio-p/studio-p15)|1.2.0.000287 |
|[EPOS SP 220 MS](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc)   |2.0.12.0   |
|[EPOS SP20](https://www.eposaudio.com/en/us/enterprise/products/sp-20-ml-142ee5ca-speakerphone-1000226)   |1.2.15   |
|[EPOS SP30](https://www.eposaudio.com/en/us/enterprise/products/sp-30-78c0cecc-bluetooth-speakerphone-1000223)   |2.1.52  |
|[EPOS SP30T](https://www.eposaudio.com/en/us/enterprise/products/sp-30t-b949fe9a-bluetooth-speakerphone-1000225)  |3.2.63  |
|[EPOS 확장 80T + 2 확장 마이크](https://www.eposaudio.com/en/us/enterprise/products/expand-80t-bluetooth-speakerphone-1000203) |스피커폰 - 4.6.55 <br/> 확장 마이크 — 0.2.314|
|[EPOS 확장 캡처 5](https://www.eposaudio.com/en/us/enterprise/products/expand-capture-5-speakerphone-1000895)  |1.0.1|
|[Jabra 510](http://www.jabra.com/support/Jabra-SPEAK&trade;-510_7510-209)   |2.10.0   |
|[Jabra 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710)   |1.8.0   |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810)   |1.2.23   |
|[Yamaha YVC-1000](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/)   |100c   |
|[Yealink CP900](https://www.yealink.com/products_150.html) |100.20.0.29 |
|[Yealink UVC30](https://www.yealink.com/product/microsoft-teams-room-system-uvc30)| 105.420.0.11 |  &#x2714; |
|[Yealink UVC40 올인원 비디오 표시줄](https://www.yealink.com/product/usb-videobar-uvc40) |128.410.0.10|  
|[Shure Intellimix P300 오디오 회의 프로세서](https://www.shure.com/products/mixers/p300)+</br></br> [Shure MXA 310 표 배열 마이크 ](https://www.shure.com/products/microphones/mxa310) | 4.1 |
|[Shure Intellimix P300 오디오 회의 프로세서](https://www.shure.com/products/mixers/p300) + </br></br> [Shshmxa 910 Intellimix 천장 배열 마이크](https://www.shure.com/products/microphones/mxa910) | 4.1|
|[Shure Intellimix P300 오디오 회의 프로세서](https://www.shure.com/products/mixers/p300)+</br></br> [Shure MXA 310 테이블 배열 마이크 ](https://www.shure.com/products/microphones/mxa310) +</br></br> [MXN5W-C 천장 스피커](https://www.shure.com/products/loudspeakers/mxn5)| P300 DSP: 4.1.11 </br> MXA310 테이블 배열 마이크: 4.1.41 </br> MXN5W-C 스피커: 1.0.4 |
|[Shure Intellimix P300 오디오 회의 프로세서](https://www.shure.com/products/mixers/p300) + </br></br> [Intellimix 천장 배열 마이크가 있는 Shure MXA 910](https://www.shure.com/products/microphones/mxa910) +</br></br> [MXN5W-C 천장 스피커](https://www.shure.com/products/loudspeakers/mxn5)| P300 DSP: 4.1.11 </br> MXA910 천장 배열 마이크: 4.1.41 </br> MXN5W-C 스피커: 1.0.4 |
|[Shure MXA 710 2ft 테이블 선형 배열 마이크](https://www.shure.com/products/microphones/mxa710) + </br></br> [Shure Intellimix P300 오디오 회의 프로세서](https://www.shure.com/products/mixers/p300) +</br></br> [MXN5-C 천장 스피커](https://www.shure.com/products/loudspeakers/mxn5)| MXA710 2ft 테이블 선형 배열 마이크: 1.2.0 </br> P300 DSP: 4.4.8 </br> MXN5-C 스피커: 1.1.1 |
|[Shure MXA 710 4ft Wall 선형 배열 마이크](https://www.shure.com/products/microphones/mxa710) + </br></br> [Shure Intellimix P300 오디오 회의 프로세서](https://www.shure.com/products/mixers/p300) +</br></br> [MXN5-C 천장 스피커](https://www.shure.com/products/loudspeakers/mxn5)| MXA710 4ft 벽 선형 배열 마이크: 1.2.0 </br> P300 DSP: 4.4.8 </br> MXN5-C 스피커: 1.1.1 |
|[Intellimix 천장 배열 마이크가 있는 Shure MXA 910](https://www.shure.com/products/microphones/mxa910) + </br> [Shure Intellimix Room Software](https://www.shure.com/products/software/intellimix_room) +</br> [Crestron UC-C100-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C100-T)| Shure Intellimix Room Software: 3.0.4.14 </br> Intellimix 천장 배열 마이크가 있는 Shure MXA 910: 4.4.11 </br> Shure MXN5-C 스피커: 1.2.1 </br> Crestron UC-C100-T: 4.8.31.0 MTR 앱 버전이 있는 windows IOT 19h2/20h2 OS 버전 </br> BIOS: ASUS Tek Computer INC 9934 8/27/2020 </br> CPU: i5-9500TCPU </br> 물리적 메모리: 8GB RAM |
|[Biamp Tesira Fore AVB VT4 고정 오디오 DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ &Dagger;</br></br> [Sennheiser TeamConnect 천장 2 마이크](https://sennheiser.com/tcc2)+ &Dagger;</br></br> [Tesira EX-UBT](https://www.biamp.com/products/tesira/tesira-expanders) &Dagger; |  Biamp DSP: 3.12.0.15  </br></br> TCC2: 1.3.3 </br></br> EX-UBT: 3.12.0.15 |
|[Biamp Tesira FORTÉ AVB VT4 오디오 DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ </br></br>[Biamp Parlé TCM-XA 천장 마이크](https://www.biamp.com/products/product-families/parle/parle-microphones)+</br></br> [Biamp Desono C-IC6 천장 탑재 라우드스피커](https://www.biamp.com/products/tesira-speakers)| 오디오 FW 버전: 3.15|
|[Biamp TesiraFORTE AVB VT4](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ </br></br>[Parle TTM-X(테이블 마이크)](https://www.biamp.com/products/product-families/parle/parle-microphones)+</br></br>[Ex-UBT]() |오디오 FW 버전: 3.15|
|[Bose ControlSpace EX-440C DSP + </br>Bose P2600A AmpLink 증폭기 +</br> Sennheiser TCC2 천장 마이크 + </br> Bose EdgeMax EM180 천장 스피커](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html)|  Bose DSP: 2.290  </br> P2600A : 1.160  </br> TCC2: 1.4.2  |  |
|[Bose ControlSpace EX-440C DSP + </br> Bose P2600A AmpLink 증폭기 + 젠하이저 TCC2 천장 마이크 + </br> Bose DesignMax DM2C-P 천장 스피커](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html)|  Bose DSP: 2.290  </br> P2600A : 1.160  </br> TCC2: 1.4.2  |  |
|[Bose ControlSpace EX-1280C DSP](https://pro.bose.com/en_us/products/signal_processing_and_networking/controlspace_ex/cs_ex_1280c.html#v=cs_ex_1280c_black) +</br>Bose P2600A AmpLink 증폭기 +</br> [젠하이저 TCC2 천장 마이크](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html) +</br> [DesignMax DM2C -LP 천장 스피커](https://pro.bose.com/en_us/products/loudspeakers/background_foreground/designmax/designmax_dm2c_lp.html#v=designmax_dm2c_lp_black) | Bose DSP: 2.290  </br> P2600A : 1.160  </br> TCC2: 1.4.2  | 
|[Bose ControlSpace EX-1280C DSP](https://pro.bose.com/en_us/products/signal_processing_and_networking/controlspace_ex/cs_ex_1280c.html#v=cs_ex_1280c_black) +</br>Bose P2600A AmpLink Amplifier+</br> [젠하이저 TCC2 천장 마이크](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html) +</br> [EdgeMax EM180 천장 스피커](https://pro.bose.com/en_us/products/loudspeakers/background_foreground/edgemax/edgemax_em180.html#v=edgemax_em180_white) | Bose DSP: 2.290  </br> P2600A : 1.160  </br> TCC2: 1.4.2  |
|[QSC Q-SYS Core 110f](https://www.qsc.com/systems/products/q-sys-ecosystem/products-peripherals-accessories/q-sys-cores/core-110f/) +</br> [젠하이저 TCC2 천장 마이크]() +</br> [QSC EnergyStar Power Amplifier SPA2-60](https://www.qsc.com/systems/products/power-amplifiers/energystar-amplifiers/spa-series/spa2-60/) +</br> [Q-SYS NS 시리즈 네트워크 스위치 NS-1108P](https://www.qsc.com/systems/products/q-sys-ecosystem/products-peripherals-accessories/network-switches/q-sys-ns-series-network-switches/) + </br> [QSC 열 Surface 탑재 스피커 AD-S402T](https://www.qsc.com/systems/products/loudspeakers/column-surface-mount-loudspeakers/acousticdesigntm-series-column-surface-mount/ad-s402t/) +</br> [QSC PTZ 20x60 카메라](https://www.qsc.com/systems/products/q-sys-ecosystem/products-peripherals-accessories/conference-room-integration/ptz-ip-conference-cameras/) |Q-sys Designer: 8.4.0.1 </br> <br> TCC2 : 1.5.1 Dante 1.2.0 </br>  <br> 해당 없음 </br>  <br>N1100v6.4.2.8 </br> 해당 없음 </br> <br> 6.3.2.2|
|[QSC Q-SYS Core 110f](https://www.qsc.com/systems/products/q-sys-ecosystem/products-peripherals-accessories/q-sys-cores/core-110f/) +</br> [젠하이저 TCC2 천장 마이크]() +</br> [QSC EnergyStar Power Amplifier SPA2-60](https://www.qsc.com/systems/products/power-amplifiers/energystar-amplifiers/spa-series/spa2-60/) +</br> [Q-SYS NS 시리즈 네트워크 스위치 NS-1108P](https://www.qsc.com/systems/products/q-sys-ecosystem/products-peripherals-accessories/network-switches/q-sys-ns-series-network-switches/) + </br> [QSC 열 Surface 탑재 스피커 AD-C6T-LP](https://www.qsc.com/systems/products/loudspeakers/ceiling-mount-loudspeakers/acousticdesigntm-series-ceiling-mount/ad-c6t-lp/?L=) +</br> [QSC PTZ 20x60 카메라](https://www.qsc.com/systems/products/q-sys-ecosystem/products-peripherals-accessories/conference-room-integration/ptz-ip-conference-cameras/) |Q-sys Designer: 8.4.0.1 </br> <br> TCC2 : 1.5.1 Dante 1.2.0 </br>  <br> 해당 없음 </br>  <br>N1100v6.4.2.8 </br> 해당 없음 </br> <br> 6.3.2.2|
|[QSC Q-SYS Core 8 Flex 프로세서](https://www.qsc.com/solutions-products/q-sys-ecosystem/processing/core-8-flex/) +</br> [QSC PTZ 20x60 카메라](https://www.qsc.com/solutions-products/q-sys-ecosystem/video/ptz-ip-conference-cameras/) +</br> [젠하이저 TCC2 천장 마이크](https://sennheiser.com/tcc2) +</br> [QSC 천장 스피커 AD-C6T-LP](https://www.qsc.com/solutions-products/loudspeakers/installed/passive/ceiling-mount/acousticdesign-series/ad-c6t-lp/) |QSC PTZ IP 20x60 카메라: 9.0 </br> QSC Q-SYS Core 8-Flex: Q-SYS Designer 9.0.1-2104.002 </br> QSC Q-SYS Nano: Q-SYS Designer 9.0.1-2104.002 </br> 젠하이저 TCC2 천장 마이크: TCC2 - 1.5.1 Dante 1.2.0 </br> SPA 시리즈 EnergyStar 앰프: N/A </br> AcousticDesign 시리즈 라우드스피커: N/A|
|[QSC Q-SYS Core Nano 프로세서](https://www.qsc.com/solutions-products/q-sys-ecosystem/processing/core-nano/) +</br> [QSC PTZ 20x60 카메라](https://www.qsc.com/solutions-products/q-sys-ecosystem/video/ptz-ip-conference-cameras/) +</br> [젠하이저 TCC2 천장 마이크](https://sennheiser.com/tcc2) +</br> [QSC 천장 스피커 AD-C6T-LP](https://www.qsc.com/solutions-products/loudspeakers/installed/passive/ceiling-mount/acousticdesign-series/ad-c6t-lp/) |QSC PTZ IP 20x60 카메라: 9.0 </br> QSC Q-SYS Core 8-Flex: Q-SYS Designer 9.0.1-2104.002 </br> QSC Q-SYS Nano: Q-SYS Designer 9.0.1-2104.002 </br> 젠하이저 TCC2 천장 마이크: TCC2 - 1.5.1 Dante 1.2.0 </br> SPA 시리즈 EnergyStar 앰프: N/A </br> AcousticDesign 시리즈 라우드스피커: N/A|


&Dagger; 고객은 번들에서 Biamp/Sennheiser에서 권장하는 Dante 인터페이스 혹은 네트워크 스위치를 선택할 수 있습니다.

#### <a name="usb-extenders"></a>USB 확장기

- 태블릿 도킹의 USB 포트는 USB 3.0과 호환됩니다. USB 2.x 확장기를 사용할 수 있지만 결국에는 USB 2.x의 속도를 제한하게 됩니다. USB 3.0 주변기기에는 확장기를 권장하지 않습니다.
- 확장기는 USB 2.0 이상 사양을 충족 해야 합니다.
  - 태블릿 도킹은 최소 두 단계의 외부 USB 허브 확장을 지원합니다. 연속적으로 두개 이상의 USB 허브를 연결하는 경우 도킹 제조사에 확인하여 시리즈 연결을 지원하는지 확인하세요.
  - 룸에 유선 GbE 연결. 충분한 길이의 이더넷 케이블.
  - 최대 2 1080-p의 HDMI 연결 가능한 디스플레이. 충분한 길이의 HDMI 케이블.

> [!NOTE]
> 룸 전면에 사용되는 소비자의 TV는 대기 모드에서 자동으로 활성 비디오 소스로 전환 될 수 있도록 HDMI의 CEC(Consumer Consumer Control) 기능을 지원/설정 해야 합니다. 이 기능은 모든 TV에서 지원 되지 않습니다.
>
> Microsoft Teams 룸에서는 키보드를 사용 하지 않습니다. 필요시 관리자는 스크린 키보드를 사용해야 합니다. Microsoft Teams 룸 장치를 이미징 하는 경우에는 USB 키보드 또는 마우스가 필요 합니다.

룸 크기에 따라 다음 테이블에 보여지는 주변기기가 권장됩니다.

**Microsoft Teams 룸 인증 오디오 주변기기**

|룸 종류|사용자 수|마이크에서 스피커 최대거리 권장사항|최대 룸 사이즈에 따른 장치|설명|
|:-----|:-----|:-----|:-----|:-----|
|**포커스** <br/> 10' x 9'   |2–4  |1.5 m  |Logitech 연결  |Logitech 연결 장치는 로컬 회의 참석자를 캡처하기 위해 룸의 앞(테이블 중앙이 아닌)에 위치 되어야 하는 카메라를 포합합니다. |
|**소형** <br/> 16' x 16'  |4–6  |2.0 m  |Jabra 510 <br/> Sennheiser SP20  |대규모 룸의 경우 재생 볼륨이 제한 될 수 있습니다.  |
|**중형** <br/> 18' x 20'  |6–12  |2.4 m  |Jabra 710 <br/> Jabra 810 <br/> Logitech MeetUp <br/> Logitech Group <br/> Polycom Trio <br/> Polycom CX5100 <br/> Sennheiser SP 220 MS <br/> Yamaha YVC-1000MS  |Logitech MeetUp은 룸의 앞(로컬 회의 참석자를 캡처하기 위해 테이블 중앙이 아닌)에 위치 되어야 하는 카메라를 포합합니다. <br/> 일반적으로, 긴 직사각형이 나 U자형 테이블이 있는 룸에서는 위성 마이크가 도움이 될 수 있습니다. <br/> 연속 체인 구성에는 SP 220 MS를 사용해야 합니다.  |
|**대형** <br/> 15' x 32'  |12–16  |3 m <br/> 이 거리는 각 위성 마이크가 연결되는 영역에도 동일하게 적용됩니다.  |Logitech Group + 위성 마이크 <br/> Polycom Trio+ 위성 마이크 <br/> Polycom CX5100 + 위성 마이크 <br/> Sennheiser SP 220 MS <br/> Yamaha YVC-1000MS + 위성 마이크  |이 행에 나열된 모든 오디오 장치는 위성 마이크 옵션을 지원합니다. <br/> CX5100은 빌트인 된 360도 카메라를 포함하므로 장치가 테이블 중앙에 위치할 수 있습니다.  <br/> 연속 체인 구성에는 SP 220 MS를 사용해야 합니다.  |

**Microsoft Teams 룸 인증 비디오 기기장치**

|룸 종류|사용자 수|최적의 룸 크기에 따른 장치|설명|
|:-----|:-----|:-----|:-----|
|**포커스** <br/> 10' x 9'  |2–4  |Logitech 연결 <br/> Logitech MeetUp <br/> Polycom CX5100  ||
|**소형** <br/> 16' x 16'  |4–6  |Logitech C930e <br/> Logitech MeetUp <br/> Logitech BRIO <br/> Logitech PTZ Pro <br/> Polycom MSR <br/> Polycom CX5100  |Logitech PTZ Pro는 종종 Logitech Group과 함께 제공  |
|**중형** <br/> 18' x 20'  |6–12  |Logitech MeetUp <br/> Logitech BRIO <br/> Logitech PTZ Pro <br/> Polycom MSR <br/> Polycom CX5100  ||
|**대형** <br/> 15' x 32'  |12–16  |Logitech PTZ Pro <br/> Polycom MSR <br/> Polycom CX5100  ||

 > [!NOTE]
 > 룸 화면 표시 해상도는 1920x1080p 보다 크지 않도록 설정 해야 합니다.

## <a name="required-software-downloads"></a>필수 소프트웨어 다운로드

Microsoft Teams 룸 이미지를 직접 작성 하려면 [Microsoft Teams 룸 콘솔을](console.md) 구성 하는 지침을 따르세요. 설치에 필요한 모든 소프트웨어를 다운로드하는 방법을 안내합니다.

> [!NOTE]
> IT 전문가는 볼륨 라이선싱 계약을 통해 Windows 10 Enterprise ISO 파일에 액세스 해야 합니다.

[SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105)는 Microsoft Teams 룸 계정 프로비전에 사용 가능한 선택적 다운로드 항목 입니다.

## <a name="see-also"></a>참고 항목

[모든 번들 찾아보기](https://products.office.com/microsoft-teams/across-devices/devices)

[Microsoft Teams 룸 계획](rooms-plan.md)

[Microsoft Teams 룸 배포](rooms-deploy.md)

[Microsoft Teams 룸 콘솔 구성](console.md)

[Microsoft Teams 룸 관리](rooms-manage.md)

[비즈니스용 Skype 추가 기능 라이선스](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)
