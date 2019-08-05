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
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
description: '요약: 비즈니스용 Skype 서버를 계획 하는 동안 클라이언트 영상 요구 사항을 검토 합니다.'
ms.openlocfilehash: 15fd424f7ad2e11d473e49e271c7fbf1db83b45c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187869"
---
# <a name="skype-for-business-client-video-resolutions"></a>비즈니스용 Skype 클라이언트 비디오 해상도
 
**요약:** 비즈니스용 Skype 서버를 계획 하는 동안 클라이언트 영상 요구 사항을 검토 합니다.
  
이 문서에서는 비즈니스용 Skype 비디오 통화에 대 한 비디오 하드웨어 지원에 대해 설명 하 고 다양 한 컴퓨터, 태블릿 및 모바일 장치 구성에 대해 예상 되는 비디오 품질을 확인 하는 방법에 대해 설명 합니다. 
  
IT 전문가는 조직에서 이미 사용 중이거나 사용 고려 사항에서 랩톱의 적합성을 평가 하는 데 유용한 정보를 찾을 수 있습니다. 또한 [솔루션 카탈로그](https://partnersolutions.skypeforbusiness.com/solutionscatalog) 에서 특정 장치에 대 한 정보를 검색할 수도 있습니다.
  
## <a name="windows-desktop-mac-and-tablet-video-requirements-and-capabilities"></a>Windows 데스크톱, Mac 및 태블릿 비디오 요구 사항 및 기능

비즈니스용 Skype는 비디오 인코딩 및 디코딩에 대 한 하드웨어 가속을 사용 하는데,이는 .H/MPEG-4, 10 부의 고급 비디오 코딩 표준에 기반을 둔 것입니다. 이렇게 하면 CPU 클럭 속도가 낮은 컴퓨터에서 더 높은 해상도의 인코딩 및 디코딩을 할 수 있습니다. 비디오 하드웨어 요구 사항은 컴퓨터 구성과 비디오 해상도에 따라 달라 집니다.
  
[Windows 및 Mac 하드웨어 요구](https://products.office.com/en-us/office-system-requirements)사항도 참조 하세요.
  
### <a name="video-hardware-requirements"></a>비디오 하드웨어 요구 사항

|**요소**|**요구 사항**|
|:-----|:-----|
|DirectX 비디오 가속 (DXVA)을 사용 하는 하드웨어 가속 H/264 디코딩  <br/> |• 그래픽 카드는 DirectX 9.0를 지원 해야 하며, DXVA2_ModeH264_VLD_NoFGT 디코딩 모드와 DirectX 9 API를 노출 해야 합니다.  <br/> • 최신 그래픽 카드 드라이버를 설치 해야 합니다.  <br/> |
|하드웨어 가속 H. 264 인코딩: 칩셋 요구 사항  <br/> |다음과 같은 Intel 하드웨어 가속 비디오 인코딩 솔루션이 지원 됩니다.  <br/> • 2 번째 및 3 세대 Intel HD 그래픽 2000, 2500, 3000, 4000 칩셋 (또는 이후 버전)이 통합 하드웨어 비디오 인코더를 사용 합니다. Intel HD 그래픽 드라이버 15.28.9.2884 설치 또는 다음을 포함 하는 최신 드라이버가 필요 합니다.  <br/> • 디스플레이 드라이버 9.17.10.2884 또는 최신 드라이버  <br/> • HMFT (하드웨어 media foundation transform) 버전 3.12.10.31 또는 최신 HMFT  <br/> 다음 AMD 하드웨어 가속 비디오 인코딩 솔루션이 지원 됩니다.  <br/> • Amd 시리즈 가속 프로세서의 통합 된 가속 처리 장치 및 여러 개의 개별 그래픽 카드에서 사용할 수 있는 AMD 비디오 코덱 엔진. AMD 비디오 코덱 엔진 드라이버 9.12.0.0 이상을 설치 해야 합니다.  <br/> |
|하드웨어 가속 H. 264 인코딩: 카메라 요구 사항  <br/> |UVC (USB Video Class) 사양 버전 1.5을 준수 하는 통합 된 H-264 하드웨어 인코더가 USB 비디오 카메라  <br/> **참고:** 비즈니스용 Skype는 Windows 8 또는 Windows 8.1에서 UVC 1.5에 대 한 지원을 포함 하는 UVC 1.5 카메라를 지원 합니다. Windows 7에는 UVC 1.5에 대 한 지원이 포함 되어 있지 않기 때문에 비즈니스용 Skype는 UVC 1.5 카메라를 하드웨어 인코딩 지원이 없는 일반 카메라로 취급 합니다. <br/> |
   
### <a name="determining-h264-video-encoding-and-decoding-capabilities"></a>H/264 비디오 인코딩 및 디코딩 기능 확인

일반적으로 특정 컴퓨터 구성의 최대 인코딩 및 디코딩 기능을 결정 하는 네 가지 주요 요인이 있습니다.
  
- DXVA를 사용 하 여 하드웨어 가속 디코딩 지원
    
- 하드웨어 가속 인코딩 지원
    
- 실제 코어 수
    
- WEI (Windows 체험 지 인덱스)
    
Windows 시스템 평가 도구 (WinSAT)는 WEI를 결정 합니다. WinSAT 도구를 실행 하면%windir%\Performance\WinSAT\DataStore 디렉터리의 컴퓨터에 공식적인 평가 XML 문서가 생성 됩니다. 이 XML 파일에는 인코딩 및 디코딩 기능을 결정 하는 데 특히 중요 한 다음 두 가지 점수가 포함 되어 있습니다.
  
- VideoEncodeScore는 컴퓨터의 소프트웨어 기반 비디오 인코딩 기능을 나타냅니다.
    
- GraphicsScore 값은 컴퓨터의 하드웨어 가속 인코딩 기능을 나타냅니다.
    
다음 세 가지 표에서는 지 원하는 하드웨어 가속에 따라 다양 한 PC 유형의 최대 인코딩 및 디코딩 기능에 대해 설명 합니다. 640x360 이상 해상도의 경우 지원 되는 최대 프레임 속도는 초당 30 프레임 (fps)입니다. 640x360 보다 낮은 해상도의 경우 지원 되는 최대 프레임 속도는 15fps입니다.
  
**DXVA 및 하드웨어 가속 인코더가 없는 컴퓨터**

|**사용할 수 있는 인코더 해상도**|**지원 되는 디코더 해상도**|**요구 사항**|
|:-----|:-----|:-----|
|424x240  <br/> |424x240 (640x360에만 해당 시나리오의 경우 15fps)  <br/> |1 코어 및 VideoEncodeScore ≥ 4.0  <br/> |
|640x360  <br/> |640x360  <br/> |2 코어 및 VideoEncodeScore ≥ 4.5  <br/> |
|640x360  <br/> |1280x720  <br/> |2 코어 및 VideoEncodeScore ≥ 4.5  <br/> |
|640x360  <br/> |1920x1080  <br/> |4 코어 및 VideoEncodeScore ≥ 4.5  <br/> |
|1280x720  <br/> |1280x720  <br/> |4 코어 및 VideoEncodeScore ≥ 7.3  <br/> |
|1280x720  <br/> |1920x1080  <br/> |4 코어 및 VideoEncodeScore ≥ 7.3  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |해당 없음  <br/> |
   
**DXVA 있지만 하드웨어 가속 인코더가 없는 컴퓨터**

|**사용할 수 있는 인코더 해상도**|**지원 되는 디코더 해상도**|**요구 사항**|
|:-----|:-----|:-----|
|424x240  <br/> |1920x1080  <br/> |1 코어 및 VideoEncodeScore ≥ 3.0  <br/> |
|640x360  <br/> |1920x1080  <br/> |2 코어 및 VideoEncodeScore ≥ 4.5  <br/> |
|960x540  <br/> |1920x1080  <br/> |2 코어 및 VideoEncodeScore ≥ 6.0  <br/> |
|1280x720  <br/> |1920x1080  <br/> |4 코어 및 VideoEncodeScore ≥ 6.7  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |4 코어 및 VideoEncodeScore ≥ 8.2  <br/> |
   
> [!NOTE]
> Windows 7의 WinSAT 점수는 최대 7.9으로 제한 됩니다. 따라서 하드웨어 가속 인코더가 없는 컴퓨터에 대 한 인코딩 접근 권한 값은 Windows 8 또는 Windows 8.1 에서만 가능 하며,이는 최대 WinSAT 점수가 9.9입니다. 
  
**DXVA 및 Intel HD 그래픽 하드웨어 가속 인코더를 사용 하는 컴퓨터**

|**사용할 수 있는 인코더 해상도**|**지원 되는 디코더 해상도**|**요구 사항**|
|:-----|:-----|:-----|
|1280x720  <br/> |1920x1080  <br/> |모든 2 차 및 3 세대 Intel HD 그래픽  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |2 차 및 3 세대 Intel HD 그래픽 및 GraphicsScore ≥ 5.0  <br/> |
   
## <a name="mobile-device-video-capabilities"></a>모바일 장치 영상 기능

다음 표에서는 지원 되는 모바일 장치에서 사용할 수 있는 최대 비디오 해상도에 대해 설명 합니다. 모바일 장치 지원에 대 한 자세한 내용은 [비즈니스용 Skype에 대 한 모바일 클라이언트 기능 비교](mobile-feature-comparison.md)를 추가 하세요.
  
|**요소**|**Windows Phone**|**iPhone**|**iPad**|**Android**|
|:-----|:-----|:-----|:-----|:-----|
|H-264 인코딩 최대 해상도  <br/> |비디오  <br/> |QVGA: iPhone 4S  <br/> VGA: iPhone 5  <br/> 720p: iPhone 5S 이상  <br/> |VGA: iPad 2 이상/이후/iPad 미니 1 이상  <br/> 720p: iPad Air/iPad 미니 2/iPad 이상  <br/> |장치 모델에 따라 최대 VGA까지  <br/> |
|H. 264 디코딩 최대 해상도  <br/> |비디오  <br/> |QVGA: iPhone 4S  <br/> VGA: iPhone 5  <br/> 720p: iPhone 5S 이상  <br/> |VGA: iPad 2 이상/이후/iPad 미니 1 이상  <br/> 720p: iPad Air/iPad 미니 2/iPad 이상  <br/> |장치 모델에 따라 최대 VGA까지  <br/> |
   

