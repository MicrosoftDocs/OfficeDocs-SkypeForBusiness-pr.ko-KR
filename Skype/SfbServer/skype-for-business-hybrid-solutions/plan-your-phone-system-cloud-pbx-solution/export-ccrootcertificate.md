---
title: Export-CcRootCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 1499e33c-6a7c-46b9-b9a1-f78d7853b45d
description: 이 Export-CcRootCertificate cmdlet은 루트 CA 인증서를 로컬 호스트 서버의 로컬 비즈니스용 Skype 클라우드 커넥터 버전 내보낼 수 있습니다.
ms.openlocfilehash: e00041088af39bf6f11abd5309ff293bd37bf38f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58625000"
---
# <a name="export-ccrootcertificate"></a>Export-CcRootCertificate
 
이 Export-CcRootCertificate cmdlet은 루트 CA 인증서를 로컬 호스트 서버의 로컬 비즈니스용 Skype 클라우드 커넥터 버전 내보낼 수 있습니다. 
  
```powershell
Export-CcRootCertificate [[-Path] <string>]
```

## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예 1

다음은 Path 매개 변수를 파일 경로가 아니라 디렉터리 경로로 설정하는 예제입니다. c:\test\CCERootCertificates.p7b 파일을 생성합니다.
  
```powershell
Export-CcRootCertificate -Path "C:\test" 
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

이 Export-CcRootCertificate cmdlet을 사용하면 루트 및 중간 인증서를 파일 경로에 저장할 수 있습니다. 재해 복구 시나리오의 경우 유용할 수 있습니다. 
  
## <a name="parameters"></a>매개 변수
<a name="DetailedDescription"> </a>

|**매개 변수**|**필수**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
|경로  <br/> |필수  <br/> |System.String  <br/> |인증서를 저장할 파일 경로입니다.  <br/> |
   
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음 이 Export-CcRootCertificate cmdlet은 파이프라인된 입력을 허용하지 않습니다. 
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

없음
  

