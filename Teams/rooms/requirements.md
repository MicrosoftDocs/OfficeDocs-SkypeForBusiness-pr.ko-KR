---
title: Microsoft 팀 방에 대 한 요구 사항
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
description: 이 문서에서는 Microsoft 팀 대화방을 지원 하기 위한 요구 사항을 요약 하 여 설명 합니다.
ms.openlocfilehash: 2496fcb1af7d85a3d1c3ba755a2431aff40d5a70
ms.sourcegitcommit: df4dde0fe6ce9e26cb4b3da4e4b878538d31decc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/15/2020
ms.locfileid: "43521604"
---
# <a name="microsoft-teams-rooms-requirements"></a>Microsoft 팀 방에 대 한 요구 사항

Microsoft 팀 객실은 공간의 크기와 사용에 따라 다양 한 인증 된 오디오 및 비디오 주변 장치를 사용 하 여 다양 한 공간으로 크기를 조정할 수 있습니다. 적절 한 핵심 장치 및 콘솔을 마이크, 스피커, 카메라, 공간에 적합 한 표시와 함께 선택 하면 매우 큰 전화 공간 및 huddle 공간을 차지 하는 매우 작은 크기의 공간에 Microsoft 팀 대화방을 배포할 수 있습니다.  [장치 전시](https://products.office.com/microsoft-teams/across-devices)에서 회의실을 구성 하는 데 사용할 수 있는 모든 인증 된 오디오 및 비디오 주변 기기의 전체 집합을 사용할 수 있습니다.

이 문서에는 Microsoft 팀 대화방을 지원 하기 위한 장치 배포 및 구성 요구 사항이 요약 되어 있습니다.

배포에는 microsoft 팀 [대화방 배포](rooms-deploy.md) 에 설명 된 대로 계정 만들기와 [microsoft 팀 대화방 콘솔 구성](console.md)에 설명 된 대로 모임 콘솔 설정이 포함 됩니다.

또한 다음을 참조 하세요.

- [비즈니스용 Skype 추가 기능 라이선스](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)
- [요금제를 기반으로 하는 라이선스 옵션: Microsoft 팀 대화방](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2)

> [!NOTE]
> Microsoft 팀 대화방은 Microsoft 팀, 비즈니스용 Skype 서버 2019, 비즈니스용 skype Server 2015 또는 비즈니스용 Skype Online에 로그인 하 고 이러한 서비스에서 호스트 하는 모임에 참가할 수 있습니다.
>
> Lync Server 2013 같은 이전 플랫폼은 Microsoft 팀 대화방에서 지원 되지 않습니다. Microsoft 팀 대화방은 21Vianet에서 운영 하는 Office 365에서 지원 되지 않습니다. 또는 GCC 높음이나 이상 또는 DoD 환경
>
> 프레미스 Exchange server가 있는 경우 Microsoft 팀 대화방에서 Exchange Server 2013 SP1 이상을 사용 해야 합니다.

## <a name="hardware-requirements"></a>하드웨어 요구 사항
하드웨어 배포에는 인증 된 오디오 및 비디오 주변 장치, 그리고 이러한 장치를 함께 통합 하는 케이블링 솔루션 등의 Microsoft 팀 실내 시스템 선택이 포함 됩니다.  이러한 옵션에 대 한 설명은 다음과 같습니다.

**지원 되는 Microsoft 팀 대화방 시스템**

현재 Microsoft 팀의 모든 회의실 장치 및 번들은 [실내 시스템 제품 전시](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=20&page=1&filterIds=)에서 사용할 수 있습니다.

  |콘솔|프로세서|할당할|공간|
  |:-----|:-----|:-----|:-----|
  |[Flex UC에서 crestron M130-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M130-T)|Core i5|8gb |128 GB |
  |[Flex UC에서 crestron B130-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B130-T)|Core i5|8gb |128 GB |
  |[Flex UC에서 crestron B140-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B140-T)|Core i5|8gb |128 GB |
  |[Flex 통합에서 crestron-M150-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M150-T) + [CCS-마이크](https://www.crestron.com/en-US/Products/Audio/Microphones/Wired-Microphones/CCS-UCA-MIC-KIT)|코어 i7|8gb |128 GB |
  [Flex UC에서 crestron B160-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B160-T)|코어 i7|8gb |128 GB|
  |[Flex UC에서 crestron C160-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C160-T)|코어 i7|8gb|128 GB|
  |[회의실 G2 용 HP 정예 슬라이스](https://www8.hp.com/us/en/elite-family/elite-slice-for-meetings.html) |Core i5 |8gb |128 GB |
  |[Microsoft 팀 대화방으로 준비 된 HP 정예 슬라이스 G2 오디오](https://store.hp.com/us/en/pdp/hp-elite-slice-for-meeting-rooms-g2-skype-room-systems-audio-ready?jumpid=cp_r12131_us/en/psg/elite_slice_for_meetings/product/shop-now-eliteslicemeeting-g2-audio) |Core i5 |8gb |128 GB |
  |[Lenovo ThinkSmart Hub 500](https://www3.lenovo.com/us/en/hub500) |Core i5 |8gb |128 GB |
  |[Logitech 탭 하기](https://www.logitech.com/product/microsoft-rooms)|Core i5|8gb |128 GB |
  |[옛 alink MVC800](https://www.yealink.com/products_125.html)|Core i5|8gb|128 GB|
  |[옛 alink MVC500](https://www.yealink.com/products_126.html)|Core i5|8gb |128 GB |
  |[옛 alink MVC300](https://www.yealink.com/products_154.html)|Core i5|8gb |128 GB |
  |[옛 alink MVC900](https://www.yealink.com/product/microsoft-teams-room-system-mvc900)|Core i5|8gb|128 GB|
  ||||||

> [!NOTE]
> - 코어 M3 프로세서는 지원 되지 않습니다.
> - 32 GB 이상의 USB 드라이브가 Windows 10 Enterprise 용 부팅 가능 Windows 설치 미디어로 구성 되어 있어야 합니다.

**도킹 스타일 시스템에 지원 되는 Surface Pro 태블릿**

  |타블렛|프로세서|할당할|공간|
  |:-----|:-----|:-----|:-----|
  |Surface Pro 6| Core i5 |16gb 또는 8gb |128 GB 이상 |
  |Surface Pro </br>(다섯째 Gen) |Core i5 |8gb 또는 4gb |128 GB 이상 |
  |Surface Pro 4 |Core i5 |8gb 또는 4gb |128 GB 이상 |

- Surface Pro 장치에는 태블릿을 회의실 테이블로 보호 하기 위한 다음 도킹 스테이션 옵션 중 하나가 필요 합니다.

  - [Logitech SmartDock](https://www.logitech.com/product/smartdock)
  - [SR의 crestr](https://www.crestron.com/products/line/sr-for-skype-for-business-room-system )
  - [Polycom MSR 시리즈](https://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.html)

### <a name="certified-firmware-versions-for-usb-audio-and-video-peripherals"></a>USB 오디오 및 비디오 주변 장치에 대 한 인증 된 펌웨어 버전

이러한 장치는 [채팅방 시스템 액세서리 제품 소개](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73&page=1&filterIds=) 및 [https://office.com/teamsdevices](https://office.com/teamsdevices)에서 확인할 수 있습니다.

|Microsoft 팀 회의실 주변 기기|인증 된 펌웨어 버전 | 카메라가 콘텐츠 카메라 사용 지원|
|:--- |:--- | :--- |
|[Huddly IQ에서 crestron](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Accessories/CCS-CAM-USB-F-400)   | 1.02.09.33901  |  |
|[Logitech Brio](https://www.logitech.com/product/brio)   |V 2.2.50| &#x2714; |
|[Logitech 930e](https://www.logitech.com/product/c930e-webcam)   | 8.0.914   | &#x2714; |
|[Logitech 집결](https://www.logitech.com/product/rally-ultra-hd-conferencecam)   |1.2.4 |
|[Logitech 잔](https://www.logitech.com/product/meetup-conferencecam)   |오디오-1.0.172 <br/> 비디오-1.0.156  |
|[Logitech ConferenceCam Connect](https://www.logitech.com/product/conferencecam-connect)   |1.1.248.0 <br/> 1.1.684   |
|[Logitech 그룹](https://www.logitech.com/product/conferencecam-group)   |8.5.778   |
|[Logitech PT;Z Pro](https://www.logitech.com/product/conferencecam-ptz-pro)   | 1.1.219   |
|[Logitech PT;Z Pro 2](https://www.logitech.com/product/conferencecam-ptz-pro2)   |
|[Poly 독수리 눈 큐브 카메라](https://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.html)  |1.2.0 |
|[Polycom EagleEye IV](https://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.mdl)   |1.0.0   |
|[Polycom CX5100](https://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.mdl)   | 1.2.0.70232   |
|[Polycom 독수리 눈 디렉터 II](https://www.polycom.com/hd-video-conferencing/peripherals/eagleeye-director-ii.html)|2.1.0.10|
|[Polycom Studio 사운드바](https://www.polycom.com/hd-video-conferencing/room-video-systems/polycom-studio.html)|1.1.2.000570|
|[Polycom Trio 8500/8800](https://www.polycom.com/voice-conferencing-solutions/conference-phones/trio.html)   |5.7.2.3205|
|[Sennheiser SP 220 MS](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc)   |2.0.12.0   |
|[Sennheiser SP20](http://en-us.sennheiser.com/sp-20-og-sp-20-ml)   |1.2.15   |
|[Sennheiser SP30](https://en-us.sennheiser.com/sp-30)   |2.1.52  |
|[Sennheiser SP30T](https://en-us.sennheiser.com/sp-30)  |3.2.63  |
|[Jabra 510](http://www.jabra.com/support/Jabra-SPEAK™-510_7510-209)   |2.10.0   |
|[Jabra 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710)   |1.8.0   |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810)   |1.2.23   |
|[Yamaha YVC-1000](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/)   |100c   |
|[옛 alink CP900](https://www.yealink.com/products_150.html) |100.20.0.29 |
|[Shure P300 Audio 회의 프로세서](https://www.shure.com/en-US/products/mixers/p300)+</br></br> [Shmxa 310 표 배열 Mic](https://www.shure.com/en-US/products/microphones/mxa310) | 4.1 |
|[Shure P300 Audio 회의 프로세서](https://www.shure.com/en-US/products/mixers/p300) + </br></br> [Intellimix 천장 MXA 910 with Array Mic](https://www.shure.com/en-US/products/microphones/mxa910) | 4.1|
|[Biamp Tesira 전경 AVB VT4 고정 오디오 DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ &Dagger;</br></br> [Sennheiser TeamConnect 천장 2 마이크](https://en-us.sennheiser.com/tcc2)+ &Dagger;</br></br> [TESIRA EX-UBT](https://www.biamp.com/products/tesira/tesira-expanders)&Dagger; |  Biamp DSP: 3.12.0.15  </br></br> TCC2: 1.3.3 </br></br> EX-UBT: 3.12.0.15 |
|[Bose ControlSpace EX, 440C DSP + </br>BOSE P2600A AmpLink 증폭기 +</br> Sennheiser TCC2 천장 마이크 + </br> bose EdgeMax 천장 스피커](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html)|  Bose DSP: 2.290  </br> P2600A: 1.160  </br> TCC2: 1.4.2  |  |
||||||

&Dagger;고객은이 번들에 대해 Dante 인터페이스 또는 Biamp/Sennheiser에서 권장 하는 네트워크 스위치를 선택할 수 있습니다.

#### <a name="usb-extenders"></a>USB extender

- 태블릿 도크의 USB 포트는 USB 3.0 호환 가능 합니다. USB 2 .x extender를 사용할 수 있지만, 이렇게 하면 끝에 USB 2. x의 속도를 제한 하 게 됩니다. USB 3.0 주변 기기에는 extender를 사용할 수 없습니다.
- Extender는 USB 2.0 이상 사양을 충족 해야 합니다.
  - 태블릿 도크는 외부 USB 허브 확장의 두 단계 이상을 지원 합니다. 2 개 이상의 USB 허브를 시리즈에 연결 하는 경우, dock 제조업체에 문의 하 여 시리즈 연결 지원 여부를 확인 합니다.
  - 실내의 유선 GbE 연결. 적절 한 길이의 이더넷 케이블.
  - HDMI 연결에 최대 2 1080-p가 표시 됩니다. 적절 한 길이의 HDMI 케이블.

> [!NOTE]
> 공간 표시의 앞에 사용 되는 소비자 TV는 대기 모드에서 자동으로 활성 비디오 원본으로 전환할 수 있도록 HDMI의 CEC (소비자 전자 컨트롤) 기능을 지원/사용 하도록 설정 해야 합니다. 이 기능은 모든 Tv에서 지원 되지 않습니다.
>
> Microsoft 팀 대화방은 키보드를 사용 하지 않습니다. 필요한 경우 관리자는 화상 키보드를 사용 해야 합니다. Microsoft 팀 회의실 장치를 이미징 하는 경우에는 USB 키보드나 마우스가 필요 합니다.

다음 표에는 방 크기를 기준으로 한 주변 기기에 대 한 권장 사항이 나와 있습니다.

**Microsoft 팀 대화방 인증 오디오 주변 장치**

|방 종류|인원 수|마이크에서 스피커 까지의 권장 최대 거리|장치-최대 공간 크기|메모|
|:-----|:-----|:-----|:-----|:-----|
|**Focus** <br/> 10 ' x 9 '   |2-4  |1.5 m  |Logitech Connect  |Logitech Connect 장치에는 로컬 모임 참석자를 캡처하기 위해 공간 (표의 중심이 아님) 앞에 배치 해야 하는 카메라가 포함 됩니다. |
|**Small** <br/> 16 ' x 16 '  |4 – 6  |2.0 m  |Jabra 510 <br/> Sennheiser SP20  |대용량 회의실에 대해 재생 볼륨을 제한할 수 있습니다.  |
|**높음이나** <br/> 18 ' x 20 '  |6 – 12  |2.4 m  |Jabra 710 <br/> Jabra 810 <br/> Logitech 잔 <br/> Logitech 그룹 <br/> Polycom Trio <br/> Polycom CX5100 <br/> Sennheiser SP 220 MS <br/> Yamaha YVC-1000MS  |Logitech 잔에는 카메라가 포함 되어 있기 때문에 (지역 모임 참석자를 캡처하기 위해 표 중앙이 아님) 카메라를 배치 합니다. <br/> 일반적으로 위성 마이크 또는 u 자형 표를 사용 하는 채팅방의 방에는 큰 도움이 됩니다. <br/> S p 220 MS는 데이지 체인을 구성 하는 데 사용 해야 합니다.  |
|**용량의** <br/> 15 ' x 32 '  |12 – 16  |3 m <br/> 이 거리는 연결 된 각 위성 마이크에 포함 되는 영역에도 적용 됩니다.  |Logitech 그룹 + 위성 마이크 <br/> Polycom Trio + 위성 마이크 <br/> Polycom CX5100 + 위성 마이크 <br/> Sennheiser SP 220 MS <br/> Yamaha YVC-1000MS + 위성 마이크  |이 행에 나열 된 모든 오디오 장치는 위성 마이크 옵션을 지원 합니다. <br/> CX5100에는 디바이스를 표 중앙에 배치할 수 있도록 기본 제공 360도 카메라가 포함 되어 있습니다. <br/> S p 220 MS는 데이지 체인을 구성 하는 데 사용 해야 합니다.  |

**Microsoft 팀 대화방 인증 영상 주변 장치**

|방 종류|인원 수|장치-최적의 공간 크기|메모|
|:-----|:-----|:-----|:-----|
|**Focus** <br/> 10 ' x 9 '  |2-4  |Logitech Connect <br/> Logitech 잔 <br/> Polycom CX5100  ||
|**Small** <br/> 16 ' x 16 '  |4 – 6  |Logitech C930e <br/> Logitech 잔 <br/> Logitech BRIO <br/> Logitech PT;Z Pro <br/> Polycom MSR <br/> Polycom CX5100  |Logitech PTZ Pro가 Logitech 그룹과 함께 제공 되는 경우가 많습니다.  |
|**높음이나** <br/> 18 ' x 20 '  |6 – 12  |Logitech 잔 <br/> Logitech BRIO <br/> Logitech PT;Z Pro <br/> Polycom MSR <br/> Polycom CX5100  ||
|**용량의** <br/> 15 ' x 32 '  |12 – 16  |Logitech PT;Z Pro <br/> Polycom MSR <br/> Polycom CX5100  ||

 > [!NOTE]
 > 방 디스플레이 해상도의 앞면은 1920x1080p 보다 크지 않도록 설정 해야 합니다.

## <a name="required-software-downloads"></a>필수 소프트웨어 다운로드

자신의 Microsoft 팀 대화방 이미지를 작성 하려면 [Microsoft 팀 대화방 콘솔 구성](console.md)의 지침을 따릅니다. 이 지침에서는 설치에 필요한 모든 소프트웨어를 다운로드 하는 방법을 안내 합니다.

> [!NOTE]
> IT 전문가는 볼륨 라이선스 계약을 통해 Windows 10 Enterprise ISO 파일에 액세스 해야 합니다.

[SkypeRoomProvisioningScript](https://go.microsoft.com/fwlink/?linkid=870105) 는 Microsoft 팀 대화방 계정을 제공 하는 데 사용할 수 있는 선택적 다운로드입니다.

## <a name="see-also"></a>참고 항목

[모든 번들 찾아보기](https://products.office.com/microsoft-teams/across-devices/devices)

[Microsoft 팀 회의실 계획](rooms-plan.md)

[Microsoft 팀 대화방 배포](rooms-deploy.md)

[Microsoft 팀 대화방 콘솔 구성](console.md)

[Microsoft 팀 대화방 관리](rooms-manage.md)

[비즈니스용 Skype 추가 기능 라이선스](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)
