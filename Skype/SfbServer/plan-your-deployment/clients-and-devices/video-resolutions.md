---
title: 비즈니스용 Skype 클라이언트 비디오 해상도
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
description: '요약: 비즈니스용 Skype 서버를 계획 하는 동안 클라이언트 비디오 요구 사항을 검토 합니다.'
ms.openlocfilehash: 126c19d817a2cd656b7d581e0d467db80e4969e5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42027979"
---
# <a name="skype-for-business-client-video-resolutions"></a>비즈니스용 Skype 클라이언트 비디오 해상도
 
**요약:** 비즈니스용 Skype 서버를 계획 하는 동안 클라이언트 비디오 요구 사항을 검토 합니다.
  
이 문서에서는 비즈니스용 Skype 비디오 통화에 대 한 비디오 하드웨어 지원에 대해 설명 하 고 다양 한 컴퓨터, 태블릿 및 모바일 장치 구성에서 예상 되는 비디오 품질을 확인 하는 방법에 대해 설명 합니다. 
  
IT 전문가 들은이 정보를 통해 조직에서 이미 사용 중이거나 사용에 대 한 고려 사항을 평가할 때 유용 합니다. 또한 [솔루션 카탈로그](https://partnersolutions.skypeforbusiness.com/solutionscatalog) 에서 특정 장치에 대 한 정보를 검색할 수도 있습니다.
  
## <a name="windows-desktop-mac-and-tablet-video-requirements-and-capabilities"></a>Windows 데스크톱, Mac 및 태블릿 비디오 요구 사항 및 기능

비즈니스용 Skype는 10kb/MPEG-2 고급 비디오 코딩 표준을 기반으로 비디오 인코딩 및 디코딩을 위한 하드웨어 가속을 사용 합니다. 이렇게 하면 CPU 클럭 속도가 낮은 컴퓨터에서 더 높은 해상도 비디오를 인코딩하고 디코딩할 수 있습니다. 비디오 하드웨어 요구 사항은 컴퓨터 구성 및 원하는 비디오 해상도에 따라 다릅니다.
  
또한 [Windows 및 Mac 하드웨어 요구 사항을](https://products.office.com/office-system-requirements)참조 하세요.
  
### <a name="video-hardware-requirements"></a>비디오 하드웨어 요구 사항

|**기능**|**요구 사항**|
|:-----|:-----|
|DXVA(DirectX 비디오 가속 설정)를 사용한 하드웨어 가속 H.264 디코딩  <br/> |• 그래픽 카드는 DirectX 9.0를 지원 해야 하며, DXVA2_ModeH264_VLD_NoFGT 디코딩 모드와 DirectX 9 API를 노출 해야 합니다.  <br/> • 최신 그래픽 카드 드라이버를 설치 해야 합니다.  <br/> |
|하드웨어 가속 H.264 인코딩: 칩셋 요구 사항  <br/> |다음과 같은 인텔 하드웨어 가속 비디오 인코딩 솔루션이 지원 됩니다.  <br/> • 2 차 및 3 세대 Intel HD Graphics 2000, 2500, 3000 및 4000 칩셋 (이상 버전)이 통합 하드웨어 비디오 인코더와 함께 사용 됩니다. Intel HD Graphics driver 15.28.9.2884 또는 다음이 포함 된 최신 드라이버를 설치 해야 합니다.  <br/> • 디스플레이 드라이버 9.17.10.2884 또는 최신 드라이버  <br/> • 하드웨어 미디어 파운데이션 변환 (HMFT) 버전 3.12.10.31 또는 최신 HMFT  <br/> 다음 AMD 하드웨어 가속 비디오 인코딩 솔루션이 지원 됩니다.  <br/> • Amd A 시리즈 가속 프로세서와 함께 다양 한 개별 그래픽 카드 및 통합 가속 처리 단위에서 사용할 수 있습니다. AMD Video Codec Engine 드라이버 9.12.0.0 이상을 설치 해야 합니다.  <br/> |
|하드웨어 가속 H.264 인코딩: 카메라 요구 사항  <br/> |UVC(USB Video Class) 사양 버전 1.5를 준수하는 통합 H.264 하드웨어 인코더가 포함된 USB 비디오 카메라  <br/> **참고:** 비즈니스용 Skype는 Windows 8 또는 Windows 8.1의 UVC 1.5 카메라를 지원 하며, UVC 1.5에 대 한 지원을 포함 합니다. Windows 7에는 UVC 1.5에 대 한 지원이 포함 되지 않으므로 비즈니스용 Skype는 UVC 1.5 카메라를 하드웨어 인코딩이 지원 되지 않는 일반 카메라로 취급 합니다. <br/> |
   
### <a name="determining-h264-video-encoding-and-decoding-capabilities"></a>H-264 비디오 인코딩 및 디코딩 기능 확인

일반적으로 특정 컴퓨터 구성에 대한 최대 인코딩 및 디코딩 기능을 확인하는 데에는 4가지 기본 요소가 있습니다.
  
- DXVA를 사용하는 하드웨어 가속 디코딩에 대한 지원
    
- 하드웨어 가속 인코딩 지원
    
- 물리적 코어 수
    
- WEI(Windows 체험 지수)
    
WinSAT(Windows 시스템 평가 도구)는 WEI를 확인합니다. WinSAT 도구를 실행하면 컴퓨터의 %windir%\Performance\WinSAT\DataStore 디렉터리에 Formal.Assessment XML 문서가 생성됩니다. 이 XML 파일에는 인코딩 및 디코딩 기능을 확인하는 데 특히 중요한 다음 두 가지 점수가 포함됩니다.
  
- VideoEncodeScore는 컴퓨터의 소프트웨어 기반 비디오 인코딩 기능을 나타냅니다.
    
- GraphicsScore 값은 컴퓨터의 하드웨어 가속 인코딩 기능을 나타냅니다.
    
다음 3개의 테이블에서는 지원하는 하드웨어 가속에 따라 서로 다른 PC 유형에 대한 최대 인코딩 및 디코딩 기능을 설명합니다. 640x360 이상 해상도의 경우 지원되는 최대 프레임 속도는 30fps(초당 프레임 수)입니다. 640x360 미만 해상도의 경우 지원되는 최대 프레임 속도는 15fps입니다.
  
**DXVA 및 하드웨어 가속 인코더가 없는 컴퓨터**

|**지원 가능한 인코더 해상도**|**지원 가능한 디코더 해상도**|**요구 사항**|
|:-----|:-----|:-----|
|424x240  <br/> |424x240(수신 전용 시나리오의 경우 15fps에서 640x360)  <br/> |1개 코어 및 VideoEncodeScore ≥ 4.0  <br/> |
|640x360  <br/> |640x360  <br/> |2개 코어 및 VideoEncodeScore ≥ 4.5  <br/> |
|640x360  <br/> |해상도 1280x720  <br/> |2개 코어 및 VideoEncodeScore ≥ 4.5  <br/> |
|640x360  <br/> |해상도 1920x1080  <br/> |4개 코어 및 VideoEncodeScore ≥ 4.5  <br/> |
|해상도 1280x720  <br/> |해상도 1280x720  <br/> |4개 코어 및 VideoEncodeScore ≥ 7.3  <br/> |
|해상도 1280x720  <br/> |해상도 1920x1080  <br/> |4개 코어 및 VideoEncodeScore ≥ 7.3  <br/> |
|해상도 1920x1080  <br/> |해상도 1920x1080  <br/> |해당 없음  <br/> |
   
**DXVA가 있지만 하드웨어 가속 인코더가 없는 컴퓨터**

|**지원 가능한 인코더 해상도**|**지원 가능한 디코더 해상도**|**요구 사항**|
|:-----|:-----|:-----|
|424x240  <br/> |해상도 1920x1080  <br/> |1개 코어 및 VideoEncodeScore ≥ 3.0  <br/> |
|640x360  <br/> |해상도 1920x1080  <br/> |2개 코어 및 VideoEncodeScore ≥ 4.5  <br/> |
|960x540  <br/> |해상도 1920x1080  <br/> |2개 코어 및 VideoEncodeScore ≥ 6.0  <br/> |
|해상도 1280x720  <br/> |해상도 1920x1080  <br/> |4개 코어 및 VideoEncodeScore ≥ 6.7  <br/> |
|해상도 1920x1080  <br/> |해상도 1920x1080  <br/> |4개 코어 및 VideoEncodeScore ≥ 8.2  <br/> |
   
> [!NOTE]
> Windows 7에서 WinSAT 점수는 최대 7.9로 제한됩니다. 따라서 하드웨어 가속 인코더가 없는 컴퓨터의 인코딩 기능은 최대 WinSAT 점수가 9.9 인 Windows 8 또는 Windows 8.1 에서만 구현할 수 있습니다. 
  
**DXVA 및 Intel HD Graphics 하드웨어 가속 인코더가 있는 컴퓨터**

|**지원 가능한 인코더 해상도**|**지원 가능한 디코더 해상도**|**요구 사항**|
|:-----|:-----|:-----|
|해상도 1280x720  <br/> |해상도 1920x1080  <br/> |모든 2세대 및 3세대 Intel HD Graphics  <br/> |
|해상도 1920x1080  <br/> |해상도 1920x1080  <br/> |2세대 및 3세대 Intel HD Graphics 및 GraphicsScore ≥ 5.0  <br/> |
   
## <a name="mobile-device-video-capabilities"></a>모바일 장치 비디오 기능

다음 표에는 지원 되는 모바일 장치에서 사용할 수 있는 최대 비디오 해상도에 대 한 설명이 나와 있습니다. 모바일 장치 지원에 대 한 자세한 내용은 [비즈니스용 Skype의 모바일 클라이언트 기능 비교](mobile-feature-comparison.md)를 통해 설명 합니다.
  
|**기능**|**Windows Phone**|**iPhone**|**용**|**Android**|
|:-----|:-----|:-----|:-----|:-----|
|H-264 인코딩 최대 해상도  <br/> |비디오  <br/> |QVGA: iPhone 4S  <br/> VGA: iPhone 5  <br/> 720p: iPhone 5S 이상  <br/> |VGA: iPad 2 이상/이후/iPad 미니 1 이상  <br/> 720p: iPad Air/iPad 미니 2/iPad 이상  <br/> |장치 모델에 따라 최대 VGA  <br/> |
|H-264 디코딩 최대 해상도  <br/> |비디오  <br/> |QVGA: iPhone 4S  <br/> VGA: iPhone 5  <br/> 720p: iPhone 5S 이상  <br/> |VGA: iPad 2 이상/이후/iPad 미니 1 이상  <br/> 720p: iPad Air/iPad 미니 2/iPad 이상  <br/> |장치 모델에 따라 최대 VGA  <br/> |
   

