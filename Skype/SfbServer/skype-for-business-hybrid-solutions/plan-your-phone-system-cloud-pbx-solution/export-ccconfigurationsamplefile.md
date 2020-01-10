---
title: Export-CcConfigurationSampleFile
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: Export-CcConfigurationSampleFile cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 샘플 구성 파일 (.ini)을 클라우드 커넥터 기기의 기기 디렉터리로 내보냅니다. 배포에 사용할 파일을 수정 하 고 이름을 바꿀 수 있습니다.
ms.openlocfilehash: b62d5d7ffa9e8f10aeae509201c5aa0a1e7fa0a4
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003428"
---
# <a name="export-ccconfigurationsamplefile"></a>Export-CcConfigurationSampleFile
 
Export-CcConfigurationSampleFile cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 샘플 구성 파일 (.ini)을 클라우드 커넥터 기기의 기기 디렉터리로 내보냅니다. 배포에 사용할 파일을 수정 하 고 이름을 바꿀 수 있습니다.
  
이 cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 1.4.1, 1.4.2에 적용 됩니다.
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a>매개 변수

없음
  
## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예제 1

다음 예제에서는 Microsoft 사이트에서 샘플 구성 파일을 다운로드 하 여 클라우드 커넥터 기기의 기기 디렉터리에 기록 합니다.
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

현재 버전의 클라우드 커넥터는 .ini 파일에 여러 매개 변수를 제공 해야 합니다. 예를 들어 클라우드 커넥터 구성 요소, 구성 요소 이름, 게이트웨이 매개 변수 등에 대 한 가상 컴퓨터의 IP 주소와 같은 매개 변수
  
클라우드 커넥터의 호스트 컴퓨터에서 실행 되는 경우이 cmdlet을 사용 하 여 Microsoft 사이트의 구성 예제와 함께 샘플 .ini 파일을 다운로드 합니다. Cmdlet은 클라우드 커넥터 기기의 기기 디렉터리에 파일을 기록 합니다. CcApplianceDirectory cmdlet을 사용 하 여 기기 디렉터리를 지정 합니다.
  
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음. Export-CcConfigurationSampleFile cmdlet은 파이프라인 입력을 허용 하지 않습니다. 
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

