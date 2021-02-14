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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: 이 Export-CcConfigurationSampleFile cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 샘플 구성 파일(.ini)을 Cloud Connector 어플라이언스 디렉터리로 내보낼 수 있습니다. 배포에 사용할 파일을 수정하고 이름을 변경할 수 있습니다.
ms.openlocfilehash: a29a3db8e77ee239263d015bd7a3efcf4f3f7c5c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801008"
---
# <a name="export-ccconfigurationsamplefile"></a>Export-CcConfigurationSampleFile
 
이 Export-CcConfigurationSampleFile cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 샘플 구성 파일(.ini)을 Cloud Connector 어플라이언스 디렉터리로 내보낼 수 있습니다. 배포에 사용할 파일을 수정하고 이름을 변경할 수 있습니다.
  
이 cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 1.4.1, 1.4.2에 적용됩니다.
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a>매개 변수

없음
  
## <a name="examples"></a>예
<a name="Examples"> </a>

### <a name="example-1"></a>예 1

다음 예제에서는 Microsoft 사이트에서 샘플 구성 파일을 다운로드하여 Cloud Connector appliance의 어플라이언스 디렉터리에 쓴다.
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

현재 버전의 클라우드 커넥터를 사용하려면 .ini 파일에 여러 매개 변수를 제공해야 합니다. 예를 들어 클라우드 커넥터 구성 요소에 대한 가상 컴퓨터의 IP 주소, 구성 요소 이름, 게이트웨이 매개 변수 등의 매개 변수가 있습니다.
  
이 cmdlet은 클라우드 커넥터의 호스트 머신에서 실행되는 경우 Microsoft 사이트에서 구성 예제가 포함된 샘플 .ini 파일을 다운로드합니다. 이 cmdlet은 클라우드 커넥터 어플라이언스 디렉터리에 파일을 쓴다. 어플라이언스 디렉터리는 Set-CcApplianceDirectory 지정합니다.
  
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음 이 Export-CcConfigurationSampleFile cmdlet은 파이프라인된 입력을 허용하지 않습니다. 
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

