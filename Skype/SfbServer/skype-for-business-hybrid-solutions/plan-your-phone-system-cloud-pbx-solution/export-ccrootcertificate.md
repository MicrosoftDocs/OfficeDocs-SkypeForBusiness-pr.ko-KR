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
localization_priority: Normal
ms.assetid: 1499e33c-6a7c-46b9-b9a1-f78d7853b45d
description: Export-CcRootCertificate cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 호스트 서버의 루트 CA 인증서를 로컬 파일로 내보냅니다.
ms.openlocfilehash: 90eadb257d91a05c05fabbfe1db84b8160ad4a7c
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003418"
---
# <a name="export-ccrootcertificate"></a>Export-CcRootCertificate
 
Export-CcRootCertificate cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 호스트 서버의 루트 CA 인증서를 로컬 파일로 내보냅니다. 
  
```powershell
Export-CcRootCertificate [[-Path] <string>]
```

## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예제 1

다음 예제에서는 경로 매개 변수를 디렉터리 경로로 설정 합니다 (파일 경로는 아님). 파일 c:\test\CCERootCertificates.p7b.를 생성 합니다.
  
```powershell
Export-CcRootCertificate -Path "C:\test" 
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

Export-CcRootCertificate cmdlet을 사용 하면 루트 및 중개 인증서를 파일 경로에 저장할 수 있습니다. 이는 재해 복구 시나리오의 경우 유용할 수 있습니다. 
  
## <a name="parameters"></a>매개 변수
<a name="DetailedDescription"> </a>

|**매개 변수**|**필수**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
|패스가  <br/> |필수  <br/> |System.String  <br/> |인증서가 저장 되는 파일 경로입니다.  <br/> |
   
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음. Export-CcRootCertificate cmdlet은 파이프라인 입력을 허용 하지 않습니다. 
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

없음
  

