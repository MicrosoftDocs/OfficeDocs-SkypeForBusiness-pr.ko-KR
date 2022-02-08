---
title: 장치 로그 구성 편집
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientDeviceUpdateEdit
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e534e6a5-fb3e-40b1-a189-fce64c42f512
description: 로그 캐시의 최대 크기, 최대 로그 파일 크기 또는 로그 파일이 삭제되기 전까지 보관되는 기간을 결정하는 로그 설정 편집 페이지에 장치 로그 구성을 추가할 수 있습니다. 조직의 요구 사항에 따라 이러한 설정을 변경할 수 있습니다.
ms.openlocfilehash: a8d1ac8d85fa08461c8f43688e874371e6cb4f60
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62386806"
---
# <a name="device-log-configuration-edit"></a>장치 로그 구성: 편집
 
로그 캐시의 최대 크기, 최대 로그 파일  크기 또는 로그 파일이 삭제되기 전까지 보관되는 기간을 결정하는 로그 설정 편집 페이지에 장치 로그 구성을 추가할 수 있습니다. 조직의 요구 사항에 따라 이러한 설정을 변경할 수 있습니다.
  
> [!CAUTION]
> 파일을 삭제하면 파일 시스템에서 영구 제거됩니다. 따라서 파일을 삭제한 후 복구할 수 없습니다. 
  
## <a name="tasks-you-can-perform"></a>수행할 수 있는 작업

로그 설정 편집 페이지에서는 **다음 작업을 수행할 수** 있습니다.
  
- 장치 로그 구성을 전역적으로 또는 특정 사이트에 추가합니다.
    
- 기존 장치 로그 구성에 대한 옵션 수정
    
## <a name="ui-reference"></a>UI 참조

다음 목록에서는 페이지의 메뉴, 명령, 필드 및 속성에 대해 설명합니다.
  
- **범위** 장치 로그 구성의 범위(전역 또는 사이트)를 식별합니다.
    
- **이름** 장치 로그 구성의 이름을 추가하거나 수정할 수 있습니다.
    
- **최대 파일 크기(bytes)** 로그 파일을 제거하기 전에 커질 수 있는 최대 크기를 지정할 수 있습니다. 기본값은 1,024,000 bytes(1MB)입니다.
    
- **최대 캐시 크기(bytes)** 해당 캐시를 지우고 데이터가 로그 파일에 기록되기 전에 로그 파일 캐시에 저장될 수 있는 최대 정보 양(bytes)을 지정할 수 있습니다. 기본값은 512,000 bytes(0.5MB)입니다.
    
- **캐시 플러시 시간(1~60분)** 로그 파일 캐시에 저장된 정보가 실제 로그 파일에 기록되는 시간을 지정할 수 있습니다. 데이터가 기록된 후 캐시가 지워진 것입니다. 기본값은 5분입니다.
    
- **로그 파일을 보관할 일 수(1-365)** 로그 파일을 삭제하기 전까지 보관할 일 수를 지정할 수 있습니다. 기본값은 10일입니다.
    
## <a name="see-also"></a>참고 항목

[장치 로그 구성](device-log-configuration.md)
