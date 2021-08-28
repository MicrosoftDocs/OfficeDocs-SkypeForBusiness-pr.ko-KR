---
title: Get-CcApplianceLogDirectory
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
ms.localizationpriority: medium
ms.assetid: 8f16d8ea-8161-4b07-9c79-d57e786b3e78
description: Get-CcApplianceLogDirectory cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 어플라이언스에 대한 로그가 저장되는 현재 디렉터리를 보여줍니다.
ms.openlocfilehash: 826599ab785d8b4d74f0792c6091b2a5e78b74e3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580362"
---
# <a name="get-ccappliancelogdirectory"></a>Get-CcApplianceLogDirectory
 
Get-CcApplianceLogDirectory cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 어플라이언스에 대한 로그가 저장되는 현재 디렉터리를 보여줍니다.
  
이 cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 1.4.1, 1.4.2에 적용됩니다.
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a>매개 변수

없음
  
## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예 1

다음 예에서는 현재 Cloud Connector 어플라이언스에 대한 로그가 저장되는 현재 폴더를 보여 주며,
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

이 Get-CcApplianceLogDirectory cmdlet은 클라우드 커넥터 어플라이언스에 대한 로그가 저장되는 현재 디렉터리를 보여줍니다. 기본 폴더는 C:\Users \% userprofile%\CloudConnector\ApplianceRoot\Logs입니다. 
  
이 cmdlet을 사용하여 디렉터리를 변경할 Set-CcApplianceDirectory 있습니다. 
  
참고: 어플라이언스 디렉터리를 변경하지 않고 로그 폴더 위치만 변경하는 cmdlet은 없습니다.
  
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음 이 Get-CcApplianceLogDirectory cmdlet은 파이프라인된 입력을 허용하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

이 명령은 파일 경로를 반환합니다.
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

