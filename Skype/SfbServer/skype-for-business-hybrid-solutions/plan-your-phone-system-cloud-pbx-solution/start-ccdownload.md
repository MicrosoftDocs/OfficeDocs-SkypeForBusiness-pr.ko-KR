---
title: Start-CcDownload
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 19338a34-1bfb-4787-b057-5e34a333711d
description: 이 Start-CcDownload cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 및 msi 파일을 동기적으로 다운로드합니다.
ms.openlocfilehash: 0d5974bb4d4fb5bc16f467410865fb571073246e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58631572"
---
# <a name="start-ccdownload"></a>Start-CcDownload
 
이 Start-CcDownload cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 및 msi 파일을 동기적으로 다운로드합니다.
  
Cloud Connector 버전 2.0 이상에서는 DownloadBitsOnly 매개 변수를 지정할 수도 있습니다.
  
```powershell
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예 1

다음 예제에서는 Cloud Connector 공용 다운로드 사이트에서 클라우드 커넥터 비트 및 msi 파일을 동기적으로 다운로드합니다.
  
```powershell
Start-CcDownload
```

### <a name="example-2"></a>예 2

다음 예제에서는 개인 다운로드 사이트에서 클라우드 커넥터 비트 및 msi 파일을 동기적으로 다운로드합니다.
  
```powershell
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a>예 3

세 번째 예제에서는 클라우드 커넥터 비트 및 msi 파일을 개인 다운로드 사이트에서 동기적으로 다운로드합니다.
  
```powershell
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

다운로드 사이트에서 사용할 수 있는 새 버전이 있는 경우 Start-CcDownload 사이트에서 msi 파일을 다운로드하여 설치한 다음 클라우드 커넥터 비트를 동기적으로 다운로드합니다. msi 파일의 새 버전이 없는 경우 클라우드 Start-CcDownload 비트만 다운로드합니다. 클라우드 커넥터 비트가 이미 다운로드된 경우 Start-CcDownload 실행되지 않습니다.
  
## <a name="parameters"></a>매개 변수
<a name="DetailedDescription"> </a>

|**매개 변수**|**필수**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
|DownloadUrlRoot  <br/> | 옵션 <br/> |System.String  <br/> | 개인 다운로드 사이트에 있는 특정 버전의 클라우드 커넥터의 전체 URL입니다. 이 매개 변수는 주의하여 사용하세요. 다운로드하는 클라우드 커넥터 버전을 알고 있어야 합니다. <br/> |
|DownloadBitsOnly  <br/> |선택  <br/> |System.Management.Automation.SwitchParameter  <br/> |다운로드 사이트에서 MSI를 다운로드하고 설치하는 단계를 건너뛰고 클라우드 커넥터 비트만 다운로드합니다.  <br/> |
   
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음 이 Start-CcDownload cmdlet은 파이프라인된 입력을 허용하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

없음
  

