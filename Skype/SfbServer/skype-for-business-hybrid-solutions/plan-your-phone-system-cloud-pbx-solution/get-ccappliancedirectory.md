---
title: Get-CcApplianceDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: CcApplianceDirectory cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 호스트 서버의 작업 디렉터리를 검색 합니다. 모든 배포 파일은이 디렉터리에 저장 됩니다.
ms.openlocfilehash: ada1b587b738d882f81557e61438d6642aa03fff
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190800"
---
# <a name="get-ccappliancedirectory"></a>Get-CcApplianceDirectory
 
CcApplianceDirectory cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 호스트 서버의 작업 디렉터리를 검색 합니다. 모든 배포 파일은이 디렉터리에 저장 됩니다. 
  
이 cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 1.4.1, 1.4.2에 적용 됩니다.
  
```
Get-CcApplianceDirectory
```

## <a name="parameters"></a>매개 변수

없음
  
## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예제 1

다음 예제에서는 클라우드 커넥터 구성 요소의 구성 및 가상 컴퓨터 파일이 저장 되는 현재 폴더를 보여 줍니다.
  
```
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

CcApplianceDirectory cmdlet은 모든 구성 및 가상 컴퓨터 파일, 로그, 외부 인증서가 클라우드 커넥터 기기에 대해 저장 되는 위치를 보여 줍니다.
  
각 클라우드 커넥터 기기에는 중재 서버, 중앙 관리 저장소, Edge 서버, 도메인 컨트롤러의 네 가지 구성 요소가 있습니다. 기본 폴더는 C:\Users\%userprofile%\CloudConnector\ApplianceRoot. Set-CCApplianceDirectory cmdlet을 사용 하 여이 폴더를 변경할 수 있습니다.
  
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음. Get-CCApplianceDirectory cmdlet은 파이프라인 입력을 허용 하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

이 명령은 파일 경로를 반환 합니다.
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

