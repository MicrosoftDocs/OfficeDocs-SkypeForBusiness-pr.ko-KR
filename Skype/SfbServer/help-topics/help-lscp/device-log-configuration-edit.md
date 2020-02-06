---
title: 장치 로그 구성 편집
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientDeviceUpdateEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e534e6a5-fb3e-40b1-a189-fce64c42f512
description: 최대 로그 캐시 크기, 최대 로그 파일 크기 또는 로그 파일을 제거 하기 전에 보관 되는 시간을 결정 하는 로그 설정 편집 페이지에 장치 로그 구성을 추가할 수 있습니다. 조직의 요구 사항에 따라 이러한 설정을 변경할 수 있습니다.
ms.openlocfilehash: 3ea368c0f3bccd7655d1bca3cb93a98a86b99c47
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822911"
---
# <a name="device-log-configuration-edit"></a>장치 로그 구성: 편집
 
최대 로그 캐시 크기, 최대 로그 파일 크기 또는 로그 파일을 제거 하기 전에 보관 되는 시간을 결정 하는 **로그 설정 편집** 페이지에 장치 로그 구성을 추가할 수 있습니다. 조직의 요구 사항에 따라 이러한 설정을 변경할 수 있습니다.
  
> [!CAUTION]
> 파일을 삭제하면 파일 시스템에서 영구 제거됩니다. 따라서 파일을 삭제한 후 복구할 수 없습니다. 
  
## <a name="tasks-you-can-perform"></a>수행할 수 있는 작업

**로그 설정 편집** 페이지에서 다음 작업을 수행할 수 있습니다.
  
- 전역 또는 특정 사이트에 대 한 디바이스 로그 구성을 추가 합니다.
    
- 기존 장치 로그 구성에 대한 옵션 수정
    
## <a name="ui-reference"></a>UI 참조

다음 목록에서는 페이지의 메뉴, 명령, 필드, 속성에 대해 설명합니다.
  
- **범위** 장치 로그 구성의 범위 (전역 또는 사이트)를 식별 합니다.
    
- **이름** 장치 로그 구성의 이름을 추가 하거나 수정할 수 있습니다.
    
- **최대 파일 크기 (바이트)** 로그 파일을 제거 하기 전에 사용할 수 있는 최대 크기를 지정할 수 있습니다. 기본값은 1024000 바이트 (1 MB)입니다.
    
- **최대 캐시 크기 (바이트)** 캐시를 삭제 하 고 데이터를 로그 파일에 기록 하기 전에 로그 파일 캐시에 보유할 수 있는 최대 정보 양 (바이트)을 지정할 수 있습니다. 기본값은 512000 바이트 (0.5 MB)입니다.
    
- **캐시 플러시 시간 (분) (1-60)** 로그 파일 캐시에 저장 되는 정보가 실제 로그 파일에 기록 되는 빈도를 지정할 수 있습니다. 데이터가 기록 된 후 캐시가 지워집니다. 기본값은 5 분입니다.
    
- **로그 파일 유지 일 수 (1-365)** 로그 파일을 삭제 하기 전에 보관 하는 일 수를 지정할 수 있습니다. 기본값은 10 일입니다.
    
## <a name="see-also"></a>참고 항목

[장치 로그 구성](device-log-configuration.md)
