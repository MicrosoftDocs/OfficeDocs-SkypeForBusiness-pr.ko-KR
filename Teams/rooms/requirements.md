---
title: Microsoft Teams 룸 요구사항
ms.author: v-lanac
author: lanachin
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
description: 적절 한 장치, 마이크, 스피커, 카메라, 디스플레이를 비롯 하 여 Microsoft 팀 대화방을 지 원하는 데 필요한 요구 사항에 대해 알아봅니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fbfad5deba6288736beea0ef69660426975bb6fa
ms.sourcegitcommit: 184f4f61a3e739a1cfa533c6d95d405d887ea25d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "44591308"
---
# <a name="microsoft-teams-rooms-requirements"></a>Microsoft Teams 룸 요구사항

Microsoft Teams 룸은 다양한 인증 오디오 및 비디오 주변기기를 사용하여 룸 크기와 용도에 따라 크기를 다르게 조정합니다. 공간에 맞는 마이크, 스피커, 카메라 및 디스플레이 장치와 함께 올바른 핵심 장치와 콘솔을 선택하면 Microsoft Teams 룸을 아주 작은 규모의 공간에서부터 매우 큰 컨퍼런스 공간이나 보드룸 같은 장소에까지 배포할 수 있습니다.  룸을 구성 하는데 사용할 수 있는 모든 사용 가능한 인증 오디오 및 비디오 주변 장치는 [장치 보기](https://products.office.com/microsoft-teams/across-devices)에서 볼 수 있습니다.

이 문서는 Microsoft Teams 룸을 지원하는데 필요한 장치 배포 및 구성 요구 사항을 간략하게 설명합니다.

배포를 위해서는 [Microsoft Teams 룸 배포에](rooms-deploy.md) 설명되어 있는 대로 계정을 생성해야 하며 [Microsoft Teams 룸 콘솔 구성에](console.md) 설명되어 있는 대로 룸 콘솔을 설정하세요.

그리고 다음을 참고하세요.

- [비즈니스용 Skype 추가 기능 라이선스](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)
- [계획에 따른 라이선스 옵션: Microsoft Teams 룸](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2)

> [!NOTE]
> Microsoft Teams 룸 로그인은 Microsoft Teams, 비즈니스용 Skype 서버 2019, 비즈니스용 Skype 서버 2015 혹은 비즈니스 온라인용 Skype에서 사용되며 다른 서비스에서 호스트하는 모임에 참가할 수 있습니다. 
>
> Lync Server 2013 같은 이전 플랫폼은 Microsoft Teams 룸에서 지원하지 않습니다. Microsoft Teams 룸은 21Vianet, GCC-High 혹은 DoD 환경에서 운영되는 Microsoft 365에서 지원되지 않습니다.
>
> 온프레미스 Exchange 서버를 사용하는 경우 Microsoft Teams 룸에서 Exchange Server 2013 SP1이나 이후 버전을 사용해야 합니다.

## <a name="hardware-requirements"></a>하드웨어 요구 사항
하드웨어 배포에는 인증 오디오 및 비디오 주변기기와 통합된 Microsoft Teams 룸 시스템 선택지와 이 장치를 모두 통합하는 케이블 솔루션을 포함합니다.  여기에서 사용 가능한 옵션에 대해 설명합니다.

**지원 되는 Microsoft Teams 룸 시스템**

모든 현재 Microsoft Teams 룸 장치 및 번들은 [룸 시스템 제품 보기](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=20&page=1&filterIds=)에서 확인 할 수 있습니다.

  |콘솔|프로세서|RAM|디스크|
  |:-----|:-----|:-----|:-----|
  |[Crestron Flex UC-M130-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M130-T)|Core i5|8GB |128GB |
  |[Crestron Flex UC- B130-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B130-T)|Core i5|8GB |128GB |
  |[Crestron Flex UC-B140-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B140-T)|Core i5|8GB |128GB |
  |[Crestron Flex UC-M150-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M150-T) + [CCS-UCA-MIC](https://www.crestron.com/en-US/Products/Audio/Microphones/Wired-Microphones/CCS-UCA-MIC-KIT)|Core i7|8GB |128GB |
  [Crestron Flex UC-B160-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B160-T)|Core i7|8GB |128GB|
  |[Crestron Flex UC-C160-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C160-T)|Core i7|8GB|128GB|
  |[회의실 G2 용 HP Elite Slice](https://www8.hp.com/us/en/elite-family/elite-slice-for-meetings.html) |Core i5 |8GB |128GB |
  |[ Microsoft Teams 룸과 HP Elite Slice G2 오디오 준비](https://store.hp.com/us/en/pdp/hp-elite-slice-for-meeting-rooms-g2-skype-room-systems-audio-ready?jumpid=cp_r12131_us/en/psg/elite_slice_for_meetings/product/shop-now-eliteslicemeeting-g2-audio) |Core i5 |8GB |128GB |
  |[Lenovo ThinkSmart Hub 500](https://www3.lenovo.com/us/en/hub500) |Core i5 |8GB |128GB |
  |[Logitech 탭](https://www.logitech.com/product/microsoft-rooms)|Core i5|8GB |128GB |
  |[Logitech 탭핑 및 Lenovo 생각 센터 M920 작음](https://www.logitech.com/en-us/video-collaboration/partners/lenovo.html)|Core i5|8GB |128GB|
  |[Yealink MVC800](https://www.yealink.com/products_125.html)|Core i5|8GB|128GB|
  |[Yealink MVC500](https://www.yealink.com/products_126.html)|Core i5|8GB |128GB |
  |[Yealink MVC300](https://www.yealink.com/products_154.html)|Core i5|8GB |128GB |
  |[Yealink MVC900](https://www.yealink.com/product/microsoft-teams-room-system-mvc900)|Core i5|8GB|128GB|
  ||||||

> [!NOTE]
> - Core M3 프로세서는 지원되지 않습니다. 
> - Windows 10 Enterprise 용 부트 가능한 Windows 설치 미디어 구성을 위해 32GB 이상의 USB 드라이브가 필요합니다.

**도킹 스타일 시스템용 Surface Pro 태블릿 지원**

  |태블릿|프로세서|RAM|디스크|
  |:-----|:-----|:-----|:-----|
  |Surface Pro 6| Core i5 |16 GB 혹은 8 GB |128GB 이상 |
  |Surface Pro </br>(5G) |Core i5 |8 GB 혹은 4 GB |128GB 이상 |
  |Surface Pro 4 |Core i5 |8 GB 혹은 4 GB |128GB 이상 |

- Surface Pro 장치에는 다음 도킹 스테이션 옵션 중 하나가 필요 합니다.

  - [Logitech SmartDock](https://www.logitech.com/product/smartdock)
  - [Crestron SR](https://www.crestron.com/products/line/sr-for-skype-for-business-room-system )
  - [Polycom MSR Series](https://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.html)

### <a name="certified-firmware-versions-for-usb-audio-and-video-peripherals"></a>USB 오디오 및 비디오 주변 기기와 인증된 펌웨어 버전

이러한 장치는 [룸 시스템 액세서리 제품 소개](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73&page=1&filterIds=) 및 [https://office.com/teamsdevices](https://office.com/teamsdevices)에서 확인할 수 있습니다.

|Microsoft Teams 룸 주변기기|인증된 펌웨어 버전 | 카메라는 콘텐츠 카메라 사용을 지원 합니다.|
|:--- |:--- | :--- |
|[Crestron Huddly IQ](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Accessories/CCS-CAM-USB-F-400)   | 1.02.09.33901  |  |
|[Huddly IQ](https://www.huddly.com/conference-cameras/iq/) |1.3.22|
|[Jabra Panacast 카메라](https://www.jabra.com/business/video-conferencing/jabra-panacast)|3.8.22|
|[Logitech Brio](https://www.logitech.com/product/brio)   |V2.2.50| &#x2714; |
|[Logitech 930e](https://www.logitech.com/product/c930e-webcam)   | 8.0.914   | &#x2714; |
|[Logitech Rally](https://www.logitech.com/product/rally-ultra-hd-conferencecam)   |1.2.4 |
|[Logitech MeetUp](https://www.logitech.com/product/meetup-conferencecam)   |오디오 — 1.0.172 <br/> 비디오 — 1.0.156  |
|[Logitech ConferenceCam 연결](https://www.logitech.com/product/conferencecam-connect)   |1.1.248.0 <br/> 1.1.684   |
|[Logitech Group](https://www.logitech.com/product/conferencecam-group)   |8.5.778   |
|[Logitech PTZ Pro](https://www.logitech.com/product/conferencecam-ptz-pro)   | 1.1.219   |
|[Logitech PTZ Pro 2](https://www.logitech.com/product/conferencecam-ptz-pro2)   |
|[Poly Eagle Eye Cube 카메라](https://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.html)  |1.2.0 |
|[Polycom EagleEye IV](https://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.mdl)   |1.0.0   |
|[Polycom CX5100](https://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.mdl)   | 1.2.0.70232   |
|[Polycom Eagle Eye Director II](https://www.polycom.com/hd-video-conferencing/peripherals/eagleeye-director-ii.html)|2.1.0.10|
|[Polycom Studio Soundbar](https://www.polycom.com/hd-video-conferencing/room-video-systems/polycom-studio.html)|1.1.2.000570|
|[Polycom Trio 8500 / 8800](https://www.polycom.com/voice-conferencing-solutions/conference-phones/trio.html)   |5.7.2.3205|
|[Sennheiser SP 220 MS](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc)   |2.0.12.0   |
|[Sennheiser SP20](http://en-us.sennheiser.com/sp-20-og-sp-20-ml)   |1.2.15   |
|[Sennheiser SP30](https://en-us.sennheiser.com/sp-30)   |2.1.52  |
|[Sennheiser SP30T](https://en-us.sennheiser.com/sp-30)  |3.2.63  |
|[Jabra 510](http://www.jabra.com/support/Jabra-SPEAK&trade;-510_7510-209)   |2.10.0   |
|[Jabra 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710)   |1.8.0   |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810)   |1.2.23   |
|[Yamaha YVC-1000](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/)   |100c   |
|[Yealink CP900](https://www.yealink.com/products_150.html) |100.20.0.29 |
|[Shure Intellimix P300 오디오 회의 프로세서](https://www.shure.com/en-US/products/mixers/p300)+</br></br> [Shure MXA 310 표 배열 마이크 ](https://www.shure.com/en-US/products/microphones/mxa310) | 4.1 |
|[Shure Intellimix P300 오디오 회의 프로세서](https://www.shure.com/en-US/products/mixers/p300) + </br></br> [Shshmxa 910 Intellimix 천장 배열 마이크](https://www.shure.com/en-US/products/microphones/mxa910) | 4.1|
|[Biamp Tesira Fore AVB VT4 고정 오디오 DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ &Dagger;</br></br> [Sennheiser TeamConnect 천장 2 마이크](https://en-us.sennheiser.com/tcc2)+ &Dagger;</br></br> [Tesira EX-UBT](https://www.biamp.com/products/tesira/tesira-expanders) &Dagger; |  Biamp DSP: 3.12.0.15  </br></br> TCC2: 1.3.3 </br></br> EX-UBT: 3.12.0.15 |
|[Bose ControlSpace EX-440C DSP + </br>Bose P2600A AmpLink 증폭기 +</br> Sennheiser TCC2 천장 마이크 + </br> Bose EdgeMax EM180 천장 스피커](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html)|  Bose DSP: 2.290  </br> P2600A : 1.160  </br> TCC2: 1.4.2  |  |
||||||

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
